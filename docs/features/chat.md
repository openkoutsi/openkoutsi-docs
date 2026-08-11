# Ask Koutsi

Everywhere else in openkoutsi, Koutsi decides what to tell you: the daily card on
your dashboard, the analysis under a ride, the guidance on a goal. **Ask Koutsi**
turns that around. You get a text box, and Koutsi answers by going and looking at
your actual training data.

That last part is the point. Koutsi can read your activities, your plan, your
goals, your zones and your fitness numbers, so it can answer things a general
chatbot cannot:

- *"I'm three weeks out from my event and my form is still negative — should I be worried?"*
- *"Work is going to eat next week. What should I cut?"*
- *"My threshold intervals keep falling apart in the last rep. What do I do about that?"*
- *"Should I be doing more Z2 or more intensity right now?"*

## Turning it on

Ask Koutsi appears in the sidebar once you switch on
**Profile → Analysis → Let Koutsi look things up**.

It shares that switch with the agentic daily card rather than having its own,
because the two need the same thing: permission for Koutsi to look data up
instead of being handed a fixed summary. A chat that cannot see your training
would just be a general-purpose chatbot in a cycling jersey.

!!! info "Your AI model has to support tool calling"
    Looking things up means calling tools, and not every model can. If the model
    you have selected cannot, the page will tell you so and point you at your AI
    settings rather than letting you write a question that was never going to be
    answered. See [Using your own AI model](using-your-own-ai-model.md).

## What Koutsi will and won't discuss

Koutsi is a cycling coach, and it stays one. Four kinds of question get four
different treatments:

| You ask about | What Koutsi does |
|---|---|
| **Coaching** — intervals, periodisation, fitness and form, pacing, adapting your plan | Answers fully. This is the job. |
| **Around the edges** — fuelling for a long ride, sleep, strength work, bike fit, race tactics | Answers as a coach would: practical and general, without claiming to be a specialist. |
| **Medical** — symptoms, pain, injury, illness, medication, or whether something your body is doing is dangerous | **Does not answer.** Points you at a doctor. |
| **Unrelated** — anything that isn't your training | Declines briefly and steers back. |

### The medical line

This is worth stating plainly, because openkoutsi holds heart rate, weight and
effort data, and that makes it very easy for an AI to sound authoritative about
your health.

**Koutsi will not tell you whether a symptom is serious, will not guess at a
diagnosis, and will not tell you to train through something.** If you ask about
chest pain, a joint that keeps swelling, a resting heart rate that worries you,
or how far to cut your food before a race, it will say that this is outside what
it can help with and that you should speak to a doctor or another qualified
clinician.

That is not Koutsi being unhelpful. It genuinely does not know, and neither does
the language model behind it — it has your power files, not your medical history.

!!! warning "If something feels wrong, ask a person"
    A chat window is the wrong place for a health question, however convenient it
    is. Talk to a doctor.

The other half matters too: asking what to eat on a four-hour ride is a question
for your coach, and Koutsi should answer it. If it refuses something that is
plainly a coaching question, that is a bug worth reporting.

## Having a conversation

Type a question and press Enter. Koutsi may take a moment — it is often making
several lookups before it writes anything, and it tells you what it is doing
while it works ("Koutsi is checking your power curve…").

Answers stream in as they are written, and they are saved as they go. You can
reload the page, close the tab, or pick the conversation up on your phone; the
answer carries on and is there when you come back.

Follow-ups work as you would expect — Koutsi remembers what you have both said in
this conversation. What it does *not* keep is the data it looked up: each turn it
goes and reads your training fresh. That is deliberate, and it means an answer
tomorrow reflects tomorrow's rides rather than a stale copy.

### Conversations

Every conversation is kept in the sidebar, named after your opening question, and
stays until you delete it. Deleting one removes everything in it, including what
you wrote, and cannot be undone.

There is a limit on how long a single conversation can get. When you reach it,
start a new one — you lose nothing by doing so, because Koutsi looks your training
up fresh each time anyway.

### Koutsi advises; you decide

Koutsi cannot change anything. It cannot move a session, edit your plan or mark a
workout done — it can only tell you what it would do. When an answer is about your
plan, there is a link to open it so you can make the change yourself.

## Limits

Ask Koutsi is the one AI feature you can trigger as often as you like, and each
question costs several AI calls rather than one. So there is a daily limit on
questions. You will not normally notice it; when you are close, the page starts
showing how many you have left.

On a server where AI features need a subscription, chat is covered by the same
subscription as everything else — see
[AI features, subscriptions and BYOK](ai-subscriptions.md).

## If something goes wrong

Because Koutsi has to look things up to answer, a chat question cannot fall back
to a simpler answer the way the daily card can. So when a question fails, it says
why:

- **Koutsi was busy** — your server was working on other AI jobs and did not get
  to yours in time. Try again in a moment.
- **Your model can't use tools** — a permanent limitation of the model you have
  selected, not a temporary glitch. Choose a different one.
- **The AI server had a problem** or **couldn't be reached** — worth another try;
  if it keeps happening, check the server in your AI settings.

Anything that can sensibly be retried offers a **Try again** button.

## Where your words go

What you type is sent to whichever AI model your server is configured to use, or
to your own if you are running one. Your conversations are stored in your own
database alongside the rest of your data, are included in your data export as
`chat.json`, and are deleted with your account.

If you use your own model (BYOK), what that model does with your messages is
between you and it — see [Your data & AI](../data-and-ai.md) and
[Privacy & consent](../privacy.md).
