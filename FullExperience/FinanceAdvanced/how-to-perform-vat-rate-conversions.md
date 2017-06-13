---
title: "How to: Perform VAT Rate Conversions"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "VAT rate, performing"
ms.assetid: aee6107d-95cf-4003-8caa-79dd52c04aad
caps.latest.revision: 13
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Perform VAT Rate Conversions
You use the VAT rate change tool to manage changes in the standard rate of VAT. You perform VAT and general posting group conversions to change VAT rates and maintain accurate VAT reporting.  
  
 Depending on your setup, the following changes are made:  
  
-   VAT and general posting groups are converted.  
  
-   Changes are implemented in general ledger accounts, customers, vendors, open documents, journal lines, etc..  
  
> [!IMPORTANT]  
>  Before you perform VAT rate change conversion, you can perform a test conversion to make sure that the VAT rate change procedure is correctly executed.  
  
### To perform VAT rate change test conversion  
  
1.  In the **Search** box, enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.  
  
2.  Verify that you have already set up the VAT product posting group conversion or the general product posting group conversion.  
  
    > [!IMPORTANT]  
    >  Clear the **Perform Conversion** check box.  
  
    > [!IMPORTANT]  
    >  Clear the **VAT Rate Change Tool Completed** check box. The check box is automatically selected when the real VAT rate change conversion is completed.  
  
3.  On the **Home** tab, in the **Process** group, choose **Convert**.  
  
4.  After the conversion is complete, on the **Home** tab, in the **Process** group, choose **VAT Rate Change Log Entries** to view the results of the test conversion.  
  
    > [!IMPORTANT]  
    >  During test conversion, the **Converted** field in the **VAT Rate Change Log Entry** table is cleared and the **Converted Date** field in the **VAT Rate Change Log Entry** table is blank.  
  
5.  Verify each entry before you perform the conversion. In particular, verify transactions which use an old VAT rate.  
  
### To perform VAT rate change conversion  
  
1.  In the **Search** box, enter **VAT Rate Change**, and then choose the **VAT Rate Change Setup** link.  
  
2.  Verify that you have already set up the VAT product posting group conversion or general product posting group conversion.  
  
3.  Select the **Perform Conversion** check box.  
  
    > [!IMPORTANT]  
    >  Clear the **VAT Rate Change Tool Completed** check box. The check box is automatically selected when the VAT rate change conversion is completed.  
  
4.  On the **Home** tab, in the **Process** group, choose **Convert**.  
  
5.  After the conversion is complete, on the **Home** tab, in the **Process** group, choose **VAT Rate Change Log Entries** to view the results of the conversion.  
  
    > [!IMPORTANT]  
    >  After the conversion is completed, the **Converted** field in the **VAT Rate Change Log Entry** table is selected and the **Converted Date** field in the **VAT Rate Change Log Entry** table is filled in with the conversion date.  
  
6.  Review each entry. In particular, review transactions which use an old VAT rate.  
  
## See Also  
 [Understanding the VAT Rate Conversion Process](../Finance/understanding-the-vat-rate-conversion-process.md)   
 [How to: Prepare VAT Rate Change Conversions](../Finance/how-to-prepare-vat-rate-change-conversions.md)   
 [How to: Set Up VAT Rate Change Tool](../Finance/how-to-set-up-vat-rate-change-tool.md)   
 [VAT Rate Change Log Entry](assetId:///f49ed6ed-116d-4a72-87a1-2803e3a6b6d0)   
 [Perform Conversion](assetId:///56986e46-63e8-45af-9e14-02f8cb864373)   
 [VAT Rate Change Setup](assetId:///0c69c648-d2b2-493a-9406-435f549ecd72)