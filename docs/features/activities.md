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
plan calendar or the dashboard activity calendar.

!!! note "More detail coming"
    Step-by-step screenshots for connecting providers will be added here.
