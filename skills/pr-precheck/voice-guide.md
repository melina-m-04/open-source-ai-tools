# Voice guide: how I talk upstream

<!-- CUSTOMIZE: Every section in this file is personal. Replace the examples
with your own voice and the mistakes you actually make. The same file is used by
repro-check, plan-check, and pr-precheck, so keep all three copies
identical. -->

## Who I am in threads

<!-- CUSTOMIZE: Describe yourself as a contributor in one or two sentences: your
experience level and how you approach unfamiliar projects. -->

I am a learner and contributor working through the repository while building my
understanding of the project. I may not have all the answers, so I distinguish
what I observed from what I think is happening and give enough concrete context
for someone else to verify it.

## Rules I write by

<!-- CUSTOMIZE: Write rules for how you phrase comments. Give each rule a Wrong
line you might realistically write and the Right line you would post instead; a
rule without a pair cannot be checked. -->

### Rule: Say what I observed

State the concrete behavior I saw instead of presenting an assumption as a fact.

- Wrong: "This is definitely a bug in the parser."
- Right: "I reproduced the error when the parser receives this input."

### Rule: Be specific about evidence

Point to the relevant command, output, file, or behavior instead of making a
vague claim that something "doesn't work."

- Wrong: "It doesn't work for me."
- Right: "Running python test.py with Python 3.12 produces ValueError: ...."

### Rule: Separate reproduction from interpretation

Do not claim that I confirmed the issue when I only observed a related behavior.

- Wrong: "I confirmed the issue is caused by the dependency."
- Right: "I reproduced the reported error with dependency version 2.4.1; I did
  not determine whether the dependency is the cause."

### Rule: Say when I cannot reproduce it

If the reported behavior does not occur, say so directly rather than changing
the conditions until I get a different failure.

- Wrong: "The issue is still present, but I got a different error."
- Right: "I could not reproduce the reported error using the documented steps
  and environment."

### Rule: Keep the comment useful

Include the information someone needs to understand or verify the result,
without filling the comment with unnecessary explanation.

- Wrong: "I followed everything and after a bunch of troubleshooting I think
  maybe there could potentially be an issue here."
- Right: "I followed the documented steps and could not reproduce the reported
  behavior."

## Things I never post

<!-- CUSTOMIZE: List the promises, tones, and shortcuts you never want in a
public comment. The skill quotes this list back when a draft crosses it. -->

- Claims that I reproduced an issue when my evidence shows a different or
  unrelated failure.
- Statements presented as facts when they are only my guesses or
  interpretations.
- "Works for me" without saying what environment or steps I used.
- Promises that I will investigate, test, or follow up unless I actually intend
  and am able to do so.
- A confident conclusion when the evidence is inconclusive.

## Upstream: how I talk to maintainers

<!-- CUSTOMIZE: Write rules for claims, questions, and follow-up pings, in the
same Wrong/Right format as above. -->

### Claims I post

#### Rule: Make my intent and first step clear

When I claim an issue, I state that I would like to work on it, name a concrete
first step, and give a realistic time for my next update. I do not imply that a
maintainer has approved my work or promise a deadline I cannot meet.

- Wrong: "I'll fix this issue ASAP and get a PR in soon."
- Right: "I'd like to work on this issue. I'll start by reproducing the reported
  behavior and reviewing the relevant code, then report back with my findings by
  [realistic date]."

#### Rule: Check that the issue is available before claiming it

I read the issue thread before claiming work and do not claim an issue that
another contributor has already asked to work on.

- Wrong: "I'm taking this issue, even though someone else has already offered to
  work on it."
- Right: "I'd like to work on this issue. I'll start by reviewing the
  reproduction steps and checking the relevant code."

### Questions I ask

#### Rule: Show what I checked before asking for help

I explain what I have already read or tried, include the relevant evidence, and
ask one focused question that a maintainer can answer.

- Wrong: "Can you explain how this whole feature works and tell me how to fix
  it?"
- Right: "I reviewed the documented reproduction steps and tried them with
  [environment/version]. I still cannot determine whether [specific behavior] is
  expected. Is there a documented constraint I should check before investigating
  further?"

#### Rule: Separate what I know from what I suspect

I describe observed behavior separately from my interpretation and avoid asking
maintainers to confirm an unsupported diagnosis.

- Wrong: "The dependency is obviously causing this bug. Can you fix it?"
- Right: "I observed [specific behavior] when running [command or steps]. I
  suspect it may involve [component], but I have not confirmed the cause. Is
  there a related area of the code you recommend examining?"

### Pings I send

#### Rule: Follow the project's pace instead of my own

I check the project's contribution guidance and existing discussion rhythm
before following up. I do not send repeated messages just because I want a
faster response.

- Wrong: "Any updates? I really need an answer today."
- Right: "Following up on my question above in case it was missed. I checked
  [relevant documentation or evidence] in the meantime and [brief update]. No
  rush; I can continue investigating while I wait."
