# Merge process

When a pull request (PR) is issued, all interested parties should express any
concerns they have about the PR, by adding comments to the PR. The commit team
(members wth write-access to the repository) will generally wait for at least
one full business day (Mon - Fri) before beginning voting to accept the PR, to
provide time for people to comment.

Acceptance of a PR is accomplished as follows:

- When the stream of comments has died down -- in particular, dissenting
  comments -- a member of the commit team will request reviews from the other
  team members.
- If the PR proposer is a member of the commit team, he/she does not have voting
  rights on this PR.
- A PR will be accepted when one of the following conditions has been met:
  - PR contains only documentation changes
    - two assenting votes have been cast with no dissenting votes.
  - PR contains any code changes
    - five assenting votes have been cast with no dissenting votes
    - at least two business days have passed since the call for votes, and two
      assenting votes have been cast with no dissenting votes
- If there are dissenting votes during the voting process, discussion will ensue
  and a new vote will be called when the points of conflict have been resolved.
- If this PR fixes a bug that should be cherry-picked into a point release, it
  is the responsibility of the person merging the PR to cherry-pick this set of
  commits into the point release branch (possibly creating that point release
  branch if it did not previously exist).
