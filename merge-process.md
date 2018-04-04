# Merge process

When a pull request (PR) is issued, all interested parties should express any
concerns they have about the PR, by adding comments to the PR.

Acceptance of a PR is accomplished as follows:

- If the PR proposer is a member of the commit team, he/she does not have voting
  rights on this PR.
- A PR will be accepted when at least three business days have passed since the reviews
  began<sup>*</sup>, and one of the following conditions has been met:
  - PR contains only documentation changes
    - two assenting votes (approvals) have been cast with no dissenting votes
      (requests for changes).
  - PR contains any code changes
    - five assenting votes (approvals) have been cast with no dissenting votes
      (requests for changes).
- Any requests for changes prevent merging the PR.
- If there are dissenting votes during the voting process, discussion will ensue.
  Either the dissenters will eventually assent, or changes will be made (new commits)
  which will clear prior votes, and a new vote can be requested.
- If this PR fixes a bug that should be cherry-picked into a point release, it
  is the responsibility of the person merging the PR to cherry-pick this set of
  commits into the point release branch (possibly creating that point release
  branch if it did not previously exist).

\* If all members listed in the CODEOWNERS file have cast assenting votes for
a PR, there is no longer a need to wait for comments from other core
members. Therefore, the PR may be accepted and merged immediately upon all
core members' having cast assenting votes for the PR.
