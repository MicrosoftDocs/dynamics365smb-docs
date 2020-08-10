---
    title: GST on Advance Payment received from Customer
    description: GST on Advance Payment received from Customer

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 06/24/2020
    ms.author: v-debapd

---
# GST on Advance Payment received from Customer

## GST on Advance Payment received from Customer

An advance received from a customer needs to be reported in GSTR-1 with GST Rate wise for whole period.

### Create a General Journal or a Bank or Cash Receipt Voucher

1. Choose the ![img](image/search.jpg)icon, enter **General Journal**, **Bank Payment Voucher** or **Cash Receipt Voucher**, and then choose the related link.
2. Select **Customer** in account type and select relevant **Customer Code**, GST customer type and registration number should not be blank on customer master.
3. Select **G/L Account** or **Bank Account** in balancing account type, and select the cash or bank account. For example, advance payment received from customer for INR 10000 on which 18% GST (i.e. 9% CGST and 9% SGST/UTGST) has to be charged.
4. GST on Advance Payment field needs to be activated in General Journal Line for computation of GST on Advance Payment. In addition, GST Group code and GST Place of Supply are to be entered for computation of GST.
1. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**Advance Payment**|10,000|
    |**GST Transitional Value**|8,474 (10000*100/118)|
    |**CGST**|763 (8,475*9%)|  
    |**SGST/UTGST**|763 (8,475*9%)|

6. GL Entries for advance payment received from customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000|  
    |**CGST Payable (Interim) Account**|763|  
    |**SGST/UTGST Payable (Interim) Account**|763| 
    |**CGST Payable Account**|-763| 
    |**SGST/UTGST Payable Account**|-763| 
    |**Customer Account**|-10000| 

## Reversal of Advance Payment received from Customer

If the customer advance needs to be corrected or the entry is wrongly posted, in such a case the entry can be reversed and new entry can be created.

1. Reversal GL Entries for advance payment received from customer, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10000| 
    |**CGST Payable Account**|763| 
    |**SGST/UTGST Payable Account**|763| 
    |**CGST Payable (Interim) Account**|-763|  
    |**SGST/UTGST Payable (Interim) Account**|-763| 
    |**Bank Account**|-10,000|  
    
> [!TIP]
> In case of Inter-State Advance Payment, IGST will be calculated.







































