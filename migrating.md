---

copyright:
  years: 2015, 2018
lastupdated: "2018-05-31"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# Migrating to {{site.data.keyword.languagetranslatorshort}} API v3 with Neural Machine Translation
{: #migrating-to-v3}

{{site.data.keyword.languagetranslatorshort}} API v2 is now retired in favor of API v3. Service enhancements will no longer be made to the v2 API. To take advantage of new features and updates, please migrate your application to {{site.data.keyword.languagetranslatorshort}} v3.
{: shortdesc}

## What's new in v3
{: #whats-new}

-  {{site.data.keyword.languagetranslatorshort}} API v3 comes with **Neural Machine Translation** (NMT) models that offer significantly improved translation results. All neural machine translation models are now available for customization.
-  Ability to use custom models as base models for further customization (decorate a custom model with a forced glossary).
-  API v3 is a simplified, all-JSON subset of the retired API v2.
-  Introduces date versioning of the API, to give developers the freedom to adapt any future API changes at their own pace

## Breaking changes
{: #breaking-changes}

- Mandatory version date for all API endpoints: API v3 requests require a version date query parameter of the form `version=2018-05-01` (date format `YYYY-DD-MM`). The latest API version is `version=2018-05-01`.
- All-JSON API:
  - The **Translate** and **Identify** methods do not offer the option to return plain text responses in v3.
  - `GET /translate` and `GET /identify` methods are not supported in v3. Use the `POST /translate` and `POST /identify` methods instead. 
- Monolingual corpus customization is not supported in v3.
- Creating custom models with both a parallel corpus and forced glossary now needs to be done in two API calls. First, customize the model with a parallel corpus. After the custom model has finished training, customize it again with the forced glossary. This change allows to quickly decorate an existing custom model with an updated glossary instead of requiring to retrain a custom model from scratch.
- Specialized patent and conversation domain models are not available in API v3. Please use the new IBM-provided, general domain neural machine translation base models. The translation quality with these new models in the patent or conversation domain is generally improved compared to the older specialized models.
- Error object keys have been renamed so that they are consistent with other Watson APIs. `error_code` has been renamed to `code`, and `error_message` has been renamed to `error`.


## Migrating your application
{: #migrating-your-application}

Support for {{site.data.keyword.languagetranslatorshort}} v3 is now available in the [Watson SDKs](https://console.bluemix.net/docs/services/watson/getting-started-sdks.html)
{: tip}

Before you migrate your application to {{site.data.keyword.languagetranslatorshort}} v3, make sure that your API calls reflect the v3 API syntax. See the [API reference](https://www.ibm.com/watson/developercloud/language-translator/api/v3) for details and examples.

If you aren't using custom models, you can begin using the v3 API with your current service instance credentials. If you use custom models and want to migrate them to v3, follow the [Migrating custom models](#migrating-custom-models) instructions to create a new service instance and recreate your models.


## Migrating custom models
{: #migrating-custom-models}

Custom models that you have trained with {{site.data.keyword.languagetranslatorshort}} v2 are not compatible with the new neural machine translation technology in {{site.data.keyword.languagetranslatorshort}} v3. To make your existing custom models available with {{site.data.keyword.languagetranslatorshort}} v3, please [retrain](customizing.html) the models that you require with the v3 API. The v3 API supports forced glossary and parallel corpus customization.

In v3, you will not be able to customize a model with a parallel corpus and forced glossary in a single API call. To customize a model with both a parallel corpus and a forced glossary, you need to do it in two steps. First, customize a base model with a parallel corpus. After the model is available, use the model ID of the available custom model as the base model for forced glossary customization.
{: tip}



















