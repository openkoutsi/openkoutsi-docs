# FAQ

A few common questions. This list will grow over time.

### What is openkoutsi?

A self-hosted cycling coaching platform. You upload or sync your rides, track your
fitness trends, and follow a training plan — all from a server you control rather
than a cloud service.

### Where is my data stored?

On the server running openkoutsi. Each user has their **own private database** and
file storage, so your activities and plans are visible only to you. You can export
your data or delete your account at any time.

### Can someone else — a coach or admin — see my activities?

No. openkoutsi runs as a single instance where every user keeps their own private
data. There is no coach role and no shared team data; an administrator manages
accounts and instance settings but does not see your training data.

### How do I sign up?

It depends on the instance. Every instance supports **invitations** — an
administrator sends you an invite link to create your account. Some instances also
enable **self-serve sign-up**: choose **Sign up** on the login page, register with
your email address, and open the verification link we email you to activate your
account. If there's no sign-up option, ask an administrator for an invitation. See
[Getting started](getting-started.md).

### I forgot my password.

On the login page, click **Forgot password?**. If the instance has email set up,
enter your email address and we'll send you a reset link (it expires in 1 hour).
Otherwise the page shows how to reach your administrator, who can generate a reset
link for you.

### How do I contact the instance operator?

Every instance is run by an **operator** (the administrator who hosts it). The
**Forgot password?** page shows an operator/admin contact when one is
configured, and the same contact appears under **Settings → About**. Use it to
reach the person running your instance — for account help, privacy requests, or
anything the app can't do for you itself.

!!! info "Public instance"
    On the public instance the operator contact is `lassi@koutsi.dev`.

### Do I have to connect Strava or Wahoo?

No. Integrations are optional. You can upload FIT files manually and use every
analysis feature without connecting any external provider.

### Why was my Wahoo connection not enough for pushing workouts?

Pushing structured workouts needs extra Wahoo permissions. If you connected Wahoo
before that feature existed, disconnect and reconnect to grant them. See
[Activities & sync](features/activities.md).

### Is this a developer or API reference?

No — this site is the **user** guide. Developer setup, deployment, and API details
live in the main openkoutsi project repository.

### I found something missing or unclear.

These docs are actively being expanded. Please open an issue in the
[openkoutsi-docs repository](https://github.com/openkoutsi/openkoutsi-docs).
