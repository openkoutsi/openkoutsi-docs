# Activities & sync

Activities are the rides openkoutsi analyses to track your fitness and check your
training plan. You can add them manually or have them appear automatically.

## Uploading FIT files

Upload a `.fit` file from your head unit or training app directly into openkoutsi.
Each upload is analysed automatically for:

- **TSS** (Training Stress Score)
- **Normalized power**
- **Zone distribution** — how long you spent in each power/heart-rate zone

Workouts are also categorised automatically using Coggan-style zones, and you can
override the category by hand if needed.

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
TSS and duration are close enough). You can also link or unlink manually from the
plan calendar or the dashboard activity calendar.

!!! note "More detail coming"
    Step-by-step screenshots for connecting providers will be added here.
