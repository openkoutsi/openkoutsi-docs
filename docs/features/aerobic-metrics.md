# Aerobic metrics

Training load and fitness tell you *how much* work you did. These four numbers
describe *how the work went* — whether your aerobic engine is getting stronger,
how steady the ride was, and how much anaerobic capacity you spent along the way.

They appear in the **Aerobic response** card on each activity, and the efficiency
trend is charted on the **Power** view.

## The four metrics

| Metric | What it tells you |
|---|---|
| **Efficiency factor** | Weighted power per heartbeat (W/bpm). How much power your heart is buying you. |
| **Variability index** | Weighted power ÷ average power. How steady the ride was: 1.00 is metronomic, above 1.10 means surging. |
| **Aerobic decoupling** | How far your power-to-heart-rate ratio drifted from the first half of the ride to the second. |
| **W′ balance** | A per-second stream showing how much of your anaerobic capacity was left at each moment. |

## Efficiency factor

This is the one to watch across a base phase. Divide the ride's weighted power by
its average heart rate and you get how many watts each heartbeat is buying you.

If that number climbs over weeks while your training load stays flat, you are
getting aerobically fitter in a way the fitness curve can't show you: the fitness
number would look identical whether you rode those hours well or badly.

The **Power** view charts your efficiency factor over time, one point per steady
endurance ride. Interval sessions, very short rides and rides missing power or
heart rate are left out, so every point on the chart is comparable with the
others.

!!! tip "Compare like with like"
    Efficiency factor moves with the kind of riding you do. A tempo ride and a
    recovery spin will not produce the same number, and neither is "better".
    The trend across similar rides is the signal; a single ride's value on its
    own is not.

## Variability index

Weighted power divided by average power — a one-number summary of how punchy the
ride was.

- **Around 1.00** — steady state. A time trial or a disciplined endurance ride.
- **1.00–1.10** — normal rolling terrain and traffic.
- **Above 1.10** — intervals, a hilly race, or a lot of stopping and starting.

openkoutsi already used this internally to categorize your workouts; now you can
see it. It is also what decides whether a decoupling figure is worth showing.

## Aerobic decoupling

Split the ride in half. Work out the power-to-heart-rate ratio for each half. If
the second half's ratio is lower, your heart rate crept up while your power
didn't — your aerobic system was fading. That drift, as a percentage, is
aerobic decoupling.

- **Under 5%** — generally considered good aerobic durability.
- **Above 5%** — you faded. Over a long ride that may simply mean you rode past
  what your endurance currently supports.

A negative number means the second half was the *more* efficient one, which
usually means you started conservatively and warmed into the ride.

### When openkoutsi won't show you a number

A decoupling figure computed over a hard interval session is noise, and
presenting noise as if it meant something is worse than showing nothing. So the
number is only stored when it can be trusted. Otherwise the card tells you why
it is missing:

| Reason shown | What it means |
|---|---|
| The ride was too short | Decoupling needs roughly an hour of steady riding. |
| No power data | Both power and heart rate are required. |
| No heart-rate data | As above. |
| The heart-rate data is unusable | A flat trace, for example. |
| The recordings don't line up | Power and heart rate have to be compared moment for moment; a long dropout on one of them makes that unreliable. |
| This was an interval session | The measurement would describe the intervals, not your durability. |
| The two halves were ridden differently | A ramp or a negative split produces a big number that reflects your pacing, not your durability. |

!!! warning "Heart-rate drift is not purely a fitness signal"
    Heat, dehydration, caffeine, altitude, illness and poor sleep all push heart
    rate up over a long ride. A hot summer ride can show high decoupling from an
    athlete whose fitness is fine.

    Read the number in the context of the day you had. A trend across many
    similar rides in similar conditions is meaningful; one ride in a heatwave
    is not.

## W′ balance

Above your critical power you are spending a finite anaerobic reserve. Below it,
you are refilling it. **W′** (pronounced "W prime") is the size of that reserve
in kilojoules, and **W′ balance** tracks how much of it you had left at every
second of the ride.

Turn it on in the stream chart on any activity to see the story of a hard
session: the reserve draining through each effort, and how much it recovered in
the gaps before the next one. A ride where the balance hits zero and stays there
looks very different from one where you kept topping it back up — even if both
have the same training load.

The critical power and W′ used are estimated from your own power bests **as they
stood on the day of that ride**, and stored with the activity. That means an old
ride keeps the W′ story it actually had at the time, instead of being quietly
rewritten every time your power curve improves.

!!! note "Needs enough power history"
    Estimating critical power takes a spread of hard efforts from two to twenty
    minutes. Until you have those — and until they produce a believable pair of
    numbers, which a diet of purely steady riding does not — openkoutsi shows no
    W′ balance rather than guessing at a reserve size. A W′ curve built on an
    invented number would look convincing and mean nothing.

!!! note "Needs 1-second recording"
    W′ balance is calculated second by second, so it needs your head unit set to
    **1-second** (not "smart") recording. On a file recorded at a lower rate the
    arithmetic would be wrong by the sampling ratio and the error would grow
    across the ride, so openkoutsi leaves the stream out instead.

## Getting these on older activities

Efficiency factor and variability index are calculated on the spot from data
every activity already has, so they show up on your whole history immediately.

Aerobic decoupling and W′ balance are derived from the per-second data streams
when an activity is processed. Rides that were uploaded before this feature
existed pick them up when you **reprocess** the activity from its detail page.

## What the AI coach sees

When you ask for an AI analysis of a ride, efficiency factor, variability index
and the decoupling figure are included in the summary sent to the model — or, if
decoupling was not measured, the reason why, so the coach doesn't invent one.
See [Your data & AI](../data-and-ai.md) for the full list of what is sent.
