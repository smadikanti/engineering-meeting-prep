Continue from both previous passes. Now build what I actually take into the meeting.

My constraints, which should shape every choice you make below. I am new here. An
engineer who knows more than I do already did this work and has momentum behind it.
My manager wants to see me operate at the level I was hired at. So my job is to make
the existing work stronger and surface risk the team has not priced yet, not to
relitigate a design. If I come across as the new person second-guessing a colleague,
I lose more than any single question could gain me.

Produce two things. First the full analysis, which stays with me. Then, at the very
end and clearly separated, the CARD SEED.

---

PART ONE: THE ANALYSIS

Write this as a document I will save and keep, not as a chat reply. It is the
durable record and I will come back to it after the meeting.

1. WHAT I UNDERSTAND WITH CONFIDENCE
   The parts of this system I could explain out loud right now and defend if
   pushed. Be strict. If I only know it from a document and not from the code, it
   does not go here.

2. WHAT I UNDERSTAND PARTIALLY
   Where I have the shape but not the detail, and specifically what detail is
   missing. These are the places where a question is cheap and useful.

3. WHERE THE RECORD IS SILENT
   Pulled forward from the reconstruction. Decisions with no recorded reasoning,
   ranked by how much they constrain what happens next. This is the highest-value
   list in the document, because it is exactly where asking teaches me something
   and where nobody can accuse me of not reading.

4. THE ARCHITECTURE DIAGRAM
   Produce it as Mermaid so I can render it and bring it as an image. Do not make
   it comprehensive. Make it the version that fits on one slide and that someone
   can correct in ten seconds.
   Show: what triggers the work, what components act, what they read and write,
   where the boundaries between the repositories fall, and where a human is still
   in the loop. Mark anything that is not yet built with a dashed edge or a clear
   label, because presenting scaffolding as though it were shipped is the mistake
   that ends my credibility in this meeting.
   Underneath the diagram, give me three or four sentences to say while it is on
   screen. The framing is fixed and non-negotiable: this is my understanding after
   a short time here, tell me where I have it wrong. It is not a review. It is me
   asking to be corrected, and the corrections are the reasoning I cannot get any
   other way.
   Then, for each box or edge where I have a question, note which question attaches
   to it, so I can ask by pointing rather than asking cold.

5. THE QUESTIONS, RANKED
   Six at most. Order them for the room rather than by importance. Open with the
   ones that are cheap for them to answer and that show I actually read the work.
   Put anything that could land as a challenge later, once the room has warmed up.
   For each question, give me:
   - the question in one plain sentence, the way I would really say it out loud
   - why it matters, one line, for my eyes only
   - the answer that would settle it
   - the answer that would worry me, and the one follow-up I would ask next
   If a question only exposes a gap without changing a decision, cut it. If the
   answer is already written down somewhere in the sources, cut it and tell me
   where it was written down instead.

6. MEETING CHOREOGRAPHY
   Minute by minute, roughly, for a thirty minute meeting. What I open with, when
   the diagram goes up, where the questions land, and where I stop talking.
   Be explicit about the silences. After the diagram, and after each of the two
   hardest questions, I should stop and let the room fill the space. Tell me
   exactly where those pauses go, because my instinct under pressure will be to
   keep talking and answer my own question, and that is how I lose the information
   I came for.
   Also tell me what to do if my manager runs the meeting and I only get openings
   rather than the floor.

7. THE FOUR I ASK IF I ONLY GET TEN MINUTES
   Meetings run short and get hijacked. Which four survive, and the one sentence
   version of the diagram framing if there is no time to present it.

8. WHAT I HOLD FOR LATER
   Questions worth asking, but not in this meeting, and who to ask instead and
   when. Naming what I am deliberately not asking is a senior signal. Asking all
   of it at once is an interrogation.

9. HOW TO RAISE THE REAL RISKS WITHOUT IT LANDING AS CRITICISM
   For the two or three genuine concerns, give me exact wording. The pattern that
   works: credit the work, ask about the scenario rather than asserting the flaw,
   and leave them room to say they already handled it without losing face. Give me
   the actual sentences, not a description of the technique.

10. WHAT I OFFER
    I should leave that meeting having taken something on. Two or three things I
    could genuinely own in my first month that help this goal and do not step on
    work already in flight. Bias toward the unglamorous piece nobody picked up,
    the missing signal, or writing up what is currently only in someone's head.
    For each, the sentence I say to commit to it, including a day.

11. THINGS I MUST NOT SAY
    Anything the artifacts do not support. Anything implying I have read more of
    the internals than I have. Any claim about my own past work that overstates it.
    Be specific and list the actual temptations, given what is in this material.

12. WHAT I EXPECT TO BE ASKED
    Five questions likely to come back at me based on what I am raising, each with
    a short honest answer. Include the ones I cannot answer yet, and what an honest
    non-answer sounds like when it comes with a next step and a date.

---

PART TWO: THE CARD SEED

Last, and clearly separated under a heading that reads exactly CARD SEED.

This is the only part of your output that leaves this machine, so follow these
rules exactly rather than approximately.

- No repository names, no service names, no internal project, tool, or system
  names, no ticket numbers, no code, no file paths, no metrics, no customer names,
  no team names.
- First names only, and only for people I will address out loud anyway. No
  handles, no titles, no reporting lines.
- Describe systems generically. The job that reacts to the event. The store it
  writes to. The step that still needs a human. If a detail cannot survive being
  made generic, leave it out of the seed and keep it in the analysis above.
- Content limited to: my one goal for the meeting, the six questions in plain
  language, the one-line reason each matters, the concerns in generic framing, the
  pauses, what I am offering, and my honest-scope lines.
- No diagram in the seed. The diagram stays here.
- The test, applied literally: it has to make complete sense to someone who knows
  nothing about this company and has never seen this code. If a line fails that
  test, rewrite it or drop it.
