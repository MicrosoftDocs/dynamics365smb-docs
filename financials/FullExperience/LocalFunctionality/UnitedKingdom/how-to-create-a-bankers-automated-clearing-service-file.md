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
# How to: Create a Bankers&#39; Automated Clearing Service File
In FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] -->, you can use Bankers' Automated Clearing Service \(BACS\) to process financial transactions electronically. To use BACS as the default vendor payment method, you must set export vendor payments to a BACS file using the **Export BACS** option. The resulting file can then be read by third\-party applications to allow electronic bank payments.  
  
 You can keep track of BACS events, such as exporting and voiding, with the **BACS Ledger Entry** table. You can keep track of BACS transmissions using the **BACS Register** table.  
  
 To create a BACS file, you must follow this sequence of activities:  
  
-   Set up vendor payment information in the **Vendor**  card window.  
  
-   Create the vendor payment using BACS.  
  
-   Export the BACS payment file.  
  
### To set up vendor payment information in the vendor card  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  Select the relevant vendor. On the **Home** tab, choose **Edit**.  
  
3.  On the **Payments** FastTab, in the **BACS Account No.** field, select the BACS account for the vendor.  
  
4.  Choose the **OK** button.  
  
### To create the vendor payment using BACS  
  
1.  In the **Search** box, enter **Vendors**, and then choose the related link.  
  
2.  In the **Vendors** window, select the relevant vendor for whom BACS payment was set up in the **Vendor** card window.  
  
3.  To open the **Payment Journal** window, on the **Home** tab, in the **Process** group, choose **Payment Journal**.  
  
4.  Fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] -->|FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] -->|  
    |---------------------------------|---------------------------------------|  
    |**Document No.**|Specifies the document number for the journal line.|  
    |**Account Type**|Select the account type as **Vendor**.|  
    |**Account No.**|Specifies the code of the vendor that you selected in the **Vendor Card** window.|  
    |**Bank Payment Type**|Specifies that the payment type to be used for the entry on the payment journal line is **BACS**.|  
    |**BACS Account No.**|Specifies the BACS account number that you have set on the vendor card.|  
    |**Amount**|Specifies the total amount including VAT.|  
  
5.  Choose the **OK** button.  
  
## See Also  
 [How to: Export BACS Files](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/how-to-export-bacs-files.md)   
 BACS Ledger Entry   
 BACS Register   
 Payment Journal   
 [United Kingdom Local Functionality](../../LocalFunctionalityForMicrosoftDynamicsNav2016/UnitedKingdom/united-kingdom-local-functionality.md)