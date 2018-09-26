---
url: /guides
title: Configure an API in Auth0
description: Learn how to configure an API using the Auth0 Dashboard.
topics:
  - api-authentication
  - oidc
  - apis
contentType: how-to
useCase:
  - secure-api
  - call-api
---
# Configure an API in Auth0

To configure an [API](/api-auth/apis.md) in Auth0, you will need to access the [Auth0 Dashboard](${manage.url)}). Once you have done so, you can follow the instructions below.

1. From the left menu, click [APIs](${manage_url}/#/apis).

::: note
Inside the API section, you will see one API that has been created automatically--the **Auth0 Management API**. For details about the features of the Management API and its available endpoints, you can visit the [Management API Explorer](/api/management/v2).
:::

2. Click the **+ Create API** button, and provide the following information for your API before clicking **Create**:

- **Name**: a friendly name for the API. Does not affect any functionality.

- **Identifier**: a unique identifier for the API. We recommend using a URL (this doesn't have to be a publicly available URL; Auth0 will not call your API at all). This value **cannot be modified** afterwards.

- **Signing Algorithm**: the algorithm with which to sign the tokens. The available values are `HS256` and `RS256`. When selecting `RS256`, the token will be signed with your tenant's private key. For more details, visit [Signing Algorithms](/concepts/signing-algorithms).

![Create a new API](/media/articles/api/overview/create-api.png)

Once you create your API, you will be able to see your API's *Quick Start*, which will guide you through any API code changes you will need to make to implement your API. These generally consist of choosing a JWT library from a pre-defined list and configuring the library to validate the [Access Tokens](/tokens/access-token) in your API.

![API Quick Starts](/media/articles/api/overview/quickstarts-view.png)

You will also see some additional dashboard views for your API.

## Dashboard Views for APIs

Other available views for your API include:

- **Settings**: lists the settings for your API, some of which are editable. In this section, you can change the token expiration time and enable offline access (so that Auth0 will allow applications to ask for Refresh Tokens for this API). For details, see [API Settings](/api-auth/dashboard/api-settings).

- **Scopes**: allows you to define the scopes for your API by setting scope names and a descriptions.

- **Machine to Machine Applications**: lists all applications for which the **Client Credentials** grant is **enabled**. (By default, this grant is **enabled* for [Regular Web Applications](/applications/webapps) and [Machine to Machine Applications](/applications/machine-to-machine)). You can authorize any listed application to request Access Tokens for your API. Optionally, you can select a subset of the defined scopes to limit an authorized application's access to your API. 

- **Test**: allows you to execute a sample Client Credentials flow with any of the authorized applications so you can check that everything is working as expected.