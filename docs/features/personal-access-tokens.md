# Personal access tokens

Signing in to openkoutsi gives your browser a session that lasts about an hour
before it quietly renews itself. That works beautifully for the app and not at
all for anything else: a nightly backup script, a cron job, a phone, or an AI
assistant that talks to your instance from outside the browser has no way to
hold a credential for longer than an hour.

A **personal access token** is that credential. You create it yourself, from
**Settings → Personal access tokens**, decide exactly what it may do, and revoke
it whenever you like.

!!! info "A token can always do *less* than you can"
    It is not a second password. A token only reaches what you granted it, and
    there are things it can **never** reach whatever you grant — the admin area,
    the sign-in endpoints, your inbox, the AI features, and the token page
    itself. It adds **duration**, not authority.

## Creating one

Open **Settings → Personal access tokens** and choose **New token**.

| Field | What to put |
|---|---|
| **Name** | What it is for, so the list still makes sense in six months — `nightly backup`, `laptop sync`, `phone`. |
| **Scopes** | Only what the tool actually needs (see below). |
| **Expires after** | 7, 30, 90, 180 or 365 days. 90 is the default. |

When you confirm, the token is shown **once**:

```
okp_3f0c1e9a-…_Rk9…
```

!!! warning "Copy it now — it is never shown again"
    Only a one-way fingerprint of the token is kept on the server, so nobody
    (including your administrator, and including you) can look it up afterwards.
    If you lose it, revoke it and create another. That is not a limitation to
    work around; it is the reason a leaked database does not leak your tokens.

Treat it like a password. Anything holding it can act on your data, within the
scopes you granted, until it expires or you revoke it.

## Scopes: granting only what is needed

A scope is one resource and one verb. Grant the smallest set that does the job —
a backup script needs to *read*, not to delete.

| Scope | Lets the token… |
|---|---|
| `activities:read` | read your activities, streams, laps and intervals |
| `activities:write` | upload, edit, reprocess and delete activities |
| `athlete:read` | read your profile, zones and settings |
| `athlete:write` | change your profile, zones and settings |
| `metrics:read` | read daily metrics, fitness/fatigue/form, power and distance bests |
| `metrics:write` | recompute derived metrics from your stored activities |
| `goals:read` / `goals:write` | read / manage your goals |
| `plans:read` / `plans:write` | read / manage training plans and planned workouts |
| `workouts:read` / `workouts:write` | read / manage structured workouts |
| `achievements:read` / `achievements:write` | read your badges / mark them seen |
| `integrations:read` / `integrations:write` | see connected providers / connect, sync, disconnect |

### The export scope is its own thing

`athlete:export` is presented apart from the others, and deliberately so. A
single call under it downloads your **entire record** — every activity, plan,
goal, metric, your inbox, and your raw FIT files — as one zip.

That is a perfectly reasonable thing for a backup tool to want, which is why it
is offered at all rather than forbidden. But it is not a "read" like the others,
so it is never bundled into one: you tick it on purpose, and every use of it is
recorded in your instance's audit log.

!!! note "Why the inbox is reachable this way but not otherwise"
    A token can never call the messages endpoint — partly because your inbox is
    correspondence with the platform rather than training data, and partly
    because that is where the warning that a token is about to expire arrives. A
    credential should not be able to read the message saying it is about to be
    cut off. The export is a different act: a separate, deliberate, audited,
    one-shot download of your own record, rather than a loop watching your mail.

## What a token can never do

Enforced by the server, not by the interface:

| Out of reach | Why |
|---|---|
| The **admin area** | Even if you are an administrator. Being an admin must not widen what a token can read about *anyone's* training data. |
| **Sign-in and account endpoints** | A token can never mint or refresh another credential, and can never delete your account. |
| **Creating, listing or revoking tokens** | A token cannot make another token. There is no chain. |
| **Your inbox** | See above. |
| **AI features** | They cost your instance money, and a credential should not be able to spend it. |

Everything else still applies as normal. If your instance requires consent to
data processing before an upload, a token-driven upload is refused just like a
browser one.

## Expiry

**Every token expires. There is no permanent one**, and the longest you can ask
for is a year.

A credential that never dies outlives the integration it was made for, the
laptop it was stored on, and usually your memory of creating it. An expiry date
is the mechanism that eventually cleans up after a tool you stopped using.

You will not be caught out by it. openkoutsi tells you:

| When | Where |
|---|---|
| 7 days before it expires | Your [inbox](inbox.md), and by email |
| 1 day before | Your inbox, and by email |
| The day it expires | Your inbox, and by email |

Each of those is sent exactly once, so this never becomes a daily nag. The
in-app message is always sent; the email needs a verified address and an
instance with email configured, and you can turn it off under **Profile →
Analysis** ("Email me before an access token expires") while keeping the in-app
notification.

!!! tip "Tokens cannot be extended"
    Expiry, like scopes and the name, is fixed when you create the token — there
    is no edit screen. When one is about to run out, create a replacement, point
    your tool at the new value, and revoke the old one. That keeps the record of
    what each token could do at any point in time honest.

## Revoking

Choose **Revoke** next to a token and confirm. It stops working **immediately** —
there is no cache and no grace period, so anything still using it starts being
refused on its very next request.

Use it the moment a token might have leaked: pasted into a public repository,
stored on a laptop you no longer have, or held by a service you no longer trust.

!!! note "Revoked and expired tokens stay in the list"
    They are not deleted, and that is on purpose. The list is your own record of
    what you issued and when it was last used — and on the server, keeping the
    fingerprint means somebody presenting a token *you revoked* is still
    recognisable as exactly that, rather than blending in with random guesses.

Two things also revoke tokens without you visiting this page:

- **Resetting your password** revokes every one of your tokens. Whatever
  prompted the reset applies to the credentials your account handed out, too.
- **Deleting your account** takes them with it, along with everything else.

## Using one

Send it in the `Authorization` header, exactly where a browser session token
would go:

```bash
curl https://your-instance.example/api/activities \
  -H "Authorization: Bearer okp_3f0c1e9a-…_Rk9…"
```

A few practical notes:

- **Keep it out of your shell history and out of version control.** Put it in an
  environment variable or a file only you can read.
- **Rate limits count per token**, not per computer, so one busy script does not
  slow down your browsing (or anybody else's).
- **A 403 means a missing scope**; the response names the scope it wanted. A
  **401** means the token is unknown, expired, revoked — or that your
  administrator has switched the feature off.

Downloading a full backup, for instance, needs a token with `athlete:export`:

```bash
curl -fL https://your-instance.example/api/athlete/export \
  -H "Authorization: Bearer $OPENKOUTSI_TOKEN" \
  -o openkoutsi-backup-$(date +%F).zip
```

## If you cannot see the card

Personal access tokens are on by default, but a self-hoster may switch them off
for their instance — a perfectly reasonable choice if they would rather no
long-lived credentials existed on their machine at all. When that has been done,
the card does not appear, and any token issued beforehand stops working. Ask
your administrator.

## Administrators

An administrator of your instance can **list and revoke** your tokens, but never
create one on your behalf and never see their **names** (you write those, and a
name can say a lot on its own). This exists for the case where a credential has
clearly been compromised and its owner cannot be reached — stopping it is then
an obligation, not a convenience.

If it happens, **you are told**: an admin revocation lands in your inbox like any
other message, and is recorded in the instance's audit log.
