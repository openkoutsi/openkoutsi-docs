# Fitness metrics

openkoutsi tracks three related numbers that together describe your training load
over time. They are shown as interactive charts on your dashboard.

## The three metrics

| Metric | Name | What it tells you |
|---|---|---|
| **CTL** | Chronic Training Load | Your long-term **fitness** — a rolling average of training stress. Rises slowly as you build form. |
| **ATL** | Acute Training Load | Your short-term **fatigue** — how tired recent training has made you. |
| **TSB** | Training Stress Balance | Your **form** (freshness) — the gap between fitness and fatigue. Positive means fresh, negative means loaded. |

These are computed from the TSS of your activities, so the more of your rides
openkoutsi sees, the more accurate they are.

## The fitness history card

Your dashboard shows a fitness history card with the CTL/ATL/TSB charts for a
period you choose. The same card also summarises your cycling totals for that
period:

- number of activities
- total active time
- total distance covered

## Keeping the numbers honest

If you delete activities, the metrics that depended on them can become stale.
openkoutsi detects this and recalculates automatically when you load your
dashboard, so your charts stay accurate.

## FTP estimation

From your power data, openkoutsi can estimate your FTP using either:

- the **20-minute** method (95% of your best 20-minute power), or
- the **Critical Power** method.

The estimate is shown on the Power view, and you can accept either one to set it
as your profile FTP.

!!! note "More detail coming"
    A worked example of reading the form (TSB) curve to time your rest will be
    added here.
