---
description: This page explains how to further customize your Docker installation
---

# Further Customization

## Install additional plugins

APIM Docker images contain the default plugins. To add an additional plugin, copy the plugin archive (a `.zip` file) into the `plugins-ext` folder.&#x20;

If you used the file structure described in [the custom install section](custom-install-with-docker-compose.md):&#x20;

* The `plugin-ext` folder is `/gravitee/apim-gateway/plugins` for the API Gateway
* The `plugin-ext` folder is `/gravitee/apim-management-api/plugins` for the Management API

You can download additional plugins from [the plugins download page](https://download.gravitee.io/#graviteeio-apim/plugins/). For more information on plugin deployment, see [Deployment](../../../overview/plugins.md#deployment).

{% hint style="warning" %}
Some plugins need to be installed on both the API Gateway and the Management API. Installation details are provided in a specific plugin’s documentation.
{% endhint %}

## Use Redis as the datastore for rate-limiting counters

{% tabs %}
{% tab title="Use Redis with docker-compose" %}
To use Redis with `docker compose`, edit the `$services.gateway.environment` section of the Docker compose file to include the following lines, and remove the line containing `gravitee_ratelimit_mongodb_uri`.

{% code title="docker-compose.yaml" %}
```yaml
      - gravitee_ratelimit_type=redis
      - gravitee_ratelimit_redis_host=gravitee-redis
      - gravitee_ratelimit_redis_port=6379
```
{% endcode %}

{% hint style="info" %}
Your Redis host and port may be different.
{% endhint %}
{% endtab %}

{% tab title="Use Redis with Docker images" %}
To use Redis with Docker images, add the following environment variables to the command used to start the API Gateway and remove the `gravitee_ratelimit_mongodb_uri` `env`.

```sh
  --env gravitee_ratelimit_type=redis \
  --env gravitee_ratelimit_redis_host=gravitee-redis \
  --env gravitee_ratelimit_redis_port=6379 \
```

{% hint style="info" %}
Your Redis host and port may be different.
{% endhint %}
{% endtab %}
{% endtabs %}

## Use JDBC connection as the datastore for management

To use JDBC as the datastore for management:

* The correct JDBC driver must be installed on the API Gateway and the Management API
* &#x20;The containers must be started using additional environment variables

### 1. Download the driver

1. Download the correct driver for your database from [Supported databases.](../../configuration/repositories/#supported-databases)
2. Place the driver in the `plugins-ext` folder. If you used the file structure described in the [custom install section](custom-install-with-docker-compose.md):
   * The `plugin-ext` folder is `/gravitee/apim-gateway/plugins` for the API Gateway&#x20;
   * The `plugin-ext` folder is `/gravitee/apim-management-api/plugins` for the Management API

{% hint style="info" %}
For more information on the JDBC plugin and drivers, see [JDBC](../../configuration/repositories/#jdbc).
{% endhint %}

### 2. Use JDBC

{% tabs %}
{% tab title="Use JDBC with docker-compose" %}
To use JDBC with `docker compose`, edit the `$services.gateway.environment` section and the `$services.management_api.environment` section of the Docker compose file to include the following lines, and remove the lines containing `gravitee_management_mongodb_uri`.

{% code title="docker-compose.yaml" %}
```yaml
       - gravitee_management_type=jdbc
       - gravitee_management_jdbc_url=jdbc:mysql://gravitee-mysql:3306/gravitee?useSSL=false&user=mysql_users&password=mysql_password
```
{% endcode %}

{% hint style="danger" %}
Make sure your `gravitee_management_jdbc_url` is appropriate for your environment. In particular, be cautious about using `useSSL=false` in production.

Your host, port, username, and password may be different.
{% endhint %}
{% endtab %}

{% tab title="Use JDBC with Docker images" %}
To use JDBC with Docker images, add the following environment variables to the commands used to start the Gateway and the management API and remove the `gravitee_management_mongodb_uri` `env`.

```sh
  --env gravitee_management_type=jdbc \
  --env gravitee_management_jdbc_url=jdbc:mysql://gravitee-mysql:3306/gravitee?useSSL=false&user=mysql_users&password=mysql_password \
```

{% hint style="danger" %}
Make sure your `gravitee_management_jdbc_url` is appropriate for your environment. In particular, be cautious about using `useSSL=false` in production.

Your host, port, username, and password may be different.
{% endhint %}
{% endtab %}
{% endtabs %}
