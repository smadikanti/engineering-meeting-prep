Continue from the reconstruction. Now form engineering judgment. This is my own
thinking. Nothing here goes into a meeting yet.

Argue their side first. Then go after the design.

1. THE BEST VERSION OF THEIR ARGUMENT

Make the case for the current direction the way its author would make it on a good
day. Cover: what is genuinely right about it, what constraint it respects that
someone new would not know about, what the more obvious approach would have cost,
and the conditions under which this is clearly the correct call.

Write it as advocacy, not as a summary with caveats.

If you cannot make this case convincingly, say so and say what you would need to
know. I am not ready to ask pointed questions about work I cannot defend.

2. WHAT THEY HAVE ALMOST CERTAINLY ALREADY THOUGHT OF

Before I raise anything, list the concerns so obvious that someone who has been
living in this for months has already handled them. Where the code or the document
shows they handled it, point at it.

Raising one of these as though it were an insight is the quickest way to look
junior, so I want them named and set aside.

3. FAILURE MODES

Work through every one of these explicitly. Do not skip one because it seems
unlikely. Say "not applicable here, because" if it does not apply.

  Partial execution. It dies halfway. What state is left behind, and can it be
  resumed or does someone clean it up by hand.
  Duplicate delivery. The same event arrives twice. Is the operation idempotent,
  and if not, what does the double effect look like.
  Retries. What retries, how many times, with what backoff, and is a retry storm
  reachable.
  Loud or quiet. When it fails, does anything anywhere say so.
  Slow dependency. Not down, just slow. Timeouts, queue growth, pileups.
  Poison input. Something that never succeeds. Does it block everything behind it.
  Wrong target. It does the right action to the wrong thing. How much damage before
  someone notices, and can it be undone.
  Clock and ordering. Out of order events, overlapping runs, daylight saving,
  timezone assumptions.
  Scale. What happens at ten times the current volume.
  Permissions. What it can do that it does not currently need to do.

For each one, in this format:

  Failure:
  Likelihood: high, medium, low, and why
  Cost if it happens:
  How we find out:
  How long until we find out:
  Who gets paged:

Then rank them by likelihood times cost, and tell me the top four.

4. THE SILENT FAILURE QUESTION

Separate section, because it is the one that actually hurts with automation.

Where could this be broken for days with nobody noticing? For each place, say what
signal would need to exist for that not to be true.

"Someone would eventually complain" is not a signal. Neither is "the logs would show
it" unless something reads the logs.

5. WHO RUNS THIS

Who operates it once it is live. What it asks of them in a normal week. What it asks
of them in a bad week. What happens when that person is on leave. What permissions
it holds and whether that scope tends to grow. Whether there is an audit trail if
someone asks what it did and why.

6. WHAT THIS MAKES HARD LATER

Split into two lists, because only one of them deserves meeting time:

  CHEAP TO REVISIT   we can change this later without much pain
  EFFECTIVELY PERMANENT  data shape, external contracts, anything with a migration

For the permanent ones: what assumption is baked in, what happens if that assumption
stops holding, and roughly what reversing it would cost.

7. ALTERNATIVES

Two or three genuinely different approaches. Always include the smallest possible
version, and always include doing less or doing nothing.

For each:

  Approach:
  What it buys:
  What it costs:
  What would have to be true for it to beat the current direction:
  Still live, or only interesting in hindsight:

Be honest about that last line. If the switching cost is already high, raising the
alternative wastes the room's time and makes me look like I want to restart their
work.

8. WHAT I WOULD NEED TO BELIEVE

Finish here. For me to be comfortable with the current direction, what would need to
be true?

Write each one as a single question a person can answer in a sentence. Not
rhetorical, not compound. These become my questions in the next prompt, so they need
to be askable out loud.

Rules:

- Label anything speculative as SPECULATION. Speculation is welcome in this pass, it
  just has to be marked.
- Rank by consequence. Four things that matter beat fifteen that are technically
  true, and fifteen will make me sound like I am reading a checklist.
- Go after the design, never the person. No comments about their judgment or what
  the work says about them.
- Do not soften anything here. Softening happens in the next prompt, where it
  belongs.
