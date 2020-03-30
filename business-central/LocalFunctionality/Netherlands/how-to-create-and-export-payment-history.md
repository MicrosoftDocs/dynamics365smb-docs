---
    title: How to Create and Export Payment History
    description: After you have created a proposal and made any modifications, you can process the proposal to create a payment history. Proposals can be created manually or automatically from a vendor or customer ledger entry.
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
# Create and Export Payment History
After you have created a proposal and made any modifications, you can process the proposal to create a payment history. Proposals can be created manually or automatically from a vendor or customer ledger entry. For more information, see [Create Proposals](how-to-create-proposals.md).  

 For exporting payment histories, the following protocols are supported:  

- BTL91 $)  
- BBV  
- PAYMUL  

## To create a payment history for a proposal  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Telebank - Bank Overview**, and then choose the related link.  

    If you want to print the proposal before you process it, choose the **Print** button.  

2.  To process the proposal, choose the **Process** action.  
3.  To view the payment history, close the **Telebank Proposal** page. Make sure the same bank account on the **Telebank – Bank Overview** page is selected, and then choose the **Payment History** action.  

The **Payment History List** page displays the payment history that you just created.  

## To export a payment history  

- On the **Payment History List** page, choose the **Export** action.  

    > [!NOTE]  
    >  A text file will be created. This file contains the path and file name as defined in the **Default File Names Field** field of the export protocol.  

## See Also  
 [Create Proposals](how-to-create-proposals.md)
