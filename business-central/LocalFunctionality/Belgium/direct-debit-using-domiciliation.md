---
title: Belgian Direct Debit Using Domiciliation [BE]
description: A domiciliation is a financial agreement between a business and its customers that facilitates the automatic collection of payments for customer invoices.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: domiciliation, direct debit, electronic banking, Belgian version
ms.search.form: 11300, 2000000, 2000001, 2000003, 2000020, 2000021, 2000022
ms.date: 04/01/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Direct debit using domiciliation

A domiciliation is a financial agreement between you and your customers, allowing you to automatically collect the payments for customer's invoices through a preferred bank account. Domiciliation can only be processed for domestic customers with domestic bank accounts. Domiciliation in foreign currencies or involving foreign banks aren't supported.  

Direct debit domiciliation is useful for companies with many customers or subscribers, such as a utility company or a publishing company.  

Before you can start using electronic banking for domiciliation, you must enter certain basic information.  

- **Domiciliation number** - This is a unique code obtained from the bank which identifies the domiciliation agreement between you, your customer, and the bank. The contract contains details regarding payment frequency, bank account numbers, and amounts. When you send your payments to the bank, the bank uses the domiciliation number to identify all parties involved.  

- **Preferred bank account** - The preferred bank account is suggested as a default bank account on all domiciliation suggestions for that customer. If necessary, you can change the bank account before posting the domiciliation suggestions. Learn more in [Generate Domiciliation Suggestions](/dynamics365/business-central/LocalFunctionality/Belgium/direct-debit-using-domiciliation).  

## Set up domiciliation

Before you can use electronic banking for domiciliation, you must enter the customer's domiciliation number and preferred bank account.  

> [!NOTE]  
> You should use one bank account per customer for all domiciliation.  

### Set up process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
1. Select the customer, and then choose the **Edit** action.  
`. Fill in the fields as described in the following table.  

    |Field|Description|  
    |-----|-----------|  
    |**Domiciliation**|Enter the domiciliation number for the customer. This number is used when you create domiciliation for this customer.|  
    |**Preferred Bank Account**|Enter the preferred bank account for transactions with this customer. This account is used when you create a payment suggestion for this customer.|  

## Generate domiciliation suggestions

After setting up domiciliation, you can start generating domiciliation suggestions. In [!INCLUDE[prod_short](../../includes/prod_short.md)], you can create domiciliation suggestions for domestic customers only.  

### Process

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Domiciliation Journal**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch, and then choose the **Suggest Domiciliations** action.  
1. Fill in the fields as displayed in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Due Date**|Enter the due date to be included in the batch job. Only entries that have a due date before or on this date is included.|  
    |**Take Payment Discounts**|Select if you want the batch job to include customer ledger entries for which you can receive a payment discount.|  
    |**Payment Discount Date**|Enter the date that is used to calculate the payment discount.|  
    |**Select Possible Refunds**|Select if you want the batch job to include refunds.|  
    |**Posting Date**|Enter the date that appears as the posting date on the lines that the batch job inserts in the domiciliation journal.|  

1. Enter any additional filter criteria.  
1. Choose the **OK** button.  

When the batch job is finished, the domiciliation journal contains all open customer ledger entries that match the filters.  

> [!NOTE]  
> The domiciliation suggestions include only customers who have a Domiciliation number set up. Learn more in the [Set up domiciliation](#set-up-domiciliation) section.  

## Edit and delete domiciliation lines

After generating domiciliation suggestions, you might want to change the domiciliation lines. For example, you might want to reassign a bank account or prevent payment for a specific customer or customer ledger entry.  

After modifying the journal lines, print the **Domiciliation Journal - Test** report to test all journal lines.  

The **Suggest Domiciliations** batch job creates domiciliation suggestions for all customers matching the specified criteria.  

### Edit a journal line  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Domiciliation Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch.  
1. Select the journal line, and edit the fields.  

### Delete a journal line  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Domiciliation Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch.  
1. Select the journal line, and then choose the **Delete** action.  
1. Choose the **Yes** button.  

## Test Domiciliation

To test the domiciliation journal lines, you can use the **Domiciliation Journal - Test** report. This report prints an overview of all journal lines, along with any errors such as missing fields or incorrect bank accounts. You have to correct all errors before you can post the lines.  

### Print a domiciliation test report  

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Domiciliation Journal**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch.  
1. Choose the **Test Report** action.  
1. Choose the **Print** button to print the report, or choose the **Preview** button to view it on the screen.  

## Export and Post Domiciliation

You can submit domiciliation to your bank by exporting the data to a file. When you export to a file, you can choose to automatically post the lines to the general ledger.  

Depending on setup of the **SEPA Direct Debit Exp. Format** field on the **Bank Account Card** page, the **File Domiciliations** action opens either of these request pages:  

- **Create Gen. Jnl. Lines** page – for the SEPA Direct Debit format.  
- **File Domiciliations** page – for domestic formats.  

### Export and post domiciliation

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Domiciliation Journals**, and then choose the related link.  
1. In the **Batch Name** field, select the required journal batch, and then choose the **File Domiciliations** action.  
1. On the **Create Gen. Jnl. Lines** page, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

   If your company is set up to use the ISABEL format, the **File Domiciliations** page appears instead.
1. Choose the **OK** button to export the file.  
1. Choose an appropriate location from where you upload the file to your bank, and then choose **Save**.  
1. Choose the **Yes** button to automatically post the domiciliation journal lines.  

   If you didn't select the **Post General Journal Lines** checkbox, you must post the domiciliation manually in the general journal.  

   > [!NOTE]  
   > After posting domiciliation in the general journal, delete the posted domiciliation on the **Domiciliation Journal** page. To do this, select all lines with status **Posted**, and then choose the **Delete** action.  

## Related information

- [Belgian Electronic Payments](belgian-electronic-payments.md)  
- [Belgian Electronic Banking](belgian-electronic-banking.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
