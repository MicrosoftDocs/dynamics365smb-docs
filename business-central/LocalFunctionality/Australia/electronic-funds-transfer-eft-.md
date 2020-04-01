---
    title: Electronic Funds Transfer (EFT)
    description: You can pay vendors using the electronic funds transfer (EFT) system in Australia.
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
You can pay vendors using the electronic funds transfer (EFT) system in Australia.  

## Setting up Electronic Funds Transfer in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]  
[!INCLUDE[d365fin](../../includes/d365fin_md.md)] can export EFT files that you can then upload to your bank’s website for additional processing. To submit EFT files, you must set up the following information:  

* You must add EFT information to the bank account or bank accounts that you will use to pay vendors electronically. The EFT-specific fields are on the **Bank Account** page.  
* For those vendors that you want to pay electronically, you must select the **EFT Payment** check box and specify the vendor bank account in the **EFT Vendor Bank Account Code** field on the **Vendor** page.  

When you have set up bank accounts and vendors, you can create EFT files that are based on entries in the payment journal. When you create an EFT file, an entry is made in the **EFT Register** table. On the **EFT Register** page, you can drill down to see the vendor ledger entries for the EFT file. On the **Payment Journal** page, you can also import existing EFT register entries to the payment journal by using the **Transfer EFT Register** batch job.

> [!NOTE]  
> Electronic Funds Transfer (EFT) uses posted and nonposted payments as the basis to calculate withholding tax amounts for applied invoices. Payments that are not applied to an invoice can only be exported to an EFT file if the **Skip WHT** check box is selected. During export of the EFT file, the payment journal lines are not deleted and cannot be deleted as long as they have a reference to an EFT register. To remove the link between the EFT register and payment journal lines, choose the **Cancel Export** action either on the **EFT Register** page or the **Payment Journal** page.       

## See Also  
[Export Payments to a Bank File](../../finance-make-payments-with-bank-data-conversion-service-or-sepa-credit-transfer.md#exporting-payments-to-a-bank-file)  
[Australia Local Functionality](australia-local-functionality.md)
