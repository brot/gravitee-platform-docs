---
description: Learn how to create your Gravitee APIs using the Gravitee API creation wizard
---

# The API Creation Wizard

The Gravitee API creation wizard provides an easy-to-use UI to create Gravitee Gateway APIs. There are two versions of the API creation wizard:

* v2: Creates APIs that use the Gravitee v2 API definition
* v4: Creates APIs that use the Gravitee v4 API definition

<table><thead><tr><th width="212">Version</th><th>Supports</th></tr></thead><tbody><tr><td><a href="v2-api-creation-wizard.md">v2 API creation wizard</a></td><td><ul><li>HTTP 1 and 2 protocols</li><li>The legacy v2 Policy Studio</li></ul></td></tr><tr><td><a href="v4-api-creation-wizard.md">v4 API creation wizard</a></td><td><ul><li>AsyncAPI spec</li><li>Asynchronous APIs</li><li>Decoupled Gateway entrypoints and endpoints to enable Gravitee's advanced protocol mediation</li><li>Policy enforcement at both the request/response and message levels</li><li>Event brokers as backend data sources</li></ul></td></tr></tbody></table>

{% hint style="info" %}
**Limitations**

v4 APIs do not support Gravitee Debug mode
{% endhint %}
