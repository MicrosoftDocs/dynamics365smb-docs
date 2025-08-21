---
title: How to convert service contracts
description: This article describes several alternative methods that you can use to convert service contracts that include VAT amounts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords:
ms.date: 12/07/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Convert service contracts that include VAT amounts

Because the VAT rate change tool can't convert service contracts, these contracts must be converted manually. This article describes several alternative methods that you can use for service contract conversion.  

> [!NOTE]  
> This article provides a high-level workflow.  

 The following procedure describes how to correct an invoice for a prepaid service contract that has been created a year in advance.  

> [!NOTE]  
> For this example, you must change your work date to 01.01.2017.  

## To correct an invoice for a prepaid service contract  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Contract Management**, and then choose the related link.  
2. Under **Lists**, choose **Service Contracts**.  
3. Create a new prepaid service contract. Enter a start date of **01.01.2017** and an invoice period year for customer **20000**.  
4. To sign the contract, choose the **Sign Contract** action.  
5. Create a service invoice.
6. The invoice is listed as an unposted service invoice. To view the service invoice, choose the **Service** action, choose the **Contract Management** action, and then choose the **Service Invoices** action.  
7. Post the service invoice.  

> [!NOTE]  
> Don't change the unposted service invoice. Since the service ledger entries are created when the invoice is created, a change in the unposted invoice will not change the already created service ledger entries. However, the VAT entries are created when the invoice is posted. This lets you change the general product posting group and the GSP product posting group on the unposted service invoice.  

### To create a credit memo for VAT difference 
 
The following procedure describes how to create a credit memo that only includes the VAT difference for the already invoiced period starting on **01.07.2017**. In this example, the VAT amount is only posted to the Financial Management module, not to the Service Management module. The VAT entries that are linked to the service ledger entry won't be corrected.  

1. Create a new general ledger account for the VAT difference. This account is used for direct posting of the VAT correction.  
2. Add a new line to the VAT posting setup.  

## To create contract expiration dates in contract lines  

The following procedure describes how to create new contracts by working with contract expiration dates in service contract lines.  

1. On the **Service Contract** page, set the contract expiration date to **30.06.2017**.  
2. Choose the **Create Credit Memo** action to automatically create a credit memo for July 2017 to December 2017.  
3. Because the contract has expired, you need to create a new contract for the period with the new VAT rate for July 1, 2017 to December 31, 2017.  

### To create a new credit memo  

The following procedure describes how to create a new credit memo using the **Get Prepaid Contract Entries** batch job. Entries that you don't want to correct from January 2017 to June 2017 will be deleted.  

1. Run the VAT rate change tool on July 1, 2017. The general product posting group or the VAT product posting group is changed. For more information, see [Work with VAT on Sales and Purchases](finance-work-with-vat.md).  
2. After running the VAT rate change tool, enter a contract expiration date for the service contract. You can now delete the service contract line and create a new line that is identical to the old one.  
3. Create a new invoice for the period of January 2017 to December 2012 using the new VAT rate.  
4. To create another credit memo, on the **Service Credit Memos** page, choose the **New** action to create a new service credit memo.  
5. Choose the **Get Prepaid Contract Entries** action.  
6. After the conversion is complete, VAT and service ledger entries will be correct.  

## Related information  

[Work with Service Contracts and Service Contract Quotes](service-how-to-create-service-contracts-and-service-contract-quotes.md)  
[Finance](finance.md)  
[Report VAT to Tax Authorities](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
