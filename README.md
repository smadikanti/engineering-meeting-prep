# Engineering meeting prep

For the situation where you are new to a team, someone competent has already done
work on a goal you are being pulled into, and you have one meeting to show judgment
without coming across as the new person reviewing a colleague's design.

What you walk in with is small: a diagram, six questions, and one thing you commit
to owning. Everything in here exists to make those six questions good.

## The one rule

**Nothing you generate goes in this repo.** This repo is prompts only.

Your inventory, analysis, script, diagram and card live in your own knowledge space,
on the machine that is allowed to hold that material. Copy prompts out of here. Do
not copy work back in. The `.gitignore` blocks the obvious filenames as a backstop,
but do not rely on it.

**One gate, in the middle.** Steps 1 to 4 run where the source material lives,
because they touch repositories and internal documents. Step 4 ends by printing a
block headed `CARD SEED` with the internal detail stripped out. That seed is the
only thing that crosses to another machine or into any live assistant.

## How each prompt file works

Open the file, select all, copy, paste. Each file contains nothing but the prompt.
No headers to strip, no editing. The filename is the label.

---

# The steps

## Step 0. Put everything in one folder

Before any prompt runs. The chain assumes one place to look.

```
automations/
  doc/            the design document or write-up from whoever did the work
  transcripts/    meeting recordings, standups, one-on-ones, in date order
  repos/          the repositories, actually cloned, not summarized
  notes/          anything you already wrote down yourself
  analysis.md     created in step 4, this is the thing that outlives the meeting
```

Clone the repos. Do not paste summaries of them. The whole chain depends on the
model reading real code, and the difference between reading the code and reading
your description of the code is the difference between this working and not.

## Step 1. Inventory

**Run:** `00-inventory.md`
**Where:** the machine with the folder
**Takes:** a few minutes

You get a list of what is there and, more importantly, an honest statement of how
much of it the model actually read.

**Before you move on:** read the coverage section. If it says STRUCTURE ONLY on
four of six repositories, everything downstream is guesswork. Either point it at
fewer repositories and run the chain twice, or accept that two of them are covered
and say so out loud in the meeting rather than bluffing.

Also check the speaker attributions. Anything marked UNCERTAIN is a quote you do not
repeat in front of the person it was attributed to.

## Step 2. Reconstruct

**Run:** `01-reconstruct.md`
**Where:** same machine, same session

You get what exists today, per repository, with a status and the evidence behind it.
Plus what is decided versus assumed versus open, and the list of decisions where
nobody wrote down the reasoning.

No opinions in this step. That is deliberate. Questions written before you
understand the work come out generic, and generic questions tell the room you
skimmed.

**Before you move on:** read it as though you were the person who built this. Would
they say it is accurate? If any part makes them look worse than the truth, fix it
now, because you are about to build questions on top of it.

## Step 3. Steelman, then stress

**Run:** `02-steelman-stress.md`
**Where:** same machine, same session

First it argues their side as well as they would. Then it goes through failure modes
one by one, what breaks later, and the alternatives.

The steelman is not a formality. Half your objections will dissolve once the case
for the current design is made properly, and the ones that survive are the real
ones. Walking into that room with only a risk list makes you a critic in month two.

**Before you move on:** look at section 2, what they have almost certainly already
thought of. Anything on that list is not a question, it is a way to look junior.

## Step 4. Build the script, the diagram, and the seed

**Run:** `03-script-and-seed.md`
**Where:** same machine, same session

This is the big one. You get:

- the script, which is your cheatsheet for running the meeting
- minute by minute choreography, including where you stop talking
- six questions, ranked, each with what a good answer and a worrying answer sound
  like
- the diagram as Mermaid
- what you offer to take on
- the `CARD SEED` at the very end

Save all of it to `analysis.md`. Fix anything that is wrong by hand. The model does
not know the politics of the room and you do.

**Then split it.** The analysis stays here. The `CARD SEED` is the only block you
copy across.

## Step 5. Make the diagram

Take the Mermaid from step 4 and turn it into an Excalidraw sketch.

Excalidraw imports Mermaid directly. Open excalidraw.com, use the Mermaid to
Excalidraw option, paste the Mermaid, and it lays the boxes out for you. Then move
things around so it reads left to right and does not overlap.

**Use Excalidraw rather than a polished diagram tool, on purpose.** The hand-drawn
look says this is a sketch of my understanding, not an architecture review I am
handing down. It invites correction, which is the entire point of putting it up.
A clean formal diagram from someone two weeks in reads as a verdict, and people
argue with verdicts instead of correcting them.

Do it before the call. Do not draw live.

Things to get right in the sketch:

- ten boxes at most, one screen, readable at whatever size it ends up on their
  monitor
- anything not built yet is dashed or explicitly labelled "not built"
- mark every place a human is still in the loop
- put a question mark on the parts you are unsure about, visibly, because that is
  where you want them to jump in
- title it something like "my understanding after two weeks, please correct"

Export it as a PNG as a backup, in case screen sharing goes wrong.

## Step 6. Build the live card

**Run:** `04-card-generator.md`
**Where:** the personal machine, in the project that has your voice instructions
**Paste under it:** the `CARD SEED` only

This prompt does not answer you. It writes Prompt E, which is what you paste into
the live assistant. So you run it once and get a generator you can reuse for the
next meeting.

It also gives you a ten line rehearsal version. **Say it out loud once.** A script
you have never spoken is a script you end up reading from, and reading on camera is
more obvious than forgetting a question.

---

# Meeting day

Three things running, and they are on purpose in three different places.

**The Excalidraw diagram** is what you share. Share the window, not the whole
desktop, and check that before the call rather than during it.

**The script from step 4** is your own reference. Second monitor, phone, or printed.
Never on the shared screen. This is the thing you glance at for what a worrying
answer sounds like and what you promised to offer.

**The live assistant with Prompt E** runs on the personal machine, off to the side.
That separation is not just a compliance thing, it is what makes the screen share
safe. If the cues and the shared screen are on the same machine, sooner or later
the room sees your cue card, and there is no recovering from that.

Run through the setup once the day before, with a real screen share, and look at
what the other side actually sees.

## How the meeting runs

Open by crediting the work and saying you are here to understand it, not review it.

Diagram up. Say your three or four sentences. Then stop talking. The silence after
the diagram is the highest value ten seconds in the meeting, because the corrections
they volunteer are the reasoning that was never written down anywhere.

Ask by pointing at the picture, not cold. Step 4 tells you which question attaches
to which box.

Stop after each of the two hardest questions. Your instinct under pressure is to
fill the gap and answer yourself, which loses you the thing you came for.

Six questions maximum. Four if it runs short. If you think of a seventh, that is the
one you hold for later, and saying out loud that you are holding some for a
follow-up is itself a good signal.

**Leave with a commitment.** Sharp questions and no commitment reads as an audit.
Sharp questions plus "I will write up the failure modes and have it to you Thursday"
reads as someone joining the work. Then Thursday has to actually happen, because
that part is what compounds.

## Step 7. Afterwards, same day

**Run:** `05-after-action.md`
**Where:** the source machine
**Paste under it:** your rough notes

Corrects the record while you still remember the parts nobody wrote down. What you
got wrong, what got answered, what you committed to, what hardened, and a corrected
diagram.

Do it the same day. The undocumented reasoning you just collected is the most
valuable thing in the folder, and it decays fast.
