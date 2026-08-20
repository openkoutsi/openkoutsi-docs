# Course recon

Every other AI feature in openkoutsi answers a question about the **past**: what
shape you are in, how that ride went, whether a goal is realistic. Course recon
answers the one question with a deadline attached — **how do I ride this thing on
Saturday?**

Upload a GPX course, and openkoutsi splits it into segments, works out what power
to hold and how long each one will take at your own FTP and weight, and asks
Koutsi to write the plan: where to spend, where to hold back, and when to eat.

## Uploading a course

A course is a route you are *going to ride* — the GPX an event organiser
publishes, or one you drew yourself. It is not a ride you already did; those go
to [Activities](activities.md).

On the **Courses** page, drop in a `.gpx` file and tell openkoutsi how you plan
to ride it:

| Input | Why it is asked |
|---|---|
| **Bike** | Tyre width and riding position decide rolling resistance and how much air you push. A gravel bike on 45 mm tyres and a TT bike on 25s produce genuinely different plans. |
| **Target time** *(optional)* | Leave it out for a steady, sustainable effort. Set it, and the plan works backwards from the finish. |
| **Start date and time** *(optional)* | Lets the plan talk about your day — when to start eating, what the last hour looks like. |
| **Goal** *(optional)* | Links the course to a [goal](goal-guidance.md) you have already set for the event. |

Your **FTP and weight come from your profile**, so they are not asked for again.
Both must be set — the physics cannot run without them.

## The segment table

The course is split where the gradient meaningfully changes, and each segment
gets a row:

- **Distance** — where it starts and how long it is
- **Gradient** — the average slope, and whether it counts as a climb, a descent
  or flat
- **Power** — what to hold, in watts and as a share of your FTP
- **Predicted split** — how long it should take, and the elapsed time at that
  point of the course

Short pieces are folded into their neighbours on purpose. A road that rolls
constantly would otherwise become hundreds of rows, and nobody paces to a 40-metre
segment.

The elevation profile above the table is shaded by gradient, and selecting a
segment highlights it on the profile — so a row of numbers and a shape on a chart
are the same thing.

!!! info "Why the numbers are not guesses"
    Every speed and split comes from the standard steady-state cycling power
    equation — gravity, rolling resistance and air drag balanced against the
    power you put in. It is arithmetic, not an opinion, and Koutsi is not allowed
    to do any of it: the coach is handed the finished table and writes about it.

## Asking for a target time

Give the course a target and openkoutsi distributes the effort across it rather
than spreading power evenly: harder on the climbs, where a watt buys the most
time, and easier on the descents, where it buys almost none.

If the target is not reachable, **you get told so instead of a number that
flatters you**:

- **Faster than the physics allows** — no human power gets you round in that
  time. The fastest modelled ride is shown instead.
- **More than you could sustain** — reachable on paper, but only at an average
  intensity nobody holds for that long. The plan says what it would take, and
  what is actually sustainable for a ride of that duration.

Either way you still get the course and its segment table. A refusal is an
answer, not an error.

## The written plan

With the table computed, **Get pacing plan** hands it to Koutsi, who writes how
to ride the day: pacing through each phase, the climbs that decide it, a fuelling
and drinking schedule built around the predicted duration and intensity, and the
points where you should check yourself and adjust.

Koutsi is given the **computed table and never the route itself** — no
coordinates, because it has no use for them. That means it will not invent local
knowledge about a road it knows nothing about, and everything it says traces back
to a number you can see.

!!! warning "The plan assumes still air and dry pavement"
    There is no wind in this model, and no surface classification yet: every
    course is treated as dry tarmac on a calm day. A headwind will move the
    splits, and it can move them a lot. Treat the times as a pacing structure
    rather than a forecast, and expect the plan to say so itself.

    **Group riding also beats this model on the flat.** The physics puts you
    alone in the wind; sitting in a bunch is far cheaper than that, so a fast
    group ride will come in under the prediction on flat sections and roughly on
    it once the road tilts up.

## Saved courses

Courses are kept, which is what makes them worth uploading:

- **Re-analyse without re-uploading.** Change bike, set or clear a target time —
  the course is solved again from what is already stored. The written plan is
  cleared when you do, because prose about the old numbers is prose about a
  different ride.
- **Delete any course**, which removes the analysis and the original file
  together.

## Your data

Course recon is the one place openkoutsi keeps a route, and it does so
deliberately — see [Your data & AI](../data-and-ai.md) for the full picture:

- The route lives in **your own database**, and the GPX you uploaded is
  **encrypted on disk**, exactly like your activity files.
- Your **rides are still stripped of location**. Uploading a course changes
  nothing about how activities are handled.
- Courses, their segment tables and the original files are all in your **data
  export**, and all removed when you delete a course or your account.
- The **coach is given the derived table, never the track**.

!!! note "Requires AI to be available"
    The segment table and the pacing numbers need no AI at all — they are
    computed on your server and work whether or not a model is configured. Only
    the *written* plan uses one. On servers where AI features require a
    subscription, you will be prompted to subscribe or to
    [connect your own model](using-your-own-ai-model.md).
