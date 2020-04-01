---
title: Responding to Requests About Personal Data
description: You must respond to data subject requests.
author: bholtorf

ms.service: dynamics365-business-central
ms.author: bholtorf
ms.custom: na
ms.date: 04/01/2020
ms.reviewer: na
ms.topic: article
---

# Responding to Requests About Personal Data  
Data subjects can request several types of actions regarding their personal data. For example, under the General Data Protection Regulation (GDPR), EU residents have the right to request the export, deletion and modification of their personal data. This is known as a *Data Subject Request*. If you have classified the sensitivity of your data, and are sure they are correct, an administrator can respond to requests by using the options under **Data Privacy** tab in the **IT Manager** Role Center. For more information about classifying data and classifying data sensitivity in [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], see [Classifying Data](/dynamics-nav/classifying-data?toc=/dynamics365/business-central/toc.json) and [Classifying Data Sensitivity](admin-classifying-data-sensitivity.md).  

## Types of Requests

The following table provides examples of the types of requests you can respond to.

> [!Note]
> While we provide capabilities for responding to these types of request, and thereby accessing, personal data, it is your responsibility to ensure that personal and sensitive data are located and classified appropriately.

|Request Type|Description and Suggested Response|
|-----|-----|
|Portability requests|A data subject can make a data portability request, meaning, in part, that you must export the data subject's personal data from your systems and provide it in in a structured, commonly used format. To respond to these requests you can use the **Data Privacy Utility** to export personal data to an Excel file or a RapidStart configuration package. Using Excel, you can edit the personal data and save it in a commonly used, machine-readable format, such as .csv or .xml. For RapidStart configuration packages, you can configure master data tables and their related tables that contain personal data. <br><br> **Note:** When you export data you specify a minimum sensitivity level. The export will include the minimum and all sensitivity levels above it. For example, if you choose to export data that is classified as Personal, the export will also include data that is classified as Sensitive. <br><br>When exporting data related to a data subject, the **Data Privacy Utility** looks for direct relationships between the data subject and data related to the data subject. Indirect relationships between data related to the data subject and other data are not exported automatically by the **Data Privacy Utility**. For example, the Contact table has directly related Contact Profile Answers data, and the Contact Profile Answers table is further related to Profile Questions data. If you want to export Profile Questions as well, you must add this table manually as a row with the appropriate filters in the configuration package that the **Data Privacy Utility** creates.|
|Requests for deletion|A data subject can request that you delete their personal data. There are several ways to delete personal data using the customization capabilities, but the decision and implementation is your responsibility. In some cases, you may choose to directly edit your data, for example deleting a contact and then running the Delete Canceled Interaction batch job to delete interactions for the contact. <br><br> **Note:** If you have specified a date in the **Allow Document Deletion Before** field on the **Sales & Receivables Setup** or **Purchases & Payables Setup** pages, you might need to change the date so that you can delete posted sales and purchase documents that you have printed and that have posting dates on or before that date.|
|Requests for correction|A data subject can request that you correct inaccurate personal data. There are several ways to do so. In some cases, you can export lists to Excel to quickly bulk-edit multiple records, and then import the updated data. For more information, see [Exporting your Business Data to Excel](about-export-data.md). You can also manually edit fields that contain personal data, such as editing information about a customer in the Customer card. However, transaction records such as general, customer, and tax ledger entries are essential to the integrity of the enterprise resource planning system. If you store personal data in business transaction records, consider using the customization capabilities to modify such personal data.|

## Restrict Data Processing for a Data Subject
A data subject can request that you temporarily stop processing their personal data. To honor such requests, you can mark their record as blocked due to privacy to stop processing their data. When a record is marked as blocked, you cannot create new transactions that use that record. For example, you cannot create a new invoice for a customer when either the customer or the salesperson is blocked. To mark a data subject as blocked, open the card for the data subject, for example the Customer, Vendor, or Contact cards, and choose the **Privacy Blocked** check box. You may need to choose **Show More** to display the field.  

## Handling Data Subject Requests While in Trial
Certain types of personal data is part of your Office 365 account and requires administrative access to export, if you receive a data subject request from a user regarding this type of personal data under the General Data Protection Regulation (GDPR). The process for handling data subject requests is different depending on the type of [!INCLUDE[d365fin](includes/d365fin_md.md)] tenant.  

If you have a paid subscription for [!INCLUDE[d365fin](includes/d365fin_md.md)], you must contact your organization's tenant administrator to make a data subject request. The administrator has the administrative rights and tools to fulfil your request.  

If you signed up for [!INCLUDE[d365fin](includes/d365fin_md.md)] from the [Trials](https://trials.dynamics.com/) page, and you have not moved out of this trial experience through a paid subscription by your organization’s tenant administrator, then you can fulfil your own data subject request in the [Work and School Privacy page in the Azure Portal](https://portal.azure.com#blade/Microsoft_AAD_IAM/GDPRViralBlade). Here, you can export and download your personal data.

On the Work and School Privacy page, you can also close your account. However, we recommend that you make sure that you have exported and deleted all data first, since deleting your account means that you lose access to [!INCLUDE[d365fin](includes/d365fin_md.md)].  

You can still mark people as blocked due to privacy and export, edit, or delete transactions as explained elsewhere in this article.  

## Exporting Data from Tables not Classified by Data Subject
If you have a situation where you have to export data that is not classified in a way so that it gets automatically exported, such as data from the Profile Answers table, you must do the following:
-	Consider if you really want or have to export this supplemental data that is unrelated to the contact, meaning that it has no direct relationship to it
-	Add this table and relationship manually to the Rapid Start package and export it directly from the Rapid Start package – that’s why we generate a Rapid Start package for you, so that you can tweak it in situations such as this.

## Handling Data About Minors
If a contact person's age is below the age of legal consent according to the laws in your region, you can indicate that by choosing the **Minor** check box on the **Contact** card. When you do, the **Privacy Blocked** check box is automatically selected. When you receive consent from the minor's parent or legal guardian, you can choose the **Parental Consent Received** check box to unblock the contact. Though you can process personal data for minors, you cannot use the profiling functionality in Dynamics 365 Sales.

> [!Note]
> The Change Log can record details such as when, and by whom, the **Parental Consent Received** check box was chosen. An administrator can set that up by using the **Change Log Setup** guide, and also choosing the **Log Modification for Parental Consent Received** check box on the **Contact** card. For more information, see [Logging Changes](across-log-changes.md).  

## See Also
[Classifying Data](/dynamics-nav/classifying-data?toc=/dynamics365/business-central/toc.json)  
[Classifying Data Sensitivity](admin-classifying-data-sensitivity.md)  
[Exporting your Business Data to Excel](about-export-data.md)  
[Logging Changes](across-log-changes.md)  
[Data Subject Requests for the GDPR](/microsoft-365/compliance/gdpr-data-subject-requests)  
