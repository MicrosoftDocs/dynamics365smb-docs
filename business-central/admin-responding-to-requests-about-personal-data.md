---
title: Responding to requests about users' personal data
description: This article explains how to respond to requests about personal data.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: concept-article
ms.date: 11/14/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Responding to requests about users' personal data

Data subjects can request several types of actions regarding their personal data. For example, under some privacy laws and regulations, they have the right to request the export, deletion, and modification of their personal data. These requests are called *Data Subject Requests*. If you have classified the sensitivity of your data, and are sure they are correct, an administrator can respond to requests by using the options in the **Data Privacy** tab in the **Administration of users, security groups and permissions** Role Center.

## Types of requests

The following table provides examples of the types of requests administrators can respond to.

> [!Note]
> While we provide capabilities for responding to these types of request, and thereby accessing, personal data, it's your responsibility to ensure that personal and sensitive data are located and classified appropriately.

|Request Type|Description and Suggested Response|
|-----|-----|
|Portability requests|A data subject can make a data portability request. You must export the data subject's personal data from your systems and provide it in a structured, commonly used format. To respond to these requests, you can use the **Data Privacy Utility** to export personal data to an Excel file or a RapidStart configuration package. Using Excel, you can edit the personal data and save it in a commonly used, machine-readable format, such as .csv or .xml. For RapidStart configuration packages, you can configure master data tables and their related tables that contain personal data. <br><br> **Note:** When you export data, you specify a minimum sensitivity level. The export includes the minimum and all sensitivity levels above it. For example, if you export data that is classified as Personal, the export also includes data classified as Sensitive. <br><br>When exporting data related to a data subject, the **Data Privacy Utility** looks for direct relationships between the data subject and data related to the data subject. Indirect relationships between data related to the data subject and other data are not exported automatically by the **Data Privacy Utility**. For example, the Contact table has directly related Contact Profile Answers data, and the Contact Profile Answers table is further related to Profile Questions data. If you want to export Profile Questions as well, you must add this table manually as a row with the appropriate filters in the configuration package that the **Data Privacy Utility** creates.<br><br>The **Data Privacy Utility** only considers tables of the type **Normal**. Data in other types of tables, such as CDS, CRM, ExternalSQL, and others resides in external systems, and portability requests should be handled in those systems.|
|Requests for deletion|A data subject can request that you delete their personal data. There are several ways to delete personal data using the customization capabilities, but the decision and implementation is your responsibility. In some cases, you might choose to directly edit your data. For example, delete a contact and then run the Delete Canceled Interaction batch job to delete interactions for the contact. <br><br> **Note:** If you've specified a date in the **Allow Document Deletion Before** field on the **Sales & Receivables Setup** or **Purchases & Payables Setup** pages, you might need to change the date so that you can delete posted sales and purchase documents that have posting dates on or before that date.|
|Requests for correction|A data subject can request that you correct inaccurate personal data. There are several ways to do so. In some cases, you can export lists to Excel to quickly bulk-edit multiple records, and then import the updated data. For more information, see [Exporting your Business Data to Excel](about-export-data.md). You can also manually edit fields that contain personal data, such as editing information about a customer in the Customer card. However, records such as general, customer, and tax ledger entries are important. If you store personal data in business transaction records, consider using the customization capabilities to modify such personal data.|

## Restrict data processing for a data subject

A data subject can request that you temporarily stop processing their personal data. To honor such requests, you can mark their record as blocked due to privacy to stop processing their data. When a record is marked as blocked, you cannot create new transactions that use that record. For example, you cannot create a new invoice for a customer when either the customer or the salesperson is blocked. To mark a data subject as blocked, open the card for the data subject, for example the Customer, Vendor, or Contact cards, and choose the **Privacy Blocked** check box. You may need to choose **Show More** to display the field.  

## Handling data subject requests when using a trial version

Certain types of personal data are part of a Microsoft 365 account, and only administrators can export the data. The process for handling data subject requests is different depending on the type of [!INCLUDE[prod_short](includes/prod_short.md)] tenant.

If you have a paid subscription for [!INCLUDE[prod_short](includes/prod_short.md)], users must contact their organization's tenant administrator to make a data subject request. Administrators have the administrative rights and tools to fulfill data subject requests.

If you signed up for [!INCLUDE[prod_short](includes/prod_short.md)] from the [Trials](https://trials.dynamics.com/) page, and you're still using the trial version, users can download and export their own data in the [Work and School Privacy page in the Azure portal](https://portal.azure.com#blade/Microsoft_AAD_IAM/GDPRViralBlade).

On the Work and School Privacy page, you can also close your account. However, we recommend that you export and delete all data first. Deleting your account means that you lose access to [!INCLUDE[prod_short](includes/prod_short.md)].

You can still mark people as blocked due to privacy and export, edit, or delete transactions as explained elsewhere in this article.  

## Exporting data from tables not classified by data subject

If you must export data that isn't classified in a way so that it's automatically exported, such as data from the Profile Answers table, you must take the following actions:

* Consider whether you really must export supplemental data that isn't directly related to the contact.
* Add the table and relationship manually to the Rapid Start package and export it directly from the Rapid Start package. We generate a Rapid Start package for you, so that you can tweak it in such situations.

## Handling data about minors

If a contact person's age is below the age of legal consent according to the laws in your region, you can indicate that by choosing the **Minor** check box on the **Contact** card. When you do, the **Privacy Blocked** check box is automatically selected. When you receive consent from the minor's parent or legal guardian, you can choose the **Parental Consent Received** check box to unblock the contact. Though you can process personal data for minors, you cannot use the profiling functionality in Dynamics 365 Sales.

> [!Note]
> The Change Log can record details such as when, and by whom, the **Parental Consent Received** check box was chosen. An administrator can set that up by using the **Change Log Setup** guide, and also choosing the **Log Modification for Parental Consent Received** check box on the **Contact** card. For more information, see [Logging Changes](across-log-changes.md).  

### Related information

<!-- [Classifying Data](/dynamics-nav/classifying-data?toc=/dynamics365/business-central/toc.json)  
[Classifying Data Sensitivity](admin-classifying-data-sensitivity.md)  -->
[Exporting your Business Data to Excel](about-export-data.md)  
[Logging Changes](across-log-changes.md)  
[Data Subject Requests](/microsoft-365/compliance/gdpr-data-subject-requests)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
