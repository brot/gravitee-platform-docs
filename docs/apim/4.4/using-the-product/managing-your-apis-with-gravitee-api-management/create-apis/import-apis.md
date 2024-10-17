---
description: Learn how to import APIs onto your Gravitee Gateway
---

# Import APIs

## Introduction

Gravitee supports importing APIs as:

* Files (YML, YAML, JSON, WSDL, XML)
* Swagger/OpenAPI spec (URL)
* API definition (URL)
* WSDL (URL)

## Import your API

To import your API:

1. Log in to your API Console
2. Select **APIs** from the left nav
3.  Select **+ Add API**&#x20;

    <figure><img src="../../../.gitbook/assets/import_add api.png" alt=""><figcaption></figcaption></figure>
4.  In the **Import an API definition** tile, click **Import**&#x20;

    <figure><img src="../../../.gitbook/assets/import_import.png" alt=""><figcaption></figcaption></figure>
5. Choose and configure an import option:
   * **Upload a file:** Import a YML, YAML, JSON, WSDL, or XML file
   * **Swagger / OpenAPI:**&#x20;
     * Provide a **Swagger descriptor URL**
     * **Create documentation:** Overwrites existing documentation or create it if it does not exist
     * **Create the path mapping for analytics:** Overwrites all of the path-mappings
     * **Create policies on paths:** Overwrites all of the policies. Policies that you can create upon import include **JSON Validation**, **Mock**, **Request Validation**, **REST to SOAP**, and **XML Validation**.
   * **API definition:** Provide a URL that links to your API definition
   * **WSDL:**&#x20;
     * Provide a **WSDL descriptor URL**
     * **Create documentation:** Overwrites existing documentation or create it if it does not exist
     * **Create the path mapping for analytics:** Overwrites all of the path-mappings
     * **Create policies on paths:** Overwrites all of the policies. Policies that you can create upon import include **JSON Validation**, **Mock**, **Request Validation**, **REST to SOAP**, and **XML Validation**.
6. Click **Import**

{% hint style="success" %}
Once you've imported your API, it will be created as a private API and you will be brought to the API menu and details page.
{% endhint %}
