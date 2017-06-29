---
title: "How to: Set Up Bank Accounts for Electronic Payments"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "bank accounts, setting up for using electronic payments"
  - "electronic payments, setting up bank accounts for"
ms.assetid: a660fa1a-6a1f-46a4-9337-457261046983
caps.latest.revision: 11
ms.author: "edupont"
manager: "terryaus"
translation.priority.ht: 
  - "es-es"
---
# How to: Set Up Bank Accounts for Electronic Payments
In FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] --> -->, you can set up bank accounts to make electronic payments.  
  
### To set up bank accounts for electronic payments  
  
1.  In the **Search** box, enter **Bank Account Card**, and then choose the related link.  
  
2.  On the **Transfer** FastTab, make sure that the **CCC Bank No.**, **CCC Bank Branch No.**, **CCC Control Digits**, and **CCC Bank Account No.** fields are filled in correctly.  
  
3.  On the **Transfer** FastTab, fill in the fields as described in the following table.  
  
    |FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)] --> --> -->|FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--FIX INCLUDE HERE<!--[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)] --> --> -->|  
    |---------------------------------|---------------------------------------|  
    |**E\-Pay Export File Path**|Enter the full path of the electronic payment file, start with the drive letter and end with a backslash \(\\\). The file name is not included here. You should use the directory where [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] is installed. For example: **C:\\NAV\\** would be a possible entry for this field. You can enter a maximum of 100 characters.|  
    |**Last E\-Pay Export File Name**|Specify the name of the file with the .txt file name extension, without the path., Because the file name will be incremented every time that an electronic payment file is exported, this file name should have digits in it. This will create a permanent record of every file that you have exported to the bank. For example, **DD000000.txt** could be a possible first entry for this field. You can enter a maximum of 50 characters.|  
  
4.  On the **Posting** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Last Remittance Advice No.**|Specify a number series that differs from the check number series. This is needed so that the numbers do not conflict with each other. The remittance advice is printed on blank paper in a form that is easy to mail to the vendor.|  
  
### To set up vendor bank accounts for electronic payments  
  
1.  In the **Search** box, enter **Vendor Bank Account Card**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Use For Electronic Payments**|Specify if this vendor bank account will be used for electronic payments. For electronic payments, only one bank account can be selected for each vendor.|  
  
3.  On the **Transfer** FastTab, make sure that the **CCC Bank No.**, **CCC Bank Branch No.**, **CCC Control Digits**, and **CCC Bank Account No.** fields are filled in correctly.  
  
## See Also  
 [Electronic Payments – AEB N34.1](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Spain/electronic-payments-–-aeb-n34.1.md)