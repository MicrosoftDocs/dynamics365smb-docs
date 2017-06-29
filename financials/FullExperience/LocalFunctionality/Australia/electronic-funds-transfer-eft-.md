---
title: "Electronic Funds Transfer (EFT)"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "electronic funds transfer (EFT)"
  - "vendor payments, EFT"
ms.assetid: 12913d1f-3a59-4c71-90f5-5683f51a0e1d
caps.latest.revision: 10
ms.author: "edupont"
manager: "terryaus"
---
# Electronic Funds Transfer (EFT)
You can pay vendors using the electronic funds transfer \(EFT\) system in Australia.  
  
## Setting up Electronic Funds Transfer in ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]-->  
 ADD INCLUDE<!--[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]--> can export EFT files that you can then upload to your bank’s website for additional processing. To submit EFT files, you must set up the following information:  
  
-   You must add EFT information to the bank account or bank accounts that you will use to pay vendors electronically. The EFT\-specific fields are on the **Transfer** FastTab in the Bank Account Card window.  
  
-   For those vendors that you want to pay electronically, you must select the EFT Payment field and specify the vendor bank account in the EFT Vendor Bank Account Code field in the Vendor Card window.  
  
 When you have set up bank accounts and vendors, you can create EFT file that are based on entries in the payment journal. For more information, see Create EFT File. When you create an EFT file, an entry is made in the **EFT Register** table. In the EFT Register window, you can drill down to see the vendor ledger entries for the EFT file. In the Payment Journal window, you can also import existing EFT register entries to the payment journal by using the **Transfer EFT Register** batch job.  
  
## See Also  
 EFT Register   
 Create EFT File   
 Transfer EFT Register   
 Bank Account Card   
 Vendor Card   
 Payment Journal