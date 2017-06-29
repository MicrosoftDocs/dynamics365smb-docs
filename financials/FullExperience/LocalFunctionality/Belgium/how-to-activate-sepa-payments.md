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
# How to: Activate SEPA Payments
To submit vendor payments electronically in Single Euro Payments Area \(SEPA\) ISO 20022 payment format, you must set up prerequisites for enabling SEPA payments.  
  
 In the following procedures describe how to enable SEPA payment and set up vendor bank accounts.  
  
### To enable countries\/regions for SEPA  
  
1.  In the **Search** box, enter **Countries\/Regions**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
3.  Select the **SEPA Allowed** check box for each country or region that you want to enable for SEPA.  
  
4.  Choose the **OK** button.  
  
### To enable bank accounts for SEPA  
  
1.  In the **Search** box, enter **Bank Accounts**, and then choose the related link.  
  
2.  Select the bank account that you want to enable for SEPA, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
3.  On the **General** FastTab, in the **Country\/Region Code** field, select the appropriate code.  
  
    > [!NOTE]  
    >  The specified country\/region code must be enabled for SEPA as described in the previous procedure.  
  
4.  Enter a value in the **Min. Balance** field.  
  
5.  On the **Transfer** FastTab, in the **SWIFT Code** field, enter a code.  
  
6.  Choose the **OK** button.  
  
### To set up vendor bank accounts for SEPA  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  Select the relevant vendor, and then, on the **Navigate** tab, in the **Vendor** group, choose **Bank Accounts**.  
  
3.  Select the vendor bank account to set up for SEPA, and then, on the **Home** tab, in the **Manage** group, choose **Edit**.  
  
4.  On the **Transfer** FastTab, in the **IBAN** and **SWIFT Code** fields, enter the international bank identifier code of the bank where the vendor has the account.  
  
5.  Choose the **OK** button.  
  
## See Also  
 [SEPA Payments](../FullExperience/sepa-payments.md)   
 [How to: File SEPA Payments](../FullExperience/how-to-file-sepa-payments.md)   
 [How to: File Non-Euro SEPA Payments](../FullExperience/how-to-file-non-euro-sepa-payments.md)   
 [How to: Set Up Export Protocols](../FullExperience/how-to-set-up-export-protocols.md)