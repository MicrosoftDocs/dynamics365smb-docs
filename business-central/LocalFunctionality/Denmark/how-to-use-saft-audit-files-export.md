---
title: Export the SAF-T audit file format in Denmark
description: This article explains how to export all required data according to the SAF-T format in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: SAF-T format, Denmark, audit file, Danish, export data
ms.search.form: 5264, 5266, 5267, 5270, 
ms.date: 03/04/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export the SAF-T audit file format in Denmark

You can export all mandatory required data according to the Standard Audit File for Tax (SAF-T) format in Denmark. SAF-T is an international standard for the electronic exchange of reliable accounting data from organizations to a national tax authority or external auditors. Danish tax authorities use Organization for Economic Co-operation and Development (OECD) standard SAF-T as the standard file format for reporting. However, some Denmark-specific fields exist in this file export.  

## Exporting audit files

Export of the SAF-T audit file format in the Danish localization is based on the **Audit Files Extension** Microsoft app. Learn more in [Audit file export](../../finance-how-to-export-audit-files.md)  

Learn more in [Danish Local Functionality](denmark-local-functionality.md), which provides a list of features that are specific to Denmark.

## Import audit files  

You can import SAF-T file in Danish localization. To do this, complete the following steps.

1. Select the search button ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Import SAF-T Files**, and then select the related link.
1. On the **Import SAF-T Files** page, select **Import SAF-T File**.
1. On the attachment page, upload the SAF-T file by using drag and drop or by browsing to the file you want to import.  

When you finish importing the external SAF-T files, the result appears in the **Import SAF-T Files** list page.

From the **Import SAF-T Files** page, you can find details about imported SAF-T files with the specific name and the date once the file is uploaded.

> [!NOTE]
> When you import the SAF-T file, keep in mind that there are no additional actions in the system based on this information. Dynamics 365 Business Central can only keep the list of uploaded files.

## Related information

- [Financial Management](../../finance.md)  
- [Understanding the General Ledger and Chart of Accounts](../../finance-general-ledger.md)  
- [Work with Dimensions](../../finance-dimensions.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
