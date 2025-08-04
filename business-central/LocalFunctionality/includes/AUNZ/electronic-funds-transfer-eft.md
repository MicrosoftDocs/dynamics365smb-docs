---
author: brentholtorf
ms.topic: include
ms.date: 03/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

## Set up Electronic Funds Transfer

[!INCLUDE[prod_short](../../../includes/prod_short.md)] can export EFT files that you can then upload to your bank's website for additional processing. To submit EFT files, you must set up the following information:  

- You must add EFT information to the bank account or bank accounts that you use to pay vendors electronically. The EFT-specific fields are on the **Bank Account** page.  
- For those vendors that you want to pay electronically, you must select the **EFT Payment** checkbox and specify the vendor bank account in the **EFT Vendor Bank Account Code** field on the **Vendor** page.  

After setting up bank accounts and vendors, you can create EFT files that are based on entries in the payment journal. When you create an EFT file, an entry is made in the **EFT Register** table. On the **EFT Register** page, you can drill down to see the vendor ledger entries for the EFT file. On the **Payment Journal** page, you can also import existing EFT register entries to the payment journal by using the **Transfer EFT Register** batch job.

> [!NOTE]  
> Electronic Funds Transfer (EFT) uses posted and nonposted payments as the basis to calculate withholding tax amounts for applied invoices. Payments that aren't applied to an invoice can only be exported to an EFT file if the **Skip WHT** checkbox is selected. During export of the EFT file, the payment journal lines aren't deleted and can't be deleted as long as they have a reference to an EFT register. To remove the link between the EFT register and payment journal lines, choose the **Cancel Export** action either on the **EFT Register** page or the **Payment Journal** page.
