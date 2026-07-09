# AI features, subscriptions and BYOK

openkoutsi's [AI features](../data-and-ai.md) — activity analysis, daily training
status, and AI plan/workout generation — normally run against the model your
instance's administrator has configured. Some instances **charge for AI** that
uses the server's own model, while keeping everything else free. This page
explains what changes on those instances and how to check your own status.

!!! info "The rest of openkoutsi stays free"
    Subscription gating only affects AI features that use the **instance's** model.
    Uploading activities, syncing with Strava/Wahoo, fitness metrics, plans and
    everything else keep working exactly as before.

## What changes on a gated instance

When your administrator turns the gate on, using the **instance's** AI model
requires an **AI-access subscription** (an entitlement granted to your account).
If you don't have one, you have two options:

1. **Bring your own AI model (BYOK).** Point openkoutsi at your own
   OpenAI-compatible endpoint under **Settings → AI / LLM**. BYOK always works,
   even on a gated instance, because the request goes to *your* provider, not the
   instance's — see [Using your own AI model](using-your-own-ai-model.md).
2. **Subscribe.** Ask your administrator for access. When you try to use an AI
   feature without a subscription (and without BYOK), openkoutsi shows an
   "AI features on this server require a subscription" message instead of running.

## Checking your status

**Settings → AI / LLM** shows a line describing your current AI access:

| You see | What it means |
|---|---|
| **Included** | The instance doesn't gate AI — everything just works. |
| **Subscription active** (optionally *until …*) | You hold an AI-access entitlement; the instance model is available. |
| **Using your own AI server** | You've set up BYOK; your own model is used and no subscription is needed. |
| **Not available — subscribe or add your own server** | The instance gates AI and you have neither a subscription nor BYOK. |

!!! note "Auto-analysis on a gated instance"
    If you enabled automatic activity analysis or daily training status but don't
    have access, those toggles stay saved but do nothing — the settings page
    explains why. They resume automatically once you subscribe or set up BYOK.

## For administrators

The gate is **off by default**, so a fresh self-hosted instance behaves exactly
as before until you enable it.

### Enabling the gate

In the **admin console → instance settings**, turn on **Require subscription for
instance LLM**. From then on, only users with an AI-access entitlement (or their
own BYOK model) can use the instance's AI features.

### Granting and revoking access

In the **admin console → users**, each user has an **LLM access** control. Grant
access (optionally with an expiry date), or revoke it later. Granting is manual
in this phase — you decide who gets access, e.g. after payment arranged out of
band.

### Reading usage stats

The **LLM usage** card aggregates how many tokens each user has consumed on the
**instance's** model, with **input and output tokens shown separately** and a
per-**provider** breakdown. Pick a period (with week/month granularity) to see
tokens per user per month — useful for working out the average AI cost per user.
Calls made through users' **own** models (BYOK) are never counted, since the
instance pays nothing for them.

For what each AI feature sends to the model and where it goes, see
[Your data & AI](../data-and-ai.md).
