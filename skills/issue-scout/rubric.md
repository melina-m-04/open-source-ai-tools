# Rubric: is this a good first issue?

## Checks

<!-- CUSTOMIZE: The profile-fit row is personal: rewrite its pass condition to
name your own interests and the kinds of work you want to avoid, matching your
fit profile in scope.md. The other checks apply to any contributor. -->

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-commits | "last 5 default-branch commits" under Repo facts | Newest commit is dated within the past 30 days | Required |
| AI-policy | "contribution policy" line under Repo facts | AI-assisted contribution is not banned | Required |
| unclaimed-issue | The "this issue:" line under Repo facts plus every comment in the Comments section | ALL of these hold: (1) assignees is `none`; (2) no linked PR is open, and no comment mentions an open PR for this issue; (3) no comment dated within 30 days before the capture date says the writer is taking or working on the issue (examples: "I'll take this", "can I work on this", "working on this"), unless a later comment withdraws it. A claim older than 30 days with no PR mentioned after it does not count. A closed, unmerged PR is not a claim. | Required |
| latest-release-within-a-year | "latest release" under Repo facts | Newest release/ship is dated within the past 365 days | Preferred |
| scope-feasible | Issue body: the work it asks for | The issue describes one identifiable piece of work someone could start: a behavior, a gap, or a task you can point at. It fails only when there is no single piece of work in it: a codebase-wide checklist, an "improve X everywhere", or a container issue tracking many sub-tasks. An open design edge, an "etc.", or several files involved never fails this check; that raises the difficulty note instead. | Required |
| profile-fit | "Issue body" under Issue, plus relevant repository/file evidence | Pass only if the actual contribution fits the user's stated interests in software engineering, full-stack web development, or AI engineering. Fail for translation-only tasks, or cybersecurity-related work. Do not infer task fit from the repository's primary language alone. | Required |

## Difficulty note

With each accepted candidate, report a one-line difficulty note in the read-out
summary:

- **straightforward**: the issue names where the change lives and the change is
  bounded.
- **moderate**: the location is yours to find, or several files are involved.
- **ambitious**: an open design edge, or an unfamiliar subsystem; name the edge,
  because claiming this issue means raising it with the maintainer early.

The note is information for the chooser, never a verdict input: it does not
appear in the fenced JSON block, it never changes accept or reject, and in eval
mode it is skipped entirely.

## Verdict rule

1. Grade every check in the table as `pass`, `fail`, or `unclear`, using only
   the evidence source named in its row.
2. Accept the issue if every `required` check passes.
3. Reject the issue if any `required` check fails.
4. `unclear` on a required check counts as `fail`.
5. `preferred` checks never change the verdict, whatever their grade, including
   `unclear`. For accepted issues, report each preferred grade in the summary.
   An accepted issue with more preferred passes ranks higher.
6. The verdict is always exactly `accept` or `reject`, never a third value.
