---
title: How to Create Reports with XBRL
description: XBRL is an XML-based language for tagging financial data, and enabling businesses to efficiently and accurately process and share their data.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 09/14/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Create Reports with XBRL

> [!NOTE]
> We're in the process of removing the features for XBRL reporting from [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Changes in 2022 release wave 1](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1).

XBRL (e**X**tensible **B**usiness **R**eporting **L**anguage) is a language, based on eXtensible Markup Language (XML), for tagging financial data, which enables businesses to efficiently and accurately process and share their data. The XBRL initiative enables global financial reporting by numerous enterprise resource planning (ERP) software companies and international accounting organizations. The goal of the initiative is to provide a standard for uniform reporting of financial information for banks, investors, and government authorities. Such business reporting can include:  

* Financial statements  
* Financial information  
* Non-financial information  
* Regulatory filings, such as annual and quarterly financial statements  

> [!NOTE]
> You can import general ledger-related schemas and create XBRL instance documents by mapping general ledger (G/L) data from the chart of accounts to elements in taxonomies designed for financial reports, such as balance sheets, income statements, and so on.
>
> The XBRL capabilities in Business Central support taxonomies for specification 2.1. However, taxonomies may contain unsupported elements such as formula linkbases or iXBRL (inline XBRL), or have other structural differences. We recommend you validate the XBRL capability before using it for reporting.
>
> Full support for taxonomies may require third-party XBRL tagging and tools. The XBRL International organization has a list of tools and services; depending on the XBRL reporting requirements for a given taxonomy, you may want to explore those resources. Learn more at [Getting Started for Business](https://go.microsoft.com/fwlink/?linkid=2153466) and [Tools and Services](https://go.microsoft.com/fwlink/?linkid=2153356).

## eXtensible Business Reporting Language

The XBRL taxonomies are maintained by www.xbrl.org. You can download taxonomies and read more detailed information on the XBRL website.  

Let's say someone wants financial information from you. They provide you with a taxonomy (an XML document) containing one or more schemas, each with one or more lines to fill out. The lines correspond to the individual financial facts required by the sender. You import this taxonomy, then fill out the schema(s) by entering the account(s) that corresponds with each line and which calculation is desired, such as net change or balance at date. In some cases you can enter a constant instead, for example, the number of employees. You are now ready to send the instance document (an XML document) to the requester. The idea is that this might be a recurring event, so unless changes have been made to the taxonomy, you just export new instance documents for new periods on request.

## XBRL comprises the following components

The XBRL **Specification** explains what XBRL is and how to build XBRL instance documents and taxonomies. The XBRL specification explains XBRL in technical terms and is intended for a technical audience.  

The XBRL **Schema** are the core low-level components of XBRL. The schema is the physical XSD (also called an XML schema definition) file that expresses how XBRL instance documents and taxonomies are to be built.

The XBRL **Linkbases** are the physical XML files that contain information about the elements defined in the XBRL Schema, such as labels in one or more languages, how they relate to each other, how to sum up elements, and so on.  

An XBRL **Taxonomy** is a "vocabulary" or "dictionary" created by a group, compliant with the XBRL specification, that enables the exchange of business information.  

An XBRL **Instance document** is a business report, such as a financial statement prepared to the XBRL specification. The meaning of the values in the instance document is explained by the taxonomy. In fact, an instance document is somewhat useless unless you know the taxonomy for which it is prepared.  

## Layered taxonomies

A taxonomy can consist of a base taxonomy, for example US GAAP (United States generally accepted accounting principles) or IAS (international accounting standards), and then have one or more extensions. To reflect this, a taxonomy refers to one or more schemas, each of which are separate taxonomies themselves. When the additional taxonomies are loaded into the database, the new elements are simply added to the end of the existing elements.  

## Linkbases

In XBRL Spec. 2, the taxonomy is described in several XML files. The primary XML file is the taxonomy schema file itself (.xsd file) which only contains an unordered list of elements or facts to be reported. In addition to this, there are usually some linkbase files (.xml). The linkbase files contain data that is complementary to the raw taxonomy (.xsd file). There are six types of linkbases files of which four have relevance for [!INCLUDE[prod_short](includes/prod_short.md)]. These are:

* Label linkbase: This linkbase contains labels or names for the elements. The file may contain labels in different languages which are identified with an XML property called 'lang'. The XML language identifier usually contains a two-letter abbreviation, and although it should be easy to guess what the abbreviation means, there is no connection to Microsoft Windows language code or the language codes defined in the demo data. Therefore, when you look up the languages for a specific taxonomy, you see all the labels for the first element in the taxonomy, meaning you can see an example of each language. A taxonomy can have several label linkbases attached to it as long as those linkbases contain different languages.  
* Presentation linkbase: This linkbase contains information about the structure of the elements or, more precisely, how the issuer of the taxonomy suggests the application presents the taxonomy to you. The linkbase contains a series of links that each connect two elements in a parent-child relationship. When applying all these links, the elements can be shown in a hierarchical way. Note that the presentation linkbase deals with just that: the presentation of elements to you.
* Calculation linkbase: This linkbase contains information about how the elements roll up. The structure is quite similar to the presentation linkbase, except that each link, or 'arc' as they are called, has a weight property. The weight can be either 1 or –1, indicating whether the element should be added to or subtracted from its parent. Note that the rollups do not necessarily align with the visual presentation.  
* Reference linkbase: This linkbase is an xml file containing supplementary information about the data required by the taxonomy issuer.

## Set up XBRL lines

After you import or update the taxonomy, the lines of the schemas must filled out with all information required to satisfy the particular financial reporting requirements. This information includes basic company information, the actual financial statements, notes to the financial statements, supplemental schedules, and so on.  

You set up XBRL lines by mapping the data in the taxonomy to the data in your general ledger.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **XBRL Taxonomies**, then choose the related link.  
2. On the **XBRL Taxonomies** page, select a taxonomy from the list.  
3. Choose the **Lines** action.  
4. Select a line and fill in the fields.  
5. To read detailed information about what to fill in, choose the **Information** action.  
6. To set up mapping the G/L accounts in the chart of accounts to the XBRL lines, choose the **G/L Map Lines** action.  
7. To add notes to the financial statement, choose the **Notes** action.  

   > [!TIP]
   > To exclude lines from the exported data, choose **NOT APPLICABLE** as the source type.

   > [!NOTE]  
   > You can only export data that corresponds to the selection in the **Source Type** field. This includes descriptions and notes.  

   > [!NOTE]  
   > Taxonomies might contain elements that [!INCLUDE[prod_short](includes/prod_short.md)] doesn't support. If an element is not supported, the **Source Type** field will display **Not Applicable** and the **Description** field will show an error message, such as **Unexpected type: "specific type not recognized"**. If you must export the element, choose a matching source type. Typically, this is a constant or a description. Doing this enables you to enter and export data, however, such elements might have validation rules that cannot be checked before exporting.

## Import an XBRL taxonomy

The first step in working with the XBRL functionality is to import a taxonomy into your company database. A taxonomy consists of one or more schemas and some linkbases. After you have completed the import of both schemas and linkbases and have applied the linkbases to the schema, you can set up the lines and map the general ledger accounts in the chart of accounts to the appropriate taxonomy lines.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **XBRL Taxonomies**, then choose the related link.  
2. On the **XBRL Taxonomies** page, create a new line and enter the name and description of the taxonomy.  
3. Choose the **Schemas** action, then insert the description of the schema.  
4. To import the schema, on the **XBRL Schemas** page, choose the **Import** action, then do one of the following steps to upload the file:

   [!INCLUDE[file-upload](includes/file-upload.md)]
5. To import the linkbase, on the **XBRL Schemas** page, choose the **Linkbases** action, then do one of the following steps to upload the file:

   [!INCLUDE[file-upload](includes/file-upload.md)] 
6. You can now choose to apply the linkbase to the schema. Repeat until you have imported all linkbases.  
7. Choose the **Apply to Taxonomy** action to apply the linkbase to the schema.  

> [!IMPORTANT]  
> Instead of individually applying the linkbases after the import, you can wait until you have imported all linkbases and then apply them at the same time. To do this, choose **NO** when you are prompted to apply the newly imported linkbase to the schema. Then select the lines with the linkbases that you want to apply.  

## Update an XBRL taxonomy

When a taxonomy changes you need to update the current taxonomy accordingly. The reason for the update can be an altered schema, an altered linkbase, or a new linkbase. After updating the taxonomy, you only need to map the lines for the changed or new lines.  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **XBRL Taxonomies**, then choose the related link.  
2. On the **XBRL Taxonomies** page, choose the **Schemas** action.  
3. To update a schema, select the schema you want to update, then choose the **Import** action.  
4. To update or add a new linkbase, choose the **Linkbases** action.  
5. Select the relevant linkbase or select <kbd>Ctrl</kbd>+<kbd>N</kbd> for a new line, select the type of linkbase, then insert a description.  
6. To import the linkbase, choose the **Import** action.  
7. Choose **Yes** to apply the linkbase to the schema.  

## Related information

[Financial Business Intelligence](bi.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
