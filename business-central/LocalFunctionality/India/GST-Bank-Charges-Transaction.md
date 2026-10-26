---
title: GST on Bank Charges Transaction
description: Learn how GST is applied to bank charges transactions in India, including calculation methods, accounting entries, and compliance requirements for Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, GST on bank charges transaction
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# GST on bank charges transaction

As per Rule 54(2) of CGST Rules, 2017, Banks shall issue a tax invoice or any other document in lieu of tax invoice. In case if an invoice isn't provided by the bank, then the bank statement shall be deemed to be an invoice. Such document shall be construed as Tax invoice even if it isn't serially numbered and whether or not it contains the address of recipient of taxable service.

Process for GST calculation on bank charges has been explained in this document.

> [!NOTE]
> The statutory background describes the original scenario. The rates and amounts below are examples, not current tax guidance.

## Calculate GST on bank charges

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Bank Payment Voucher**, and then choose the related link.
1. Select **G/L Account** in **Account Type** field and select relevant general ledger account in **Account No.** field.
1. Select **Bank Account** in **Bal. Account Type** field and select relevant bank account in **Bal. Account No.** field.
1. **GST Registration No.** and **GST Registration Status** fields shouldn't be blank on **Bank Account**.
1. **Location Code** shouldn't be blank on **Bank Payment Voucher**.
1. Select **Bank Charge** on the voucher line. The selected G/L account must match the **Account** on the bank charge setup.
1. Choose **Bank Charges** and select the relevant **Bank Charge** code. Check **GST Credit**, **GST Group Code**, and **HSN/SAC Code** on the charge line.
1. Enter **GST Document Type** and **External Document No.**, and review the tax calculation before posting.

## Bank charge posting examples

Intra-State Bank Payment with GST on Bank Charges where Input Tax Credit is available, for example bank charge of INR 10000 to be paid to bank and GST (9% CGST and 9% SGST) has to be calculated on bank charges amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charge Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

- Once posted the bank payment GL entries for Intra-state bank charges with GST where Input Tax Credit is available will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charges**|10000|  
    |**CGST Receivable Account**|900|
    |**SGST/UTGST Receivable Account**|900|
    |**Bank Account**|-11800|

Inter-State Bank Payment with GST on Bank Charges where Input Tax Credit is available, for example bank charge of INR 10000 to be paid to bank and 18% IGST has to be calculated on bank charges amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charge Amount**|10,000|  
    |**IGST**|1800|  

- Once posted the bank payment GL entries for Inter-state bank charges with GST where Input Tax Credit is available will be as following:

    |Particulars|Amount|
    |----------------------------------|----------------------------------|  
    |**Bank Charges**|10000|  
    |**IGST Receivable Account**|1800|
    |**Bank Account**|-11800|

Intra-State Bank Payment with GST on Bank Charges where Input Tax Credit isn't available, for example bank charge of INR 10000 to be paid to bank and GST (9% CGST and 9% SGST) has to be calculated on bank charges amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charge Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|

- Once posted the bank payment GL entries for Intra-state bank charges with GST where Input Tax Credit isn't available will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charges**|11800|  
    |**Bank Account**|-11800|

Inter-State Bank Payment with GST on Bank Charges where Input Tax Credit isn't available, for example bank charge of INR 10000 to be paid to bank and 18% IGST has to be calculated on bank charges amount.

- GST calculation appears in the Fact Box as following:

    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charge Amount**|10,000|  
    |**IGST**|1800|

- Once posted the bank payment GL entries for Inter-state bank charges with GST where Input Tax Credit isn't available will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Charges**|11800|  
    |**Bank Account**|-11800|

## Deemed value calculation for GST base amount in foreign exchange transactions

As per GST law, A person supplying the services of exchange of foreign currency may exercise option to ascertain value in terms of Rule 32(2)b for a financial Year. In service related to supply of foreign currency, including money changing, the problem of valuation always arises, therefore the Rule states that, consideration should be taken to the difference in the buying rate or the selling rate.

### Calculate GST on foreign exchange bank charges

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Bank Receipt Voucher**, and then choose the related link.
1. Select **Vendor** or **Customer** in **Account Type**, and select the relevant account in **Account No.**.
1. Select **Bank Account** in Bal. Account Type field and select relevant bank account in Bal. Account No. field.
1. **GST Registration No.** and **GST Registration Status** fields shouldn't be blank on Bank Account.
1. Enter the **Currency Code**, amount, and **Location Code**. Leave **Bank Charge** cleared on the voucher line for a foreign exchange charge.
1. Choose **Bank Charges**, and select a **Bank Charge** code with **Foreign Exchange** selected in its setup.
1. Enter **External Document No.** and **GST Document Type** on the **Journal Bank Charges** line. Check **GST Credit**, **GST Group Code**, and **HSN/SAC Code**, and review the calculated tax.

Let us take the following example and check the GL entries of the posted transactions for different scenarios.

|Bank Charge Code|Lower limit|Upper limit|Formula |Min. Deemed Value|Max Deemed Value|Deemed %|Fixed Amount|
|---------|---------|--|--|--|--|--|--|
|BKCHG_01|0|10,00,000|Deemed %|0|0|1%|0|

- Sample values for transactions

  |Component|Amount|
  |----------------------------------|---------------------------------------|  
  |**CGST**|9%|  
  |**SGST**|9%|
  |**IGST**|18%|
  |**Document Type**|Refund or Payment|
  |**Account Type**|Vendor or Customer (Registered)|
  |**Amount**|USD -1000|
  |**Currency**|USD (Exchange Rate 65)|
  |**Amount (LCY)**|INR -65000|
  |**Bank Charge**|BKCHG_01|
  |**GST Transactional Value**|INR 650 (65,000 × 1%)|
  |**GST Amount**|INR 117 (650 × 18%)|

- Once posted the bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Refund for Bank Charges and GST is posted with Credit Availment and GST Document Type Invoice, will be as following:

    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Refund**|**Vendor**|-65000|  
    |**Refund**|**SGST/UTGST Receivable Account**|58.50|
    |**Refund**|**CGST Receivable Account**|58.50|
    |**Refund**|**Bank Account**|64883|

- The bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Payment for Bank Charges and GST is posted with Credit Availment and GST Document Type as Invoice, will be as following:

    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Payment**|**Customer**|-65000|  
    |**Payment**|**SGST/UTGST Receivable Account**|58.50|
    |**Payment**|**CGST Receivable Account**|58.50|
    |**Payment**|**Bank Account**|64883|

- The bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Refund for Bank Charges and GST is posted with Credit Non-Availment and GST Document Type as Invoice, will be as following:

    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Refund**|**Vendor**|-65000|  
    |**Refund**|**Other Charges**|117|
    |**Refund**|**Bank Account**|64883|

- The bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Payment for Bank Charges and GST is posted with Credit Non-Availment and GST Document Type as Invoice, will be as following:

    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Payment**|**Customer**|-65000|  
    |**Payment**|**Other Charges**|117|
    |**Payment**|**Bank Account**|64883|

## Related information

[GST Bank Charges Overview](GST-Bank-Charges-Overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
