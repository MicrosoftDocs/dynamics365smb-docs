---
title: Export accounting data to Regnskab Basis in Denmark
description: This article describes how to upload a comma-separated values (CSV) file that contains accounting data to Regnskab Basis in Denmark.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: CSV file upload, Regnskab Basis, Denmark, accounting data
ms.search.form: 5264, 5266, 5267, 5270, 
ms.date: 03/04/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Export accounting data to Regnskab Basis in Denmark

Integration of Microsoft Dynamics 365 Business Central with comma-separated values (CSV) file uploads is required by Danish bookkeeping act Regnskab Basis and marks a pivotal advancement in financial data management. This streamlined process enables your business to effortlessly import large datasets, and helps enhance accuracy and efficiency.

This article explains the seamless CSV upload process in Regnskab Basis and its transformative impact on Denmark's financial landscape. You can export all required data as a CSV file according to the Danish requirements for Regnskab Basis. Before you begin, install the **Audit Files Extension** Microsoft app, and map general ledger (GL) accounts with the standard chart of accounts. Learn more in [Standard chart of accounts in Denmark](how-to-set-up-standard-coa.md).

## Export accounting data to Regnskab Basis

1. Select the search button ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **RB Accounting File**, and then select the related link.
1. On the **RB Accounting File** page, on the **Mapping Header** FastTab, in the **Please select a mapping header to use for export** field, specify the code for the mapping with the standard chart of accounts that you'll use.
1. On the **Period for Accounting File Export** FastTab, the system enters default values in the **Starting Date** and **Ending Date** fields, based on the mapping that you're using. You can update the values as you require.
1. In the **Income Statement Amount** field, set up the amount type that you want to use. The default value is **Net Change**.
1. In the **Balance Sheet Amount** field, set up the amount type that you want to use. The default value is **Balance at Date**.
1. When you've completed the setup, select **Generate File**. A .csv file for **amounts using in calculation methods**, **GL Accounts mapped in mapping**, and **starting and ending dates** is generated.
1. After the file is generated, manually upload it to the official service.

Learn more in [Danish Local Functionality](denmark-local-functionality.md).

## Related information

- [Financial Management](../../finance.md)  
- [Understanding the General Ledger and Chart of Accounts](../../finance-general-ledger.md)  
- [Work with Dimensions](../../finance-dimensions.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
