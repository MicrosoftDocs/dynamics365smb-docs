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
# Swiss Electronic Payments Using DTA
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can make electronic payments for invoices using the DatenTrägerAustausch \(DTA\) electronic payment method. Swiss banks use the DTA electronic payment method to settle payments efficiently using standardized payment records. This method is based on data carriers and data transfer. This electronic service allows you to convert payments electronically in DTA format, and then submit them to your bank for payment.  
  
> [!NOTE]  
>  Before you use the DTA electronic payment method, you must define the DTA settings for making electronic payments in the DTA setup. For more information, see the DTA Setup table.  
  
 With DTA electronic payments, you can do the following:  
  
-   Generate vendor payments by processing the automatic DTA payment. For more information, see [How to: Suggest DTA Payment for Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-suggest-dta-payment-for-vendors.md).  
  
-   Verify the list of vendors and payment information. For more information, see [How to: Verify a List of Vendors for DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-verify-a-list-of-vendors-for-dta-payments.md).  
  
-   Submit the DTA file to the bank electronically, where vendor payments are released in a few hours. For more information, see [How to: Submit DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-submit-dta-payments.md). After this has been done, the payment journal can be posted.  
  
 In the payment journal, you can have the DTA payments suggested based on posted invoices. The suggested payments contain vendor and external document number information, and can be modified. For more information, see [How to: Suggest DTA Payment for Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-suggest-dta-payment-for-vendors.md) and the DTA Payment Journal window.  
  
 When you want to pay a vendor by using DTA, you generate a DTA file, which contains data from the payment journal line and the general journal line. Optionally, the DTA file can combine several payments to the vendor. The DTA file also contains posting text.  
  
> [!NOTE]  
>  If you combine payments to the vendor, the posting text must include the document numbers of the invoices. Also, if the length of the document number is longer than 50 characters, the word "etc." will be added to the field.  
  
## See Also  
 [Swiss Electronic Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments.md)   
 [How to: Suggest DTA Payment for Vendors](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-suggest-dta-payment-for-vendors.md)   
 [How to: Verify a List of Vendors for DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-verify-a-list-of-vendors-for-dta-payments.md)   
 [How to: Submit DTA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-submit-dta-payments.md)   
 [How to: Export Payments Using EZAG](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/how-to-export-payments-using-ezag.md)   
 [Swiss Electronic Payments Using ESR](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-esr.md)   
 [Swiss Electronic Payments Using LSV\+](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Switzerland/swiss-electronic-payments-using-lsv-.md)   
 Payment Journal   
 DTA Setup