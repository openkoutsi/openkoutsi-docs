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
| **Target** *(optional)* | Leave it out for a steady, sustainable effort, or pace the course to a **finish time** or an **average power**. Either one can be changed later without re-uploading. |
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
constantly would otherwise become hundreds of rows, and nobody paces to a
40-metre segment.

!!! note "A sharp surface change is never folded away"
    That folding is about *pacing* rows, and it does not apply to a short
    stretch where the road turns bad. If 130 metres of the course is mud in the
    middle of 40 kilometres of asphalt, it keeps its own row, its own numbers,
    its own stripe on the profile and its own sentence in the plan. You cannot
    pace to it, but you certainly need to know it is coming.

The elevation profile above the table is shaded by gradient, and selecting a
segment highlights it on the profile — so a row of numbers and a shape on a chart
are the same thing.

!!! info "Why the numbers are not guesses"
    Every speed and split comes from the standard steady-state cycling power
    equation — gravity, rolling resistance and air drag balanced against the
    power you put in. It is arithmetic, not an opinion, and Koutsi is not allowed
    to do any of it: the coach is handed the finished table and writes about it.

## Asking for a target

Give the course a target and openkoutsi distributes the effort across it rather
than spreading power evenly: harder on the climbs, where a watt buys the most
time, and easier on the descents, where it buys almost none. There are two ways
to say what you want, and they are alternatives — a course is paced to one or
the other, never both.

### A finish time

Name the time you want to finish in, and the plan is solved backwards from it.
If the time is not reachable, **you get told so instead of a number that
flatters you**:

- **Faster than the physics allows** — no human power gets you round in that
  time. The fastest modelled ride is shown instead.
- **More than you could sustain** — reachable on paper, but only at an average
  intensity nobody holds for that long. The plan says what it would take, and
  what is actually sustainable for a ride of that duration.

Either way you still get the course and its segment table. A refusal is an
answer, not an error.

### An average power

Name the watts instead, and the question turns around: you fix the effort and
openkoutsi reports the finish time it produces. This is the number your head
unit shows at the end — **an average, not a power to hold everywhere.** The same
distribution still applies, so the climbs run above it and the descents below.

A power target cannot be impossible the way a time can: any number of watts is
rideable, the only question is for how long. So the one thing it can be is more
than you would sustain for the ride it produces, and when it is, **you still get
the full plan** — the splits are exactly what you asked for, and they are what
shows how long you would be holding it.

!!! tip "Which one to ask for"
    A time target answers *"can I get round in four and a half hours, and what
    would it cost?"* A power target answers *"I know what I can hold — what does
    that make the day look like?"* The first is the question before an event with
    a cut-off; the second is the one after a good test, or on a long day where
    finishing well matters more than finishing fast.

### Changing your mind

A target is not a decision you make once at upload. On any saved course you can
set one, swap a time for a power (or the other way round) or clear it entirely,
and the course is solved again from what is already stored — no re-upload. The
written plan is cleared when you do, because prose about the old numbers is
prose about a different ride.

## The written plan

With the table computed, **Get pacing plan** hands it to Koutsi, who writes how
to ride the day: pacing through each phase, the climbs that decide it, a fuelling
and drinking schedule built around the predicted duration and intensity, and the
points where you should check yourself and adjust.

Koutsi is given the **computed table and never the route itself** — no
coordinates, because it has no use for them. That means it will not invent local
knowledge about a road it knows nothing about, and everything it says traces back
to a number you can see.

!!! warning "The plan assumes still air"
    There is no wind in this model: every course is treated as a calm day. A
    headwind will move the splits, and it can move them a lot. Treat the times
    as a pacing structure rather than a forecast, and expect the plan to say so
    itself. Unless your server classifies road surfaces (below), every course
    is also treated as dry tarmac — which the plan says out loud too.

    **Group riding also beats this model on the flat.** The physics puts you
    alone in the wind; sitting in a bunch is far cheaper than that, so a fast
    group ride will come in under the prediction on flat sections and roughly on
    it once the road tilts up.

## Road surface

On servers that have it switched on, openkoutsi works out **what is under the
road** and feeds it into the numbers. Gravel is slower than tarmac at the same
power, so knowing which is which changes the target, the predicted split and
quite possibly the tyres you fit.

Each segment gets a surface — asphalt, paved, hardpack, cobbles, gravel, dirt or
grass — and the elevation profile grows a ribbon underneath it in the same
colours, so the shape of the day and the state of the road are one picture.

### Confirmed, or a guess

**Every surface comes with a confidence, and the two are not the same claim.**

OpenStreetMap is a volunteer map, and how thoroughly roads are described varies
enormously — dense across Germany and the Netherlands, thin across rural North
America. Where somebody recorded a surface, openkoutsi says **confirmed**. Where
nobody did, the class comes from the *type* of road instead, and openkoutsi says
**inferred**.

!!! info "What “inferred” actually means"
    It means **openkoutsi could not confirm a surface tag for that stretch** —
    not that the road is definitely untagged, and not that the answer is
    definitely wrong. A road genuinely recorded as asphalt often reads as
    inferred too, because "explicitly paved" and "nobody said" look identical
    from the outside. The label errs towards under-claiming, on purpose: it will
    sometimes tell you it is unsure when it is right, and it will not tell you
    it is sure when it is not.

    In practice: treat a **confirmed** gravel sector as a fact to plan around,
    and an **inferred** one as worth checking against the event's own
    information before you choose tyres.

!!! note "Asphalt is never confirmed"
    Smooth tarmac and a road nobody has described look **identical** to
    openkoutsi — the map gives the same answer for both — so asphalt can only
    ever come out inferred. Marking that on every asphalt row would repeat one
    sentence hundreds of times and bury the rows where confidence tells you
    something, so it is said once, under the surface summary, instead. The rows
    that do carry an **inferred** mark are the ones worth your attention: a
    rougher surface openkoutsi found but could not pin down.

### Sectors you are warned about

Where the road turns sharply worse — tarmac to mud, asphalt to loose gravel —
the course lists that stretch above the segment table with its distance, and the
written plan mentions it explicitly. **Short ones included.** A 130-metre sector
is too short to pace to and too important to leave as a colour you might not
look at.

### Your route does not leave your server

Classifying a surface means matching your route against map data, which needs
the coordinates. That matching runs **on your own server**, against a routing
container your server administrator set up and built map data for. Your route is
not sent to a mapping company, an API, or anyone else — see
[Your data & AI](../data-and-ai.md).

### If your server does not have it

Then course recon works exactly as described everywhere else on this page, and
every course is solved as dry tarmac — which the written plan states plainly
rather than leaving you to assume. Nothing is broken and nothing is missing a
piece it promised you; the surface simply is not part of the answer.

Surfaces are also worked out **after** your segment table appears, so uploading
a course is no slower on a server that has them. And because your courses are
kept, a server that switches this on later can classify the ones you uploaded
before — no re-upload, just **Add surface data** on the course.

## Saved courses

Courses are kept, which is what makes them worth uploading:

- **Re-analyse without re-uploading.** Change bike, or set, swap or clear the
  [target](#changing-your-mind) — the course is solved again from what is
  already stored. The written plan is cleared when you do, because prose about
  the old numbers is prose about a different ride.
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
- Working out road surfaces matches your route **on your own server**, against a
  routing container it runs itself. The route goes nowhere else.

!!! note "Requires AI to be available"
    The segment table and the pacing numbers need no AI at all — they are
    computed on your server and work whether or not a model is configured. Only
    the *written* plan uses one. On servers where AI features require a
    subscription, you will be prompted to subscribe or to
    [connect your own model](using-your-own-ai-model.md).
