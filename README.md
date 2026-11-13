# open-source-ai-tools

AI skills that help with every step of contributing to an open source repo.

## Why this exists

Contributing to open source is often hard to start. Finding a suitable issue,
confirming the bug is reproducible, planning a change maintainers will accept,
and submitting a clean PR each take judgment. These skills turn that judgment
into repeatable checks, so you spend less time guessing and more time
contributing. They support your work. They don't write your code or submit
anything on your behalf.

## Skills

| Skill | Purpose |
|---|---|
| `issue-scout` | Find and grade issues worth working on based on experiences and interests |
| `repro-check` | Confirm you can reproduce a bug before you start fixing it |
| `plan-check` | Review your plan for scope, fit, and open questions before you code |
| `pr-precheck` | Check your PR against the project's guidelines before you submit it |

### What each skill checks

- **`issue-scout`**: searches for candidate issues and grades each one against a
  rubric, such as whether it is unclaimed, well scoped, and a fit for your
  background.
- **`repro-check`**: verifies the bug can be reproduced, with clear steps,
  environment details, and expected vs. actual behavior.
- **`plan-check`**: checks that your scope is realistic, your approach fits the
  project, and open questions are raised before you write code.
- **`pr-precheck`**: reviews scope, tests, description, and tone against the
  project's contribution guidelines, so maintainers get a clean review.

## Repository structure

```text
skills/
  issue-scout/    # SKILL.md plus rubric, scope, and search strategy
  repro-check/    # SKILL.md plus rubric, scope, and voice guide
  plan-check/     # SKILL.md plus procedure, rubric, scope, and voice guide
  pr-precheck/    # SKILL.md plus procedure, rubric, scope, voice guide,
                  # and contract
```

## Usage

### Prerequisites

- [Claude Code](https://claude.com/claude-code) installed (see the [skills
  docs](https://docs.claude.com/en/docs/claude-code/skills) if you're new to
  skills)
- A terminal with `git` available

### Install

Clone the repo:

```bash
git clone https://github.com/melina-m-04/open-source-ai-tools.git
cd open-source-ai-tools
```

Install **all** skills at once:

```bash
cp -R skills/* ~/.claude/skills/
```

Or install a **single** skill:

```bash
cp -R skills/issue-scout ~/.claude/skills/
```

Start a new Claude Code session afterward so the skills are picked up.

### Run a skill

Skills load automatically when your request matches their description. You can
also name one directly:

```text
Use the issue-scout skill to find issues in owner/repo that match my experience
Use the repro-check skill to confirm I can reproduce this bug
Use the plan-check skill to review my plan for issue #123
Use the pr-precheck skill to check my PR before I submit it
```

### Recommended workflow

1. `issue-scout`: find an issue
2. `repro-check`: reproduce the problem
3. `plan-check`: review your approach before writing code
4. `pr-precheck`: check your PR before submitting

Each step builds on the one before it: `repro-check` and `plan-check` only grade
issues that `issue-scout` has saved to
`~/.claude/skills/issue-scout/scan-output.md`. To check an issue you found some
other way, run `issue-scout` on its URL first.

### Files you provide

The checks read your drafts from the working directory of your fork:

| Skill | You provide |
|---|---|
| `repro-check` | Your draft claim comment and, once you have one, your draft repro report, plus the issue URL |
| `plan-check` | `plan.md` (with a `## Deviations` section) and your draft plan comment, plus the issue URL |
| `pr-precheck` | `plan.md`, `pr_draft.md` (PR title and description), `test_evidence.md` (test output and before/after repro output), and your committed branch |

### Customize

Sections you need to personalize before your first run are marked with a `<!--
CUSTOMIZE: ... -->` comment. To list them all, run `grep -rn CUSTOMIZE skills/`.

- Each skill's `scope.md` controls what it covers. Edit it to fit your own
  experience, interests, and target projects.
- The `voice-guide.md` in `repro-check`, `plan-check`, and `pr-precheck`
  controls your tone and language and flags content you never want to post. Keep
  the three copies in sync when you edit one.

### Update

Pull the latest changes and copy the skills over again:

```bash
git pull
cp -R skills/* ~/.claude/skills/
```

## Costs

These skills run inside [Claude Code](https://claude.com/claude-code), so what
you pay depends on how you sign in:

- **Subscription (Pro, Max, Team, Enterprise):** usage is included in your plan
  up to its limits. See [claude.com/pricing](https://claude.com/pricing) for
  current plans.
- **API / Console:** you pay per token. See the [API pricing
  page](https://platform.claude.com/docs/en/about-claude/pricing) for current
  rates.

### What drives the cost of these skills

- **Searching and reading:** `issue-scout` reads many issues per scan, so it
  will usually use the most tokens. The other three work on a single issue,
  plan, or PR.
- **Model choice:** a smaller model costs less than a larger one. Switch with
  `/model`.
- **Session length:** Claude Code resends the whole conversation on each
  request, so long sessions cost more. Run `/clear` between unrelated tasks.
- **Thinking effort:** lower it with `/effort` for simple checks.

### Check your own usage

Run `/usage` in Claude Code after a skill finishes. On an API key it shows an
estimated session cost; on a subscription it shows how much of your plan limit
you used. For billing, use the usage page in the Claude Console.
