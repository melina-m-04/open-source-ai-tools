# Scope: where your plan lands

## Where your issue lives

Any public repository, one issue at a time: the issue your claim names. That
issue comes to you through your own evidence trail, the scout's saved read-out
(a site pick graded in direct mode, usually saved in
`~/.claude/skills/issue-scout/scan-output.md`, or a scan's top five) and the
claim you posted on it. Do not grade plans for an issue you have not claimed. If
the issue is not in the scout's read-out, stop and suggest running `issue-scout`
in direct mode on the issue URL first.

## Contribution rules for public repositories

- **A posted plan is a claim with an approach attached.** If someone
  else has already posted a concrete plan on the issue, do not post a
  competing one; engage theirs in the thread, or pick again. On a
  public project, parallel plans are a race that wastes maintainer
  time.
- **Maintainer direction outranks your plan.** If the thread already
  says how the maintainers want this handled, your plan either follows
  that direction or opens a conversation about it before you build.
  Building against stated direction wastes your work and their
  patience.
- **Branch conventions are the repo's, not yours.** The
  `fix/<issue>-<slug>` habit is a good default, but the repo's
  contributing docs decide branch, commit, and PR conventions. The
  repo's stated asks always win.
- **Deviations get reported upstream, not just recorded.** If your approach
  changes materially after you posted the plan comment, say so in the thread
  before the pull request appears. A maintainer who read plan A should never be
  surprised by diff B.
