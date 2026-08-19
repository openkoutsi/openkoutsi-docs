# Features overview

openkoutsi brings your rides, your fitness trends, and your training plan together
in one self-hosted place. This section explains how to use each area. Pick a topic
below.

<div class="grid cards" markdown>

- :material-bike-fast: **[Activities & sync](activities.md)**

    Upload FIT files or sync automatically from Strava and Wahoo. See your
    activities analysed for training load, weighted power, and time in zones.

- :material-chart-line: **[Fitness metrics](fitness-metrics.md)**

    Track your fitness, fatigue, and form — as interactive
    charts on your dashboard.

- :material-heart-pulse: **[Aerobic metrics](aerobic-metrics.md)**

    Efficiency factor, aerobic decoupling, variability index and W′ balance —
    the numbers that describe *how* a ride went, not just how much of it there was.

- :material-chart-bar-stacked: **[Time in zones](time-in-zones.md)**

    See weekly accumulated time in each power and heart-rate zone, so you can
    tell easy weeks from hard ones at a glance.

- :material-chart-timeline-variant: **[Intensity distribution](intensity-distribution.md)**

    Find out whether a whole block came out polarized, pyramidal or
    threshold-heavy — the shape a single week can never show you.

- :material-calendar-check: **[Training plans & workouts](training-plans.md)**

    Generate periodized plans, build structured interval workouts, and push them
    to your Wahoo or Garmin head unit.

- :material-map-marker-path: **[Course recon](course-recon.md)**

    Upload the GPX of a course you are going to ride and get it back as a segment
    table — power targets and predicted splits from your own numbers — plus a
    written pacing plan.

- :material-trophy: **[Achievements & streaks](achievements.md)**

    Earn badges for milestones — long rides, big climbs, finished plans — and keep
    a streak of consistent weeks going.

- :material-inbox: **[Inbox](inbox.md)**

    Messages from openkoutsi — new achievements and, if you administer the
    instance, events on it. Click one to read it in full.

- :material-key-chain: **[Personal access tokens](personal-access-tokens.md)**

    Scoped, revocable credentials for your own tooling — a backup script, a cron
    job, an AI client — so something other than your browser can reach the API.

- :material-robot-outline: **[AI assistants (MCP)](mcp.md)**

    Let Claude, Copilot in VS Code, or another MCP client ask your instance about
    your training directly — read-only, scoped, and revocable at any time.

</div>

## Other capabilities

openkoutsi also includes, among other things:

- **Goals** — set training or event goals with optional target metrics and dates,
  and ask the AI coach for a realism verdict and concrete steps to reach each one
  (see [Goal guidance](goal-guidance.md)).
- **Activity labels & notes** — tag rides (for example *race* or *commute*) and add
  free-text notes.
- **AI coaching analysis** — optional per-activity analysis and a daily training
  status summary, powered by an OpenAI-compatible backend you configure. See
  [Your data & AI](../data-and-ai.md) for what gets sent to a model.
- **[Ask Koutsi](chat.md)** — put your own questions to the AI coach and have it
  answer by looking at your actual training data. It stays a cycling coach:
  health questions go to a doctor, not to Koutsi.
- **Privacy controls** — export your data or delete your account at any time. See
  [Your data & AI](../data-and-ai.md).

!!! note
    Each of these will get its own page as the documentation grows.
