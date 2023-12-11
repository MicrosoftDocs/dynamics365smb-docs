---
title: Keeping data for five years in Denmark
description: This article describes how to automatically keep data based on the Danish bookkeeping act.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 
ms.date: 12/11/2023
ms.author: altotovi

---

# Keeping transactional data for five years in Denmark 

Based on Danish bookkeeping act, Dynamics 365 Business central as a digital standard bookkeeping system must support storage of the company´s recorded transactions and receipts covered by § 3 for five years from the end of the financial year. Together with digital vouchers, those posted transactions must be preserved so that they can't be changed, backdated. or deleted by the company or a user. A software provider must keep them stored in a structured and machine-readable format during this period, regardless of any termination of customer relations with the company, or the company's bankruptcy or forced dissolution.    

To provide these requirements, Microsoft will export all required transactional data and the related digital vouchers on a daily basis in the account-protected Azure Blob Storage. After the data and vouchers are posted, they can't be changed, backdated, or deleted by the company. These data can be available only for Danish authorities based on official request based on the law, and even then, access to this data is read-only. Because the system saves data daily, data not required by the law (older than 5 years from the end of the financial year the material concerns) can automatically be located and removed based on the requirement for not keeping data more than required by the law. Microsoft won't keep data in this storage prior to the law requirements - from 2024 year.   

## Mandatory usage of CVR Number 

The CVR Number must be populated before users post to the general ledger. To do this, follow these steps:  

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Company Information**, and then select the related link.
2. In the **Registration No.** field, enter the CVR Number for your company.
3. Close the page.


For more information, see [Danish Local Functionality](denmark-local-functionality.md).

## See also

[Financial Management](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
