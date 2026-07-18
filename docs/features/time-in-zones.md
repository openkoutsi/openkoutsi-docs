# Time in zones

openkoutsi adds up how long you spend in each training zone and shows it **week by
week**, for both **power** and **heart rate**. It's the quickest way to see whether
your training is as easy — or as hard — as you intended.

## The weekly chart

Your dashboard shows a **Time in zones** card with one stacked bar per week, over
the period you choose with the dashboard's time selector. There are two charts side
by side:

- **Power** — time in each power zone (needs power data and power zones).
- **Heart rate** — time in each heart-rate zone (needs heart-rate data and HR zones).

Each colour is a zone, from cool (easy) to warm (hard), so a glance tells you how
your week was distributed — lots of blue and green for an endurance block, more
orange and red when you've been doing intensity.

!!! info "You need zones set up"
    Time in zones is only calculated for the zones you have configured. Set your
    heart-rate and power zones in **Profile**, or
    [sync them from a connected provider](activities.md#syncing-zones-and-ftp).

## How it's measured

For every activity, openkoutsi walks through your second-by-second power and
heart-rate recording and tallies how many seconds fall into each zone. Those
per-activity totals are then summed across all the (cycling) activities in each
calendar week, starting on Monday.

## Your history stays put when you change zones

The time-in-zone breakdown for an activity is **captured when the activity is
processed**, using the zones you had at that moment. If you later adjust your
zones — a new FTP, a fresh threshold test — only **future** activities use the new
boundaries. Past weeks keep the numbers they were recorded with, so your history
doesn't shift under you every time your fitness changes.

!!! tip "Refreshing older rides"
    Activities recorded before this feature existed don't have a stored breakdown
    yet. openkoutsi fills them in the first time they're needed, using your current
    zones, and then freezes them like everything else.

## Related

- [Fitness metrics](fitness-metrics.md) — training load, form and your weekly load.
- [Activities & sync](activities.md) — where zone distribution first appears, per
  activity.
