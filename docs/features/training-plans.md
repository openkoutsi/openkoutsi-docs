# Training plans & workouts

openkoutsi can build you a structured training plan and turn its days into
detailed interval workouts you can ride from your head unit.

## Generating a plan

Create a **periodized** plan that progresses through the classic phases:

**Base → Build → Peak → Taper**

You give the plan a name, a goal, a start date, and a length, and openkoutsi lays
out the workouts across the weeks.

## Editing a plan

Plans are not fixed once created. You can:

- edit the plan's metadata (name, goal, start date, length)
- add, edit, or delete individual planned workouts from the calendar day view
- regenerate a plan's workouts (rule-based or AI)

!!! info "Completed workouts are protected"
    Workouts you have already done are locked from editing and are preserved when
    you regenerate a plan.

## The training calendar

Your dashboard calendar shows both **performed** and **planned** workouts with
distinct markers (completed, pending, skipped). From a day, you can mark a planned
workout as **done** or **skipped** without opening the full plan.

When you skip a workout you can record a reason (illness, injury, fatigue, travel,
weather, and so on). This keeps your training log accurate and gives the AI
coaching features useful context.

### One workout, several activities

Sometimes a single session ends up recorded as more than one activity — you
accidentally stopped the recording, paused for a coffee break, or did a couple of
back-to-back virtual rides. You can link **each** of those activities to the same
planned workout, and their durations and Load are counted together towards the
goal.

Open the planned workout from the calendar, link the first activity, then use
**Link another activity** to add the rest. Each linked activity is listed and can
be unlinked on its own.

!!! tip "Example"
    A long ride is planned, but you accidentally stop recording halfway and end up
    with two medium rides. Link both to the planned workout and their combined time
    and Load satisfy it — no need to merge the files.

!!! note
    Automatic matching still links a single activity that already covers the day's
    workout on its own. When the session was split into parts that each fall short,
    link the extra activities by hand.

## Structured workouts

Build interval workouts and export them for your device:

- **Zwift** — export as a `.zwo` file.
- **Head units** — export as a FIT workout file. Repeat blocks are flattened into
  individual consecutive steps so they display reliably on Wahoo and Garmin
  devices.

### Pushing workouts to Wahoo

If you have connected Wahoo, you can send a structured workout straight to your
account as a scheduled planned workout. It then appears under **Planned Workouts**
on your ELEMNT / RIVAL.

- Schedule it for today through six days out.
- Re-pushing the same workout updates it instead of creating a duplicate.

### Generating workouts from a plan

In one action, openkoutsi can auto-synthesize structured interval workouts for a
plan's upcoming days (using a configured LLM). Generated workouts are cached on
the planned workout, so already-generated days and rest days are skipped and no
extra work is repeated. A per-day summary shows what was generated, skipped, or
failed. The results appear in the **Workouts** tab, where you can review, edit,
and upload them to Wahoo individually.

!!! note "More detail coming"
    A full walkthrough of building an interval workout from scratch will be added
    here.
