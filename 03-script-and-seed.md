Continue from both previous passes. Build what I take into the meeting.

My constraints, which should shape everything below. I am new here. Someone who
knows this system better than I do already did the work and has momentum. My manager
wants to see me operate at the level I was hired at. So the job is to make the
existing work stronger and surface risk nobody has priced yet. It is not to
relitigate a design. If I come across as the new person second-guessing a colleague,
I lose more than any question gains me.

Produce two things. The analysis, which stays on this machine. Then the CARD SEED,
which is the only part that leaves.

================================================================
PART ONE: THE ANALYSIS
================================================================

Write this as a document I will save and reread, not as a chat reply.

1. WHAT I UNDERSTAND WITH CONFIDENCE

The parts I could explain out loud right now and defend under a follow-up question.

Be strict. If I know it from a document but not from the code, it does not go here,
it goes in section 2.

2. WHAT I UNDERSTAND PARTIALLY

Where I have the shape but not the detail. Say which detail specifically. These are
where a question is cheap and makes me look like I read the work.

Format: I understand X, but I do not know Y.

3. WHERE THE RECORD IS SILENT

From the reconstruction, ranked by how much each one constrains what happens next.
Highest value list in the document. This is where a question teaches me something
and where nobody can say I should have read it.

4. THE DIAGRAM

Mermaid, so I can render it and bring an image. Do not draw it live in the meeting.

Not comprehensive. The version that fits on one screen and that someone can correct
in ten seconds. Ten boxes at most.

Show: what triggers the work, the components that act, what each reads and writes,
where the boundaries between repositories fall, and every place a human is still in
the loop.

Use a dashed edge or an explicit "not built" label for anything that is scaffolded
or planned. Presenting scaffolding as shipped is the mistake that ends my
credibility in this room, so be conservative. If you are not sure it is built, mark
it as unsure.

Under the diagram, give me three or four sentences to say while it is on screen.
The framing is fixed: this is my understanding after a short time here, tell me
where I have it wrong. It is not a review, it is a request to be corrected.

Then map each of my questions to a box or an edge, so I ask by pointing at the
picture rather than asking cold.

5. THE QUESTIONS

Six at most. Ordered for the room, not by importance. Cheap ones that show I read
the work go first. Anything that could land as a challenge goes later, once the room
has warmed up.

For each, this exact format:

  Q1. [the question, one plain sentence, the way I would actually say it]
  Why:      [one line, my eyes only]
  Attaches to: [which box or edge on the diagram]
  Settles it: [the answer that means I stop worrying]
  Worries me: [the answer that means there is a real problem]
  Then I ask: [the one follow-up, only if worried]

Worked example of the tone I want, so you can match it:

  Q1. When this runs twice on the same event, does the second run notice?
  Why:      idempotency is nowhere in the code I read and nothing guards it
  Attaches to: the worker box
  Settles it: there is a dedupe key or the operation is naturally idempotent
  Worries me: "it shouldn't happen twice"
  Then I ask: what happens today if it does

Cut any question where the answer is already written down in the sources, and tell
me where it was written down instead. Cut any question that exposes a gap without
changing a decision.

6. CHOREOGRAPHY

Rough minute by minute for a thirty minute meeting. Assume my manager may run it and
I get openings rather than the floor.

Format:

  0 to 3     what I say to open
  3 to 8     diagram up, what I say, then I stop
  ...

Mark every place I stop talking with STOP AND WAIT on its own line.

Be specific about those. After the diagram, and after each of the two hardest
questions, I go quiet and let the room fill it. My instinct under pressure is to
keep talking and answer my own question, and that loses me the information I came
for.

Also give me: how to get in if the meeting is being driven by someone else, and how
to close if we are running out of time.

7. IF I ONLY GET TEN MINUTES

Which four questions survive. Plus a one sentence version of the diagram framing for
when there is no time to present it.

8. HOLDING FOR LATER

Questions worth asking, but not in this meeting.

Format: question | who to ask instead | when

Saying out loud that I am holding some questions for a follow-up is a good signal.
Asking all of them at once is an interrogation.

9. RAISING THE REAL RISKS WITHOUT IT LANDING AS CRITICISM

For the two or three genuine concerns. Give me the exact sentences, not a
description of the technique.

The pattern that works: credit the work, ask about a scenario instead of asserting a
flaw, and leave them an easy way to say they already handled it.

Worked example of the shape:

  Not: "there's no idempotency here"
  Instead: "the retry path looks solid. If the same event came through twice, is
  there something upstream catching that, or is that still open?"

10. WHAT I OFFER

I should leave having taken something on. Two or three things I could genuinely own
in my first month that help this goal and do not step on work in flight.

Bias toward: the unglamorous piece nobody picked up, the missing signal or alerting,
writing down what currently only exists in one person's head, or the test coverage
on the risky path.

For each, give me the sentence I say to commit to it, including a specific day.

11. THINGS I MUST NOT SAY

Specific to this material, not generic advice. List the actual temptations: claims
the artifacts do not support, anything implying I read more of the internals than I
did, and any claim about my own past work that overstates it.

12. WHAT THEY WILL ASK ME

Five questions likely to come back at me based on what I am raising. Each with a
short honest answer.

Include the ones I cannot answer yet, and show what an honest non-answer sounds like
when it comes with a next step and a date.

================================================================
PART TWO: THE CARD SEED
================================================================

Last, under a heading that reads exactly CARD SEED.

This is the only part of your output that leaves this machine. Follow these rules
exactly, not approximately.

Strip all of these:

  repository names
  service, system, tool, and internal project names
  team names
  ticket or issue numbers
  code, file paths, function names
  metrics and numbers
  customer or partner names
  anything acronym-shaped that an outsider would not recognise

Keep first names only, and only for people I will say out loud in the room. No
handles, no titles, no reporting lines.

Describe systems generically:

  "the scheduler in the ingest repo"     becomes  "the job that kicks it off"
  "writes to the events table in Postgres" becomes "writes to the store"
  "the manual approval in the ops tool"  becomes  "the step that still needs a person"

Include only: my one goal for the meeting, my opening, the six questions in plain
language, the one-line reason each matters, where I stop and wait, the concerns in
generic framing, what I am offering, and my honest-scope lines.

No diagram in the seed. The diagram stays here.

Apply this test literally to every line before you write it: would this make
complete sense to someone who knows nothing about this company and has never seen
this code? If not, rewrite it generically or leave it out. If a detail cannot
survive being made generic, it was too specific to glance at mid-sentence anyway.
