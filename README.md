# M365 Copilot API Examples

A [Bruno](https://www.usebruno.com/) API collection with worked examples for the
Microsoft 365 Copilot / Microsoft Graph APIs — covering both **application** and
**delegated** authentication flows.

## What's inside

| Folder | Auth flow | Examples |
| --- | --- | --- |
| `Application Auth Examples/` | OAuth2 client credentials (app-only) | Enterprise Copilot interactions (all / biz-chat only / time-filtered) |
| `Delegate Auth Examples/` | OAuth2 authorization code (on behalf of a user) | Chat Bot (create conversation, query), Meeting AI Insights, search events |

## Prerequisites

- [Bruno](https://www.usebruno.com/downloads) (desktop app or CLI)
- An Azure AD **app registration** with the appropriate Microsoft Graph
  permissions for the requests you want to run (e.g. `User.Read`,
  `Calendars.ReadBasic`, `OnlineMeetings.Read`, and the relevant Copilot /
  interaction scopes).

## Setup

1. **Open the collection** — in Bruno, *Open Collection* and point it at this
   folder.

2. **Select an environment** — pick `Copilot API (Delegate)` or
   `Copilot API (Application)` from the environment dropdown.

3. **Fill in the secret variables.** This repo intentionally ships the
   environment files with their values stripped — every variable is marked as a
   Bruno *secret*, so the values live only in your local Bruno store and are
   never committed. Set the following for the environment you're using:

   | Variable | Description |
   | --- | --- |
   | `tenantId` | Your Azure AD tenant ID |
   | `appId` | The client (application) ID of your app registration |
   | `secret` | The client secret for that app registration |

4. **Run a request.** The folder-level OAuth2 config wires `{{tenantId}}`,
   `{{appId}}` and `{{secret}}` into the token endpoints, so once the variables
   are set Bruno fetches tokens automatically.

## A note on secrets

Environment values are stored as Bruno secret variables and are **not** part of
the committed files. Bruno keeps them in its local app data (outside this
folder), so cloning the repo gives you the request structure without any
tenant-specific credentials — fill in your own to run it.
