# Cluely setup

Where Prompt E goes, how the app behaves in a live call, and the two settings that
will embarrass you if you get them wrong.

Verify the details in the app. Cluely ships changes often and some of the
compatibility notes in their docs are dated.

## Where the prompt goes

Prompt E is a **system prompt**, not something you paste into the chat bar during
the call.

1. Open the desktop app
2. Hover your profile icon, click **Customize Cluely**
3. Edit the **System Prompt** directly, or **Add Files**
4. Name it something you will recognise in a dropdown, like `Technical review`

At meeting time, the **Customize Cluely dropdown** sits at the top left of the Live
Insights card, so you switch to that mode in one click. You can switch modes during
a call as well as before it.

**Keep it short.** On the individual plan this is a plain text prompt editor with a
limited context window. Knowledge base sync and the large context window are
enterprise features. This is the real reason Prompt E has to fit on one screen, and
why you never paste the analysis in here.

You can attach files with **Add Files**, but the same rule applies as everywhere
else in this chain: sanitized card only. Nothing from `analysis.md`.

## Before the call

**Invisibility is opt in.** It is off until you turn it on. Eye icon on the command
bar, or profile icon, Settings, Make Invisible.

**Then check it for real.** Their docs note that invisibility works in Microsoft
Teams when you share **one window, not the full screen**. They also list devices
where it does not work at all, older Windows and pre-2020 Apple hardware. That note
is dated, so do not trust it either way. Start a solo session, share your screen to
yourself in a test meeting, and look.

Cluely stays visible in the task bar and Activity Monitor regardless. Invisibility
covers screen share, not someone glancing at your machine.

Other settings worth setting once:

- **Meeting audio language**, so transcription does not degrade
- **Change display**, to put the card on a monitor you are not sharing
- **Disable auto launch**, so it does not appear during a meeting you did not plan
  for it

## The safest configuration

Run Cluely on the **personal machine**, beside you, and share the Excalidraw sketch
from the **work machine**.

Nothing about invisibility settings, window versus full screen, or an accidental
overlay can bite you, because the cues are not on the machine doing the sharing.
This is worth more than any setting in the app.

## What actually gets captured

Be deliberate about this one rather than discovering it later.

Prompt E is sanitized, so no internal detail is in your configuration. But Listen
mode transcribes the meeting. If the microphone is picking up an internal
conversation, that audio goes to an outside vendor, and running it on a personal
laptop beside the call does not change that. It is the same question Granola raised,
and the room does not know it is happening.

**The middle path, and probably the right one here.** Toggle **Audio off** using the
waveform switch in the nav bar. Cluely then works as a heads-up card with a chat bar
you can type into. You keep the card, the questions, the pushback lines, and typed
CMD Enter lookups. You give up live transcription and the automatic prompts. For
this meeting that trade is fine, because the card is the part you actually need and
the automatic suggestions are the part most likely to hurt you.

Decide before the call. Do not decide while it is starting.

## During the call

Shortcuts worth knowing:

| Keys | Does |
|---|---|
| `Cmd Enter` | Ask the chat bar anything |
| `Cmd Shift Enter` | Answer without typing, for when invisibility is on |
| `Tab` | Answers the top automatic suggestion |
| `Cmd \` | Hide and show the widget |
| `Cmd R` | Clear session context |

The card also has default actions: what should I say next, follow up questions, fact
check, who am I talking to, recap.

**Use it for two things.** Checking whether a question of yours went unanswered, and
catching what someone just committed to. That is it.

**Do not use Tab.** Automatic suggestions produce fluent, generic engineering
questions, and a generic question two weeks in is exactly the thing that makes a
room suspicious. Your six questions came out of reading their actual code. Nothing
generated live will beat them.

**Do not read from it.** The eye movement is obvious on camera. Glance, look back,
speak from memory. That is what the rehearsal pass in step 6 is for.

**Smart Mode** is the lightning icon, and it is for coding help. Leave it off.

If it gets noisy mid-call, `Cmd \` and carry on. The printed script does the job.

## Dry run, the day before

Ten minutes, in this order:

1. Start a solo session and confirm your mode is selected in the dropdown
2. Read the card top to bottom and check nothing internal slipped into the seed
3. Turn invisibility on, share the Excalidraw window in a test call, and look at
   what the other side sees
4. Decide audio on or off, and set it
5. Say the rehearsal lines out loud once

## If Cluely is not usable

Print the card. A sheet of paper next to your keyboard does most of the work, cannot
crash, cannot be screen shared, and does not tempt you into reading a generated
answer out loud.
