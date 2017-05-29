# Requesting changes

- Ensure that if your proposed changes alter or extend functionality of qooxdoo,
  that you also provide tests to show that the changes both work properly and are
  backward-compatible.
  - If the changes are not backward-compatible, discuss on the Discussion List
    how to resolve it. Likely, you will be asked to create a new function to
    implement the new functionality, and possibly mark the original function as
    deprecated.
- Be sure you have created a separate, feature branch, for your proposed changes.
  Any modification done to the branch after your impending pull request has been
  issued will be applied to the pull request, so you need to be sure that you
  aren't making unrelated changes to that same branch after your pull request
  has been made.
- Push your committed branch to your github repository.
- From the github web page of your repository, use the Pull Request button, and
  select your feature branch that includes the proposed changes.
