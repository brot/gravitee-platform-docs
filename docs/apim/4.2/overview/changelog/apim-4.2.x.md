---
description: >-
  This page contains the changelog entries for APIM 4.2.x and any future patch
  APIM 4.2.x releases
---

# APIM 4.2.x
 
## Gravitee API Management 4.2.22 - November 5, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Sync process failed if subscription exists without the linked API [#10140](https://github.com/gravitee-io/issues/issues/10140)

**Management API**

* Page revisions are still present when the associated API is deleted [#10039](https://github.com/gravitee-io/issues/issues/10039)
* API webhook notifier is not working for subscriptions [#10056](https://github.com/gravitee-io/issues/issues/10056)
* Alert Templates are always created in default environment [#10126](https://github.com/gravitee-io/issues/issues/10126)

**Console**

* Code blocks and long strings of text cause overflow of documentation text in the new dev portal [#10048](https://github.com/gravitee-io/issues/issues/10048)

**Other**

* \[gravitee-policy-jwt] Complete gateway disruption occurred in retrieving JWT public keys after startup under a heavy load of API calls [#10119](https://github.com/gravitee-io/issues/issues/10119)

</details>


 
## Gravitee API Management 4.2.21 - October 24, 2024
<details>

<summary>Bug Fixes</summary>

**Management API**

* Dictionaries not deployed after migration from 3.20.x to 4.x [#10026](https://github.com/gravitee-io/issues/issues/10026)
* User with environment role is not able to create notifications [#10068](https://github.com/gravitee-io/issues/issues/10068)

**Console**

* Unable to delete Cors Allow-Origin URL [#9765](https://github.com/gravitee-io/issues/issues/9765)
* Rollback from history removes groups of users from API  [#10074](https://github.com/gravitee-io/issues/issues/10074)
* Upgrade nginx image to 1.27.2 [#10116](https://github.com/gravitee-io/issues/issues/10116)

**Portal**

* Upgrade nginx image to 1.27.2 [#10116](https://github.com/gravitee-io/issues/issues/10116)

**Helm Charts**

* Set the HaProxy.ProxyProtocol with the Helm chart [#10027](https://github.com/gravitee-io/issues/issues/10027)

</details>


 
## Gravitee API Management 4.2.20 - October 10, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Invalid error content/type when using v4 emulation [#9930](https://github.com/gravitee-io/issues/issues/9930)
* \[3.20.X and 4.4.X] DNS Resolution fails for hosts having more than 30 A records [#10051](https://github.com/gravitee-io/issues/issues/10051)
* \[Gateway Distributed Sync] Properly differentiate v2 from v4 API events [#10055](https://github.com/gravitee-io/issues/issues/10055)
* Error Key champ not present when using Response Template [#9931](https://github.com/gravitee-io/issues/issues/9931)

**Management API**

* Missing braces in webhook notifier messages when special characters are present [#9856](https://github.com/gravitee-io/issues/issues/9856)
* Debug mode not working when too many gateway started events [#9977](https://github.com/gravitee-io/issues/issues/9977)
* Issue on permissions of the ORGANIZATION_USER role [#10040](https://github.com/gravitee-io/issues/issues/10040)

**Helm Charts**

* Add serviceAccount in helm chart  [#10057](https://github.com/gravitee-io/issues/issues/10057)

**Other**

* \[gravitee-policy-groovy] Groovy script compilation blocks the Vertx event loop [#9653](https://github.com/gravitee-io/issues/issues/9653)
* \[gravitee-policy-generate-jwt] Generate JWT policy generates incorrect tokens [#9975](https://github.com/gravitee-io/issues/issues/9975)

</details>


 
## Gravitee API Management 4.2.19 - September 30, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Transfer subscription does not use new plan when V4 emulation is disabled [#10047](https://github.com/gravitee-io/issues/issues/10047)

**Management API**

*  mgmt-api ERROR i.g.r.a.s.n.i.EmailNotifierServiceImpl - No emails extracted from \[] [#9965](https://github.com/gravitee-io/issues/issues/9965)
* Dictionaries not deployed after migration from 3.20.x to 4.x [#10026](https://github.com/gravitee-io/issues/issues/10026)
* Validation for unique names is MISSING in Categories  [#10053](https://github.com/gravitee-io/issues/issues/10053)

**Console**

* Display issue with lateral collasped menu [#9792](https://github.com/gravitee-io/issues/issues/9792)
* API History shows warning for all policies [#9866](https://github.com/gravitee-io/issues/issues/9866)
* \[APIM] Read only Health check configuration [#9902](https://github.com/gravitee-io/issues/issues/9902)
* API Category endpoint does not work [#9906](https://github.com/gravitee-io/issues/issues/9906)
* No display of resource property for redis cache [#10001](https://github.com/gravitee-io/issues/issues/10001)
* Not able to see API events in Dashboard [#10018](https://github.com/gravitee-io/issues/issues/10018)
* Analytics dashboard filtered become empty when a tenant is selected [#10019](https://github.com/gravitee-io/issues/issues/10019)
* Allow API member with right to Env Group to see all group member's of an API [#10021](https://github.com/gravitee-io/issues/issues/10021)

**Helm Charts**

* APIM Helm chart doesn't configure SSL keystore secret [#9854](https://github.com/gravitee-io/issues/issues/9854)

**Other**

* \[gravitee-entrypoint-webhook] V4 Message API Webhook Timeout Behavior [#9750](https://github.com/gravitee-io/issues/issues/9750)
* \[gravitee-policy-callout-http] Callout policy does not work as expected with fire&forget mode on v4 engine for v2 API [#9937](https://github.com/gravitee-io/issues/issues/9937)
* Command creation failure in database when illegal character is used on a message header in a webhook API [#9979](https://github.com/gravitee-io/issues/issues/9979)
* \[gravitee-policy-message-filtering] Solace Message Acknowledgement [#10010](https://github.com/gravitee-io/issues/issues/10010)
* \[gravitee-policy-data-logging-masking] DLM policies will not allow the DataDog Reporter to forward logs to DataDog if a property is not found [#10044](https://github.com/gravitee-io/issues/issues/10044)

</details>


 
## Gravitee API Management 4.2.18 - September 13, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Debug mode can impact the sync process [#9976](https://github.com/gravitee-io/issues/issues/9976)

**Management API**

* Upgrade 4.2.5 -> 4.4.2 fails due to existing dashboards type column [#9893](https://github.com/gravitee-io/issues/issues/9893)
* Version is always #1 in api history [#9950](https://github.com/gravitee-io/issues/issues/9950)

**Console**

* Message-level conditions not working in v4 policy studio [#9335](https://github.com/gravitee-io/issues/issues/9335)
* Deprecated plan design are no longer accessible [#9966](https://github.com/gravitee-io/issues/issues/9966)

**Helm Charts**

* \[Helm] Gateway technical ingress miss common label [#9998](https://github.com/gravitee-io/issues/issues/9998)

**Other**

* \[gravitee-policy-assign-attributes] - Assign Attributes Policy value field needs to support multiline. [#10012](https://github.com/gravitee-io/issues/issues/10012)

</details>

<details>

<summary>Improvements</summary>

**Helm Charts**

* \[Helm] rework the definition of probes startup, liveness and readiness [#9996](https://github.com/gravitee-io/issues/issues/9996)

</details>


 
## Gravitee API Management 4.2.17 - August 30, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Decrypt api properties using debug mode [#9943](https://github.com/gravitee-io/issues/issues/9943)
* Impossible to create Date from string in groovy scripts [#9967](https://github.com/gravitee-io/issues/issues/9967)
* XPath not working as expected in gravitee expression language [#9974](https://github.com/gravitee-io/issues/issues/9974)

**Management API**

* Unresponsive/slow UI when emails are sent in APIM 3.x, 4.x [#9522](https://github.com/gravitee-io/issues/issues/9522)

**Console**

* Inappropriate rights for users [#9875](https://github.com/gravitee-io/issues/issues/9875)

</details>


 
## Gravitee API Management 4.2.16 - August 14, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Gateway issue - Memory Leak [#9924](https://github.com/gravitee-io/issues/issues/9924)

**Management API**

* Total APIs for Portal API Category endpoint always returns 0 [#9922](https://github.com/gravitee-io/issues/issues/9922)
* Re: \[APIM/Gateway] Override an email template doesn't work [#9934](https://github.com/gravitee-io/issues/issues/9934)

**Console**

* Application names overflow container under API, Plans and Subscriptions [#9872](https://github.com/gravitee-io/issues/issues/9872)

</details>


 
## Gravitee API Management 4.2.15 - August 1, 2024
<details>

<summary>Bug Fixes</summary>

**Management API**

* Missing semicolon in Subscriptions Export [#9878](https://github.com/gravitee-io/issues/issues/9878)

**Console**

* Creating a personal token with the same name does not trigger a visual warning [#9873](https://github.com/gravitee-io/issues/issues/9873)

**Other**

* APIM RPM installation overwrite portal configuration [#9914](https://github.com/gravitee-io/issues/issues/9914)

</details>



## Gravitee API Management 4.2.14 - July 19, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Gateway Unhealthy when rate limit repository is set to none [#9869](https://github.com/gravitee-io/issues/issues/9869)

**Management API**

* We do not allow a different DNS for the API of the portal and the console [#9721](https://github.com/gravitee-io/issues/issues/9721)
* JDBC Connection Pool Management Error - follow up ticket [#9851](https://github.com/gravitee-io/issues/issues/9851)

**Console**

* Non idempotent operation when creating APIs/Appplications/Users [#9688](https://github.com/gravitee-io/issues/issues/9688)

**Helm Charts**

* We do not allow a different DNS for the API of the portal and the console [#9721](https://github.com/gravitee-io/issues/issues/9721)

</details>

<details>

<summary>Improvements</summary>

**Console**

* Paginated audit events loading to avoid memory issues [#9768](https://github.com/gravitee-io/issues/issues/9768)

</details>



## Gravitee API Management 4.2.13 - July 5, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* 500 Internal server error when logs enabled [#9719](https://github.com/gravitee-io/issues/issues/9719)
* Enabled Logging with condition does not work properly [#9756](https://github.com/gravitee-io/issues/issues/9756)
* Transfer subscription does not use new plan when V4 emulation is disabled [#9772](https://github.com/gravitee-io/issues/issues/9772)
* Upgrade to gio 4.4.0 corrupts API Keys [#9834](https://github.com/gravitee-io/issues/issues/9834)
* Add Base64 class in Expression Language whitelist [#9850](https://github.com/gravitee-io/issues/issues/9850)

**Management API**

* Override an email template with multiple REST API [#9445](https://github.com/gravitee-io/issues/issues/9445)
* Cannot Create Local User (no email to set password) [#9680](https://github.com/gravitee-io/issues/issues/9680)
* Error in Gravitee OpenAPI spec [#9711](https://github.com/gravitee-io/issues/issues/9711)
* Endpoint's target url can be saved with a space or tab [#9791](https://github.com/gravitee-io/issues/issues/9791)
* Unable delete existing PAT tokens [#9801](https://github.com/gravitee-io/issues/issues/9801)
* Error on platform analytics and logs screens when too many applications and/or APIs [#9823](https://github.com/gravitee-io/issues/issues/9823)

**Console**

* Correct API properties Expression Language for v4 APIs [#9694](https://github.com/gravitee-io/issues/issues/9694)
* When updating a service account email through API, no mail validation is performed [#9709](https://github.com/gravitee-io/issues/issues/9709)
* Enabled Logging with condition does not work properly [#9756](https://github.com/gravitee-io/issues/issues/9756)
* Cannot subscribe to API plans via the web [#9758](https://github.com/gravitee-io/issues/issues/9758)
* Cannot Save Dashboard Updates in UI [#9771](https://github.com/gravitee-io/issues/issues/9771)
* Unable to Add Members to Group During Group Creation [#9783](https://github.com/gravitee-io/issues/issues/9783)
* Endpoint's target url can be saved with a space or tab [#9791](https://github.com/gravitee-io/issues/issues/9791)
* In some cases it is difficult to view the configuration in the history menu. [#9800](https://github.com/gravitee-io/issues/issues/9800)
* Policy - losing focus when opening documentation [#9802](https://github.com/gravitee-io/issues/issues/9802)
* Dashboard widget not working  [#9820](https://github.com/gravitee-io/issues/issues/9820)
* Client Id not saved between Security section and subscriptions during application creation [#9828](https://github.com/gravitee-io/issues/issues/9828)
* JSON to XML policy does not work with default configuration for V4 proxy APIs [#9833](https://github.com/gravitee-io/issues/issues/9833)

**Other**

* \[gravitee-policy-ipfiltering] CIDR block /32 (single IP) not working in the IP Filtering Policy [#9602](https://github.com/gravitee-io/issues/issues/9602)
* \[gravitee-resource-oauth2-provider-keycloak] Update of 'gravitee-resource-oauth2-provider-keycloak' Plugin [#9628](https://github.com/gravitee-io/issues/issues/9628)
* \[gravitee-policy-jwt] 500 error on jwt plan with GATEWAY_KEYS when using  "Emulate v4 engine" [#9693](https://github.com/gravitee-io/issues/issues/9693)
* \[MongoDb] Upgraders should use prefix for collection names [#9807](https://github.com/gravitee-io/issues/issues/9807)

</details>

<details>

<summary>Improvements</summary>

**Management API**

* PrimaryOwner not given in list of APIs [#9678](https://github.com/gravitee-io/issues/issues/9678)
* The name of API/Application/Plan is not given in list of API's subscriptions [#9679](https://github.com/gravitee-io/issues/issues/9679)
* Improve API synchronization state computation [#9852](https://github.com/gravitee-io/issues/issues/9852)

**Other**

* \[gravitee-policy-aws-lambda] Allow to dynamically configure AWS policy credentials [#9444](https://github.com/gravitee-io/issues/issues/9444)

</details>


 
## Gravitee API Management 4.2.12 - June 19, 2024
<details>

<summary>Bug Fixes</summary>

**Console**

* Allow users to configure keepalive timeout in the console for V2 APIs [#9651](https://github.com/gravitee-io/issues/issues/9651)
* Filter on 208 status code not available [#9784](https://github.com/gravitee-io/issues/issues/9784)

**Portal**

* Documentation too slow [#9788](https://github.com/gravitee-io/issues/issues/9788)

**Helm Charts**

* Improve the ingress configuration to redirect HTTPS [#9710](https://github.com/gravitee-io/issues/issues/9710)

**Other**

* \[gravitee-endpoint-kafka] Kafka sender options customization not taken into account [#9656](https://github.com/gravitee-io/issues/issues/9656)
* \[gravitee-policy-json-validation] v4 Policy Studio UI doesn't support multi-line values [#9799](https://github.com/gravitee-io/issues/issues/9799)

</details>

<details>

<summary>Improvements</summary>

**Other**

* \[gravitee-entrypoint-webhook] Support 500 responses for DLQ : add client_id and errors stack in the message sent to DLQ [#9740](https://github.com/gravitee-io/issues/issues/9740)
* \[gravitee-endpoint-kafka] Add a option on kafka endpoint to remove Confluent Wire format header [#9795](https://github.com/gravitee-io/issues/issues/9795)

</details>


 
## Gravitee API Management 4.2.11 - June 7, 2024
<details>

<summary>Bug Fixes</summary>

**Gateway**

* Error in the gateway when upgrading connection from http1.1 to http2 [#9757](https://github.com/gravitee-io/issues/issues/9757)
* Socket.io disconnect/reconnect latency [#9766](https://github.com/gravitee-io/issues/issues/9766)

**Management API**

* Pushing an API with API Designer fails [#9761](https://github.com/gravitee-io/issues/issues/9761)
* Gitlab fetcher CronSequenceGenerator deprecation [#9733](https://github.com/gravitee-io/issues/issues/9733)
* Inheritance of a V2 API endpoint configuration is not set when importing an OpenAPI spec [#9775](https://github.com/gravitee-io/issues/issues/9775)

</details>

<details>

<summary>Improvements</summary>

**Other**

* \[gravitee-policy-groovy] Have access to the binary value of a message content [#9767](https://github.com/gravitee-io/issues/issues/9767)

</details>



## Gravitee API Management 4.2.10 - May 24, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Gateway monitoring page has no data [#9677](https://github.com/gravitee-io/issues/issues/9677)
* The Assign Content policy seems to be broken when using with Retry policy [#9737](https://github.com/gravitee-io/issues/issues/9737)

**Management API**

* Logs mismatched between environments [#9599](https://github.com/gravitee-io/issues/issues/9599)
* Incompatible QoS between entrypoints and endpoints [#9608](https://github.com/gravitee-io/issues/issues/9608)
* Unable to Search Users by Company Name and Country in Users API [#9702](https://github.com/gravitee-io/issues/issues/9702)

**Console**

* Incompatible QoS between entrypoints and endpoints [#9608](https://github.com/gravitee-io/issues/issues/9608)

</details>

## Gravitee API Management 4.2.9 - May 10, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Portal global API search is returning a 500 "maxClauseCount is set to 1024" [#9730](https://github.com/gravitee-io/issues/issues/9730)

**Other**

* \[gravitee-policy-ratelimit] Thread Blocked on AsyncRateLimitRepository [#9717](https://github.com/gravitee-io/issues/issues/9717)

</details>

<details>

<summary>Improvements</summary>

**Helm Charts**

* Enhance the experience of deploying Gateway with Redis SSL using Helm Chart [#9726](https://github.com/gravitee-io/issues/issues/9726)

**Other**

* \[gravitee-entrypoint-webhook] Support 500 responses for DLQ [#9722](https://github.com/gravitee-io/issues/issues/9722)

</details>

## Gravitee API Management 4.2.8 - April 26, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Error in OpenApi spec [#9665](https://github.com/gravitee-io/issues/issues/9665)
* Unable to update the service account email through API [#9682](https://github.com/gravitee-io/issues/issues/9682)

**Console**

* Cannot create Backend-to-Backend Application from UI Console [#9636](https://github.com/gravitee-io/issues/issues/9636)

**Portal**

* Problem of swagger interpretation with redocly [#9673](https://github.com/gravitee-io/issues/issues/9673)

**Other**

* \[gravitee-policy-cache] Cache Policy Always Caches the First Response [#9534](https://github.com/gravitee-io/issues/issues/9534)
* \[gravitee-policy-cache] Cache Policy Does Not Correctly Return Images [#9585](https://github.com/gravitee-io/issues/issues/9585)
* \[gravitee-policy-cache] Time to live setting not working [#9692](https://github.com/gravitee-io/issues/issues/9692)

</details>

## Gravitee API Management 4.2.7 - April 11, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Secret Provider Setup [#9586](https://github.com/gravitee-io/issues/issues/9586)
* 431 (Request Header Fields Too Large) when submitting large JWT to gRPC API [#9652](https://github.com/gravitee-io/issues/issues/9652)

**Management API**

* Installation collection can have more than one entry [#9641](https://github.com/gravitee-io/issues/issues/9641)

**Console**

* Performance issue with the analytics dashboard [#9658](https://github.com/gravitee-io/issues/issues/9658)

**Portal**

* Cannot Scroll in Markdown Documents [#9634](https://github.com/gravitee-io/issues/issues/9634)
* Showing Gravitee.io in Dev Portal browser tab only while the page loads [#9663](https://github.com/gravitee-io/issues/issues/9663)

**Other**

* Fail to enable the service on SUSE [#9501](https://github.com/gravitee-io/issues/issues/9501)
* Upgrade 3.20.22 to 4.2.2 - File report missing node metrics [#9589](https://github.com/gravitee-io/issues/issues/9589)
* \[gravitee-policy-cache] Concurrency issue with v4 emulation engine [#9635](https://github.com/gravitee-io/issues/issues/9635)
* \[gravitee-resource-auth-provider-http] Timeout when body parsing is failing [#9640](https://github.com/gravitee-io/issues/issues/9640)
* API List showing type as "Undefined" for v4 APIs in Postgres env [#9643](https://github.com/gravitee-io/issues/issues/9643)
* Authentication Provider table column too small [#9664](https://github.com/gravitee-io/issues/issues/9664)

</details>

## Gravitee API Management 4.2.6 - March 29, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Update import remove all members when a group is defined as a PO [#9596](https://github.com/gravitee-io/issues/issues/9596)
* Gravitee 4.2 OpenAPI issues [#9632](https://github.com/gravitee-io/issues/issues/9632)

**Other**

* \[gravitee-policy-ipfiltering] DNS Lookup fails with some DNS servers [#9592](https://github.com/gravitee-io/issues/issues/9592)
* \[gravitee-resource-auth-provider-http] Timeout when authentication condition is failing [#9611](https://github.com/gravitee-io/issues/issues/9611)
* Liquibase changelog 4.0.20-dashboards adding NOT NULL column without default value [#9626](https://github.com/gravitee-io/issues/issues/9626)
* APIM DashboardTypeUpgrader raises an error when used with DocumentDB [#9631](https://github.com/gravitee-io/issues/issues/9631)

</details>

<details>

<summary>Improvements</summary>

**Management API**

* Allow to configure KeepAliveTimeout for HTTP endpoint [#9541](https://github.com/gravitee-io/issues/issues/9541)

</details>

## Gravitee API Management 4.2.5 - March 22, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Improve HealthCheck service for v2 APIs [#9543](https://github.com/gravitee-io/issues/issues/9543)

**Management API**

* Deleted users still appear in query [#9477](https://github.com/gravitee-io/issues/issues/9477)
* Condition field in JDBC dbs is too short [#9595](https://github.com/gravitee-io/issues/issues/9595)

**Console**

* Console Menu doesn't work with latency [#9591](https://github.com/gravitee-io/issues/issues/9591)
* \[shared API key] API key mode not displayed on application screen [#9612](https://github.com/gravitee-io/issues/issues/9612)

**Other**

* API v4 proxy - problem with client SSL certificate [#9562](https://github.com/gravitee-io/issues/issues/9562)
* Flow Id is lost when updating API with UI, causing it to regenerate new flow [#9597](https://github.com/gravitee-io/issues/issues/9597)

</details>

<details>

<summary>Improvements</summary>

**Portal**

* Do not allow user to change their email through the portal [#9617](https://github.com/gravitee-io/issues/issues/9617)

</details>

## Gravitee API Management 4.2.4 - March 1, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Override HTTP Method [#9526](https://github.com/gravitee-io/issues/issues/9526)

**Management API**

* Shared API Key Does Not Always Bind to Subscriptions When Concurrent Requests Are Made [#9502](https://github.com/gravitee-io/issues/issues/9502)
* NullPointer Exception when importing an API with group as PO and members [#9507](https://github.com/gravitee-io/issues/issues/9507)
* APIM: Creating application with "@" in name automatically converts it to "@" [#9514](https://github.com/gravitee-io/issues/issues/9514)
* API description required with POST /apis/ on mAPI v2 [#9527](https://github.com/gravitee-io/issues/issues/9527)
* Not possible to create endpoint and endpoint-group with same name [#9533](https://github.com/gravitee-io/issues/issues/9533)
* Importing an API with a group as PO but no PO user in this group should not be possible [#9587](https://github.com/gravitee-io/issues/issues/9587)

**Console**

* No longer possible to compare "published" and "to deploy" status [#9491](https://github.com/gravitee-io/issues/issues/9491)
* Re: Error when clicking on top failed API in platform dashbaord [#9498](https://github.com/gravitee-io/issues/issues/9498)
* Remove last user in group shows error [#9517](https://github.com/gravitee-io/issues/issues/9517)
* \[endpoints] updating name or deleting group used as DLQ prevent updating API [#9535](https://github.com/gravitee-io/issues/issues/9535)
* \[endpoints] creating an endpoint group should display endpoint configuration [#9582](https://github.com/gravitee-io/issues/issues/9582)

**Portal**

* Documentation menu hidden [#9590](https://github.com/gravitee-io/issues/issues/9590)

</details>

## Gravitee API Management 4.2.3 - February 16, 2024

<details>

<summary>Bug fixes</summary>

**Management API**

* Excluded groups on plan are not displayed after being imported or promoted to a new environment [#9116](https://github.com/gravitee-io/issues/issues/9116)
* Private APIs on the Portal are wrongly displayed [#9513](https://github.com/gravitee-io/issues/issues/9513)
* Modifying API definition causes loss of endpoint configuration [#9520](https://github.com/gravitee-io/issues/issues/9520)

**Console**

* When validating a JWT subscription, I'm asked to customize an APIkey [#9489](https://github.com/gravitee-io/issues/issues/9489)

**Portal**

* Documentation gets encoded after deployment [#9490](https://github.com/gravitee-io/issues/issues/9490)
* Customization problems in the Developer Portal [#9495](https://github.com/gravitee-io/issues/issues/9495)
* Subscriptions Not Visible in Portal If There Is a Push Plan [#9511](https://github.com/gravitee-io/issues/issues/9511)

**Other**

* "Propagate client Accept-Encoding header" option missing in V4 [#9475](https://github.com/gravitee-io/issues/issues/9475)
* \[policy-request-validation] Un-required OpenAPI fields added as required in Validate Request policy [#9509](https://github.com/gravitee-io/issues/issues/9509)

</details>

## Gravitee API Management 4.2.2 - February 2, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Unable to populate attributes using the Assign Attributes policy due to enabled v4 Engine [#9420](https://github.com/gravitee-io/issues/issues/9420)
* Conditional logging [#9486](https://github.com/gravitee-io/issues/issues/9486)
* Timeout when connecting to WebSocket API using header Connection:Upgrade,Keep-Alive [#9487](https://github.com/gravitee-io/issues/issues/9487)

**Management API**

* Cannot Create API with Webhook Only Entrypoint [#9462](https://github.com/gravitee-io/issues/issues/9462)
* Use legacy configuration when upgrading to 4.2.x [#9483](https://github.com/gravitee-io/issues/issues/9483)

</details>

<details>

<summary>Improvements</summary>

**Gateway**

* Add API ID in healthcheck logs [#9493](https://github.com/gravitee-io/issues/issues/9493)

</details>

## Gravitee API Management 4.2.1 - January 19, 2024

<details>

<summary>Bug fixes</summary>

**Gateway**

* Sometimes path-mapping is not working [#9450](https://github.com/gravitee-io/issues/issues/9450)
* Management API does not encode a value in the URL used in a pipe [#9461](https://github.com/gravitee-io/issues/issues/9461)
* gRPC backend received unexpected headers [#9463](https://github.com/gravitee-io/issues/issues/9463)

**Management API**

* Unable to switch to gRPC endpoint type from the Console UI [#9456](https://github.com/gravitee-io/issues/issues/9456)
* Updating an API reset the gRPC type of the endpoint [#9464](https://github.com/gravitee-io/issues/issues/9464)

**Console**

* Unable to edit Dictionaries anymore [#9451](https://github.com/gravitee-io/issues/issues/9451)
* Navigation in a multi-environments console is messed up [#9467](https://github.com/gravitee-io/issues/issues/9467)

**Portal**

* Docs not loaded instantly [#9452](https://github.com/gravitee-io/issues/issues/9452)

**Helm Charts**

* Backward incompatibility during Helm upgrade with old `values.yml` [#9446](https://github.com/gravitee-io/issues/issues/9446)

</details>

<details>

<summary>Improvements</summary>

**Gateway**

* Access request host property in Expression Language [#9453](https://github.com/gravitee-io/issues/issues/9453)

</details>
