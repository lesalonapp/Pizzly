<a href="https://heroku.com/deploy?template=https://github.com/Bearer/Pizzly" rel="nofollow"><img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy to Heroku" height="26"></a>
<a href="https://console.platform.sh/projects/create-project/?template=https://github.com/Bearer/Pizzly&utm_campaign=deploy_on_platform?utm_medium=button&utm_source=affiliate_links&utm_content=https://github.com/Bearer/Pizzly" rel="nofollow"><img src="https://platform.sh/images/deploy/deploy-button-lg-blue.svg" alt="Deploy with Platform.sh" height="26"></a>
<a href="https://www.bearer.sh/?ref=pizzly" rel="nofollow"><img src="/views/assets/img/badges/bearer-badge.png?raw=true" alt="Sponsored by Bearer.sh" height="26"></a>

# Pizzly 🐻 - The OAuth Integration Proxy

<div align="center">

<img src="/views/assets/img/logos/pizzly.png?raw=true" width="300">

The OAuth Integration Proxy

<!-- Build badge || License Badge || Heroku badge
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
-->
</div>

Pizzly is an OAuth Integration Proxy that acts as an abstraction layer to simplify integrating with OAuth API. It lets you connect 50+ OAuth APIs out-of-the-box and automatically manages retrieving, storing, and refreshing OAuth tokens. It also supports adding new OAuth APIs by using a simple file definition.

Pizzly is made available as an open-source project by [Bearer.sh](https://bearer.sh/?ref=pizzly).

## Summary

- [Why Pizzly?](#why-pizzly)
- [How it works?](#how-it-works)
- [Key Features](#key-features)
- [Installation](#installation)
  - [Manual Install](#manual-install)
  - [PaaS Deployment](#paas-deployment)
- [Getting Started](#getting-started)
  - [Using Pizzly as a complete API proxy](#using-pizzly-as-a-complete-api-proxy)
  - [Using Pizzly as an OAuth manager](#using-pizzly-as-an-oauth-manager)
- [Supported APIs](#supported-apis)
- [License](#license)

## Why Pizzly?

Pizzly originally started at Bearer.sh as a way to simplify the developer's journey and ease the building of API integrations. OAuth is a great framework, but the difficulty and wide range of implementation makes it painful to use and tends to slow down the ability to integrate with new APIs.

_But seriously, why Pizzly? We're fan of bears and fell in love with this [sweet hybrid](https://en.wikipedia.org/wiki/Grizzly–polar_bear_hybrid) one 🐻_

## How it works?

You can use Pizzly as a **complete API proxy**, it means that each API request will go through the service. Pizzly forwards each request to the third-party API using a config file, it authenticates each request with the right `access_token` and handles token refreshness if needed.

![Diagram of Pizzly used in the proxy service mode](views/assets/img/docs/pizzly-diagram-api-proxy-mode.jpg?raw=true)

Pizzly is also available as a standalone **OAuth manager**, helping you retrieve the initial token, but you'll have to refresh it when needed _(read more with the [Getting Started](https://github.com/Bearer/Pizzly/wiki/Getting-started))_.

## Key Features

- Manage retrieving, storing, and refreshing OAuth tokens _(aka the OAuth dance)_
- No scope limitations
- Retrieve and store complete OAuth payload
- Support of OAuth 1, OAuth 1a and OAuth 2.0
- JavaScript library to connect from your web-app (three-legged OAuth flow)
- Provides configurations for over 50+ OAuth APIs (see list below)
- Support adding new OAuth APIs using a file definition
- 1-click deploy to Heroku or major cloud hosting solutions

## Installation

At the heart of Pizzly is a Node.js application that uses PostgreSQL as a database. It is straightforward to install on Heroku using the **[deploy to Heroku](https://heroku.com/deploy?template=https://github.com/Bearer/Pizzly)** button, but you can install it anywhere.

### Manual Install

To run Pizzly on your machine, follow these steps (or [follow our step-by-step guides](https://github.com/Bearer/Pizzly/wiki/Getting-started)):

```bash
git clone https://github.com/Bearer/Pizzly
cd pizzly
yarn install
yarn db:setup
yarn start
```

Then open the dashboard in your browser at:

```
http://localhost:8080/
```

You will need Node.js and PostgreSQL installed first. Read our [getting started](https://github.com/Bearer/Pizzly/wiki/Getting-started) to follow a step-by-step installation guide.

### PaaS Deployment

Click the buttons below for an automated deployment so you can test it. Once deployed, go to the application and connect to an API.

| Heroku Install                                                                                                                                                                              | Platform.sh Install                                                                                                                                                                                                                                                                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <a href="https://heroku.com/deploy?template=https://github.com/Bearer/Pizzly" rel="nofollow"><img src="https://www.herokucdn.com/deploy/button.svg" alt="Deploy to Heroku" height="40"></a> | <a href="https://console.platform.sh/projects/create-project/?template=https://github.com/Bearer/Pizzly&utm_campaign=deploy_on_platform?utm_medium=button&utm_source=affiliate_links&utm_content=https://github.com/Bearer/Pizzly" rel="nofollow"><img src="https://platform.sh/images/deploy/deploy-button-lg-blue.svg" alt="Deploy with Platform.sh" height="40"></a> |

## Getting Started

### Using Pizzly as a complete API proxy

Follow this step-by-step guide on [how to use Pizzly as a proxy service](https://github.com/Bearer/Pizzly/wiki/Tutorial-:-Proxy) and learn how to:

1. Initiate the OAuth dance to retrieve a token
2. Call the third-party API
3. Retrieve data from that API

### Using Pizzly as an OAuth manager

Follow a step-by-step guide on [how to use Pizzly as an OAuth manager](https://github.com/Bearer/Pizzly/wiki/Tutorial-:-OAuth) and learn how to:

1. Save a configuration for an API (with clientId/clientSecret and scopes)
2. Initiate the OAuth dance to retrieve a token
3. Use Pizzly's API to retrieve the OAuth payload (e.g. `access_token`, `refresh_token`, etc.)

> If you're looking to monitor, track performance, detect anomalies to your API requests, have a look to [Bearer.sh](https://bearer.sh/?ref=pizzly), the monitoring agent. If you're using Pizzly in API proxy mode, it's as simple as adding your Bearer Developer Key to the environment variable `$BEARER_SECRET_KEY` - you can [get yours for free here 🚀](https://bearer.sh/?ref=pizzly)

## Services

Pizzly works as a self-hosted instance that provides different services including:

- [an auth manager](https://github.com/Bearer/Pizzly/wiki/Reference-:-Auth);
- [a proxy service](https://github.com/Bearer/Pizzly/wiki/Reference-:-Proxy);
- [a developer's dashboard](https://github.com/Bearer/Pizzly/wiki/Reference-:-Dashboard);
- [an API](https://github.com/Bearer/Pizzly/wiki/Reference-:-API);
- and [a JavaScript library](/src/clients/javascript/) to interact with each service from your frontend;

## Supported APIs

[![Some pre-configured APIs with Pizzly](/views/assets/img/docs/pizzly-preconfigured-apis.jpg)](https://github.com/Bearer/Pizzly/wiki/Supported-APIs)

More than 50 APIs are preconfigured to work out-of-the-box. Including:

- **Communication**: Gmail, Microsoft Teams, Slack, Zoom;
- **CRM**: Front, Hubspot, Salesforce, etc.
- **Developer tools**: BitBucket, GitHub, GitLab, etc.
- **Finance**: Xero, Sellsy, Zoho Books, etc.
- **Productivity**: Asana, Google Drive, Google Sheets, Jira, Trello, etc.
- **Social**: Facebook, LinkedIn, Reddit, etc.
- **[and more...](https://github.com/Bearer/Pizzly/wiki/Supported-APIs)**

Each API consists of a JSON configuration file, stored within the `/integrations` directory. Here's an example with the GitHub configuration file ([`/integrations/github.json`](/integrations/github.json)):

```json
{
  "name": "GitHub",
  "auth": {
    "authorizationURL": "https://github.com/login/oauth/authorize",
    "tokenURL": "https://github.com/login/oauth/access_token",
    "authType": "OAUTH2",
    "tokenParams": {},
    "authorizationParams": {},
    "auth": { "accessType": "offline" }
  },
  "request": {
    "baseURL": "https://api.github.com/",
    "headers": {
      "Accept": "application/vnd.github.v3+json",
      "Authorization": "token ${auth.accessToken}",
      "User-Agent": "Pizzly"
    }
  }
}
```

And adding new APIs is straightforward. Just create a new configuration file within the `/integrations` folder of your Pizzly's instance. If you feel like sharing, you can even create a PR so that other developers will be able to use it as well!

## License

This project is licensed under the terms of the MIT license. See the [LICENSE file](LICENSE.md) for more information.
