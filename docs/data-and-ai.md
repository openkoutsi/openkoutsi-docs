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

!!! warning "Two things you can do that send data elsewhere"
    Both are deliberate acts, and neither happens on its own:

    - **Connecting Strava or Wahoo**, which is what makes the sync work.
    - **Creating a [personal access token](features/personal-access-tokens.md)** —
      a long-lived credential you hand to your own tooling so it can read (and,
      if you grant it, write) your data from outside the browser. Whatever holds
      that token can pull your data off the instance for as long as the token
      lives, within the scopes you granted.

    A token is not a leak: you create it, you choose its scopes, you see it in a
    list, and you can revoke it at any moment. But it is the one credential that
    lets something *other than your browser* reach your data, so it is worth
    knowing which tools hold one — and revoking the ones you no longer use.

## The AI features are optional

openkoutsi has six features that use a language model:

| Feature | What it does |
|---|---|
| **Activity analysis** | Written coaching feedback on a single ride. |
| **Daily training status** | A short summary of your current form and what to do next. |
| **[Goal guidance](features/goal-guidance.md)** | Judges how realistic a goal is and how to reach it. |
| **[Ask Koutsi](features/chat.md)** | Answers questions you type, by looking up your training data. |
| **AI plan generation** | Builds a training plan from your requirements. |
| **AI workout generation** | Turns a planned day into a structured interval workout. |

!!! info "Nothing is sent unless you opt in"
    These features only run when **both** of these are true:

    1. An LLM endpoint has been **configured** (by you, or instance-wide by your
       administrator), and
    2. **You trigger the feature** — e.g. you click *Analyse* on an activity,
       *Generate* on a plan, or send a question in *Ask Koutsi*.

    If no LLM is configured, or you never use these actions, **no data is ever
    sent to any model.** Every other feature keeps working without it.

## How to tell what a model wrote

Koutsi's coaching text is written by a language model, not by a person. Because
it arrives in a chat bubble in a coach's voice, that is easy to forget — so
every place the text appears carries a short **AI-generated** note underneath
it. You will see it under:

- the **AI Analysis** on an activity,
- **Koutsi Daily Feedback** on the dashboard, and
- **AI guidance** on a goal.

The note is there from the moment the answer starts appearing, not only once it
has finished. Training plans are marked differently — an **AI** tag next to the
plan's name in the plan list — because a generated plan is a set of workouts
rather than prose.

!!! warning "Treat it as a suggestion"
    A language model can be confidently wrong. It sees the summary described
    below and nothing else — not how you slept, not that you were ill last week,
    not a niggle you have been riding through. Use its feedback as one input
    alongside your own judgement, and **do not treat it as medical or
    professional advice.**

If you are reading your data through the API or your own tooling rather than in
the browser, the same disclosure is available there: the fields carrying
generated prose ship a companion `*_ai_generated` flag.

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

You can set your **own** endpoint under **Settings → AI / LLM** — see
[Using your own AI model (BYOK)](features/using-your-own-ai-model.md). Once you
do, only *your* configuration is used for your account; otherwise the AI features
use whatever endpoint your administrator has configured instance-wide.

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
    - average / weighted power, intensity, training load, average / peak heart rate
    - the ride's aerobic metrics: efficiency factor, variability index, and the
      aerobic decoupling figure — or, when decoupling was not measured, the reason
      why (see [Aerobic metrics](features/aerobic-metrics.md)). These are computed
      on your server from the ride's data; the underlying per-second streams are
      never sent.
    - your FTP and max heart rate
    - your fitness/fatigue/form going into the ride
    - the interval breakdown and any personal records set
    - the activity's **labels and your notes** on it (free text you wrote)

=== "Daily training status"

    A snapshot of your recent training:

    - your FTP and max heart rate
    - your current fitness, fatigue and form
    - your **intensity distribution** over the last 12 weeks: the share of easy,
      tempo/threshold and hard work, the shape it makes, and whether your zones
      changed inside that window (see
      [Intensity distribution](features/intensity-distribution.md)). This is computed
      on your server from your stored zone totals; the underlying per-second streams
      are never sent.
    - the **last 28 days** of activities (date, sport, duration, training load)
    - your active plan's name, dates, and this week's planned workouts
    - your active **goals** (title, target, status)

=== "AI plan generation"

    The requirements for the plan you asked for:

    - length, periodization style, intensity preference, training days per week
    - your **goal/event** and any **extra description** you typed
    - your FTP and current fitness
    - your **intensity distribution** over the last 12 weeks, as one line — the
      shape and the three percentages — so the plan is written against what you
      have actually been doing

=== "AI workout generation"

    The description of the planned day being expanded:

    - workout type and sport
    - the planned description, target duration, and target training load
    - your FTP

## When you let Koutsi look things up

The two lists above describe the normal case: openkoutsi decides in advance what
the coach needs, assembles that fixed summary, and sends it once. There is an
optional setting — **Profile → Analysis → Let Koutsi look things up** — that
changes how the two coaching features work, and it changes this page's answer
along with it. The same setting is what turns on
[Ask Koutsi](features/chat.md), which works this way and no other.

With it on, Koutsi is not handed a summary. It is given a short list of
**questions it may ask about your own training data**, and it decides which ones
to ask before writing. That lets it follow a thread: if your form number looks
off, it can go and look at the rides behind it and tell you *why*, instead of
repeating the number back to you.

!!! info "What changes about what is sent"
    Instead of one fixed summary, several requests are sent, each carrying the
    answers to the questions asked so far. So:

    - **The exact contents vary by run.** Two days with the same data can send
      different things, because Koutsi asked different questions.
    - **More is sent in total.** Three to five requests instead of one, and each
      one repeats what came before. If an **external provider** is configured,
      that means more of your training data crossing the internet, more often.
    - **The boundary is unchanged.** Everything under *What is never sent* below
      still holds, and the questions Koutsi may ask are a fixed, short list — it
      cannot invent a new one.

The questions available to it are these, and all of them are **read-only** and
scoped to **your own** data:

| Koutsi can ask | And gets back |
|---|---|
| How am I doing right now? | Fitness, fatigue, form, recent volume, your FTP and max heart rate |
| What have I done lately? | Recent activities — date, sport, duration, load |
| What did I ride on a given day? | Matching activities, searchable by date, sport, session type or name |
| How did that session actually go? | One activity in detail: intervals, time in zones, notes, RPE, aerobic metrics |
| Am I on track with my plan? | Active plans, this week's sessions, whether they were done |
| Will I make my goals? | Your goals, their targets and current progress |
| How strong am I? | Your power curve and FTP estimate |
| Have I been training polarized? | Your intensity distribution |
| Where has my time gone? | Weekly time in each power and heart-rate zone |

There is no question that returns your raw ride files, your location data, or
anything belonging to another user — those are not on the list, so they cannot
be asked for.

!!! tip "You will see what it is doing"
    While Koutsi is gathering, the card tells you which question it is on —
    *"Koutsi is checking your power curve…"* — rather than showing a bare
    spinner. When the answer starts arriving, the card looks exactly as it always
    does.

The setting is **off unless you turn it on**, and turning it back off takes
effect on the next run. It also needs a model that supports this way of working:
if yours does not, openkoutsi quietly falls back to the fixed summary and the
feature behaves exactly as it did before — you do not need to check, and nothing
breaks.

### Ask Koutsi sends what you type

[Ask Koutsi](features/chat.md) works the same way, with two differences worth
knowing about.

The first is that **you** choose what is sent. Everything else on this page is a
summary openkoutsi assembled; a chat question is free text you wrote, and it goes
to the model exactly as typed. The same advice as for activity notes applies, more
strongly: if an external provider is configured, do not type anything into the box
you would not want leaving your server.

The second is that a conversation is **kept**. Your questions and Koutsi's answers
are stored in your own database so you can come back to them, which nothing else
here does — the daily card overwrites yesterday's. Earlier turns are replayed to
the model on later questions so it can follow the thread, though older ones drop
off as a conversation gets long. What Koutsi looked *up* is not stored or
replayed: each question triggers a fresh look at your current data.

You can delete any conversation, and deleting one removes everything in it.
Conversations are included in your data export as `chat.json` and are deleted with
your account.

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
- **Check what else can read your data.** **Settings → Personal access tokens**
  lists every long-lived credential you have issued, what each one may do, and
  when it was last used. Revoking one takes effect immediately — see
  [Personal access tokens](features/personal-access-tokens.md).
