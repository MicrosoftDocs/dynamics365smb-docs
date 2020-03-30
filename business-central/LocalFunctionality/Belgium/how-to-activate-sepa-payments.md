---
    title: How to Activate SEPA Payments
    description: To submit vendor payments electronically in Single Euro Payments Area (SEPA) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.

    services: project-madeira 
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

The following procedures describe how to enable SEPA payment and set up vendor bank accounts.  

## To enable countries/regions for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Countries/Regions**, and then choose the related link.  
2.  Choose the **Edit List** action.  
3.  Select the **SEPA Allowed** check box for each country or region that you want to enable for SEPA.  
4.  Choose the **OK** button.  

## To enable bank accounts for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bank Accounts**, and then choose the related link.  
2.  Select the bank account that you want to enable for SEPA, and then choose the **Edit** action.  
3.  In the **Country/Region Code** field, select the appropriate code.  

    > [!NOTE]  
    >  The specified country/region code must be enabled for SEPA as described in the previous procedure.  

4.  Enter a value in the **Min. Balance** field.  
5.  In the **SWIFT Code** field, enter a code.  
6.  Choose the **OK** button.  

## To set up vendor bank accounts for SEPA  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendors**, and then choose the related link.  
2.  Select the relevant vendor, and then choose the **Bank Accounts** action.  
3.  Select the vendor bank account to set up for SEPA, and then choose the **Edit** action.  
4.  In the **IBAN** and **SWIFT Code** fields, enter the international bank identifier code of the bank where the vendor has the account.  
5.  Choose the **OK** button.  

## See Also  
 [SEPA Payments](sepa-payments.md)   
 [File SEPA Payments](how-to-file-sepa-payments.md)   
 [File Non-Euro SEPA Payments](how-to-file-non-euro-sepa-payments.md)   
 [Set Up Export Protocols](how-to-set-up-export-protocols.md)
