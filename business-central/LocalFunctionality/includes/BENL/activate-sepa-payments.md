---
author: edupont04

ms.service: dynamics365-business-central
ms.topic: include
ms.date: 08/26/2020
ms.author: edupont
---
To submit vendor payments electronically in Single Euro Payments Area (SEPA) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments in your company.  

The following procedures describe how to set up SEPA payments, including how to modify the setup for specific vendors.  

## To enable countries/regions for SEPA  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Countries/Regions**, and then choose the related link.  
2. Choose the **Edit List** action.  
3. Select the **SEPA Allowed** check box for each country or region that you want to enable for SEPA.  
4. Choose the **OK** button.  

## To enable bank accounts for SEPA  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bank Accounts**, and then choose the related link.  
2. Select the bank account that you want to enable for SEPA, and then choose the **Edit** action.  
3. On the **General** FastTab, in the **Country/Region Code** field, select the appropriate code.  

    > [!NOTE]  
    > The specified country/region code must be enabled for SEPA as described in the previous procedure.  

4. Enter a value in the **Min. Balance** field.  
5. On the **Transfer** FastTab, in the **SWIFT Code** field, enter a code.  
6. Choose the **OK** button.  

## To set up a SEPA ISO 20022 export protocol  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export Protocols**, and then choose the related link.  
2. On the **Export Protocols** page, choose the **New** action.  
3. Fill in the fields as described in the following table. [!INCLUDE [tooltip-inline-tip_md](../../../includes/tooltip-inline-tip_md.md)]
4. Choose the **OK** button.  

## To set up vendor bank accounts for SEPA  

1. Choose the ![Lightbulb that opens the Tell Me feature](../../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.  
2. Select the relevant vendor, and then choose the **Bank Accounts** action.  
3. Select the vendor bank account to set up for SEPA, and then choose the **Edit** action.  
4. On the **Transfer** FastTab, in the **IBAN** and **SWIFT Code** fields, enter the international bank identifier code of the bank where the vendor has the account.  
5. Choose the **OK** button.  
