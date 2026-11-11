---
title: Convert Service Contracts After a VAT Rate Change
description: Review ways to handle a VAT rate change for prepaid service contracts in Business Central, including VAT corrections and replacement contracts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: service contract, service contracts, convert service contract, convert service contracts, VAT, VAT rate change
ms.date: 11/11/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Convert service contracts after a VAT rate change

Because the VAT rate change tool can't convert service contracts, these contracts must be converted manually. This article describes several alternative methods that you can use for service contract conversion.  

> [!NOTE]  
> This article provides a high-level workflow.  

The following procedure describes how to correct an invoice for a prepaid service contract that has been created a year in advance.

> [!NOTE]  
> For this example, you must change your work date to 01.01.2017.  

## Correct an invoice for a prepaid service contract  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Contracts**, and then choose the related link.
1. Choose **New**.
1. Create a prepaid service contract for customer **20000**. Set **Starting Date** to **01.01.2017** and **Invoice Period** to **Year**.
1. To sign the contract, choose the **Sign Contract** action.
1. Choose **Create Service Invoice**.
1. [!INCLUDE[open-search](includes/open-search.md)], enter **Service Invoices**, and then choose the related link.
1. Open and post the service invoice.

> [!NOTE]  
> Changing the unposted invoice doesn't update the service ledger entries that were created with it. VAT entries, however, are created when the invoice is posted. You can change the general product posting group and VAT product posting group on the unposted invoice, but those changes don't update the existing service ledger entries.

### Set up a VAT difference correction

The following steps prepare the setup for a credit memo that includes only the VAT difference for the already invoiced period starting on **01.07.2017**. You must still create and post the credit memo. This type of correction affects financial entries but doesn't recreate the original service ledger entries.

1. Create a new general ledger account for the VAT difference. This account is used for direct posting of the VAT correction.  
1. Add a new line to the VAT posting setup.

## Create contract expiration dates in contract lines  

The following procedure describes how to create new contracts by working with contract expiration dates in service contract lines.  

1. On the **Service Contract** page, set the contract expiration date to **30.06.2017**.  
1. Choose the **Create Service Credit Memo** action to create a credit memo for July 2017 to December 2017.
1. Because the contract has expired, create a new contract for July 1, 2017 to December 31, 2017 with the new VAT rate.

### Create a new credit memo  

The following procedure describes how to create a credit memo using **Get Prepaid Contract Entries**. This batch job creates credit memo lines from service ledger entries. It doesn't delete posted service ledger entries.

1. Run the VAT rate change tool on July 1, 2017. The general product posting group or the VAT product posting group is changed. Learn more in [Work with VAT on Sales and Purchases](finance-work-with-vat.md).  
1. After running the VAT rate change tool, enter a contract expiration date for the service contract. You can now delete the service contract line and create a new line that's identical to the old one.
1. Create a new invoice for January 2017 to December 2017 using the new VAT rate.
1. On the **Service Credit Memos** page, choose **New**, and enter the customer and other required header information.
1. Choose **Get Prepaid Contract Entries**, and filter to the relevant service contract.
1. Review the generated credit memo lines. Remove credit memo lines for January 2017 to June 2017 that you don't want to correct.
1. Verify the VAT rates and amounts on the credit memo and replacement invoice before posting them. Running **Get Prepaid Contract Entries** alone doesn't post the correction.

## Related information  

[Work with Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md)  
[Finance](finance.md)  
[Report VAT to Tax Authorities](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
