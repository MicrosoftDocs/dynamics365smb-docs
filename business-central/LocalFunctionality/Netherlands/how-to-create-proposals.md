---
    title: How to Create Proposals
    description: Proposals can be generated manually or automatically based on either vendor or customer ledger entries.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Create Proposals
Proposals can be generated manually or automatically based on either vendor or customer ledger entries.  

> [!IMPORTANT]  
>  To create a proposal, you must use the **Owner Information** field in the Vendor Bank Account Card and Customer Bank Account Card pages.  

> [!NOTE]  
>  At any time and at any level, before processing a proposal, the transaction mode and bank account can be modified. At the lowest level on the relevant vendor or customer ledger entries.  

## To create proposals manually  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Telebank - Bank Overview**, and then choose the related link.  
2.  Select the relevant bank account and then choose the **Proposal** action.  
3.  At a minimum, you must fill in the **Account Type**, **Account No.**, **Transaction Mode**, **Bank Account No.**, and **Amount** fields.  

4.  If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## To create proposals automatically from sales  

1. Set up a card for the customer who sent the invoice with appropriate values for the **Currency Code**, **Transaction Mode**, and **Bank Account** fields.
2. Create a sales invoice or credit memo, enter the customer and relevant items and post the invoice.
3. Check whether the **Currency Code**, **Transaction Mode**, and **Bank Account** fields of the invoice/credit memo contain appropriate values. By default, they will be copied from the customer card.  

4.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Telebank - Bank Overview**, and then choose the related link.  
5.  Select the relevant bank account, and then choose the **Proposal** action.  
6.  Choose the **Get Entries** action.  

    You can use the Get Proposal Entries Batch Job batch job to generate proposal lines based on relevant customer ledger entries.  

    > [!NOTE]  
    >  Only proposal lines will be created for ledger entries that have a transaction mode of account type **Customer** and a link to the active bank account.  

6.  If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## To create proposals automatically from purchases  

1.  Set up a card for the vendor that sent the invoice with appropriate values for **Currency Code**, **Transaction Mode**, and **Bank Account** fields.  
2.  Create a purchase invoice or credit memo, enter the vendor and relevant items.
3. Post the invoice.
4. Check whether the **Currency Code**, **Transaction Mode**, and **Bank Account** fields of the invoice/credit memo contain appropriate values. By default, they will be copied from the vendor card.  
5.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Telebank - Bank Overview**, and then choose the related link.  
6.  Select the relevant bank account, and then choose the **Proposal** action.  
7.  Choose the **Get Entries** action.  

    You can use the Get Proposal Entries Batch Job batch job to generate proposal lines based on relevant vendor ledger entries.  

    > [!NOTE]  
    >  Only proposal lines will be created for ledger entries that have a transaction mode of account type **Vendor** and a link to the active bank account.  

6.  If you want to view or adjust the proposal's detail lines, choose the **Detail Information** action. To return to the proposal, close the **Proposal Detail Line** page.  

## See Also  
 [Register New Customers](../../sales-how-register-new-customers.md)   
 [Invoice Sales](../../sales-how-invoice-sales.md)   
 [Record Purchases](../../purchasing-how-record-purchases.md)   
 [Create and Export Payment History](how-to-create-and-export-payment-history.md)
