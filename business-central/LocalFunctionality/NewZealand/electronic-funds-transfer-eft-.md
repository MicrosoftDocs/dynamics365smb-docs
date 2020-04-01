---
    title: Electronic Funds Transfer (EFT)
    description: You can pay vendors using the electronic funds transfer (EFT) system in New Zealand.
    author: bholtorf
    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Electronic Funds Transfer (EFT)
You can pay vendors using the electronic funds transfer (EFT) system in New Zealand.  

## Setting up Electronic Funds Transfer in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] can export EFT files that you can then upload to your bank’s website for additional processing. To submit EFT files, you must set up the following information:  

* You must add EFT information to the bank account or bank accounts that you will use to pay vendors electronically. The EFT-specific fields are in the **Transfer** FastTab on the **Bank Account** page.  
* For those vendors that you want to pay electronically, you must select the **EFT Payment** check box and specify the vendor bank account in the **EFT Vendor Bank Account Code** field on the **Vendor** page.  

When you have set up bank accounts and vendors, you can create EFT file that are based on entries in the payment journal. When you create an EFT file, an entry is made in the **EFT Register** table. On the EFT Register page you can drill down to see the vendor ledger entries for the EFT file. On the Payment Journal page,you can also import existing EFT register entries to the payment journal by using the **Transfer EFT Register** batch job.

## See Also  
[Export Payments to a Bank File](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)  
[New Zealand Local Functionality](new-zealand-local-functionality.md)
