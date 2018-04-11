---
title: Responding to Requests About Personal Data
description: You must respond to data subject requests.
author: bholtorf

ms.author: bholtorf
ms.custom: na
ms.date: 03/13/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
---

# Responding to Requests About Personal Data  
Data subjects can request several types of actions regarding their personal data. If you have classified the sensitivity of your data, and are sure they are correct, an administrator can respond to requests by using the options under **Data Privacy** on the **Manage Users, User Groups, and Permissions** Role Center or, if you are using the Windows client, in the **IT Manager** Role Center. For more information about classifying data and classifying data sensitivity, see [Classifying Data](/dynamics-nav/classifying-data) and [Classifying Data Sensitivity](admin-classifying-data-sensitivity.md).

The following table provides examples of the types of requests you can respond to.

> [!Note]
> While we provide capabilities for responding to these types of request, and thereby accessing, personal data, it is your responsibility to ensure that personal and sensitive data are located and classified appropriately.

|Request Type|Description and Suggested Response|
|-----|-----|
|Portability requests|A data subject can make a data portability request, meaning, in part, that you must export the data subject's personal data from your systems and provide it in in a structured, commonly used format. To respond to these requests you can use the **Data Privacy Utility** to export personal data to an Excel file or a RapidStart configuration package. Using Excel, you can edit the personal data and save it in a commonly used, machine-readable format, such as .csv or .xml. For RapidStart configuration packages, you can configure master data tables and their related tables that contain personal data. <br><br> **Note:** When you export data you specify a minimum sensitivity level. The export will include the minimum and all sensitivity levels above it. For example, if you choose to export data that is classified as Personal the export will also include data that is classified as Sensitive. |
|Requests for deletion|A data subject can request that you delete their personal data. There are several ways to delete personal data using the customization capabilities, but the decision and implementation is your responsibility. In some cases, you may choose to directly edit your data, for example deleting a contact and then running the Delete Canceled Interaction batch job to delete interactions for the contact. <br><br> **Note:** If you have specified a date in the **Allow Document Deletion Before** field on the **Sales & Receivables Setup** or **Purchases & Payables Setup** pages, you might need to change the date so that you can delete posted sales and purchase documents that you have printed and that have posting dates on or before that date.|
|Requests for correction|A data subject can request that you correct inaccurate personal data. There are several ways to do so. In some cases, you can export lists to Excel to quickly bulk-edit multiple records, and then import the updated data. For more information, see [Exporting your Business Data to Excel](https://docs.microsoft.com/en-us/dynamics-nav-app/about-export-data). You can also manually edit fields that contain personal data, such as editing information about a customer in the Customer card. However, transaction records such as general, customer, and tax ledger entries are essential to the integrity of the enterprise resource planning system. If you store personal data in business transaction records, consider using the customization capabilities to modify such personal data.|

## Restrict Data Processing for a Data Subject
A data subject can request that you temporarily stop processing their personal data. To honor such requests, you can mark their record as blocked due to privacy to stop processing their data. When a record is marked as blocked, you cannot create new transactions that use that record. For example, you cannot create a new invoice for a customer when either the customer or the salesperson is blocked. To mark a data subject as blocked, open the card for the data subject, for example the Customer, Vendor, or Contact cards, and choose the **Privacy Blocked** check box. You may need to choose **Show More** to display the field.

## Handling Data About Minors
If a contact person's age is below the age of legal consent according to the laws in your region, you can indicate that by choosing the **Minor** check box on the **Contact** card. When you do, the **Privacy Blocked** check box is automatically selected. When you receive consent from the minor's parent or legal guardian, you can choose the **Parental Consent Received** check box to unblock the contact. Though you can process personal data for minors, you cannot use the profiling functionality in Microsoft Dynamics 365 for Sales.

> [!Note]
> The Change Log can record details such as when, and by whom, the **Parental Consent Received** check box was chosen. An administrator can set that up by using the **Change Log Setup** guide, and also choosing the **Log Modification for Parental Consent Received** check box on the **Contact** card. For more information, see [Logging Changes](/dynamics-nav-app/across-log-changes).  

## See Also
[Classifying Data](https://docs.microsoft.com/en-us/dynamics-nav/classifying-data)  
[Classifying Data Sensitivity](admin-classifying-data-sensitivity.md)  
[Exporting your Business Data to Excel](about-export-data.md)  
