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

The IBM Watson Document Translator allows you to translate documents from one language to another while preserving file formatting. Translate over 12 file formats including MS Office, Open Office, PDF file types. This tutorial walks you through the commands to translate a document from English to French.
{:shortdesc}

## Before you begin
{: #prerequisites}

You will need either your {{site.data.keyword.languagetranslatorshort}} credentials or your {{site.data.keyword.Bluemix_notm}} account credentials to log into the Document Translator.

- Go to the [Document Translator ![External link icon](../../icons/launch-glyph.svg "External link icon")](ibm.biz/doc-translator){: new_window}

- Select either *Language Translator Credentials* or *Bluemix User Credentials* from the drop-down:

    - For *Language Translator Credentials*, depending on your service instance, you authenticate by providing either your `username` and `password`, or `apikey` and `{apikey_value}`.
    - For *Bluemix User Credentials*, provide your {{site.data.keyword.Bluemix_notm}} account user name and password.

- Click **Login** to log in

## Step 1: Select a document to translate

- Select **Browse**, and select a document from your system to translate. The maximum file size in this preview release is limited to 100MB.

- Choose a language *From* and *To* from the drop-down menus. Additional language support will be added in future updates.

- Click **Translate**.

### Results
The Document Translator begins to translate your document.

## Step 2: Review your translated document

- Open the *Show Documents List* drop-down to see the tasks you have sent to the Document Translator.

- Once the Status shows as `done`, select **Get** to download and save your translated document. You can also choose to delete the document by selecting **Del**.

- If you have uploaded a larger document, you will be able to track status in the dropdown: 

Initial | Extracted | Segmented | Translated | Inserted | Done

## Supported File Types

**Note:** In this technology preview the following types are supported:

**Microsoft:**
Word (.doc, .docx)
PowerPoint (.ppt, .pptx)
Excel (.xls, .xlsx)
Rich Text Format (.rtf)

**Open Office:**
Writer (.odt)
Impress (.odp)
Calc (.ods)

**Additional**
PDF (.pdf) - translation result returned as .docx and .pdf (or .txt if conversion fails ...)
HTML (.htm, .html)
XML (.xml)
JSON (.json) - all values of type string and string array are translated
TEXT (.txt)
