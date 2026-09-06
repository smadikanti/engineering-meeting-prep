Take inventory of what I have. Do not analyze the work, do not summarize what it
does, do not form a view. I want to know what is in front of me and how much of it
you actually read.

The material is in one folder:

  doc/          a design document or write-up
  transcripts/  meeting recordings and standups, in date order
  repos/        cloned repositories
  notes/        anything I wrote down myself

Produce these six sections.

1. WHAT IS HERE

One line per source, in this format:

  path | kind | date | size or length

For each repository also give: date of the most recent commit, roughly how many
commits landed in the last ninety days, and how many different people committed.

2. COVERAGE

This is the most important section and I read it before I read anything else.

Label every source with exactly one of these:

  READ FULLY      you processed all of it
  SAMPLED         you read part of it, and you say which part
  STRUCTURE ONLY  you read directory and file names, not the contents
  SKIPPED         you did not read it, and you say why

For repositories, name the actual files you read. Do not write "reviewed the
codebase". A real answer looks like this:

  repos/scheduler | SAMPLED | read main.py, handlers/, config/prod.yaml.
  Did not read tests/ or the migrations directory.

If you ran out of room, say where you stopped. Six repositories is more than most
sessions can hold, and I would rather know you read two properly than believe you
read all six.

3. STALE OR SUPERSEDED

Anything that has not been touched in a while, or that looks replaced by something
else in the folder. Give the evidence: last commit date, a comment saying it moved,
a document that refers to it in the past tense. Do not conclude it is dead. I will
ask.

4. TRANSCRIPT SPEAKERS

Per transcript, list who appears to be speaking, and mark each name CONFIDENT or
UNCERTAIN.

Mark UNCERTAIN when the label is generic like Speaker 1, when a name appears only
once, when the same person seems split across two labels, or when a name is spelled
inconsistently.

I may repeat one of these quotes in a room with the person who said it, so a wrong
attribution costs me more than a missing one.

5. MISSING

Things I would expect to exist and do not see. Go through this list explicitly and
mark each present or absent:

  tests
  continuous integration config
  deployment config
  monitoring or alerting config
  runbook or on-call documentation
  decision records
  a rollout or migration plan
  a README with more than a title
  any kind of changelog

Absent is a question for the meeting, not a fault. Report it flatly.

6. READING ORDER

If I had one hour with this material myself, what would I read and in what order.
One line each on why.

Rules:

- Never invent a name, a handle, a team, a service, or an acronym. If it is not in
  the sources, write UNKNOWN.
- Do not explain why anything exists or whether it is a good idea. That is the next
  prompt.
- If two sources describe the same thing differently, note the difference and move
  on. Do not reconcile them.
- Keep the whole thing under two pages. This is an index, not an analysis.
