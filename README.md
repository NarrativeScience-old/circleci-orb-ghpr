# CircleCI Orb: GitHub PR

[![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/narrativescience/ghpr)](https://circleci.com/orbs/registry/orb/narrativescience/ghpr)
[![License](https://img.shields.io/badge/License-BSD%203--Clause-blue.svg)](https://opensource.org/licenses/BSD-3-Clause)

Set of git utilities to manage GitHub Pull Requests in CI. This orb was created to address the need to simulate the result of merging the head branch into a PR's target base branch.

Additional features:

- Posting PR comments on success/failure/always
- Sending Slack notifications to PR authors

The commands in the orb will expose the following environment variables:

* `GITHUB_PR_BASE_BRANCH` - The base branch for the PR.
* `GITHUB_PR_NUMBER` - The number of the PR.
* `GITHUB_PR_TITLE` - The title of the PR.
* `GITHUB_PR_COMMIT_MESSAGE` - The current commit's message.
* `GITHUB_PR_AUTHOR_USERNAME` - The PR author's username.
* `GITHUB_PR_AUTHOR_NAME` - The PR author's name.
* `GITHUB_PR_AUTHOR_EMAIL` - The PR author's email address.

All these commands will work out-of-the-box in jobs using the
[`machine` executor](https://circleci.com/docs/2.0/executor-types/#using-machine).

## Getting Started

To use this orb, there are a few environment variables to set.
These can be set in a [Context](https://circleci.com/docs/2.0/contexts/)
or your [Project's Environment Variables](https://circleci.com/docs/2.0/env-vars/#setting-an-environment-variable-in-a-project).

### Setting up a GitHub service user

It's recommended to create a service GitHub user with at least Read access to your
repository and set the following environment variables:

* `GITHUB_USERNAME` - Username of the service user that has read/write permissions to the repo.
* `GITHUB_PASSWORD` - Password of the service user.
* `GITHUB_EMAIL` - Email of the service user.
* `GITHUB_TOKEN` - API token for the GitHub user

### Enabling Slack Notifications

To use the Slack related orb commands, create or use an existing
[workspace bot](https://slack.com/help/articles/115005265703-Create-a-bot-for-your-workspace)
and set the following environment variables:

* `SLACK_OAUTH_TOKEN` - [OAuth token](https://api.slack.com/docs/token-types#bot) for the Slack
bot that will be used to send Slack messages.

The bot user will need at least the following bot token scopes:

* [`chat:write`](https://api.slack.com/scopes/chat:write)
* [`chat:write.public`](https://api.slack.com/scopes/chat:write.public)
* [`users:read`](https://api.slack.com/scopes/users:read)
* [`users.profile:read`](https://api.slack.com/scopes/users.profile:read)
* [`users:read.email`](https://api.slack.com/scopes/users:read.email)
* [`im:write`](https://api.slack.com/scopes/im:write)

Messages show as being sent by the user associated with the `SLACK_OAUTH_TOKEN`.

#### Example notification
<img width="714" alt="Screen Shot 2020-06-03 at 21 55 38" src="https://user-images.githubusercontent.com/29710511/83716664-29337f00-a5f6-11ea-988f-898093d2ae90.png">

