# Search strategy: where your scout looks, and why

## Queries

<!-- CUSTOMIZE: Write queries that come from your fit profile in scope.md. Quote
the line of the profile each query traces to, and change --language, --label,
and other filters to match your interests. -->

From: "I want to work on projects in Python."

```bash
gh search issues --label "good first issue" --language python --state open \
  --limit 100 \
  --json title,repository,labels,assignees,commentsCount,updatedAt,url
```

From: "I have experience in Software Engineering, Full-Stack Web App
Development, and AI Engineering."

```bash
gh search issues --label "help wanted" --language python --state open \
  --limit 100 \
  --json title,repository,labels,assignees,commentsCount,updatedAt,url
```

## Ranking filters

<!-- CUSTOMIZE: Optional: adjust these to rank by what matters to you. Filters
may only use fields the search query returns. -->

Drop any result that has one or more assignees.

Prefer results with fewer comments over results with more comments.

When results have the same number of comments, prefer the most recently updated
issue.

If two results have the same comment count and update time, preserve their
original search order.

## How many to grade

<!-- CUSTOMIZE: Optional: grade more candidates per scan for more choice, or
fewer to save tokens. -->

Grade the top **5** ranked results per scan.
