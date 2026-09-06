I have a meeting soon with my manager, and possibly the engineer who has been
driving this work. I am new to this team. My job in that meeting is to ask good
questions, not to arrive with answers.

Before I form any opinion, reconstruct the work accurately from what is in this
folder. Sources, in priority order: the repositories, the design document or
write-up, and the meeting transcripts. Where the code and the prose disagree,
the code is what shipped and the prose is what was intended, and I want to see
both.

Produce this, and nothing beyond it:

1. COVERAGE
   Repeat it here, briefly. Which repositories you read fully, which you sampled,
   which you only skimmed. Everything below this line should be read in light of
   this paragraph.

2. PROBLEM STATEMENT AS THEY SEE IT
   In their words, not mine. Quote the source where you can. If the repositories
   and the document describe the problem differently, show both and flag the gap
   rather than reconciling them.

3. WHAT EXISTS TODAY
   Per repository: what it does, its entry points, what triggers it, what it acts
   on, and what it writes to. Mark each as SHIPPED, IN PROGRESS, SCAFFOLDED ONLY,
   or STALE, and give the evidence behind that label, such as recent commit
   activity, test coverage, configuration, or dead code paths.
   Also show how the repositories relate to each other. What calls what, what
   shares a data store, what is independent. If they do not connect, say that.

4. THE DIRECTION THEY HAVE COMMITTED TO
   The architectural shape this is heading toward, and how firmly it is committed.
   Separate what is decided, what is assumed, and what is still open. Firmness
   matters more than correctness right now, because it tells me which questions
   are useful and which are already too late to ask.

5. CLAIMS VERSUS EVIDENCE
   A table: claim made in the document or a transcript, supported by the code or
   not, and where. I want to know which parts of the story are built and which
   parts are still intention. This is not a gotcha. Intention is normal at this
   stage. I just need to know which is which before I speak.

6. DECISION POINTS WITH NO RECORDED REASONING
   Places where a real alternative existed and the work took one path. For each:
   what was chosen, what the obvious alternative was, and whether any reasoning is
   recorded anywhere in the repositories, the document, or the transcripts.
   Do not judge the choice. I only want to know where the record is silent,
   because that is where asking is useful. Everywhere the reasoning is already
   written down, asking is noise and makes me look like I did not read.

7. WHAT I CANNOT DETERMINE FROM ARTIFACTS
   Everything that needs a human. Constraints, history, prior attempts, deadlines,
   who asked for this, what was tried and abandoned, what the deadline is tied to.
   Be generous with this list. It is the raw material for my questions, and I would
   rather ask than assume.

Rules:
- No recommendations, no critique, no alternatives in this pass. Reconstruction
  only. There is a later prompt for judgment.
- Every factual statement carries its source. If you inferred it, label it
  INFERRED and say what you inferred it from.
- If two sources disagree, surface the disagreement instead of resolving it.
- Never invent a name, a handle, a team, a service, or an acronym. If it is not in
  the sources, write UNKNOWN.
- Attribute quotes only where the transcript speaker labels were marked CONFIDENT.
  Otherwise write that someone said it, without naming them.

The bar for this output: if I showed it to the engineer who did the work, they
would say yes, that is accurate, including the parts that are unfinished.
