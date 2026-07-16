# Privacy & consent

openkoutsi processes personal and health-related data — things like your heart
rate, weight, power, and training activities. This page explains the **consent**
you're asked for, and how to exercise your rights over that data: **export**,
**deletion**, and **withdrawing consent**.

For the specifics of what the optional AI features send and where, see
[Your data & AI](data-and-ai.md).

## Accepting the data-processing terms

The first time you sign in, openkoutsi asks you to **explicitly accept** the
processing of your personal and health data before you can use the app. The
consent screen summarises what is stored and processed — account details
(including your email address if you sign up or verify one), profile picture,
health metrics (weight, heart-rate and power zones), training activities, data
from any providers you connect, and any AI analysis you enable — and links to the
full **privacy policy**.

!!! tip "Read the full policy"
    The consent screen has a **Read the full privacy policy** link, and the same
    link is available any time under **Settings → About**. On the public instance
    the policy lives at [koutsi.dev/privacy](https://koutsi.dev/privacy).

Because health data is treated as sensitive, this consent is explicit and
separate — you tick the box yourself, and nothing is processed until you do.

### If you decline

You can't use the service without accepting the terms, but declining is not a
dead end. From the decline screen you can **download a copy of your data**,
**permanently delete your account**, or simply **log out**.

### If the policy changes

If the privacy policy changes in a material way, you'll be asked to review and
**accept the new version** the next time you sign in. Until you do, the app stays
behind the consent screen.

## Your rights over your data

openkoutsi is built so your data stays yours. You can act on the main GDPR
rights directly in the app.

### Export your data

Go to **Profile → Data export** and choose **Download**. You'll get a
`openkoutsi_export.zip` archive — a complete copy of your data in open,
machine-readable formats that you can keep or take elsewhere. It includes:

- your **profile** and analysis settings (your AI/LLM key is never included),
- your **activities**, with their notes, labels, and AI analysis,
- your **training plans** and **goals**,
- your **structured workouts**,
- your **daily fitness metrics** (fitness/fatigue/form) and **personal records**,
- your **inbox** messages and **weight log**, and
- the original **`.fit` files** for every activity that has one.

### Delete your account

Go to **Profile → Delete account**. This **permanently** removes your account
and everything in your private database — activities, plans, goals, metrics, and
uploaded files — and disconnects any linked Strava/Wahoo accounts. It cannot be
undone, so export first if you want a copy.

### Withdraw consent

Withdrawing consent to processing means the app can no longer function for you.
To withdraw, **delete your account** (which erases all your data), or contact the
instance operator. Disabling only the **AI** analysis is separate and doesn't
affect the rest of the app — see [Your data & AI](data-and-ai.md).

## Who can see your data

Your training and health data lives in your **own private database** and is
visible only to you — not to other users, and not to an administrator. Uploaded
FIT files and avatars are stored encrypted. Normal use never sends your data
anywhere except between your browser and your own server (and to Strava/Wahoo, or
an AI provider, only when *you* choose to connect them).

!!! info "Self-hosting? You're the data controller"
    This page describes how the software behaves. If you **run** an openkoutsi
    instance, you are the data controller for its users and are responsible for
    providing your own privacy policy; set its address with the
    `PRIVACY_POLICY_URL` setting so the consent screen links to it.
