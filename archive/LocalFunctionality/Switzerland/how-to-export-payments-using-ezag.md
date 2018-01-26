---
    title: How to Export Payments Using EZAG
    description: You can generate a file for electronic payment using the Elektronischer Zahlungsauftrag (EZAG) method, and export it for the bank to use for the payments.

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
# Export Payments Using EZAG
You can generate a file for electronic payment using the Elektronischer Zahlungsauftrag (EZAG) method, and export it for the bank to use for the payments.  

## To export payments using EZAG  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.  
2.  In the **Batch Name** field, select the journal batch name.  
3.  Choose the **Generate EZAG File** action.  
4.  In the **EZAG File** batch job, on the **Options** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**Debit to bank**|Specify the code of the bank to be charged.|  
    |**Combined payment for vendor**|Specify if the payment lines that have the same vendor, currency, bank, and debit bank in the generated EZAG file will be combined.|  
    |**Shipment with disk**|Specify if the EZAG file will be saved to a disk so that you can deliver it to the bank.|  

5.  Choose the **OK** button. The EZAG file is generated.  

## See Also  
 [Swiss Electronic Payments Using DTA](swiss-electronic-payments-using-dta.md)   
 [Suggest DTA Payment for Vendors](how-to-suggest-dta-payment-for-vendors.md)   
 [Verify a List of Vendors for DTA Payments](how-to-verify-a-list-of-vendors-for-dta-payments.md)   
 [Submit DTA Payments](how-to-submit-dta-payments.md) 
