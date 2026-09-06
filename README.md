# Engineering meeting prep

You are new to a team. Someone competent already did work on a goal you are being
pulled into. You have one meeting to show judgment without coming across as the new
person reviewing a colleague's design.

You walk in with three things: a sketch, six questions, one commitment.

## Rules

**Nothing you generate goes in this repo.** Prompts only. Your analysis, script,
diagram and card live in your own knowledge space, on the machine allowed to hold
that material.

**Steps 1 to 4 run where the source material lives.** Step 4 prints a block headed
`CARD SEED` with internal detail stripped. That seed is the only thing that crosses
to another machine or into a live assistant.

**Each prompt file is only the prompt.** Open, select all, copy, paste.

---

## Step 0. One folder

```
automations/
  doc/            the design document from whoever did the work
  transcripts/    meetings and standups, in date order
  repos/          cloned, not summarized
  notes/          anything you wrote yourself
  analysis.md     created in step 4
```

Clone the repos. The chain depends on the model reading real code.

## Step 1. Inventory · `00-inventory.md`

What is there, and how much of it the model actually read.

**Check before moving on:** the coverage section. If four of six repos came back
STRUCTURE ONLY, split the run or say so in the meeting. Do not bluff coverage.
Also: anything marked UNCERTAIN is a quote you never repeat in front of the person
it was attributed to.

## Step 2. Reconstruct · `01-reconstruct.md`

What exists today per repo, with evidence. Decided versus assumed versus open.
Decisions where nobody recorded the reasoning.

No opinions in this step, on purpose. Questions written before you understand the
work come out generic, and generic questions tell the room you skimmed.

**Check:** would the person who built this say it is accurate? Fix it now if not.

## Step 3. Steelman, then stress · `02-steelman-stress.md`

Their case made properly, then failure modes, lock-in, alternatives.

Half your objections dissolve at the steelman. The ones that survive are the real
ones.

**Check:** section 2, what they have already thought of. Anything on that list is
not a question.

## Step 4. Script, diagram, seed · `03-script-and-seed.md`

The big one. You get the script, minute by minute choreography, six ranked
questions, the Mermaid for the diagram, what you offer, and the `CARD SEED`.

Save it as `analysis.md`. Fix what is wrong by hand, because the model does not
know the room.

The analysis stays here. Only the seed travels.

## Step 5. Draw it in Excalidraw

Paste the Mermaid into excalidraw.com using Mermaid to Excalidraw, then tidy the
layout. Export a PNG as backup. Do it before the call.

Excalidraw on purpose. A polished diagram from someone two weeks in reads as a
verdict and people argue with verdicts. A sketch titled "my understanding after two
weeks, please correct" gets corrected, and those corrections are reasoning that was
never written down anywhere.

- ten boxes maximum
- dashed or labelled "not built" for anything scaffolded
- mark where a human is still in the loop
- visible question marks where you are unsure, so they know where to interrupt

## Step 6. Live card · `04-card-generator.md`

Personal machine, in the project with your voice instructions. Paste the `CARD SEED`
under it.

It writes **Prompt E**, which is what goes into the live assistant. Reusable for the
next meeting.

Prompt E is a system prompt, not something you paste mid-call. Setup, settings and
the two things that will embarrass you are in **`cluely-setup.md`**.

Say the rehearsal version out loud once. A script you have never spoken is a script
you read from, and reading on camera is more obvious than forgetting a question.

---

## Meeting day

| Surface | Where | Room sees it |
|---|---|---|
| Excalidraw sketch | Work machine, share the window not the desktop | Yes |
| Script from step 4 | Second screen, phone, or printed | No |
| Prompt E in the live assistant | Personal machine, off to the side | No |

Cues on a separate machine is what keeps the screen share safe. Same machine, and
eventually the room sees your cue card.

Test the share once the day before and look at what the other side sees.

**Running it:** open by crediting the work. Sketch up, three sentences, then stop
talking. That silence is the highest value ten seconds in the meeting. Ask by
pointing at boxes, not cold. Stop again after each hard question. Six questions,
four if it runs short. A seventh is one you hold for later, and saying you are
holding some is itself a good signal.

**Leave with a commitment.** Questions and no commitment reads as an audit.
Questions plus "I will write up the failure modes and have it to you Thursday" reads
as someone joining the work. Then Thursday has to happen.

## Step 7. Same day · `05-after-action.md`

Paste your rough notes. Corrects the record while you still remember what nobody
wrote down: what you got wrong, what got answered, what you committed to, what
hardened, and a corrected diagram.

Do it the same day. That reasoning decays fast.
