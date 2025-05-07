---
title: TCS calculation on Sales and Receipt Transactions
description: TCS calculation on Sales and Receipt Transactions Transactions

author: v-debapd

    
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English
ms.date: 04/01/2021
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# TCS Calculation on Sales and Receipt Transactions



TCS can be collected on goods (Items) and services (G/L Account) transactions. TCS calculations can be done through following documents:

- Sales Order
- Sales Invoice
- Sales Return Order
- Sales Credit Memo
- General Journal
- Sales Journal
- Cash Receipt Voucher
- Bank Receipt Voucher

## TCS calculation on general journal, sales journal, cash receipt journal, sales invoice, sales order, sales return order, sales credit memo.

- Create General Journal, Sales Journal, Cash Receipt Journal or Bank Receipt Journal

  1.  Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, **Sales Journal**, **Cash Receipt Voucher** or **Bank Receipt Voucher**, and then choose the related link. 
  2. Select **Customer** in Account Type and select relevant customer code in Account No. field. 
  3. Select **G/L Account** or **Bank Account** in Bal. Account Type and select relevant expense account in Bal. Account. No. field.
  4. Select relevant **TCS Nature of Collection** in journal line. **Location Code** and **T.C.A.N No.** fields should not be blank.

- Create Sales Invoice or Sales Order

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoice**, **Sales Order**, **Sales Return Order** or **Sales Credit Memo**, and then choose the related link.
  2. Select **Customer**, **Location Code** on **Sales Order**, **Sales Invoice**, **Sales Return Order** or **Sales Credit Memo** header.
  3. Select **G/L Account** or **Item Code** on **Sales Order**, **Sales Invoice**, **Sales Return Order** or **Sales Credit Memo** line.
  4. **TCS Nature of Collection**, **Location Code** and **T.C.A.N No.** fields should not be blank.

### TCS to be calculated on customer invoice (through general journal, sales journal, sales invoice or sales order)

For example, invoice has been issued to customer for INR 10,000 on which 1% TCS is applicable for Nature of Collection 'Scrap'.
  
  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|10000|  
    |**TCS Amount**|100 (10000*1%)|

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10100|
    |**TCS Payable Account**|-100|
    |**Sales Account**|-10000|

## TCS to be calculated on customer advance payment (through general journal, cash receipt journal)

For example, advance payment received from customer for INR 10,000 on which 1% TCS is applicable for Nature of collection 'Scrap'

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|10000|  
    |**TCS Amount**|99 (10000x1%/101)|

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000|
    |**TCS Payable Account**|-99|
    |**Customer Account**|-9901|

## Adjustment of calculated TCS on advance payment against sales invoice

TCS which has been calculated on advance payment can be adjusted while creating Sales Invoice against that advance payment. TCS will not be calculated on Customer Invoices if advance payment, on which TCS has already been calculated, is applied to the invoice. System should check the TCS base amount on which TCS has been calculated on advance payment with the line amount of Sales Invoice and TCS will only be calculated on the line amount which is more than the TCS base amount. For example: If TCS base amount was 10,000.00 in advance payment and line amount is 20,000.00 on sales invoice, then TCS will be calculated on 10,000.00 on sales invoice.

  - GL Entries for TCS on Customer advance payment using Cash Receipt Journal, will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Bank Account**|10000|
    |**TCS Payable Account**|-99|
    |**Customer Account**|-9901|

  - GL Entries for TCS on Customer Invoice using Sales Invoice against advance payment, will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|20101|
    |**TCS Payable Account**|-101|
    |**Sales Account**|-20000|

> [!NOTE]
> TCS is calculated after adjusting the TCS amount which was earlier calculated on advance payment.


## TCS to be calculated on non-resident customer invoice in foreign currency

For example, invoice has been raised to foreign customer for USD 10,000 on which 1% TCS is applicable for Nature of collection 'Scrap'. All foreign currency amounts will get converted into INR based on currency exchange rates. Exchange rate considered for this example is 1 USD = 65 INR.

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|USD 10000 or INR 650000|  
    |**TCS Amount**|INR 6500(650000x1%)|

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|656500|
    |**TCS Payable Account**|-6500|
    |**Sales Account**|-650000|



## TCS calculation on higher rate if customer is not having PAN

For example, invoice has been raised to customer for INR 50,000 on which 1% TCS is applicable for Nature of collection 'Scrap'. But if there is no PAN available for customer then higher TCS of 5% is applicable.

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|50000|  
    |**TCS Amount**|2500(50000x5%)|

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|52500|
    |**TCS Payable Account**|-2500|
    |**Sales Account**|-50000|

## TCS calculation on multiple nature of goods in single invoice

For example, invoice has been raised to customer for INR 1,00,000. INR 50,000 each towards two nature of goods 'Scrap' and 'Timber'.

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|100000|  
    |**TCS Amount on Scrap**|500(50000x1%)|
    |**TCS Amount on Timber**|2500(50000x5%)

  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|103000|
    |**TCS Payable Account - Scrap**|-500|
    |**TCS Payable Account - Timber**|-2500|
    |**Sales Account - Scrap**|-50000|
    |**Sales Account - Timber**|-50000|

## TCS on sale of scrap @ lower rate

For example, invoice has been raised to customer for INR 1,00,000 towards sale of Scrap. Customer has a certificate of income tax at Lower rate @ 0.5% on Scrap instead of normal rate.

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|100000|  
    |**TCS Amount**|500(100000x0.5%)|
    
  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|103000|
    |**TCS Payable Account**|-500|
    |**Sales Account**|-100000|

## TCS on sale of scrap @ zero rate

For example, invoice has been raised to customer for INR 1,00,000 towards sale of Scrap. Customer has a certificate of income tax at Zero rate @ 0% on Scrap instead of normal rate.

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|100000|  
    |**TCS Amount**|0(100000x0%)|
    
  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|100000|
    |**Sales Account**|-100000|

## TCS to be calculated on sales return (sales return order or sales credit memo)

For example, sales return from customer for INR 10,000 on which 1% TCS is applicable for Nature of collection “Scrap”.

  - In this case TCS calculation will be as following:

    |Component|Value|
    |----------------------------------|---------------------------------------|  
    |**TCS Base Amount**|10000|  
    |**TCS Amount**|100(10000x1%)|
    
  - GL Entries will be as following:
     
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Sales Account**|10000|
    |**TCS Payable Account**|100|
    |**Customer Account**|-10100|

> [!NOTE]
> If Credit Memo is created before remittance of Tax to government, then TCS entries will get reversed proportionately, on the basis of the quantity returned. In case TCS amount has been remitted to Income Tax department, TCS Payable account will not be reversed.


## Related information 
[TCS Threshold](TCS-Threshold.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
