# CircleCI Orb: GitHub PR [![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/narrativescience/ghpr)](https://circleci.com/orbs/registry/orb/narrativescience/ghpr) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

[View in CircleCI Orb Registry](https://circleci.com/orbs/registry/orb/narrativescience/ghpr)

Set of git utilities to manage GitHub Pull Requests in CI, namely simulating the result of
merging the head branch into the PR's target base branch.

To use, create a service GitHub user with at least Read access to your repository and set the following environment variables in a [Context](https://circleci.com/docs/2.0/contexts/) or your [Project's Environment Variables](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project):

* `GITHUB_USERNAME` - Username of the service user that has read/write permissions to the repo.
* `GITHUB_PASSWORD` - Password of the service user.

The commands in the orb will expose the following environment variables:

* `GITHUB_PR_BASE_BRANCH` - The base branch for the PR.
* `GITHUB_PR_NUMBER` - The number of the PR.
