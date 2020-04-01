---
    title: How to Set Up Payment Steps
    description: To use payment management, you must set up steps for payment documents and define payment steps for each payment status.

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
# Set Up Payment Steps
To use payment management, you must set up steps for payment documents and define payment steps for each payment status. For example, "Creation of documents," "Documents created,” and "Creation of payments." For more information, see [Set Up Payment Statuses](how-to-set-up-payment-statuses.md).  

## To set up payment steps  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Slip Setup**, and then choose the relevant link.  
2.  Select a payment class, and then choose the **Steps** action.  
3.  In the **Name** field, enter a name for the payment step. You can enter a maximum of 50 alphanumeric characters.  
4.  Choose the **Edit** action.  
5.  On the **Payment Step Card** page, fill in the fields as described in the following table.  

    |**Field**|**Description**|  
    |---------------------------------|---------------------------------------|  
    |**Name**|The payment step name that you entered on the **Payment Step** page.|  
    |**Previous Status**|The previous status, from which the step was last executed. The default value is 0. When the previous status is equal to the next status, the status is not modified after it is executed. Therefore, this payment step is optional and can be executed indefinitely.|  
    |**Previous Status Name**|The name of the status selected in the **Previous Status** field.|  
    |**Next Status**|The status at which this payment step ends.|  
    |**Next Status Name**|The name of the status selected in the **Next Status** field. This field cannot be modified.|  
    |**Action Type**|The type of action to be performed by this step. <br /><br /> **Ledger:** If you specify **Ledger**, you must define the additional ledger information on the **Payment Step Ledger** page.<br /><br /> **Report:** If you specify **Report**, you specify which report in the **Report No.** field.<br /><br /> **File:**<br /><br /> * If you specify **File**, you specify the type of file in the **Export Type** field: **Report** or **XMLPort**.<br /><br /> * For SEPA Credit Transfer files, specify **XMLport**, and then set the **Export No.** field to 1000.<br /><br /> * For SEPA Direct Debit files, specify **XMLport**, and then set the **Export No.** field to 1010.|  
    |**Report No.**|The identification number for the report. This field is available if the **Action Type** field is set to **Report**.|  
    |**Export Type**|The export type for the file. This field is available if the **Action Type** field is set to **File**.<br /><br /> For example, see [Export Payments](how-to-export-payments.md).|  
    |**Export No.**|The identification code for the selected export type. This field is available if the **Action Type** field is set to **File**.|  
    |**Verify Lines RIB**|Select to verify that the Relevé d'Identité Bancaire (RIB) key value specified on the payment slip line has been correctly reported.|  
    |**Verify Due Date**|Select to verify that the due date on the billing and payment line has been correctly reported.|  
    |**Source Code**|The source code that is linked to the payment step.<br /><br /> This field is available if the **Action Type** field is set to **Ledger**.|  
    |**Reason Code**|The reason code that is linked to the payment step.<br /><br /> This field is available if the **Action Type** field is set to **Ledger**.|  
    |**Header Nos. Series**|The number series code that must be used to assign numbers to the header for a new payment slip.<br /><br /> This field is available if the **Action Type** field is set to **Create New Document**.|  
    |**Correction**|Select to mark the payment entries as corrections. This field is available if the **Action Type** field is set to **Ledger**.|  
    |**Realize VAT**|Select to indicate that unrealized VAT should be reversed and VAT should be declared for this payment step.<br /><br /> This field is available if the **Unrealized VAT Reversal** field on the **Payment Class** page is set to **Delayed**.|  
    |**Verify Header RIB**|Select to verify that the RIB key value specified on the payment slip header has been correctly reported.|  
    |**Acceptation Code<>No**|Select to verify that the acceptance code for each payment line is not a number.|  

6.  Choose the **OK** button.  

If the action type of the payment step is **Ledger**, you must set up additional ledger information for the payment step.  

## To set up ledger information for a payment step  

1.  On the **Payment Step Card** page for the payment step, choose the **Ledger** action.  
2.  On the **Payment Step Ledger** page, choose the **New** action.  
3.  Fill in the fields as described in the following table.  

    |**Field**|**Description**|  
    |---------------------------------|---------------------------------------|  
    |**Sign**|The type of posting entry.|  
    |**Description**|The entry description.|  
    |**Accounting Type**|The accounting type that is used for posting the entry.|  
    |**Account Type**|The account type for posting the entry. This field is available if the **Accounting Type** is **Setup Account**.|  
    |**Account No.**|The account number to which the entry is posted. The account number displayed here depends on the type selected in the **Account Type** field. This field is available if the **Accounting Type** is **Setup Account**.|  
    |**Customer Posting Group**|The code for the customer posting group to which the entry is posted. This field is available if the **Accounting Type** is **Payment Line Account**, **Associated G/L Account**, or **Header Payment Account**.|  
    |**Vendor Posting Group**|The code for the vendor posting group to which the entry is posted. This field is available if the **Accounting Type** is **Payment Line Account**, **Associated G/L Account**, or **Header Payment Account**.|  
    |**Root**|The root for the general ledger accounts group. This is used if the **Accounting Type** is **G/L Account / Month** or **G/L Account / Week**.|  
    |**Memorize Entry**|Select to indicate that the ledger entries created in this step will be retained and applied to newly posted entries. If you select this check box, the **Detail Level** field is not available.|  
    |**Application**|The method for applying the entries. If you have cleared the **Memorize Entry** check box, and have set this field to **None**, the **Detail Level** field is available.|  
    |**Detail Level**|The method for posting the payment lines.|  
    |**Document Type**|The type of document assigned to the ledger entry.|  
    |**Document No.**|The method for assigning the document number to the ledger entry.|  

4.  Choose the **OK** button.  

## See Also  
 [Payment Management](payment-management.md)   
 [Set Up Payment Classes](how-to-set-up-payment-classes.md)   
 [Set Up Payment Addresses](how-to-set-up-payment-addresses.md)   
 [Create Payment Slips](how-to-create-payment-slips.md)   
 [Post Payment Slips](how-to-post-payment-slips.md)   
 [Archive Payment Slips](how-to-archive-payment-slips.md)   
 [Export or Import Payment Management Setup Parameters](how-to-export-or-import-payment-management-setup-parameters.md)
