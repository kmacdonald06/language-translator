---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-19"

---
<!-- Attribute definitions -->
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:curl: .ph data-hd-programlang='curl'}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}

# Using the Document Translator
{: #doc-translator-tutorial}

The Watson Document Translator allows you to translate documents from one language into another language, for a variety of file formats. This tutorial walks you through the commands to translate a document from English to French.
{:shortdesc}

## Before you begin
{: #prerequisites}

You will need either your {{site.data.keyword.languagetranslatorshort}} credentials or your {{site.data.keyword.Bluemix_notm}} account credentials to log into the Document Translator.

- Go to the [Document Translator ![External link icon](../../icons/launch-glyph.svg "External link icon")](ibm.biz/doc-translator){: new_window}

- Select either *Language Translator Credentials* or *Bluemix User Credentials* from the drop-down:

    - For *Language Translator Credentials*, depending on your service instance, you authenticate by providing either your `username` and `password`, or `apikey` and `{apikey_value}`.
    - For *Bluemix User Credentials*, provide your {{site.data.keyword.Bluemix_notm}} account user name and password.

- Click the **Login** button to log in

## Step 2: Select a document to translate

- Select the **Browse** button, and select a document from your system to translate. Supported document types are listed.

- Choose a language *From* and *To* from the drop-down menus

- Select the **Translate** button.

### Results
The Document Translator begins to translate your document.

## Step 3: Review your translated document

- Open the *Show Documents List* drop-down to see the tasks you have sent to the Document Translator.

- Once the Status shows as `done`, select the **Get** button to download and save your translated document. You can also choose to delete the document by selecting the **Del** button.
