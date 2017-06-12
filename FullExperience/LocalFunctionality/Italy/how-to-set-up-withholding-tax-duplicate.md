---
title: "How to: Set Up Withholding Tax-duplicate"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "vendor payments, setting up withholding tax"
  - "tax, withholding"
  - "payments, vendor"
  - "payments, withholding tax"
  - "withholding tax, setting up"
ms.assetid: 90bfd783-7e81-42d6-bd87-68ce95f8ba2b
caps.latest.revision: 38
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "it-it"
---
# How to: Set Up Withholding Tax-duplicate
Companies must pay withholding tax to the government for third\-party services and vendor purchases. Withholding tax is calculated during invoice payment rather than during invoice posting.  
  
### To set up withholding tax codes  
  
1.  In the **Search** box, enter **Withhold Tax**, and then choose the link for the **Setup** area for payables.  
  
2.  Under **Lists**, choose **Code**.  
  
3.  To open a new withholding code, on the **Home** tab, choose **New**.  
  
4.  Enter information into the relevant fields.  
  
5.  To open add lines to the withhold code, on the **Navigate** tab, choose **Withhold Code Lines**.  
  
6.  Enter information into the relevant fields.  
  
7.  Choose the **OK** button.  
  
8.  To close the **Withhold Codes** window, choose the **OK** button.  
  
### To set up withholding tax for vendors  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  Select the relevant vendor, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  Fill in the FastTabs as described in the following table.  
  
    |FastTab|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |-------------|---------------------------------------|  
    |**General**|The vendor personal data.|  
    |**Communication**|The contact details for the vendor.|  
    |**Invoicing**|The invoicing details for the vendor.|  
    |**Payments**|The payment information for the vendor.|  
    |**Receiving**|The subcontracting information for the vendor.|  
    |**Foreign Trade**|The foreign trade information for the vendor.|  
    |**Free Lance Fee**|Select the relevant withholding tax code in the **Withholding Tax Code** field to include the withholding tax information.|  
  
4.  To close the **Vendor Card** window, choose the **OK** button.  
  
### To calculate withholding tax for purchase invoices  
  
1.  In the **Search** box, enter **Purchase Invoices**, and then choose the related link.  
  
2.  Select the relevant purchase invoice, and then on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **Navigate** tab, in the **Invoice** group, Choose **Withhold Taxes\-Soc. Sec.**.  
  
4.  In the **Withh. Taxes\-Contribution Card** window, on the **Withhold Taxes** FastTab, in the **Withholding Tax Code** field, select the code for the withholding tax.  
  
5.  To calculate the withholding tax amount before posting, on the **Home** tab, in the **Process** group, choose **Calculate**.  
  
6.  Choose the **OK** button.  
  
### To make a vendor payment  
  
1.  In the **Search** box, enter **Payment Journals**, and then choose the related link.  
  
2.  In the **Batch Name** field, specify the relevant journal batch.  
  
3.  To create a new payment journal line, enter the relevant information in the fields.  
  
4.  To make a vendor payment, on the **Home** tab, in the **Process** group, choose **Post**.  
  
    > [!NOTE]  
    >  The amount in the new line in the **Payment Journal** window is the withholding tax payment amount.  
  
5.  To close the **Payment Journal** window, choose the **OK** button.  
  
## See Also  
 [Vendor Card](../Topic/\($%20N_26%20Vendor%20Card%20$\).md)   
 [Purchase Invoice](../Topic/\($%20N_51%20Purchase%20Invoice%20$\).md)   
 [Payment Journal](../../Finance/-$-n_256-payment-journal-$-.md)   
 [How to: Print Withholding Tax Reports](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Italy/how-to-print-withholding-tax-reports.md)