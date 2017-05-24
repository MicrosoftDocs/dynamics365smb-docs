---
title: "How to: Create Payment Slips"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "payment slips"
  - "payment files"
ms.assetid: e1d42533-6e6c-4ee2-9d25-53eac831ca50
caps.latest.revision: 34
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "fr-fr"
---
# How to: Create Payment Slips
You can create payments slips to manage vendor and customer payments. Before you create payment slips, you must set up payment classes. For more information, see [How to: Set Up Payment Classes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-classes.md).  
  
 The following procedure describes how to create payment slips for vendor payments, but the same steps also apply to creating payment slips for customer payments.  
  
### To create a payment slip for vendors  
  
1.  In the **Search** box, enter **Payment Slips**, and then choose the relevant link.  
  
2.  On the **Home** tab, choose **New**.  
  
3.  In the **\($ N\_10868 Payment Slip $\)** window, choose a field to open the **\($ N\_10860 Payment Class List $\)** window.  
  
4.  Select a payment class, and then choose the **OK** button.  
  
5.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10865\_2 Currency Code $\)**|Specify the currency code to be used for the payment lines.|  
    |**\($ T\_10865\_4 Posting Date $\)**|Specify the posting date.|  
    |**\($ T\_10865\_5 Document Date $\)**|Specify the document date.|  
    |**\($ T\_10865\_16 Amount \(LCY\) $\)**|The total amount from the payment lines. This field is updated automatically when the net line amounts are changed.<br /><br /> [!INCLUDE[bp_fieldnoneditable](../../Finance/includes/bp_fieldnoneditable_md.md)]|  
  
6.  On the **Lines** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10866\_4 Account Type $\)**|The account type to which the payment line is posted.|  
    |**\($ T\_10866\_5 Account No. $\)**|The unique identification number for the account to which the entry will be posted.|  
  
7.  In the **\($ T\_10866\_25 Bank Account Code $\)** field, select a bank name from the list, and then choose **Advanced**.  
  
8.  Optionally, for SEPA, in the **\($ N\_426 Select – Vendor Account List $\)** window, on the **Home** tab, in the **Manage** Group, choose **Edit**.  
  
     Fill in the following fields if needed:  
  
    -   **\($ T\_288\_17 Country\/Region Code $\)**. In the list, choose **Advanced**, and make sure that the **SEPA Allowed** check box is selected for the code that you select.  
  
    -   **\($ T\_288\_25 Swift Code $\)**  
  
    -   **\($ T\_288\_24 IBAN $\)**  
  
     Choose the **OK** button to close the window.  
  
9. Optionally, for SEPA, on the **Navigate** tab, choose **Header RIB**. Select the **\($ T\_10865\_31 Bank Country\/Region Code $\)** field, and then choose **Advanced**. Make sure the **\($ T\_9\_10800 SEPA Allowed $\)** check box is selected. Also make sure that the **IBAN** and **SWIFT Code** fields are filled in.  
  
10. On the **Home** tab, in the **Process** group, choose **\($ B\_10862 Suggest Vendor Payments $\)**.  
  
    > [!NOTE]  
    >  You can also manually fill in the payment lines.  
  
11. In the **\($ B\_10862 Suggest Vendor Payments $\)** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ B\_10862\_N\_2\_1120001 Last Payment Date $\)**|The last payment date for the vendor ledger entries that are to be included in the batch job.|  
    |**\($ B\_10862\_N\_2\_1120002 Find Payment Discounts $\)**|Select to include vendor ledger entries for which you can receive a payment discount.|  
    |**\($ B\_10862\_N\_2\_1120000 Summarize per $\)**|The criteria for summarizing the payment line.|  
    |**\($ B\_10862\_N\_2\_1120003 Use Vendor Priority $\)**|Select to sort the suggested payments based on the value in the **Priority** field on the vendor cards. For more information, see [\($ T\_23\_46 Priority $\)](../Topic/\($%20T_23_46%20Priority%20$\).md).|  
    |**\($ B\_10862\_N\_2\_1120004 Available Amount \(LCY\) $\)**|The maximum amount that is available for payments in local currency.|  
    |**\($ B\_10862\_N\_2\_1120005 Currency Filter $\)**|The code for the currency to be included in the batch job.|  
  
12. On the **Vendor** FastTab, select the appropriate filters.  
  
13. Choose the **OK** button.  
  
     The payment lines are automatically created.  
  
14. In the **\($ N\_10868 Payment Slip $\)** window, on the **Posting** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_10865\_13 Source Code $\)**|The source code for the payment slip.|  
    |**\($ T\_10865\_9 Department Code $\)**|The relevant dimension code.|  
    |**\($ T\_10865\_10 Project Code $\)**|The relevant dimension code.|  
    |**\($ T\_10865\_14 Account Type $\)**|The account type to which or from which the payments will be transferred.|  
    |**\($ T\_10865\_15 Account No. $\)**|The account number to which or from which the payments will be transferred.|  
  
15. Optionally, for SEPA, in the **\($ T\_10865\_15 Account No. $\)** field, choose **Advanced**.  
  
     In the **\($ N\_371 Bank Account List $\)** window, on the **Home** tab, choose **Edit**.  
  
     Fill in the following fields if needed:  
  
    -   **General** FastTab  
  
        -   **\($ T\_270\_35 Country\/Region Code $\)**  
  
    -   **Transfer**  FastTab  
  
        -   **\($ T\_270\_111 Swift Code $\)**  
  
        -   **\($ T\_270\_110 IBAN $\)**  
  
    -   **RIB** FastTab  
  
        -   **\($ T\_270\_1210 Payment Export Format $\)**: SEPA  
  
        -   **\($ T\_270\_115 SEPA CT Msg. ID No. Series $\)**: Bank  
  
16. Choose the **OK** button.  
  
     After you create a payment slip, you can generate payment files and send them to the bank electronically.  
  
    > [!NOTE]  
    >  A payment file can be created if the payment slip displays **File** for the **\($ T\_10862\_6 Action Type $\)** field. For more information, see [\($ T\_10862\_6 Action Type $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/-$-t_10862_6-action-type-$-.md).  
  
### To create a payment file  
  
1.  In the **Search** box, enter **Payment Slips**, and then choose the relevant link.  
  
2.  Select a payment slip, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  In the **\($ N\_10868 Payment Slip $\)** window, on the **Actions** tab, in the **Posting** group, choose **Generate file**.  
  
4.  Choose the **Yes** button, and then choose the **OK** button.  
  
     The payment file is generated and exported according to the export type that is specified in the **\($ N\_10866 Payment Step $\)** window.  
  
5.  In the case of error, review the errors listed in the **File Export Errors** FactBox, and take the appropriate action.  
  
## See Also  
 [Payment Management](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/payment-management.md)   
 [How to: Set Up Payment Classes](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-classes.md)   
 [How to: Set Up Payment Statuses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-statuses.md)   
 [How to: Set Up Payment Steps](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-steps.md)   
 [How to: Set Up Payment Addresses](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-set-up-payment-addresses.md)   
 [How to: Post Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-post-payment-slips.md)   
 [How to: Archive Payment Slips](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-archive-payment-slips.md)   
 [How to: Export or Import Payment Management Setup Parameters](../../LocalFunctionalityForMicrosoftDynamicsNav2016/France/how-to-export-or-import-payment-management-setup-parameters.md)   
 [\($ T\_23\_46 Priority $\)](../Topic/\($%20T_23_46%20Priority%20$\).md)   
 [\($ T\_349 Dimension Value $\)](assetId:///abbe4b49-2198-452c-9fa0-108cf5e6d7af)