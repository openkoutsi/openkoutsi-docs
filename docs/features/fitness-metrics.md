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

!!! tip "Keep your weight up to date"
    Efforts from before your first logged weight have no W/kg value and are left
    out of the W/kg curve. Update your weight in **Profile** whenever it changes
    so your power-to-weight records stay accurate.

## FTP estimation

From your power data, openkoutsi can estimate your FTP using either:

- the **20-minute** method (95% of your best 20-minute power), or
- the **Critical Power** method.

The estimate is shown on the Power view, and you can accept either one to set it
as your profile FTP.

!!! note "More detail coming"
    A worked example of reading the form curve to time your rest will be
    added here.
