---
title: Keep transactional data for five years in Denmark 
description: This article describes how to automatically keep data based on the Danish bookkeeping act.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: retain data, bookkeeping act, dk, denmark, cvr number
ms.search.form: 
ms.date: 11/17/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Keep transactional data for five years in Denmark

Based on the Danish bookkeeping act, Dynamics 365 Business Central, as a digital standard bookkeeping system, must support storage of the company's recorded transactions and receipts that are covered by §3 for five years from the end of the financial year. Together with digital vouchers, those posted transactions must be preserved so that they can't be changed, backdated, or deleted by the company or a user. A software provider must keep them stored in a structured and machine-readable format during that period, regardless of any termination of customer relations with the company, or the company's bankruptcy or forced dissolution.

To meet these requirements, Microsoft exports all required transactional data and the related digital vouchers on a daily basis in the account-protected Azure Blob Storage. After the data and vouchers are posted, they can't be changed, backdated, or deleted by the company. This data can be made available only to Danish authorities in response to an official request based on the law. Even then, access to this data is read-only.

Because the system saves data daily, data that isn't required by the law (that is, data that's older than five years from the end of the financial year that the material concerns) can be automatically located and removed, based on the requirement for not keeping data longer than is required by the law. Microsoft doesn't keep data in this storage before the law requires (that is, from the year 2024).

## Mandatory use of the CVR number

The Central Business Register (CVR) number must be filled in before users post to the general ledger. To fill it in, follow these steps:

1. Select the search button ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do"), enter **Company Information**, and then select the related link.
1. In the **Registration No.** field, enter the CVR number for your company.
1. Close the page.

> [!IMPORTANT]
> After you enter the CVR number in the **Registration No.** field on the **Company Information** page, the Nemhandel APIs validate the number in the production environment. Once you post the first transaction, the company is treated as a production entity and can no longer be deleted. However, if you accidentally create a company in the production environment using a real CVR number but haven't posted any transactions, you can still delete it.

Learn more in [Denmark Local Functionality](denmark-local-functionality.md), which provides a list of features that are specific to Denmark.

## Related information

[Financial Management](../../finance.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
