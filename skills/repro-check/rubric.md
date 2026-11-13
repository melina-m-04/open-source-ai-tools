# Rubric: is this reproduction package ready to post?

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| env-recorded | The environment record in the repro report, including the versions/configuration needed to reproduce the issue; look specifically at the report's environment section/record | The recorded environment contains enough concrete information to determine what environment produced the observed result and to reproduce it without guessing essential details | Required |
| steps | The reproduction steps in the repro report, together with any referenced setup commands or fixtures in the package; look at the report's steps/instructions section and the referenced setup files, scripts, or fixtures | A person with access to the package can follow the steps in order and reach the reported test point without needing undocumented essential actions or information | Required |
| honest-outcome | The claim comment and stated outcome in the repro report, read against the actual reproduction evidence/output excerpt in the package | The stated outcome accurately reflects the evidence, and the package does not claim reproduction or confirmation that the evidence does not support | Required |
| claim-intent | The candidate claim comment, read against the issue it is posted on | The comment states what the author actually did and what they intend to do next in terms specific to this issue, and makes no commitment the author cannot honestly back: no fixed delivery deadline, no guaranteed fix, no request to reserve or hold the issue. A comment whose stated intent would read identically on any other issue fails | Required |
| disclosure | The AI/contribution policy in the repo-facts block, read against both candidate comments; treat every package as AI-assisted work | If the stated policy requires disclosing AI assistance in comments of this kind, the comments disclose it in the terms the policy asks (the tool used, and the extent of the assistance). If the stated policy imposes no such requirement on issue comments, including when the repo-facts block states no AI policy, this check passes; that is a pass, not an unclear | Required |

## Verdict rule

Accept if every required check passes. Reject if any required check fails. An
unclear result is the same as a fail for that check.
