---
description: >-
  This page contains the changelog entries for AM 4.5.x and any future minor or
  patch AM 4.5.x releases
---

# AM 4.5.x

## Gravitee Access Management 4.5.1 - October 25, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* AM Refresh token active set to false [#10065](https://github.com/gravitee-io/issues/issues/10065)
* The "path" parameter for SCIM patch requests does not function as expected [#10073](https://github.com/gravitee-io/issues/issues/10073)
* why does "Skip MFA enrollment" also skips MFA validation on login [#10086](https://github.com/gravitee-io/issues/issues/10086)
* Password rules not displayed in the registration confirmation webpage [#10089](https://github.com/gravitee-io/issues/issues/10089)

**Other**

* /sendChallenge returns status code 0 [#10097](https://github.com/gravitee-io/issues/issues/10097)
* Original access token out of an OpenID federation is not able to be used for the mapping into the ID token going back to the application [#10104](https://github.com/gravitee-io/issues/issues/10104)
* Gravitee AM SAML not working [#10106](https://github.com/gravitee-io/issues/issues/10106)
* Error message on IP filtering policy always returns remote address [#10108](https://github.com/gravitee-io/issues/issues/10108)

</details>

## Gravitee Access Management 4.5 - October 10, 2024

{% hint style="warning" %}
AM 4.5.0 introduce some deprecations which may have an impact on your systems. Please refer to the "Deprecations" section here after for more details.
{% endhint %}

<details>

<summary>What's new</summary>

### Repositories

A new repository scope named `gateway` has been introduced in AM 4.5.0.

### Token generation

For all domains created from AM 4.5.0 the `sub` claim will not represent the user internalID as it was the case previously.

### AWS Certificate plugin

An AWS certificate plugin is now available as EE feature. Thanks to this plugin you can load certificate provided by AWS Secret Manager.

### Reporters

Reporters have been improved in this new version of Access Management:

* additional reporters can be configured as "global" in order to collect audits events coming from all the domains linked to this organization.
* Events for domain creation and domain deletion are now published in the organization reporters.
* The kafka reporter has been improved to manage Schema Registry

### OpenID

We improved the OAuth2 / OpenID specification more strictly regarding the usage of the response\_mode paramet

### Group mapper

Identity Providers now provide a [Group Mapper](../../guides/identity-providers/user-and-role-mapping.md) section.

### Cache Layer

A cache layer has been introduce to limit the Database access during the user authentication flow.

</details>

<details>

<summary>Breaking Changes</summary>

### Redirect Uris

On application creation or update `redirect_uris` is now required for application with type WEB, NATIVE or SPA.

### Token generation

For all domains created from AM 4.5.0 the `sub` claim will not represent the user internalID as it was the case previously. The `sub` value is now an opaque value computed based on the user externalId and the identity provider identifier. Even if this value is opaque, it will remain the same for a given user across multiple token generations as per the requirement of the OIDC specification.

<mark style="color:red;">**NOTE:**</mark> For all domains created in previous version, the sub claim remains the user internalId.

### Repositories

A new repository scope named `gateway` has been introduced in AM 4.5.0.

The new gateway scope will manage entities which was previously managed by the `oauth2` scope and the `management` scope:

* ScopeApproval
* AuthenticationFlowContext
* LoginAttempts
* RateLimit
* VerifyAttempt

If you managed to define two differente databases for the `management` and the `oauth2` scopes, please configure the `gateway` scope to target the same database as the `oauth2` scope as ScopeApproval are now managed by the `gateway` scope. If you want to dedicate a database for the gateway scope you will have to migrate the scope\_approvals collection to the new database.

Previously, all the settings related to the repositories where define at the root level of the `gravitee.yaml` with the scope name as section name

{% code lineNumbers="true" %}
```yaml
management:
  type: mongodb
  mongodb: 
    uri: ...
    
oauth2:
  type: mongodb
  mongodb: 
    uri: ...
```
{% endcode %}

Starting from 4.5.0, a `repositories` section has been introduce to easily identify the settings related to the repository layer.

<pre class="language-yaml" data-line-numbers><code class="lang-yaml"><strong>repositories:
</strong><strong>  management:
</strong><strong>    type: mongodb
</strong>    mongodb: 
      uri: ...
    
  oauth2:
    type: mongodb
    mongodb: 
      uri: ...
  
  gateway:
    type: mongodb
    mongodb: 
      uri: ...
</code></pre>

If you were using environment variable to provide database settings remember to:

* adapt the variable name to include the "repositories" keyword, for example:\
  `GRAVITEE_MANAGEMENT_TYPE=... => GRAVITEE_REPOSITORIES_MANAGEMENT_TYPE=...`
* add the settings for the gateway scope\
  `GRAVITEE_GATEWAY_TYPE=... => GRAVITEE_REPOSITORIES_GATEWAY_TYPE=...`

</details>

<details>

<summary>Deprecations</summary>

### Audits

For kafka and File reporters, the `status` attibute has been deprecated for removal. The recommanded way to get access to the status is now the `outcome` structure which contains the `status` and a `message` fields. If you are using one of these reporter, please update your consumer to rely on the outcome structure

</details>
