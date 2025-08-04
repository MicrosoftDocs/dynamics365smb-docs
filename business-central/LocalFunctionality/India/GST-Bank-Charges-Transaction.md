---
title: GST on Bank Charges Transaction
description: GST on Bank Charges Transaction

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# GST on Bank Charges Transaction


As per Rule 54(2) of CGST Rules, 2017, Banks shall issue a tax invoice or any other document in lieu of tax invoice. In case if an invoice is not provided by the bank, then the bank statement shall be deemed to be an invoice. Such document shall be construed as Tax invoice even if it is not serially numbered and whether or not it contains the address of recipient of taxable service.

Process for GST calculation on bank charges has been explained in this document.

### GST calculation on bank charges

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Payment Voucher**, and then choose the related link.
2. Select **G/L Account** in **Account Type** field and select relevant general ledger account in **Account No.** field.
3. Select **Bank Account** in **Bal. Account Type** field and select relevant bank account in **Bal. Account No.** field.
4. **GST Registration No.** and **GST Registration Status** fields should not be blank on **Bank Account**.
5. **Location Code** should not be blank on **Bank Payment Voucher**.
6. **Bank Charge** field should be marked true, select **Process** on the ribbon and click on **Bank Charges** -> select **Bank Charge** code and system will calculate the GST on bank charge amount. **GST Credit**, **GST Group Code** and **HSN/SAC Code** should not be blank on **Bank Charge** Code.

### GST on bank charges

Intra-State Bank Payment with GST on Bank Charges where Input Tax Credit is available, for example bank charge of INR 10000 to be paid to bank and GST (9% CGST and 9% SGST) has to be calculated on bank charges amount.
    
  - GST calculation will appear in the Fact Box, as following:

       |Component|Amount|
       |----------------------------------|---------------------------------------|  
       |**Bank Charge Amount**|10,000|  
       |**CGST**|900|  
       |**SGST**|900|
    

  - Once posted the bank payment GL entries for Intra-state bank charges with GST where Input Tax Credit is available, will be as following:
    
     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Bank Charges**|10000|  
     |**CGST Receivable Account**|900|
     |**SGST/UTGST Receivable Account**|900|
     |**Bank Account**|-11800|

Inter-State Bank Payment with GST on Bank Charges where Input Tax Credit is available, for example bank charge of INR 10000 to be paid to bank and 18% IGST has to be calculated on bank charges amount.
    
  - GST calculation will appear in the Fact Box, as following:

      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Bank Charge Amount**|10,000|  
      |**IGST**|1800|  
       

  - Once posted the bank payment GL entries for Inter-state bank charges with GST where Input Tax Credit is available, will be as following:

      |Particulars|Amount|
      |----------------------------------|----------------------------------|  
      |**Bank Charges**|10000|  
      |**IGST Receivable Account**|1800|
      |**Bank Account**|-11800| 

Intra-State Bank Payment with GST on Bank Charges where Input Tax Credit is not available, for example bank charge of INR 10000 to be paid to bank and GST (9% CGST and 9% SGST) has to be calculated on bank charges amount.

  - GST calculation will appear in the Fact Box, as following:

      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Bank Charge Amount**|10,000|  
      |**CGST**|900|  
      |**SGST**|900|
    

  - Once posted the bank payment GL entries for Intra-state bank charges with GST where Input Tax Credit is not available, will be as following:
    
      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Bank Charges**|11800|  
      |**Bank Account**|-11800|

Inter-State Bank Payment with GST on Bank Charges where Input Tax Credit is not available, for example bank charge of INR 10000 to be paid to bank and 18% IGST has to be calculated on bank charges amount.
    
  - GST calculation will appear in the Fact Box, as following:

      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Bank Charge Amount**|10,000|  
      |**IGST**|1800|  
       

  - Once posted the bank payment GL entries for Inter-state bank charges with GST where Input Tax Credit is not available, will be as following:
    
      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Bank Charges**|11800|  
      |**Bank Account**|-11800| 


## Deemed value calculation for GST base amount in foreign exchange transactions

As per GST law, A person supplying the services of exchange of foreign currency may exercise option to ascertain value in terms of Rule 32(2)b for a financial Year. In service related to supply of foreign currency, including money changing, the problem of valuation always arises, therefore the Rule states that, consideration should be taken to the difference in the buying rate or the selling rate.

### GST calculation on bank charges for bank payment

   1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Bank Receipt Voucher**, and then choose the related link.
   2. Select **G/L Account** in Account Type field and select relevant **Vendor** or **Customer** account in Account No. field.
   3. Select **Bank Account** in Bal. Account Type field and select relevant bank account in Bal. Account No. field.
   4. **GST Registration No.** and **GST Registration Status** fields should not be blank on Bank Account.
   5. Select Process on the ribbon and click on Bank Charges -> select Bank Charge code and system will calculate the GST on bank charge amount. **External Document No.** and **GST Document Type** fields should not be blank on **Journal Bank Charges** line.
   6. GST Credit, GST Group Code and HSN/SAC Code should not be blank on Bank Charge Code.

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
    |**GST Transactional Value**|INR 6500|
    |**GST Amount**|INR 1170|

- Once posted the bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Refund for Bank Charges and GST is posted with Credit Availment and GST Document Type Invoice, will be as following:
    
    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Refund**|**Vendor**|-65000|  
    |**Refund**|**SGST/UTGST Receivable Account**|585|
    |**Refund**|**CGST Receivable Account**|585|
    |**Refund**|**Bank Account**|63830|

- The bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Payment for Bank Charges and GST is posted with Credit Availment and GST Document Type as Invoice, will be as following:
    
    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Payment**|**Customer**|-65000|  
    |**Payment**|**SGST/UTGST Receivable Account**|585|
    |**Payment**|**CGST Receivable Account**|585|
    |**Payment**|**Bank Account**|63830|

- The bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Refund for Bank Charges and GST is posted with Credit Non-Availment and GST Document Type as Invoice, will be as following:
    
    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Refund**|**Vendor**|-65000|  
    |**Refund**|**Other Charges**|1170|
    |**Refund**|**Bank Account**|63830|

- The bank payment GL entries for Intrastate Bank Receipt Voucher with Document Type as Payment for Bank Charges and GST is posted with Credit Non-Availment and GST Document Type as Invoice, will be as following:
    
    |Document Type|Particulars|Amount|
    |------|----------------------------------|---------------------------------------|  
    |**Payment**|**Customer**|-65000|  
    |**Payment**|**Other Charges**|1170|
    |**Payment**|**Bank Account**|63830|




## Related information 
[GST Bank Charges Overview](GST-Bank-Charges-Overview.md)
































[!INCLUDE[footer-include](../../includes/footer-banner.md)]
