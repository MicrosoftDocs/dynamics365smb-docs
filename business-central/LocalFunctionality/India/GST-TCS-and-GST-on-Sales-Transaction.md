---
title: Calculation of TCS as per the Income Tax Act, 1961 and GST on Sales Transactions
description: Calculation of TCS as per the Income Tax Act, 1961 and GST on Sales Transactions

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Calculation of TCS as per the Income Tax Act, 1961 and GST on Sales Transactions


The Government has placed the responsibility on the e-commerce operators to collect the ‘tax’ at a specified rate from the supplier. This shall be done by the Operator by paying the supplier the price of the product or services, less the tax, calculated at the specified rate.

The process of calculation of TCS and GST has been explained in this document.

## Create a sales invoice

1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoice**, and then choose the related link.

2. Select **Customer** on **Sales Invoice** header.

3. Select **Item** on **Sales Invoice** line. GST Group Code, HSN/SAC Code should not be blank on the Item. 

For example, there is a sales invoice for INR 10,000 and 18% GST (i.e. 9% CGST and 9% SGST/UTGST in case of Intra-State or Intra-Union Territory transaction or 18% IGST in case of Inter-State transaction) and 1% TCS as per Income Tax Act, 1961 has to be charged on the invoice amount.

-  GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**CGST**|900|  
    |**SGST**|900|
    |**TCS**|100|

-  On posting of sales invoice, GL Entries will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|11900|  
    |**SGST/UTGST Payable Account**|-900|  
    |**CGST Payable Account**|-900|
    |**TCS Payable Account**|-100|
    |**Sales Account**|-10000|

> [!TIP]
> In case of Inter-State Sales, IGST will be calculated with TCS as per the Income Tax Act, 1961.














## Related information 
[GST Kerala Flood Cess](GST-and-Kerala-Flood-Cess-on-Sales.md)


























[!INCLUDE[footer-include](../../includes/footer-banner.md)]
