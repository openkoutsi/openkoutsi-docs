# Your data & AI

This page explains how openkoutsi handles your data, and — if you choose to use
the optional AI features — exactly **what** is sent to a language model (LLM) and
**where** it goes.

## How your data is stored

Everything you put into openkoutsi stays on the server your instance runs on:

- Each user has their **own private database**. Your activities, plans, metrics,
  and profile are visible only to you — not to other users, and not to an
  administrator.
- Uploaded **FIT files and avatars are stored encrypted** on the server.
- You can **export your data or delete your account** at any time.

Normal use of openkoutsi — uploading rides, syncing from Strava/Wahoo, viewing
your metrics and plans — never sends your training data anywhere except between
your browser and your own server (and to Strava/Wahoo when *you* connect them).

## The AI features are optional

openkoutsi has four features that use a language model:

| Feature | What it does |
|---|---|
| **Activity analysis** | Written coaching feedback on a single ride. |
| **Daily training status** | A short summary of your current form and what to do next. |
| **AI plan generation** | Builds a training plan from your requirements. |
| **AI workout generation** | Turns a planned day into a structured interval workout. |

!!! info "Nothing is sent unless you opt in"
    These features only run when **both** of these are true:

    1. An LLM endpoint has been **configured** (by you, or instance-wide by your
       administrator), and
    2. **You trigger the feature** — e.g. you click *Analyse* on an activity or
       *Generate* on a plan.

    If no LLM is configured, or you never use these actions, **no data is ever
    sent to any model.** Every other feature keeps working without it.

## Where your data goes

openkoutsi talks to any **OpenAI-compatible** chat API. The endpoint is chosen by
whoever configures it, and *that choice decides whether any data leaves your
server*:

- **A local model** (for example [Ollama](https://ollama.com/) running on the same
  machine, `http://localhost:11434/v1`) — the request never leaves your server.
  Nothing is shared with a third party.
- **An external provider** (for example a hosted OpenAI-compatible API) — the
  request is sent over the internet to that provider and is subject to **their**
  privacy policy and data-retention terms.

!!! warning "Know your endpoint"
    Whether your training data leaves your server depends entirely on the endpoint
    that is configured. If you want your data to stay fully self-hosted, use a
    local model. If an external provider is configured, treat anything the
    features send (see below) as shared with that provider.

You can set your **own** endpoint under **Settings → AI / LLM**, which overrides
the instance-wide default for your account. An administrator sets the instance
default; a global server setting is the final fallback.

## Choosing which model to use

Your administrator can offer **several models** to choose from — for example a
fast local model alongside one or more hosted providers. When more than one is
available, a **Model** dropdown appears under **Profile → Analysis**. Pick the
one you'd like the AI features to use, or leave it on **Default** to follow the
administrator's choice.

!!! warning "Your model choice can change where your data goes"
    Each model an administrator sets up points at its own endpoint. Picking a
    **local** model keeps your data on the server; picking a **hosted provider**
    sends the request (see *What is sent to the model* below) to that provider,
    under their privacy and data-retention terms. If you're unsure where a model
    runs, ask your administrator or choose one you know is local.

## What is sent to the model

Only the data relevant to the feature you triggered is included — as a compact
text summary, never your raw files. In detail:

=== "Activity analysis"

    A summary of the **one** activity you analysed:

    - sport, date/time, duration, distance, elevation gain
    - average / normalized power, intensity factor, TSS, average / peak heart rate
    - your FTP and max heart rate
    - your fitness/fatigue/form (CTL/ATL/TSB) going into the ride
    - the interval breakdown and any personal records set
    - the activity's **labels and your notes** on it (free text you wrote)

=== "Daily training status"

    A snapshot of your recent training:

    - your FTP and max heart rate
    - your current CTL/ATL/TSB
    - the **last 28 days** of activities (date, sport, duration, TSS)
    - your active plan's name, dates, and this week's planned workouts
    - your active **goals** (title, target, status)

=== "AI plan generation"

    The requirements for the plan you asked for:

    - length, periodization style, intensity preference, training days per week
    - your **goal/event** and any **extra description** you typed
    - your FTP and current fitness (CTL)

=== "AI workout generation"

    The description of the planned day being expanded:

    - workout type and sport
    - the planned description, target duration, and target TSS
    - your FTP

## What is never sent

Regardless of which feature you use, openkoutsi does **not** send:

- your **name, email, or login credentials**
- your **raw FIT files** or any **GPS / route / location** data
- any **other user's** data
- your stored **API key** to anywhere other than the endpoint it authenticates
  against (and keys are held **encrypted** at rest)

!!! tip "Free-text fields"
    The features do include free text *you* wrote — activity **notes**, goal
    **titles**, and plan **descriptions** — because that context improves the
    coaching. If an **external** provider is configured, avoid putting anything
    sensitive in those fields, or switch to a local model.

## Staying in control

- **Don't want AI at all?** Leave the LLM unconfigured (or don't use the AI
  actions). Everything else works exactly the same.
- **Want it fully private?** Point **Settings → AI / LLM** at a local model, or
  pick a local model from the **Profile → Analysis** dropdown if your
  administrator offers one.
- **Changed your mind?** Clear the endpoint in your settings; future actions send
  nothing. You can also export or delete your data at any time.
