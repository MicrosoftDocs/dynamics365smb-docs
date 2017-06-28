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
  
## Setting up Electronic Funds Transfer in [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)]  
 [!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] can export EFT files that you can then upload to your bank’s website for additional processing. To submit EFT files, you must set up the following information:  
  
-   You must add EFT information to the bank account or bank accounts that you will use to pay vendors electronically. The EFT\-specific fields are on the **Transfer** FastTab in the [\($ N\_370 Bank Account Card $\)](assetId:///c44f01ce-a89a-441e-a543-1a1e951edcaa) window.  
  
-   For those vendors that you want to pay electronically, you must select the [\($ T\_23\_11624 EFT Payment $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-t_23_11624-eft-payment-$-.md) field and specify the vendor bank account in the [\($ T\_23\_11625 EFT Vendor Bank Account Code $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-t_23_11625-eft-vendor-bank-account-code-$-.md) field in the [\($ N\_26 Vendor Card $\)](../Topic/\($%20N_26%20Vendor%20Card%20$\).md) window.  
  
 When you have set up bank accounts and vendors, you can create EFT file that are based on entries in the payment journal. For more information, see [\($ B\_11608 Create EFT File $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-b_11608-create-eft-file-$-.md). When you create an EFT file, an entry is made in the **\($ T\_11609 EFT Register $\)** table. In the [\($ N\_11615 EFT Register $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-n_11615-eft-register-$-.md) window, you can drill down to see the vendor ledger entries for the EFT file. In the [\($ N\_256 Payment Journal $\)](../../Finance/-$-n_256-payment-journal-$-.md) window, you can also import existing EFT register entries to the payment journal by using the **\($ B\_11607 Transfer EFT Register $\)** batch job.  
  
## See Also  
 [\($ T\_11609 EFT Register $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-t_11609-eft-register-$-.md)   
 [\($ B\_11608 Create EFT File $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-b_11608-create-eft-file-$-.md)   
 [\($ B\_11607 Transfer EFT Register $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Australia/-$-b_11607-transfer-eft-register-$-.md)   
 [\($ N\_370 Bank Account Card $\)](assetId:///c44f01ce-a89a-441e-a543-1a1e951edcaa)   
 [\($ N\_26 Vendor Card $\)](../Topic/\($%20N_26%20Vendor%20Card%20$\).md)   
 [\($ N\_256 Payment Journal $\)](../../Finance/-$-n_256-payment-journal-$-.md)