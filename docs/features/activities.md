# Activities & sync

Activities are the rides openkoutsi analyses to track your fitness and check your
training plan. You can add them manually or have them appear automatically.

## Uploading activity files

Drop a file from your head unit or training app straight onto the activities page.
openkoutsi reads three formats:

| Format | Typically from | Carries |
|---|---|---|
| `.fit` | head units (Garmin, Wahoo, Zwift…) | everything — power, laps, the device's own totals |
| `.tcx` | training platforms and older devices | power, laps, distance |
| `.gpx` | phone apps and route exports | position, elevation, usually heart rate — **no power** |

All three are analysed the same way, automatically, for:

- **Training load**
- **Normalized power** (where the file recorded power)
- **Zone distribution** — how long you spent in each power/heart-rate zone

Workouts are also categorised automatically using Coggan-style zones, and you can
override the category by hand if needed.

You can also drop **many files at once**, gzipped files, or a whole `.zip`
archive — see [bringing your history with you](../getting-started.md) for the
Strava bulk-export route. Large drops become a background import with a progress
panel and a per-file result list, so nothing has to be watched.

!!! note "A ride with no power is still a complete ride"
    A `.gpx` file has no power data to read, so an activity imported from one has
    no average or weighted power, no power records and no power-zone time. That is
    the file, not a failed import: the **training load comes from heart rate**
    instead, and the ride counts towards your fitness and fatigue as normal. The
    activity says so on its own page.

!!! info "Your route is not stored"
    GPX and TCX files are made of GPS coordinates. openkoutsi uses them only to
    derive distance and elevation gain and then discards them — no route or
    location data is ever saved. See [Your data & AI](../data-and-ai.md).

### Downloading the original

Every uploaded or imported activity keeps the **original file, exactly as you
sent it** — a GPX stays a GPX. The download button on an activity gives it back
in its own format, and it is the file openkoutsi re-reads if you reprocess the
activity later.

## Average speed

An activity's summary shows its **average speed**, next to distance and duration.

openkoutsi shows the speed your recording carried — the average of the device's
own speed readings, which is the figure your head unit displayed and the one
Strava and Wahoo report for the same ride. For a workout you logged by hand, or a
file that carried no speed readings at all, the speed is worked out from distance
and elapsed time instead.

!!! note "Why the two figures can differ"
    A ride with stops in it — traffic lights, a café, waiting at a junction — has a
    lower average once the stopped time counts towards it. That is why openkoutsi
    prefers the recorded figure wherever there is one, rather than recomputing it
    and quietly disagreeing with your head unit.

## Adding activities manually

Not every workout comes from a device. When you train without a head unit — or want
to log a session from a notebook or spreadsheet — use **Add activity** on the
activities page to enter the details by hand.

Every field is optional, so fill in as much or as little as you remember:

- **Sport type** and **date**
- **Duration** (minutes) and **distance** (kilometres)
- **Average** and **maximum heart rate**
- **Average power** and **average cadence**
- **Elevation**, a **name**, and either an **RPE** (1–10) or an explicit **training load**

If you don't provide a training load, openkoutsi estimates one from what you did enter, in this
order of preference:

1. an explicit **training load** value, if you gave one;
2. otherwise your **RPE** (perceived effort), scaled by duration;
3. otherwise your **average heart rate**, using the maximum heart rate on your profile.

Manually added activities are tagged with a **Manual** source badge and count towards
your fitness metrics and training-plan matching just like uploaded or synced rides.

!!! tip "Only need to log the effort?"
    Entering just a date, duration and RPE is enough to keep your fitness, fatigue and form
    curves accurate on days you trained without a device.

## Rating perceived effort (RPE)

Power and heart rate tell openkoutsi how hard a ride *was*; **RPE** (Rate of Perceived
Exertion, a 1–10 score) tells it how hard the ride actually **felt**. Illness, heat, poor
sleep and life stress can all make an easy-looking ride feel brutal — recording your own
read on the session gives the AI coaching analysis a signal the numbers can't provide (for
example, a modest intensity paired with a high RPE points to a fatigued day).

### The after-ride prompt

After a significant **cycling** ride lands — whether it synced in the background or you
uploaded a FIT file — openkoutsi gently asks you to rate it the next time you look at your
dashboard. That includes bringing the app back from the background: if you leave it open on
your phone, ride, and come back to it later, the prompt is waiting for you. A ride that
arrives while you are already looking at the dashboard is picked up within a minute, and the
**refresh** button next to the "updated N min ago" label asks for anything pending straight
away.

- **Rate** — pick an effort from **1** (very easy) to **10** (maximal). You can also add a
  short **note** and tick **"This was a commute"** to tag the ride.
- **Skip** — move on without rating this ride.
- **Ask again later** — dismiss the prompt; the same ride leads the queue next time.

If several rides are waiting, the prompt works through them one after another in a single
sitting until the queue is empty or you dismiss it. Only cycling rides are prompted, and
rides tagged as a **commute** drop out of the queue — so everyday commutes and easy spins
don't nag you.

!!! note "No backfilling your history"
    The prompt only ever asks about rides that arrive *after* you start using the feature —
    it will never march you through your entire past activity history.

### Setting RPE from the activity

You can also set or change the RPE on **any** activity at any time. Open the activity and
use the **1–10 selector** in the *Labels & Notes* card, right next to where you edit labels
and notes. Tap a number to set it, or tap it again to clear it.

### Turning the prompt on or off

Prefer not to be asked? On your **profile**, toggle **"Ask me to rate effort after
uploads"** off (or back on). Turning the prompt off doesn't stop you setting RPE by hand
from the activity view.

## Labels, and finding your commutes

Every activity can carry a **label**: *race* or *commute*. Labels are more than
decoration — a ride labelled **commute** drops out of the RPE prompt, hides its aerobic
metrics (stops and traffic make the numbers meaningless), counts towards the *Commuter*
badge, and can be filtered out of the activity list so you see only real training.

Set a label by opening an activity and tapping it in the *Labels & Notes* card.

### Letting openkoutsi find them for you

Riding to work and back means tapping that label some five hundred times a year, so
openkoutsi can spot commutes for you. Go to **Settings → Commute detection** and describe
what your commute looks like:

- **Sport types** — the exact ones, so an e-bike commute can be told apart from your
  weekend road rides even when the distances overlap
- **Distance** and **duration** bands
- **Times of day** — your local clock. Most people want two windows: one out, one back
- **Days** of the week

!!! info "No GPS involved"
    openkoutsi never stores where your rides went, so it cannot recognise a commute by its
    route. It goes by the shape of the ride instead: the same short trip, at the same times,
    on working days. That works well, and it means your address is never in the picture.

### You always get the last word

A rule **suggests** the label; it never applies it on its own. Suggestions reach you in
three places:

- **The after-ride prompt** arrives with *"This was a commute"* already ticked, and a line
  saying why. Leave it ticked to confirm, untick it to say no.
- **The activity page** shows the suggestion with **Yes** / **No** buttons.
- **Activities → Suggested commutes** lets you work through a whole backlog at once.

Saying **no** is permanent: that ride will never be suggested again, even if you reprocess
it later. If you would rather stop being asked about a rule you trust, turn on **"Apply this
label without asking"** for it.

!!! tip "Let openkoutsi write the rule"
    Once you have labelled **ten** rides as commutes, the settings screen offers to build a
    rule from them — sensible distances, durations and time windows already filled in, ready
    for you to adjust. Below ten rides there simply isn't enough to go on.

### Your history

New rides are checked as they arrive. To look at everything you have already imported, use
**Scan my history** in the settings card. That is a deliberate button rather than something
that happens by itself, because it can look at a decade of riding at once.

Editing a rule re-checks everything still awaiting an answer: narrow a rule and the
suggestions it no longer stands behind quietly disappear, widen it and rides it now covers
are picked up. Answers you have already given are never touched.

### Rides you tagged in Strava

If you tick **Commute** on a ride in Strava, openkoutsi takes it at its word and labels the
ride straight away — no confirmation needed. That is your own decision arriving with the
ride, not a guess. Wahoo has no equivalent, and a **bulk export** from Strava arrives as
plain activity files with the flag stripped out, so for imported history the rules above are
what will find your commutes.

### When a rule looks wrong

The settings card watches for two things and tells you about them, without changing anything
by itself:

- rides you labelled by hand that a rule *nearly* caught — a sign the rule is a little too
  tight
- rules whose suggestions you keep turning down — a sign they are too loose

You decide what, if anything, to change. Only you know whether that 9 km ride was the
commute or the long way home.

## Syncing from Strava

Connect your Strava account to import your history and have new rides flow in
automatically:

1. Your administrator configures Strava credentials on the instance.
2. From your settings, connect ("authorise") Strava.
3. openkoutsi imports your recent history and keeps up to date as you ride.

## Syncing from Wahoo

Connecting Wahoo works the same way and also enables **pushing structured
workouts** back to your Wahoo account (see
[Training plans & workouts](training-plans.md)).

!!! info "Reconnecting for new permissions"
    Some features need additional Wahoo permissions. If you connected Wahoo before
    a feature was added, you may need to disconnect and reconnect to grant the new
    access.

## Syncing zones and FTP

You can sync your heart-rate / power zones and FTP from a connected provider so
your profile stays consistent with the device you train with.

## Linking activities to your plan

When you have a [training plan](training-plans.md), uploaded activities are
matched automatically to the planned workout for that day (by sport, and when the
training load and duration are close enough). You can also link or unlink manually from the
plan calendar or the dashboard activity calendar. When linking manually you can pick
from activities recorded within two days of the planned workout, so a session done a
day early or late still counts towards it.

!!! note "More detail coming"
    Step-by-step screenshots for connecting providers will be added here.
