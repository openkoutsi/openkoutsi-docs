# Garage

Your bikes, and everything that follows from owning one: how far each has been
ridden, what has been done to it, and what is bolted to it.

Rides attach themselves. Tell openkoutsi that gravel rides happen on the gravel
bike, and from then on they land there without you touching anything — with a
one-click correction for the ride where the guess was wrong.

## Adding a bike

On the **Garage** page, add a bike and fill in as much as you know:

| Field | Why it is asked |
|---|---|
| **Name** | What you call it. |
| **Tyre width** and **riding position** | The only two things the [course recon](course-recon.md) pacing model reads off a bike: width sets rolling resistance, position sets how much air you push. |
| **Starting odometer** *(optional)* | Kilometres the bike had already ridden before openkoutsi ever saw it. |
| **Rides on this bike** *(optional)* | The ride types that should be attached to this bike automatically. |

!!! tip "The starting odometer matters more than it looks"
    Almost every bike you add has history behind it. Without a starting figure,
    "these tyres have done 900 km" is only counting from the day you started
    using openkoutsi — so every wear figure reads low and every service interval
    is wrong. Set it once and everything downstream is right.

Your bikes are the same list the **Courses** page offers when you analyse a
route, so a bike added here shows up there immediately. There is no second list
to keep in step.

## Distance: two numbers, on purpose

Each bike shows up to two figures, and they mean different things:

- **Tracked** — the rides openkoutsi has actually attached to this bike, added
  up. This is what it has observed.
- **Lifetime** — tracked distance plus the starting odometer you entered. Shown
  only when you have set a baseline.

They are kept apart deliberately. One is arithmetic on your ride history; the
other leans on a number you typed from memory. When a figure looks wrong, you can
see straight away which half to go and check.

Rides logged without a distance — an indoor session where you only recorded time
— simply contribute nothing. They never blank out the total.

## Attaching rides to a bike

Under **Rides on this bike**, pick the ride types this bike claims: road rides,
gravel rides, mountain bike rides, e-bike rides, virtual rides, and so on. Every
new ride of those types is attached to that bike as it arrives, whether it came
from Strava, from a file you uploaded, or from a workout you logged by hand.

**A ride type can belong to only one bike.** If you try to give *gravel rides* to
a second bike, openkoutsi refuses and tells you which bike already has them —
because with two claimants there is no right answer, and picking one would be
wrong half the time and never say so.

A ride type nobody has claimed is simply left alone: the ride gets no bike rather
than a guess. Runs, swims and everything else are never attached to a bike.

### Rides you already have

Claiming a ride type only affects rides that arrive **from then on**. To go back
through what you already have, use **Attach past rides**.

It looks at every ride with no bike on it and attaches the ones whose type is
claimed. Rides that already have a bike — whether openkoutsi matched them or you
chose it yourself — are left exactly as they are.

!!! note "Why this is a button and not automatic"
    It walks your entire history, which for a decade of riding is a lot of rides.
    That is your call to make, not something that should happen quietly while you
    are editing a bike.

### When the guess is wrong

Open any ride and use the **Bike** card to change it. The card also says *how*
the current bike got there:

- **Matched by sport** — openkoutsi attached it from the ride type.
- **You chose this** — you set it yourself.

Setting it to **No bike** is a choice like any other — for a rental, a borrowed
frame, or a ride that simply was not on one of yours. It sticks the same way, and
the bike's totals drop the ride immediately.

That distinction is the point. Once you have chosen a bike by hand, **nothing
puts the guess back**: not reprocessing the ride, not a fresh sync from your
provider, not attaching past rides, not changing what a bike claims later. Your
correction is the final word on that ride.

The picker here offers every bike you have, including retired ones — correcting
an old ride onto the bike you actually rode it on is exactly what this is for,
and that is often a bike you no longer own.

## Maintenance

Log what you do to a bike: the date, **what** you worked on, the odometer reading
at the time, and a note.

The **what** — tyres, chain, cassette, brake pads, a full service — is what makes
the log answer questions instead of just recording prose. "How many kilometres
did these tyres last?" is a question about two tyre changes, and openkoutsi can
only work out the gap between them if it knows both entries are about tyres. The
list covers the usual parts; anything you type that is not on it is kept as you
wrote it.

For each entry the log shows:

- **Previous lasted** — how far the part you replaced had run, measured from the
  last entry for that same part.
- **Fitted N ago** — for the part currently on the bike, how far it has run since
  you fitted it. Tyres fitted at 4 200 km on a bike now at 6 000 have done 1 800,
  and that is usually the number you actually want.

Where a reading is missing, the span is shown as unknown rather than as zero —
"unknown" and "no wear at all" are not the same claim.

!!! info "An odometer reading never moves"
    What you record is the reading at that moment, stored exactly as entered. It
    does not shift when you import older history, correct a starting odometer, or
    move a ride to a different bike. A maintenance log that quietly rewrote
    itself would be worse than no log at all.

## Accessories

Note what is fitted to the bike — a child trailer, a rack, a set of lights, a
frame bag.

This is a record, not a calculation. A loaded child trailer really does change
how a bike rides, but openkoutsi does **not** feed accessories into course pacing
predictions: doing that properly is its own piece of work, and a prediction that
half-accounted for a trailer would be worse than one that plainly does not.

## Retiring a bike

Sold it? **Retire** it rather than deleting it.

A retired bike:

- keeps every ride, every kilometre and its whole maintenance history;
- stops collecting new rides, even if it still claims a ride type;
- drops out of the course analysis bike picker;
- stays available when you correct an individual ride;
- can be brought back at any time.

Deleting is the other thing. The rides survive — nothing you have recorded is
lost — but they stop belonging to any bike, so the totals and the maintenance
history go with it. If what you mean is "stop showing me this", retire it.
