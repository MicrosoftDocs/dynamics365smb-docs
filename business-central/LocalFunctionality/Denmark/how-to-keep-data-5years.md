---
title: Keeping data for 5 years in Denmark
description: This article describes how System automaticall keeps data in Denmark based on bookkeeping act.
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.search.form: 
ms.date: 12/08/2023
ms.author: altotovi

---

# Keeping transactional data for 5 years in Denmark 

Based on Danish bookkeeping act, Dynamics 365 Business central as a digital standard bookkeeping system must support the storage of the company´s recorded transactions and receipts covered by § 3 for 5 years from the end of the financial year. Those posted transactions together with digital vouchers must be preserved so that they cannot be changed, backdated or deleted by the company or any user. Software provider must keep them stored in a structured and machine-readable format in this period, regardless of any termination of customer relations with the company or the company's bankruptcy or forced dissolution.    

To provide these requirements, Microsoft will daily export in the account-protected Azure Blob Storage all required transactional data as well as the related digital vouchers, where after postingg they cannot be changed, backdated, or deleted by the company. These data can be available only for Danish authorities based on official request based on the law, and even then, access to this data is read-only. The system saves data on the daily level, so data not required by the law (older than 5 years from the end of the financial year the material concerns) can automatically be located and removed based on GDPR requirement for not keeping data more than required by the law. Microsoft will not keep data in this storage before required by the law - from 2024 year.   

## Mandatory usage of CVR Number ##

CVR Number must be populated before users start with the posting to the general ledger. To do this, follow next steps:  

1. Select the search button ![Magnifying glass button that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Company Information**, and then select the related link.
2. Enter CVR Number your company has been registered with, to the **Registration No.** field.
3. Close the page.


For more information, see [Danish Local Functionality](denmark-local-functionality.md).

## See also

[Financial Management](../../finance.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
