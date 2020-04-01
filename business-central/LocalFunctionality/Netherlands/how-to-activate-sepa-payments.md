---
    title: How to Activate SEPA Payments
    description: To submit vendor payments electronically in Single Euro Payments Area (SEPA) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.

    documentationcenter: ''
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
# Activate SEPA Payments
To submit vendor payments electronically in Single Euro Payments Area (SEPA) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.  

In the following procedures, the first four describe how to enable SEPA payments, and the remaining two relate to the individual vendors.  

## To enable countries/regions for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Countries/Regions**, and then choose the related link.  
2.  Choose the **Edit List** action.  
3.  Select the **SEPA Allowed** check box for each country or region that you want to enable for SEPA.  
4.  Choose the **OK** button.  

## To enable bank accounts for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.  
2.  Select the bank account that you want to enable for SEPA, and then choose the **Edit** action.  
3.  On the **General** FastTab, in the **Country/Region Code** field, select the appropriate code.  

    > [!NOTE]  
    >  The specified country/region code must be enabled for SEPA as described in the previous procedure.  

4.  Enter a value in the **Min. Balance** field.  
5.  On the **Transfer** FastTab, in the **SWIFT Code** field, enter a code.  
6.  Choose the **OK** button.  

## To set up a SEPA ISO 20022 export protocol  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Export Protocols**, and then choose the related link.  
2.  On the **Export Protocols** page, choose the **New** action.  
3.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Code**|Sets the export protocol code, such as **SEPA ISO20022**.|  
    |**Description**|Provides the description for the export protocol.|  
    |**Check ID**|Sets the ID for the codeunit to check payment, such as **11000010**.|  
    |**Check Name**|Sets the name of the codeunit.|  
    |**Export Protocol Type**|Specifies the type of the export protocol:<br /><br /> -   **Report**<br />-   **XMLPort**|  
    |**Export ID**|Sets the ID for the batch job to export payment, such as **11000011**.<br /><br /> If you select XMLPort as your export protocol type, then choose an ID such as **1000**.|  
    |**Export Name**|The name of the batch job.|  
    |**Docket ID**|Sets the ID for the batch job to inform the contact on combined payments, such as **11000004**.<br /><br /> This does not apply to XMLPort protocol types.|  
    |**Docket Name**|The name of the docket report.|  
    |**Default File Names**|Sets the location to export payment and collection data.|  

4.  Choose the **OK** button.  

## To enable transaction modes for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transaction Modes**, and then choose the related link.  
2.  Select the transaction mode that you want to enable for SEPA, and then choose the **Edit** action.  
3.  On the **Transaction Mode Card** page, on the **Paym. Proposal** FastTab, in the **Export Protocol** field, select the SEPA export protocol that you have created, such as **SEPA ISO20022**.  
4.  Choose the **OK** button.  

## To verify vendor payment transaction modes for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendors**, and then choose the related link.  
2.  Select the vendor that you want to verify the transaction mode for, and then choose the **View** action.  
3.  On the **Payments** FastTab, in the **Transaction Mode Code** field, verify that the vendor payment transaction mode is one that has been enabled for SEPA.  
4.  Choose the **OK** button.  

## To set up vendor bank accounts for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendors**, and then choose the related link.  
2.  Select the relevant vendor, and then choose the **Bank Accounts** action.  
3.  Select the vendor bank account to set up for SEPA, and then choose the **Edit** action.  
4.  On the **Transfer** FastTab, in the **IBAN** and **SWIFT Code** fields, enter the international bank identifier code of the bank where the vendor has the account.  
5.  Choose the **OK** button.  

## See Also  
 [Single EURO Payments Area (SEPA)](single-euro-payments-area-sepa-.md)   
 [Submit Vendor Payments Electronically in SEPA ISO 20022 Payment Format](how-to-submit-vendor-payments-electronically-in-sepa-iso-20022-payment-format.md) 
