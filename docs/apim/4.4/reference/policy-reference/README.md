---
description: Detailed documentation for all of Gravitee's policies
---

# Policy Reference

## Overview

Gravitee policies fall into several functional categories: security, transformation, restrictions, performance, routing, and monitoring & testing. Although the implementation details of each policy are unique, they share a common installation and deployment and are compatible with subsets of phases.

## Installation and deployment

Each version of Gravitee API Management (APIM) includes a number of policies in the default distribution. [Gravitee Enterprise Edition policy plugins](../../overview/gravitee-apim-enterprise-edition/#enterprise-plugins) are available for download [here](https://download.gravitee.io/).

To use a different version of the policy or add a custom policy, you can follow the deployment instructions below.

<details>

<summary>How to deploy a plugin</summary>

Please check the policy documentation to ensure the policy version you select is compatible with your version of APIM.

To deploy the plugin, follow these steps:

1. Download the plugin archive (a `.zip` file) from [the plugins download page](https://download.gravitee.io/#graviteeio-apim/plugins/).
2. Add the file into the Gateway and Management API `plugins` folders. The default location is ${GRAVITEE\_HOME/plugins} but this can be modified in [the `gravitee.yaml` file.](../../getting-started/configuration/apim-gateway/general-configuration.md#configure-the-plugins-repository) For most installations, the Gateway and Management API `plugins` folders are at `/gravitee/apim-gateway/plugins` and `/gravitee/apim-management-api/plugins`, respectively.
3. Restart your APIM nodes.

</details>

## Configuration

Policies can be added to flows that are assigned to an API or to a [plan](../../guides/api-exposure-plans-applications-and-subscriptions/plans/). Gravitee supports configuring policies [through the Policy Studio](../../guides/policy-studio/) in the Management Console or interacting directly with the Management API.

## Phases

Policies can be applied to the request or the response of a Gateway API transaction, which are broken up into phases that depend on the API definition version. Each policy is compatible with a subset of the available phases.

{% tabs %}
{% tab title="v4 API definition" %}
v4 APIs have the following phases:

* `onRequest`: This phase is executed before invoking the backend services for both proxy and message APIs. Policies can act on the headers and the content for proxy APIs.
* `onMessageRequest`: This phase occurs after the `onRequest` phase and allows policies to act on each incoming message before being sent to the backend service. This only applies to message APIs.
* `onResponse`: This phase is executed after invoking the backend services for both proxy and message APIs. Policies can act on the headers and the content for proxy APIs.
* `onMessageResponse`: This phase after the `onResponse` phase and allows policies to act on each outgoing message before being sent to the client application. This only applies to message APIs.
{% endtab %}

{% tab title="v2 API definition" %}
v2 APIs have the following phases:

* `onRequest`: This phase only allows policies to work on request headers. It never accesses the request body.
* `onRequestContent`: This phase always occurs after the `onRequest` phase. It allows policies to work at the content level and access the request body.
* `onResponse`: This phase only allows policies to work on response headers. It never accesses the response body.
* `onResponseContent`: This phase always occurs after the `onResponse` phase. It allows policies to work at the content level and access the response body.
{% endtab %}
{% endtabs %}
