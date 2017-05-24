---
title: "How to: Activate SEPA Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "vendor payments, SEPA"
  - "SEPA, activating payments"
ms.assetid: 12af0fae-694d-43ff-890b-096dd24024b2
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "fr-be"
  - "nl-be"
---
# How to: Activate SEPA Payments
To submit vendor payments electronically in Single Euro Payments Area \(SEPA\) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.  
  
 In the following procedures describe how to enable SEPA payment and set up vendor bank accounts.  
  
### To enable countries\/regions for SEPA  
  
1.  In the **Search** box, enter **\($ N\_10 Countries\/Regions $\)**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
3.  Select the **\($ T\_9\_2000005 SEPA Allowed $\)** check box for each country or region that you want to enable for SEPA.  
  
4.  Choose the **OK** button.  
  
### To enable bank accounts for SEPA  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank account that you want to enable for SEPA, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, in the **\($ T\_270\_35 Country\/Region Code $\)** field, select the appropriate code.  
  
    > [!NOTE]  
    >  The specified country\/region code must be enabled for SEPA as described in the previous procedure.  
  
4.  Enter a value in the **\($ T\_270\_20 Min. Balance $\)** field.  
  
5.  On the **Transfer** FastTab, in the **\($ T\_270\_111 SWIFT Code $\)** field, enter a code.  
  
6.  Choose the **OK** button.  
  
### To set up vendor bank accounts for SEPA  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  Select the relevant vendor, and then, on the **Navigate** tab, in the **Vendor** group, choose **Bank Accounts**.  
  
3.  Select the vendor bank account to set up for SEPA, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
4.  On the **Transfer** FastTab, in the **\($ T\_288\_24 IBAN $\)** and **\($ T\_288\_25 SWIFT Code $\)** fields, enter the international bank identifier code of the bank where the vendor has the account.  
  
5.  Choose the **OK** button.  
  
## See Also  
 [SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/sepa-payments.md)   
 [How to: File SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-file-sepa-payments.md)   
 [How to: File Non\-Euro SEPA Payments](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-file-non-euro-sepa-payments.md)   
 [How to: Set Up Export Protocols](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Belgium/how-to-set-up-export-protocols.md)