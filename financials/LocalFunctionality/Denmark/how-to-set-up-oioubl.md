---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# How to: Set Up OIOUBL
You must define a location for storing Offentlig Information Online UBL \(OIOUBL\) files when you create electronic documents such as invoices or credit memos. You must also define payment methods, payment terms, and item charges, and you must set up relevant customers for OIOUBL.  
  
### To set up OIOUBL file locations for sales and receivables  
  
1.  In the **Search** box, enter **\($ N\_459 Sales & Receivables Setup $\)**, and then choose the related link.  
  
2.  In the **\($ N\_459 Sales & Receivables Setup $\)** window, on the **OIOUBL** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Invoice Path**|The path and name of the folder where you want to store the OIOUBL files for sales invoices.|  
    |**Cr. Memo Path**|The path and name of the folder where you want to store the OIOUBL files for sales credit memos.|  
    |**Reminder Path**|The path and name of the folder where you want to store the OIOUBL files for reminders.|  
    |**Fin. Chrg. Memo Path**|The path and name of the folder where you want to store the OIOUBL files for finance charge memos.|  
  
3.  In the **Default OIOUBL Profile Code** field, select the profile that most of your public sector customers use.  
  
     When you select a profile, ADD INCLUDE<!--[!INCLUDE[navnow](includes/oioubl-electronic-invoicing-overview.md).  
  
    1.  To create a new profile, choose the **Default OIOUBL Profile Code** field, and then choose **New**.  
  
    2.  In the **OIOUBL Profile List** window, fill in the fields as described in the following table.  
  
        |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](includes/bp_tabledescription_md.md)]-->|  
        |---------------------------------|---------------------------------------|  
        |**Code**|Specifies the code for the OIOUBL profile.|  
        |**Profile ID**|Specifies the profile that you want to support in the electronic documents that you send to customers in the Danish public sector, such as **Procurement-BilSim-1.0**.|  
  
4.  Choose the **OK** button.  
  
> [!IMPORTANT]  
>  External document numbers are required for OIOUBL documents even if you did not select the **Ext. Doc. No. Mandatory** field on the **General** FastTab. If the document does not have an external document number, you will receive an error message.  
  
### To set up OIOUBL file locations for service management  
  
1.  In the **Search** box, enter **Service Mgt. Setup**, and then choose the related link.  
  
2.  In the **Service Mgt. Setup** window, on the **OIOUBL** FastTab, in the **Output Paths** section, fill in the fields as described in the following table.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_tablefield](includes/bp_tabledescription_md.md)]-->|  
    |---------------------------------|---------------------------------------|  
    |**Service Invoice Path**|The path and name of the folder where you want to store the OIOUBL files for service invoices.|  
    |**Service Cr. Memo Path**|The path and name of the folder where you want to store the OIOUBL files for service credit memos.|  
  
3.  Choose the **OK** button.  
  
 You must also add an OIOUBL payment channel to the payment methods that you use for electronic invoices. You must also set a code for the relevant payment terms.  
  
### To set up payment methods and payments terms  
  
1.  In the **Search** box, enter **Payment Methods**, and then choose the related link.  
  
2.  In the **Payment Methods** window, for each payment method that you will use for electronic invoices, in the **Payment Channel** field, select a payment channel. The following table describes the options.  
  
    |ADD INCLUDE<!--[!INCLUDE[bp_optionsheading](includes/bp_tabledescription_md.md)]-->|  
    |-------------------------------------|---------------------------------------|  
    |**Payment Slip**|The payment is made by using a payment slip, such as giro or an FI card \(Fællesindbetalingskort\). **Important:**  This payment channel is not supported in the standard version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
    |**Account Transfer**|The payment is made by transfer from the customer’s bank account.|  
    |**National Clearing**|The payment is made by transfer from the customer’s bank account and is processed by a clearing house.|  
    |**Direct Debit**|The payment is made by using the unified bank payment service \(PBS\).|  
  
3.  In the **Search** box, enter **Payment Terms**, and then choose the related link.  
  
4.  In the **Payment Terms** window, for each payment term that you will use for electronic invoices, in the **OIOXML Code** field, select a code. For more information, see OIOUBL Code.  
  
 Next, you must categorize your item charges.  
  
### To set up item charges  
  
1.  In the **Search** box, enter **Item Charges**, and then choose the related link.  
  
2.  In the **Item Charges** window, for each item charge, in the **Charge Category** field, select a category. For more information, see Charge Category.  
  
 You must also make sure that the OIOUBL Country-Region Code field is filled in for Denmark in the **Countries\/Regions** window.  
  
 Finally, you must specify EAN numbers and account codes for the relevant customers. For more information, see [How to: Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md).  
  
## See Also  
 [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)   
 [How to: Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)   
 Payment Methods   
 [\($ N\_459 Sales & Receivables Setup $\)-duplicate](-$-n_459-sales-receivables-setup-$-duplicate.md)   
 Service Mgt. Setup   
 Countries\/Regions   
 Item Charges