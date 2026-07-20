# Activities & sync

Activities are the rides openkoutsi analyses to track your fitness and check your
training plan. You can add them manually or have them appear automatically.

## Uploading FIT files

Upload a `.fit` file from your head unit or training app directly into openkoutsi.
Each upload is analysed automatically for:

- **Training load**
- **Normalized power**
- **Zone distribution** — how long you spent in each power/heart-rate zone

Workouts are also categorised automatically using Coggan-style zones, and you can
override the category by hand if needed.

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
uploaded a FIT file — the next time you open your dashboard openkoutsi gently asks you to
rate it:

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
