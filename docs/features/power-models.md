# Power models

The Power view can fit several **power–duration models** to your power curve and
draw them on top of your real bests. A model is a formula that describes how the
most power you can hold falls as the effort gets longer — from a few-second
sprint down to a steady hour. Comparing the modelled curves with your actual
efforts shows where you are already close to your potential and where there is
room to improve.

## The models

openkoutsi fits four models, each with its own strengths:

| Model | Good for |
|---|---|
| **Critical Power (2-param)** | The classic threshold model over ~2–20 minutes. |
| **Critical Power (3-param)** | Adds a realistic ceiling on short sprints, so it also fits ~30 s efforts. |
| **Exponential** | Follows the smooth drop from your sprint power down toward threshold. |
| **Power law** | Describes the long, enduring part of the curve well. |

Each model is fit only to the range of durations it describes well, and every
model reports a **fit error** — the average gap between the model and your
actual bests. A smaller fit error means the model matches you more closely.

## Overlaying the curves

On the Power view, tick the models you want to see and they are drawn as dashed
lines over your real power curve. You can show as many or as few as you like:

- Where a dashed line sits **on** your real curve, the model agrees with you.
- Where your real curve sits **below** a model, that duration may be untested —
  a hint of power you might have in you.

!!! info "Watts only"
    The modelled curves are calculated in watts, so they appear when the power
    curve is shown in **Watts**. Switch back from **W/kg** to see them.

## Estimated potential

Below the curve, the **Estimated potential** table turns the models into
concrete numbers. For each model it shows your predicted best power at four key
efforts, next to your actual best at the same duration:

| Metric | Effort | What it reflects |
|---|---|---|
| **Neuromuscular Power** | 5 seconds | Your peak sprint power. |
| **Anaerobic Capacity** | 1 minute | Short, hard efforts under fatigue. |
| **Maximal Aerobic Power** | 5 minutes | The top of your aerobic engine. |
| **FTP** | ~20 minutes | The power you can hold at threshold. |

The table also lists each model's fitted parameters — critical power (CP),
anaerobic work capacity (W′) and maximal power (Pmax) where they apply.

!!! note "These are estimates"
    The numbers come from modelling the efforts already in your history — they
    are not the result of a dedicated test. The more full-effort rides
    openkoutsi has seen across a range of durations, the more trustworthy the
    models become. See the [power curve](fitness-metrics.md) for how your bests
    are collected.
