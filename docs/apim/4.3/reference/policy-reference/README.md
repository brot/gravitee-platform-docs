---
description: Detailed documentation for all of Gravitee's policies
---

# Policy Reference

## Overview

Gravitee policies fall into several functional categories: security, transformation, restrictions, performance, routing, and monitoring & testing. Although the implementation details of each policy are unique, they share a common installation and deployment and are compatible with subsets of phases.

The following compatibility matrix uses checkmarks to indicate which policies are supported by each of the API types Gravitee offers.

{% hint style="info" %}
Policies cannot currently be applied to v4 TCP proxy APIs
{% endhint %}

<table><thead><tr><th width="257">Policy</th><th data-type="checkbox">v2 API</th><th data-type="checkbox">v4 HTTP proxy API</th><th data-type="checkbox">v4 message API</th></tr></thead><tbody><tr><td>API Key</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Assign Attributes</td><td>true</td><td>true</td><td>true</td></tr><tr><td>Assign Content</td><td>true</td><td>true</td><td>true</td></tr><tr><td>Assign Metrics</td><td>true</td><td>true</td><td>true</td></tr><tr><td>AVRO to JSON</td><td>true</td><td>true</td><td>true</td></tr><tr><td>AVRO to Protobuf</td><td>true</td><td>true</td><td>true</td></tr><tr><td>AWS Lambda</td><td>true</td><td>false</td><td>false</td></tr><tr><td>Basic Authentication</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Cache</td><td>true</td><td>false</td><td>false</td></tr><tr><td>Circuit Breaker</td><td>true</td><td>false</td><td>false</td></tr><tr><td>Cloud Events</td><td>false</td><td>false</td><td>true</td></tr><tr><td>Data Logging Masking</td><td>true</td><td>false</td><td>false</td></tr><tr><td>Dynamic Routing</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Generate HTTP Signature</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Generate JWT</td><td>true</td><td>true</td><td>false</td></tr><tr><td>GeoIP Filtering</td><td>true</td><td>true</td><td>false</td></tr><tr><td>GraphQL Rate Limit</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Groovy</td><td>true</td><td>true</td><td>true</td></tr><tr><td>HTTP Callout</td><td>true</td><td>true</td><td>false</td></tr><tr><td>HTTP Signature</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Interrupt</td><td>true</td><td>true</td><td>false</td></tr><tr><td>IP Filtering</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Javascript</td><td>true</td><td>true</td><td>false</td></tr><tr><td>JSON to JSON</td><td>true</td><td>true</td><td>true</td></tr><tr><td>JSON to XML</td><td>true</td><td>true</td><td>true</td></tr><tr><td>JSON Threat Protection</td><td>true</td><td>true</td><td>false</td></tr><tr><td>JSON Validation</td><td>true</td><td>true</td><td>false</td></tr><tr><td>JSON Web Signature</td><td>true</td><td>true</td><td>false</td></tr><tr><td>JSON Web Token</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Keyless</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Latency</td><td>true</td><td>true</td><td>true</td></tr><tr><td>Message Filtering</td><td>false</td><td>false</td><td>true</td></tr><tr><td>Mock</td><td>true</td><td>false</td><td>false</td></tr><tr><td>OAuth2</td><td>true</td><td>true</td><td>false</td></tr><tr><td>OpenID Connect UserInfo</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Override HTTP Method</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Protobuf to JSON</td><td>true</td><td>true</td><td>true</td></tr><tr><td>Rate Limit</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Regex Threat Protection</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Request Content Limit</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Request Validation</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Resource Filtering</td><td>true</td><td>true</td><td>false</td></tr><tr><td>REST to SOAP</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Retry</td><td>true</td><td>false</td><td>false</td></tr><tr><td>Role-based Access Control</td><td>true</td><td>true</td><td>false</td></tr><tr><td>SSL Enforcement</td><td>true</td><td>true</td><td>false</td></tr><tr><td>Traffic Shadowing</td><td>true</td><td>false</td><td>false</td></tr><tr><td>Transform Headers</td><td>true</td><td>true</td><td>true</td></tr><tr><td>Transform Query Params</td><td>true</td><td>true</td><td>false</td></tr><tr><td>WS Security Authentication</td><td>true</td><td>true</td><td>false</td></tr><tr><td>XML to JSON</td><td>true</td><td>true</td><td>true</td></tr><tr><td>XML Threat Protection</td><td>true</td><td>true</td><td>false</td></tr><tr><td>XML Validation</td><td>true</td><td>true</td><td>false</td></tr><tr><td>XSLT</td><td>true</td><td>true</td><td>false</td></tr></tbody></table>

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
