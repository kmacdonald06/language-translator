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

# Migrating to {{site.data.keyword.languagetranslatorshort}} v3
{: #migrating-to-v3}

{{site.data.keyword.languagetranslatorshort}} v2 is now deprecated and will be retired on June 1, 2019. Service enhancements will no longer be made to the v2 API. To take advantage of new features and updates, migrate your application to {{site.data.keyword.languagetranslatorshort}} v3.
{: shortdesc}

## What's new in v3
{: #whats-new}

New Neural Machine Translation models offer improved translation results, and are now available for customization.

## Breaking changes
{: #breaking-changes}

- v3 API requests require a version date query parameter of the form `version=2018-05-01`.
- The **Translate** and **Identify** methods do not offer the option to return plain text responses in v3.
- `GET /translate` and `GET /identify` methods are not supported in v3. Use the `POST /translate` and `POST /identify` methods instead. 
- Custom models trained with the v2 API are not compatible with v3. To use custom models in v3, you will need to train new models.
- Creating custom models with both a parallel corpus and forced glossary now needs to be done in two API calls. First, customize the model with a parallel corpus. After the custom model has finished training, customize it again with the forced glossary.
- Monolingual corpus customization is not supported in v3.
- Each translation model that is currently available in v3 is designed for a general domain. News, patent, and conversational domain models are not available in v3. 
- Error object keys have been renamed so that they are consistent with other Watson APIs. `error_code` has been renamed to `code`, and `error_message` has been renamed to `error`.


## Migrating your application
{: #migrating-your-application}

Support for {{site.data.keyword.languagetranslatorshort}} v3 is not yet available in the [Watson SDKs](https://console.bluemix.net/docs/services/watson/getting-started-sdks.html), but it's coming very soon. If you're using one of the Watson SDKs in your application, you can stay tuned to releases by following the change log files in the SDK GitHub repositories.
{: tip}

Before you migrate your application to {{site.data.keyword.languagetranslatorshort}} v3, make sure that your API calls reflect the v3 API syntax. See the [API reference](https://www.ibm.com/watson/developercloud/language-translator/api/v3) for details and examples.

If you aren't using custom models, you can begin using the v3 API with your current service instance credentials. If you use custom models and want to migrate them to v3, follow the [Migrating custom models](#migrating-custom-models) instructions to create a new service instance and recreate your models.


## Migrating custom models
{: #migrating-custom-models}

Custom models that you trained with {{site.data.keyword.languagetranslatorshort}} v2 are not compatible with {{site.data.keyword.languagetranslatorshort}} v3. To use custom models with {{site.data.keyword.languagetranslatorshort}} v3, you will need to [train new models](customizing.html) with the v3 API. The v3 API supports forced glossary and parallel corpus customization only.

1. Create a new {{site.data.keyword.languagetranslatorshort}} service instance
  - Go to the [{{site.data.keyword.languagetranslatorshort}} service page](https://console.bluemix.net/catalog/services/lanuguage-translator) in the {{site.data.keyword.cloud_notm}} Catalog, and log in to {{site.data.keyword.cloud_notm}}.
  - From the Region selector, choose the Resource Controller version of the region that you used in your previous {{site.data.keyword.languagetranslatorshort}} instance. For example, if you created your instance in US South, select **US South (RC)**.
  - Select the **Advanced** pricing plan.
  - Click **Create**.
2. Use your new service credentials to recreate your custom model with the same training data that you used to create your model in {{site.data.keyword.languagetranslatorshort}} v2. For more information, view the [Customizing your model](customizing.html) page.

In v3, you will not be able to customize a model with a parallel corpus and forced glossary in a single API call. To customize a model with both a parallel corpus and a forced glossary, you need to do it in two steps. First, customize a base model with a parallel corpus. After the model is available, use the model ID of the available custom model as the base model for forced glossary customization.
{: tip}



















