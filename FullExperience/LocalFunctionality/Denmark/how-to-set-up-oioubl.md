---
title: "How to: Set Up OIOUBL"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "OIOUBL, setting up"
  - "electronic invoices, setting up"
  - "payment methods, setting up for OIOUBL"
ms.assetid: 0cdede5c-1c5a-4a19-a9b5-e7eafbeedf98
caps.latest.revision: 25
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
---
# How to: Set Up OIOUBL
You must define a location for storing Offentlig Information Online UBL \(OIOUBL\) files when you create electronic documents such as invoices or credit memos. You must also define payment methods, payment terms, and item charges, and you must set up relevant customers for OIOUBL.  
  
### To set up OIOUBL file locations for sales and receivables  
  
1.  In the **Search** box, enter **\($ N\_459 Sales & Receivables Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_459 Sales & Receivables Setup $\)** window, on the **OIOUBL** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_311\_13600 Invoice Path $\)**|The path and name of the folder where you want to store the OIOUBL files for sales invoices.|  
    |**\($ T\_311\_13601 Cr. Memo Path $\)**|The path and name of the folder where you want to store the OIOUBL files for sales credit memos.|  
    |**\($ T\_311\_13602 Reminder Path $\)**|The path and name of the folder where you want to store the OIOUBL files for reminders.|  
    |**\($ T\_311\_13603 Fin. Chrg. Memo Path $\)**|The path and name of the folder where you want to store the OIOUBL files for finance charge memos.|  
  
3.  In the **\($ T\_311\_13604 Default OIOUBL Profile Code $\)** field, select the profile that most of your public sector customers use.  
  
     When you select a profile, [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] updates open sales documents and service documents with the specified profile. For more information, see [OIOUBL Electronic Invoicing Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/oioubl-electronic-invoicing-overview.md).  
  
    1.  To create a new profile, choose the **\($ T\_311\_13604 Default OIOUBL Profile Code $\)** field, and then choose **New**.  
  
    2.  In the **\($ N\_13600 OIOUBL Profile List $\)** window, fill in the fields as described in the following table.  
  
        |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
        |---------------------------------|---------------------------------------|  
        |**\($ T\_13600\_1 Code $\)**|Specifies the code for the OIOUBL profile.|  
        |**\($ T\_13600\_2 Profile ID $\)**|Specifies the profile that you want to support in the electronic documents that you send to customers in the Danish public sector, such as **Procurement\-BilSim\-1.0**.|  
  
4.  Choose the **OK** button.  
  
> [!IMPORTANT]  
>  External document numbers are required for OIOUBL documents even if you did not select the **\($ T\_311\_8 Ext. Doc. No. Mandatory $\)** field on the **General** FastTab. If the document does not have an external document number, you will receive an error message.  
  
### To set up OIOUBL file locations for service management  
  
1.  In the **Search** box, enter **\($ N\_5919 Service Mgt. Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_5919 Service Mgt. Setup $\)** window, on the **OIOUBL** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Service Invoice Path**|The path and name of the folder where you want to store the OIOUBL files for service invoices.|  
    |**Service Cr. Memo Path**|The path and name of the folder where you want to store the OIOUBL files for service credit memos.|  
  
3.  Choose the **OK** button.  
  
 You must also add an OIOUBL payment channel to the payment methods that you use for electronic invoices. You must also set a code for the relevant payment terms.  
  
### To set up payment methods and payments terms  
  
1.  In the **Search** box, enter **\($ N\_427 Payment Methods $\)**, and then choose the related link.  
  
2.  In the **\($ N\_427 Payment Methods $\)** window, for each payment method that you will use for electronic invoices, in the **\($ T\_289\_13600 Payment Channel $\)** field, select a payment channel. The following table describes the options.  
  
    |[!INCLUDE[bp_optionsheading](../../DesignAndEngineering/includes/bp_optionsheading_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |-------------------------------------|---------------------------------------|  
    |**Payment Slip**|The payment is made by using a payment slip, such as giro or an FI card \(Fællesindbetalingskort\). **Important:**  This payment channel is not supported in the standard version of [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)].|  
    |**Account Transfer**|The payment is made by transfer from the customer’s bank account.|  
    |**National Clearing**|The payment is made by transfer from the customer’s bank account and is processed by a clearing house.|  
    |**Direct Debit**|The payment is made by using the unified bank payment service \(PBS\).|  
  
3.  In the **Search** box, enter **\($ N\_4 Payment Terms $\)**, and then choose the related link.  
  
4.  In the **\($ N\_4 Payment Terms $\)** window, for each payment term that you will use for electronic invoices, in the **\($ T\_3\_13600 OIOXML Code $\)** field, select a code. For more information, see [\($ T\_3\_13600 OIOUBL Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-t_3_13600-oioubl-code-$-.md).  
  
 Next, you must categorize your item charges.  
  
### To set up item charges  
  
1.  In the **Search** box, enter **\($ N\_5800 Item Charges $\)**, and then choose the related link.  
  
2.  In the **\($ N\_5800 Item Charges $\)** window, for each item charge, in the **\($ T\_5800\_13600 Charge Category $\)** field, select a category. For more information, see [\($ T\_5800\_13600 Charge Category $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-t_5800_13600-charge-category-$-.md).  
  
 You must also make sure that the [\($ T\_9\_13600 OIOUBL Country\-Region Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/-$-t_9_13600-oioubl-country-region-code-$-.md) field is filled in for Denmark in the **\($ N\_10 Countries\/Regions $\)** window.  
  
 Finally, you must specify EAN numbers and account codes for the relevant customers. For more information, see [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md).  
  
## See Also  
 [OIOUBL Electronic Invoicing Overview](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/oioubl-electronic-invoicing-overview.md)   
 [How to: Set Up Customers for OIOUBL](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Denmark/how-to-set-up-customers-for-oioubl.md)   
 [\($ N\_427 Payment Methods $\)](../Topic/\($%20N_427%20Payment%20Methods%20$\).md)   
 [\($ N\_459 Sales & Receivables Setup $\)\-duplicate](../../Sales/-$-n_459-sales-receivables-setup-$-duplicate.md)   
 [\($ N\_5919 Service Mgt. Setup $\)](../Topic/\($%20N_5919%20Service%20Mgt.%20Setup%20$\).md)   
 [\($ N\_10 Countries\/Regions $\)](assetId:///bf41e72c-c814-4b75-8364-efb0136882a4)   
 [\($ N\_5800 Item Charges $\)](../Topic/\($%20N_5800%20Item%20Charges%20$\).md)