# Engineering meeting prep

A prompt chain for the situation where you are new to a team, someone competent has
already done work on a goal you are being pulled into, and you have one meeting to
show judgment without coming across as the new person reviewing a colleague's design.

The output of the whole chain is small: a diagram, six questions, and one thing you
commit to owning. Everything else exists to make those six questions good.

## Read this part first

**Nothing you generate belongs in this repo.** This repo holds prompts only. Your
inventory, your analysis, your script, and your card live in your own knowledge
space, on the machine that is allowed to hold that material. Copy prompts out of
here. Do not copy work back in.

**Two machines, one gate.** Prompts 00 through 03 run wherever the source material
lives, because they touch repositories and internal documents. Prompt 03 ends by
emitting a block headed `CARD SEED`, which is deliberately stripped of internal
detail. That seed is the only thing that crosses to another machine or into any
live assistant. If a detail cannot survive being made generic, it stays in your
analysis and never reaches the card. This is not only a boundary rule. A card you
glance at mid-sentence has to be short and generic anyway, so the redaction makes
the artifact better.

**Each prompt file contains nothing but the prompt.** Open the file, copy all of
it, paste it. No editing, no stripping headers. The filename is the only label.

## Run order

| File | Runs where | What goes in | What comes out |
|---|---|---|---|
| `00-inventory.md` | Source machine | The folder from step 0 | A manifest of what exists, and an honest statement of what could not be read |
| `01-reconstruct.md` | Source machine | Manifest plus all sources | Accurate reconstruction, no opinions, plus the list of things artifacts cannot answer |
| `02-steelman-stress.md` | Source machine | Output of 01 | Their argument made at its strongest, then failure modes and alternatives |
| `03-script-and-seed.md` | Source machine | Outputs of 01 and 02 | Meeting script, architecture diagram, the analysis file, and the `CARD SEED` |
| `04-card-generator.md` | Personal machine | The `CARD SEED` only | Prompt E, which is what you paste into the live assistant |
| `05-after-action.md` | Source machine | Your meeting notes | Updated analysis, answered questions, new open ones |

## Step 0, before any prompt runs

Put everything in one folder. The chain assumes a single place to look.

```
automations/
  doc/            the design document or write-up from whoever did the work
  transcripts/    meeting recordings, standups, one-on-ones, in date order
  repos/          the repositories, cloned, not summarized
  notes/          anything you already wrote down yourself
  analysis.md     created by prompt 03, this is the durable artifact
```

Two warnings that matter more than they sound.

Six repositories is more than a model will genuinely read. It will cover two of
them well and speak confidently about all six. Every prompt in this chain asks for
a coverage statement for that reason. Read the coverage statement before you trust
anything below it.

Transcription tools mislabel speakers, routinely. Any quote attributed to a person
is a guess until you verify it. Do not repeat an attributed quote in a room where
that person is sitting unless you have checked it.

## The three rules the chain is built on

**Reconstruct before you judge.** Questions written before you understand the work
come out generic, and generic questions tell the room you skimmed. Prompt 01
produces no opinions at all. Its bar is that the person who did the work would read
it and say yes, that is accurate, including the parts that are unfinished.

**Steelman before you stress.** Prompt 02 makes their case as well as they would
make it, and only then goes looking for what breaks. Half your objections dissolve
at that step, and the ones that survive are the real ones. Walking in with only a
risk list makes you a critic, which is the fastest way to lose the room.

**Cut hard.** Six questions, four if the meeting collapses to ten minutes, and an
explicit list of what you are deliberately not asking and who you will ask instead.
Naming what you are holding is the senior signal. Asking everything is a deposition.

## On the diagram

Prompt 03 produces an architecture diagram as Mermaid. Render it before the call
and bring it as an image. Do not draw it live.

The framing does the work: this is my understanding after two weeks, tell me where
I have it wrong. It is not a challenge, it forces a correction, and the corrections
are the undocumented reasoning you cannot get any other way. Hang your questions off
boxes on the diagram rather than asking them cold.

## Leave with a commitment

Sharp questions and no commitment reads as an audit. Sharp questions plus one thing
you own by a named day reads as someone joining the work. Prompt 03 asks for
candidates. Pick one in the room, and then actually do it, because that part is what
compounds.
