---
    title: Electronic Funds Transfer (EFT)
    description: You can pay vendors using the electronic funds transfer (EFT) system in Australia.
    services: project-madeira 
    documentationcenter: ''
    author: bholtorf
    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 05/29/2018
    ms.author: bholtorf

---
# Electronic Funds Transfer (EFT)
You can pay vendors using the electronic funds transfer (EFT) system in Australia.  

## Setting up Electronic Funds Transfer in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] can export EFT files that you can then upload to your bank’s website for additional processing. To submit EFT files, you must set up the following information:  

* You must add EFT information to the bank account or bank accounts that you will use to pay vendors electronically. The EFT-specific fields are on the **Transfer** FastTab on the **Bank Account** page.  
* For those vendors that you want to pay electronically, you must select the **EFT Payment** check box and specify the vendor bank account in the **EFT Vendor Bank Account Code** field on the **Vendor** page.  

When you have set up bank accounts and vendors, you can create EFT file that are based on entries in the payment journal. When you create an EFT file, an entry is made in the **EFT Register** table. On the EFT Register page you can drill down to see the vendor ledger entries for the EFT file. On the Payment Journal page, you can also import existing EFT register entries to the payment journal by using the **Transfer EFT Register** batch job.

> [!NOTE]  
> Electronic Funds Transfer (EFT) uses posted and not yet posted payments as base for withholding tax amounts calculation and applied inovoices as reference for withholding tax amounts calculation. Payments that are not applied to any invoice can be exported to EFT file only when they have Skip WHT flag set to Yes. Otherwise they cannot be exported to EFT file. During export of EFT file, Payment Journal lines are no longer deleted and cannot be deleted as long as they have reference to **EFT Register**. To remove the link between **EFT Register** and Payment Journal lines, click **Cancel Export** action either in **EFT Register** page or on Payment Journal page.       

## See Also  
[Export Payments to a Bank File](../../payables-how-export-payments-bank-file.md)  
[Australia Local Functionality](australia-local-functionality.md)
