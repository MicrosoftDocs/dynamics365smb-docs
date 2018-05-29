---
    title: Electronic Funds Transfer (EFT)
    description: You can pay vendors using the electronic funds transfer (EFT) system in Australia.

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
# Electronic Funds Transfer (EFT)
You can pay vendors using the electronic funds transfer (EFT) system in Australia.  

## Setting up Electronic Funds Transfer in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
 [!INCLUDE[d365fin](../../includes/d365fin_md.md)] can export EFT files that you can then upload to your bank’s website for additional processing. To submit EFT files, you must set up the following information:  

-   You must add EFT information to the bank account or bank accounts that you will use to pay vendors electronically. The EFT-specific fields are on the **Transfer** FastTab in the Bank Account Card window.  

-   For those vendors that you want to pay electronically, you must select the EFT Payment field and specify the vendor bank account in the EFT Vendor Bank Account Code field in the Vendor Card window.  

 When you have set up bank accounts and vendors, you can create EFT file that are based on entries in the payment journal. For more information, see Create EFT File. When you create an EFT file, an entry is made in the **EFT Register** table. In the EFT Register window, you can drill down to see the vendor ledger entries for the EFT file. In the Payment Journal window, you can also import existing EFT register entries to the payment journal by using the **Transfer EFT Register** batch job.

## See Also  
[Export Payments to a Bank File](../../payables-how-export-payments-bank-file.md)
[Australia Local Functionality](australia-local-functionality.md)
