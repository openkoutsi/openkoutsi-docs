# Intensity distribution

Time in zones tells you about **last week**. Intensity distribution tells you about
the **block** — the shape your training took over the last twelve weeks, and whether
it was the shape you meant.

## The three bands

Distribution is described against three intensity bands rather than your seven power
zones, because that's the language the training research uses:

- **Easy** — below your first threshold (LT1). Zones 1–2.
- **Tempo / threshold** — between your two thresholds. Zones 3–4.
- **Hard** — above your second threshold (LT2). Zones 5 and up.

The band boundaries come from your own zones, so they move when your zones do. There
is no hidden assumption about where your thresholds sit as a fraction of FTP.

## The four shapes

openkoutsi names the shape of the distribution:

- **Polarized** — mostly easy riding, with the hard days genuinely hard and little in
  between.
- **Pyramidal** — a broad easy base, less tempo and threshold, least hard riding.
- **Threshold-heavy** — a large share of moderate work: the grey zone between easy
  and hard.
- **Almost all easy** — very little above your first threshold at all.

!!! note "No shape is the right one"
    Polarized and pyramidal are both well-supported ways to train, and which suits
    you depends on your event, your phase and your history. The point of this view
    isn't to reach a particular shape — it's to find out whether the block you *did*
    matches the block you *planned*. A base phase that quietly became threshold-heavy
    is the classic case, and it's invisible week by week.

## The two ways of counting — and why they disagree

The card has a **By time** / **By session** toggle, and the two will usually give you
different answers. That's expected, not a bug.

=== "By time"

    Adds up every second of every ride. This is the default, and it matches the
    numbers in your [Time in zones](time-in-zones.md) chart exactly.

    The catch: warm-ups, recoveries between intervals and the roll home all land in
    the easy band regardless of what the session was *for*. That inflates the easy
    band and makes almost everyone look pyramidal — including athletes doing
    genuinely polarized training.

=== "By session"

    Counts each ride whole, by what it was for. A VO2max session counts as one hard
    session even if most of its minutes were spent recovering between efforts.

    This is how the polarization research usually counts, and it's closer to how
    you'd describe your own week out loud. It needs each ride to have a workout
    category, which openkoutsi assigns automatically from your power data.

Because the two methods answer slightly different questions, the method in use is
always shown on the card. A distribution figure without its method attached doesn't
mean much.

## Power or heart rate

For the time-based method you can measure against your **power** zones or your
**heart-rate** zones. openkoutsi uses power when you have power zones set up and
falls back to heart rate otherwise, so riding without a power meter doesn't cost you
the feature. The session-based method uses workout categories and so has no power/HR
distinction.

## Your training plan's phases

On the **Plan** page, the same card appears scoped to your plan's current phase — the
run of build or recovery weeks you're in right now — instead of a fixed twelve weeks.
That's the comparison worth making: a base phase is *supposed* to be mostly easy, and
this is where you find out whether it was.

The window only ever runs up to today, so a phase with weeks still ahead of it won't
look like it fell short.

## When to take it with a pinch of salt

Two warnings can appear under the chart, and both are worth reading:

- **Partial coverage** — how many rides in the window actually had usable zone data.
  A shape drawn from 6 of 40 rides is not describing your block.
- **Zones changed** — your zones or FTP moved inside the window, so the bands weren't
  measured against the same boundaries throughout. Your history is deliberately
  [frozen at the zones in effect at the time](time-in-zones.md), which is right for a
  weekly chart but means a long window can mix vintages.

!!! info "Cycling only, for now"
    Intensity distribution covers cycling activities. Running and swimming need their
    own sport-specific intensity models.

## Related

- [Time in zones](time-in-zones.md) — the week-by-week view this builds on.
- [Training plans & workouts](training-plans.md) — phases, build and recovery weeks.
- [Fitness metrics](fitness-metrics.md) — training load, fitness, fatigue and form.
