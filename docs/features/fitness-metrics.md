# Fitness metrics

openkoutsi tracks three related numbers that together describe your training load
over time. They are shown as interactive charts on your dashboard.

## The three metrics

| Metric | What it tells you |
|---|---|
| **Fitness** | Your long-term fitness — a 42-day rolling average of training load. Rises slowly as you build form. |
| **Fatigue** | Your short-term fatigue — a 7-day rolling average showing how tired recent training has made you. |
| **Form** | Your freshness — the gap between fitness and fatigue. Positive means fresh, negative means loaded. |

These are computed from the **training load** of your activities, so the more of
your rides openkoutsi sees, the more accurate they are.

## The fitness history card

Your dashboard shows a fitness history card with the fitness, fatigue and form charts for a
period you choose. The same card also summarises your cycling totals for that
period:

- number of activities
- total active time
- total distance covered

## Looking ahead

If you have an active training plan, the fitness history chart continues past
today as a **dashed line**. That section is a forecast: it runs the same model
forward over the training load your plan prescribes for each remaining day, so
you can see where your fitness, fatigue and form are heading before you ride any
of it.

A vertical **Today** marker separates the two. Everything to its left is measured
from activities you actually did; everything to its right is modeled.

The dashed part reaches as far ahead as the period you have selected, up to three
months: pick **1W** and you see a week ahead, **1M** a month, and **3M** or longer
the full three-month outlook. That way the forecast never crowds out the history
you asked to look at.

Two places use the forecast directly:

- **Goal outlook** — when a goal's target date falls inside the forecast window,
  your dashboard shows the form you're projected to have on that day. This is the
  quickest way to answer *"will I be fresh on race day?"*.
- **Plan ramp warning** — if a plan's projected fitness climbs faster than the
  week-over-week progression the plan was built with, the plan page says so. It's
  a hint that the plan may be more aggressive than intended, not an error.

!!! note "The forecast assumes you do the plan"
    Every projected day counts the planned workout as completed exactly as
    prescribed. Miss sessions and the real curve will sit lower; ride more than
    planned and it will sit higher. Days with no planned workout — and planned
    workouts with no target load — count as rest, so the line decays through
    them. Once your plan ends, the forecast keeps going with no training at all,
    which is why the tail falls away: that's what detraining looks like.

The forecast is recalculated every time you look at it, so editing your plan
updates it immediately.

## Keeping the numbers honest

If you delete activities, the metrics that depended on them can become stale.
openkoutsi detects this and recalculates automatically when you load your
dashboard, so your charts stay accurate.

## Power curve

The Power view shows your **power curve** — your best average power for each
duration, from a one-second sprint to multi-hour efforts. You can switch the
curve between two units:

- **Watts** — your best absolute power for each duration.
- **W/kg** — watts per kilogram, ranked by your best *power-to-weight* effort.

The W/kg view uses the bodyweight that applied **at the time of each effort**,
taken from your weight history, rather than your current weight. That way a
strong effort from when you were lighter shows up as the W/kg record it was,
instead of being hidden behind a higher-wattage ride at a heavier weight.

Each effort keeps the weight it was ridden at. When you record a new weight it
applies to activities **from that day onward** — earlier rides are not re-scored,
so your W/kg history stays exactly as it was when you rode it.

!!! tip "Keep your weight up to date"
    Efforts from before your first logged weight have no W/kg value and are left
    out of the W/kg curve — and logging a weight later does not fill them in,
    since openkoutsi has no way to know what you weighed back then. Update your
    weight in **Profile** whenever it changes so your power-to-weight records
    stay accurate.

## FTP estimation

From your power data, openkoutsi can estimate your FTP using either:

- the **20-minute** method (95% of your best 20-minute power), or
- the **Critical Power** method.

The estimate is shown on the Power view, and you can accept either one to set it
as your profile FTP.

!!! note "More detail coming"
    A worked example of reading the form curve to time your rest will be
    added here.
