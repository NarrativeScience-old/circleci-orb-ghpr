# CircleCI Orb: GitHub PR

[![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/narrativescience/ghpr)](https://circleci.com/orbs/registry/orb/narrativescience/ghpr) [![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

Set of git utilities to manage GitHub Pull Requests in CI. This orb was created to address the need to simulate the result of merging the head branch into a PR's target base branch.

Additional features:

- Posting PR comments on success/failure/always
- Sending Slack notifications to PR authors

The commands in the orb will expose the following environment variables:

* `GITHUB_PR_BASE_BRANCH` - The base branch for the PR.
* `GITHUB_PR_NUMBER` - The number of the PR.

## Getting Started

To use this orb, there are a few environment variables to set. These can be set in a [Context](https://circleci.com/docs/2.0/contexts/) or your [Project's Environment Variables](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project).

### Setting up a GitHub service user

It's recommended to create a service GitHub user with at least Read access to your repository and set the following environment variables:

* `GITHUB_USERNAME` - Username of the service user that has read/write permissions to the repo.
* `GITHUB_PASSWORD` - Password of the service user.
* `GITHUB_EMAIL` - Email of the service user.

### Enabling Slack Notifications

To use the Slack related orb commands, create or use an existing [workspace bot](https://slack.com/help/articles/115005265703-Create-a-bot-for-your-workspace) and set the following environment variables:

* `SLACK_OAUTH_TOKEN` - [OAuth token](https://api.slack.com/docs/token-types#bot) for the Slack bot that will be used to send Slack messages.

This orb uses the [email associated with commits](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address) to look up the user in a Slack workspace. Therefore, to receive notifications, committers should set their `user.email` in their `git config` to be the same email associated with their Slack account.
