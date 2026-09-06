I have a meeting soon with my manager, and possibly the engineer who has been doing
this work. I am new to this team. In that meeting my job is to ask good questions,
not to arrive with answers.

Reconstruct what exists. No opinions in this pass.

Sources in priority order: the repositories, then the design document, then the
transcripts. Where the code and the document disagree, the code is what shipped and
the document is what was intended. Show me both.

Produce these seven sections.

1. COVERAGE

Repeat it from the inventory in three or four lines. Which repositories you read
fully, which you sampled, which you only skimmed. Everything below should be read
in the light of this section.

2. THE PROBLEM AS THEY DESCRIBE IT

In their words. Quote the document and the transcripts directly where you can, with
the source in brackets after each quote.

If the document and the code imply different problems, show both and say so. That
gap is often the most useful thing in this whole pass.

3. WHAT EXISTS TODAY

One block per repository, in this shape:

  NAME
  Status:      SHIPPED | IN PROGRESS | SCAFFOLDED ONLY | STALE
  Evidence:    what made you pick that status
  Triggered by: cron, webhook, manual run, another service, unclear
  Reads from:  
  Writes to:   
  Entry points: actual file and function names
  Does:        three or four sentences, plain

For the status, use real evidence and say it out loud. Recent commits, whether the
tests exercise the main path or only the helpers, whether the config points at
production, whether large parts are unreachable. "Looks finished" is not evidence.

Then, after the blocks, describe how the repositories relate. What calls what, what
shares a database or queue, what is genuinely independent. If they do not connect
at all, say that plainly, because that is worth knowing.

4. THE DIRECTION THEY HAVE COMMITTED TO

The shape this is heading toward. Then split everything into three lists:

  DECIDED    written down, or built, or stated flatly in a meeting
  ASSUMED    everyone seems to believe it, nobody wrote it down
  STILL OPEN actively unresolved

How firm each item is matters more to me than whether it is right. Firmness tells
me which questions are still useful and which ones are too late to ask.

5. CLAIMS VERSUS EVIDENCE

A table:

  claim | where it was said | supported by the code | where in the code

Cover every substantive claim in the document and the transcripts. Mark each
supported, partly supported, not yet built, or contradicted.

This is not a gotcha. Intention running ahead of code is normal. I just need to know
which is which before I open my mouth.

6. DECISIONS WITH NO RECORDED REASONING

Places where a real alternative existed and the work went one way. For each:

  What was chosen:
  Obvious alternative:
  Reasoning recorded anywhere: yes and where, or no

Do not judge the choice. I only want to know where the record is silent, because
that is where a question teaches me something. Where the reasoning is already
written down, a question just shows I did not read it, so tell me where it is
written instead.

7. WHAT I CANNOT DETERMINE FROM THE ARTIFACTS

Everything that needs a person. Be generous here. Include at least: why this work
was started and who asked for it, what was tried before and abandoned, what the
deadline is attached to, what constraints came from outside the team, who depends
on this shipping, and who will run it afterwards.

Group them by who is likely to know the answer.

Rules:

- No recommendations, no critique, no alternatives anywhere in this pass. There is a
  later prompt for judgment and putting it here will pollute it.
- Every factual statement carries its source, as a file path, a document section, or
  a transcript with a date.
- If you inferred something, write INFERRED and say what you inferred it from.
- If two sources disagree, show the disagreement. Do not pick a winner.
- Never invent a name, a handle, a team, a service, or an acronym. Write UNKNOWN.
- Only attribute a quote to a person if the inventory marked that speaker CONFIDENT.
  Otherwise write "someone in the standup on that date said".

The bar: if I showed this to the engineer who did the work, they would say yes, that
is accurate, including the parts that are unfinished.
