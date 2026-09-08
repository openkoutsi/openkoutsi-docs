# Aerobic metrics

Training load and fitness tell you *how much* work you did. These four numbers
describe *how the work went* — whether your aerobic engine is getting stronger,
how steady the ride was, and how much anaerobic capacity you spent along the way.

They appear in the **Aerobic response** card on each ride, and the efficiency
trend is charted on the **Power** view.

!!! note "Rides only — and training rides at that"
    The card is shown on cycling activities only. Every figure in it is defined
    against cycling power, so on a run, a swim or a gym session there is nothing
    for it to say.

    It is also hidden on rides you have labelled **commute**. Stops, traffic and
    a loaded bike make these numbers describe the journey rather than your
    aerobic fitness. Remove the label on the activity page if you want the card
    back for a particular ride.

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

### Stops, and which part of the ride is measured

Half of a ride is a strange thing to talk about once you have stopped in the
middle of it. Stand around for an hour at lunch and your heart rate is back where
it started; comparing what came before against what came after measures the
lunch, not your durability.

So the figure is taken over the **longest continuous block** of the ride:

- **A short stop changes nothing.** Anything under ten minutes — a traffic light,
  a puncture, a coffee — is ridden through. Your heart rate is back where it was
  within a couple of minutes of rolling again, so the ride either side of it is
  still one ride. A five-minute stop on a seven-hour ride is measured straight
  across.
- **A long stop divides the ride,** and the longest piece is the one measured.
  The card then tells you how much of the ride the figure covers — "measured over
  4h 12m of 7h 03m" — so a number over part of your day is never presented as the
  whole of it.
- **A stop is time with nothing recorded on it,** whichever way your head unit
  writes it down: paused so that nothing at all is logged, or left running while
  the power meter — which stops broadcasting when the cranks stop — goes quiet
  and the strap keeps counting. Neither is a fault, and neither costs you the
  figure any more.

A heart-rate strap that drops out *while you are riding* is a different thing: the
watts have no pulse to be paired against, and that still shows as recordings that
don't line up.

### When openkoutsi won't show you a number

A decoupling figure computed over a hard interval session is noise, and
presenting noise as if it meant something is worse than showing nothing. So the
number is only stored when it can be trusted. Otherwise the card tells you why
it is missing:

| Reason shown | What it means |
|---|---|
| The ride was too short | Decoupling needs roughly an hour of steady riding. |
| Stops broke the ride up | The ride was long enough, but no continuous stretch of it lasted the hour the measurement needs — stop-start riding with long breaks in it. |
| No power data | Both power and heart rate are required. |
| No heart-rate data | As above. |
| The heart-rate data is unusable | A flat trace, for example. |
| The recordings don't line up | Power and heart rate have to be compared moment for moment; a heart-rate strap dropping out repeatedly while you ride makes that unreliable. |
| This was an interval session | The measurement would describe the intervals, not your durability. Judged on variability index together with how hard the ride was and how long it lasted — nobody rides intervals for four hours — so a long ride made variable by descents, junctions and stops still gets its figure. |
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

!!! note "A reprocess re-reads the recording, it does not re-make it"
    Reprocessing recomputes from the streams the activity was stored with, so a
    ride keeps the recording it arrived with. Rides uploaded before openkoutsi
    put every stream on a shared clock — where a dropout leaves a marked hole
    rather than silently shortening the channel — keep the older shape, and on
    those a long strap dropout genuinely does leave power and heart rate out of
    step. **Upload the ride again** (or re-sync it from your provider) if you
    want it read on the shared clock.

## What the AI coach sees

When you ask for an AI analysis of a ride, efficiency factor, variability index
and the decoupling figure are included in the summary sent to the model — or, if
decoupling was not measured, the reason why, so the coach doesn't invent one.
See [Your data & AI](../data-and-ai.md) for the full list of what is sent.
