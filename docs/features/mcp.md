# AI assistants (MCP)

You can let an AI assistant — Claude, GitHub Copilot in VS Code, or anything else
that speaks the **Model Context Protocol** — ask your openkoutsi instance about
your training directly, instead of you copying numbers into a chat window.

Ask *"how's my form looking before Saturday?"* and the assistant fetches your
current fitness, fatigue and form, checks where you are in your plan, and answers
from your real data.

!!! info "Read-only, and only ever *your* data"
    An assistant connected this way can **read** and nothing else. It cannot
    upload, edit or delete anything, cannot change your profile, and cannot see
    another user's training — not even if you administer the instance.

## What the assistant can ask for

Ten questions, deliberately shaped like the things a coach actually wants to
know rather than like database tables:

| It can ask… | And gets |
|---|---|
| **Training status** | Fitness, fatigue and form, recent load, and how you are trending — for today, or for any past date |
| **Recent activities** | Your latest rides with their headline numbers |
| **Find an activity** | One ride, looked up by date or description |
| **Activity detail** | A single ride in depth — intervals, zones, aerobic numbers |
| **Plan status** | Where you are in your training plan, and how adherence looks |
| **Goal progress** | How each goal is tracking against its target and date |
| **Power profile** | Your best power over the standard durations |
| **Intensity distribution** | Whether a block came out polarized, pyramidal or threshold-heavy |
| **Zone totals** | Accumulated time in each power and heart-rate zone |
| **Your profile** | Your FTP, heart rates, weight, age, training zones, the hours a week you have and the coaching tone you asked for |

!!! tip "Ask about the past, not just today"
    **Training status** takes a date, so *"what shape was I in the week before
    last year's gran fondo?"* is a question the assistant can actually answer —
    and *"is this build steeper than my last one?"* is two of those questions
    side by side. Everything moves with the date you ask about: the fitness
    numbers, the trend, and the four-week volume totals, so the two answers are
    genuinely comparable. Ask for a date before your history begins and it says
    so, naming the date your records start — it will not quietly report zeros.

What it deliberately **cannot** get:

- **Raw data streams.** A three-hour ride holds around eleven thousand samples
  per channel. The assistant gets computed summaries instead — that is the whole
  design, not a limitation to work around.
- **Your location.** No GPS coordinates are ever returned.
- **Your name or your date of birth.** The profile question answers with your age
  in whole years, never the date it was worked out from.
- **Your inbox, your account, or anything administrative.**
- **A full export.** The `athlete:export` scope is not callable this way. One
  call that downloads your entire record is the opposite of a focused question —
  see [Personal access tokens](personal-access-tokens.md#the-export-scope-is-its-own-thing).

!!! warning "Your data goes to whoever runs the assistant"
    This is the one thing worth pausing on. When Claude or Copilot fetches your
    fitness numbers, those numbers travel to that assistant's provider, exactly
    like anything else you type into it. That is a deliberate act on your part
    and entirely reasonable — but it is a different privacy posture from normal
    use of openkoutsi, where your training data never leaves your own server.
    See [Your data & AI](../data-and-ai.md).

## Before you start

Three things need to be true:

1. **Your instance publishes the endpoint.** It is on by default; an
   administrator can switch it off under **Admin → Settings → Allow the MCP
   server**.
2. **You can reach it.** The address is your instance's API address with `/mcp`
   on the end — for example `https://api.your-instance.example/mcp`. If you
   reach openkoutsi over the internet, whoever set it up needs to have routed
   that path through.
3. **You have a personal access token** with the right scopes. That is the next
   step.

## Step 1 — Create a token

Go to **Settings → Personal access tokens → New token**. Give it a name you will
recognise later (`claude desktop`, `vs code`), pick an expiry, and grant these
five scopes:

| Scope | Needed for |
|---|---|
| `metrics:read` | Training status, power profile, intensity distribution, zone totals |
| `athlete:read` | Training status and power profile — both need this **as well as** `metrics:read` |
| `activities:read` | Recent activities, find an activity, activity detail |
| `plans:read` | Plan status |
| `goals:read` | Goal progress |

Grant fewer if you want less: a token with only `metrics:read` and
`athlete:read` gives the assistant your fitness picture and nothing about
individual rides. Leave `athlete:export` unticked — no assistant tool can use it.

The token is shown **once**. Copy it before closing the dialog. Everything else
about tokens — expiry, revoking, what they can never reach — is on the
[Personal access tokens](personal-access-tokens.md) page.

## Step 2 — Point your assistant at it

Most MCP clients take the same two pieces of information: the address, and the
token as an `Authorization` header. The common configuration shape looks like
this:

```json
{
  "mcpServers": {
    "openkoutsi": {
      "url": "https://api.your-instance.example/mcp",
      "headers": {
        "Authorization": "Bearer okp_…"
      }
    }
  }
}
```

For **VS Code**, use the recipe below instead — it keeps the token out of the
configuration file.

!!! tip "No trailing slash"
    The address ends `/mcp`, not `/mcp/`. The two are different paths, and the
    second one will not answer.

## Step 3 — VS Code

VS Code talks to MCP servers from **Copilot Chat in agent mode**. You will need a
recent VS Code with Copilot Chat installed and signed in.

### Add the server

Open the Command Palette (`Ctrl+Shift+P` / `Cmd+Shift+P`) and run **MCP: Open
User Configuration**. This opens your personal `mcp.json`, which applies to every
workspace. Add:

```json
{
  "inputs": [
    {
      "type": "promptString",
      "id": "openkoutsi-pat",
      "description": "openkoutsi personal access token",
      "password": true
    }
  ],
  "servers": {
    "openkoutsi": {
      "type": "http",
      "url": "https://api.your-instance.example/mcp",
      "headers": {
        "Authorization": "Bearer ${input:openkoutsi-pat}"
      }
    }
  }
}
```

Save it. VS Code asks for the token the first time it connects and keeps it in
its own secret storage — so the file you just edited never contains your
credential.

!!! warning "Use the *user* configuration, not the workspace one"
    VS Code also reads `.vscode/mcp.json` inside a project folder. That file is
    easy to commit to a repository by accident. Your training data is personal
    and the token is a credential, so keep this one in the user configuration
    where it belongs to you rather than to a project.

### Start it and try it

1. Command Palette → **MCP: List Servers** → **openkoutsi** → **Start Server**.
2. Open Copilot Chat and switch the mode selector to **Agent**.
3. Check the tools icon — the openkoutsi tools should be listed there. Untick any
   you would rather it did not use.
4. Ask it something:

    > What does my training status look like, and am I on track with my plan?

The assistant will call **Training status** first — it needs no input and tells
it whether the interesting question is about load, freshness or plan adherence —
and follow up from there.

## If it does not connect

| What you see | What it usually means |
|---|---|
| The client cannot reach the server at all | The address is wrong, or `/mcp` is not routed through to openkoutsi from outside. Try the address in a browser: you should get a short error about the request method, not a "not found" page. |
| A message about the MCP server being disabled | Your administrator has switched it off under **Admin → Settings**. |
| The assistant connects but every tool is refused | The token is unknown, expired or revoked. Check its status under **Settings → Personal access tokens**. |
| Some tools work and others say a scope is missing | The token was granted fewer scopes than the tool needs. Scopes cannot be edited — create a replacement token and revoke the old one. |
| Everything is slow or intermittently refused | You have hit the rate limit, which counts per person rather than per token. Give it a minute. |

!!! note "A missing scope is not an error"
    Assistants see **every** tool listed, including ones your token cannot call,
    and a refusal comes back as a readable explanation rather than a failure.
    Hiding the tools would make a scope you simply did not grant look like a
    feature your instance does not have. If the assistant tells you it needs
    `plans:read`, that is the system working.

## Turning it off again

Any of these stops an assistant immediately, and you can pick whichever fits:

- **Revoke the token** (**Settings → Personal access tokens → Revoke**). Takes
  effect on the very next request, with no grace period. This is the one to use
  if a token might have leaked.
- **Remove the server** from your client's configuration, if you just want to
  disconnect one tool.
- **Ask your administrator to switch the endpoint off** for the whole instance.
  Note that this affects everyone on it.

Your token also disappears on its own eventually — every token expires, and you
are warned in your [inbox](inbox.md) beforehand.
