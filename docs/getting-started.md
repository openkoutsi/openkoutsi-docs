# Getting started

This page covers your first steps as a user of an openkoutsi instance. It assumes
someone has already deployed openkoutsi to a server — if you are setting up the
server itself, see the deployment guide in the main project repository instead.

## Accessing your instance

Open the address of your openkoutsi instance in a web browser (for example, the
URL your administrator gave you). openkoutsi works on both desktop and mobile.

## First-run setup

The very first time an openkoutsi instance is opened, it shows a **setup wizard**
that creates the first **administrator** account. If you are the person standing
up the instance, complete this wizard to create your admin login. There are no
teams — one deployment is a single instance shared by its users.

If the instance is already set up, you will see the normal login page instead.

## Getting an account

How you get an account depends on how the instance is configured.

**By invitation (always available):**

1. An administrator issues you an **invitation**.
2. You open the invite link and create your account with it.

**By self-serve sign-up (only if the administrator has enabled it):**

1. On the login page, choose **Sign up** and register with your **email address**.
2. Open the verification link we email you to confirm your address and activate
   your account.

If you don't see a sign-up option, the instance is invite-only — ask an
administrator for an invitation.

Once your account exists, you log in from the instance's login page. Your training
data is entirely your own — each user has a **private database**, and no one else
(not even an administrator) sees your activities or plans.

!!! info "Roles"
    There are two roles. Most people are a **user**, who owns and manages their
    own profile and training data. An **instance administrator** can additionally
    manage users, issue invitations, and edit instance-wide settings (such as the
    optional AI configuration).

## Bringing your history with you

Fitness, fatigue and form are built from what you have already done, so openkoutsi
is far more useful on day one if it knows about the last few years rather than
only about today's ride. There are two ways to bring that history across, and they
work well together.

### From a file export

If you already train with Strava, ask it for a **bulk export** of your data and
import the archive whole:

1. In Strava, go to **Settings → My Account → Download or Delete Your Account**,
   choose **Request your archive**, and wait for the email — it can take a few
   hours.
2. Download the `.zip` it links to. **Do not unpack it.**
3. In openkoutsi, open **Activities** and drop the `.zip` onto the upload area
   (or use **Choose files or an archive**).

openkoutsi walks the archive itself, finds the activity files inside — Strava
packs them as compressed `.fit`, `.tcx` and `.gpx` — and imports them in the
background. You can keep using openkoutsi while it runs, and a progress panel
shows how far along it is.

The same works for any pile of activity files, not just a Strava export: select
as many `.fit`, `.gpx` or `.tcx` files as you like, gzipped or not, or a `.zip`
of your own.

### What you see when it finishes

An import reports **every file**, not just a total:

- **Imported** — the activity is now in openkoutsi.
- **Already here** — an activity from that moment already exists, so this file
  was skipped. This is normal and not an error. It also happens *within* one
  archive: an export often contains the same ride as both a `.fit` and a `.tcx`,
  and openkoutsi keeps the richer of the two.
- **Failed** — with the reason, so you can see whether a file was corrupt, was
  not an activity at all, or was something openkoutsi does not read.

Re-importing the same archive later is safe: everything already present is
skipped and reported as such.

!!! note "GPX rides have no power"
    A `.gpx` file records position, elevation and usually heart rate — but not
    power. Activities imported from one therefore show no average or weighted
    power, no power records, and no power-zone time, no matter what power meter
    you were riding. Their **training load is derived from heart rate** instead,
    so they still count towards your fitness and fatigue. Where the same ride
    exists as a `.fit` or `.tcx`, openkoutsi prefers that copy for exactly this
    reason.

!!! info "Your route is not stored"
    GPX and TCX files are built around GPS coordinates. openkoutsi reads them
    only to work out how far you went and how much you climbed, and then discards
    them — your route is never stored, and importing these formats does not
    change that. See [Your data & AI](data-and-ai.md).

### From a connected provider

Connecting **Strava** or **Wahoo** imports your recent history automatically and
keeps new rides flowing in as you ride — see
[Activities & sync](features/activities.md). Do both if you like: the file import
covers the deep history, the connection keeps you current, and anything that
arrives twice is recognised as a duplicate rather than counted twice.

## Your athlete profile

Once you are in, set up your athlete profile (such as your FTP and heart-rate /
power zones). These values are used to analyse your activities and to build
training plans. Many of them can also be synced automatically from a connected
provider — see [Activities & sync](features/activities.md).

!!! tip "Next step"
    With your profile in place, bring in some rides. Continue to
    [Activities & sync](features/activities.md).
