---
title: Import from Foreign Vendor
description: Learn how to process imports from foreign vendors in India, including GST and reverse charge procedures for goods and services.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, foreign vendor import
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Import from foreign vendor

Purchasing goods in India from a place outside India is import of goods. For services, if the supplier is located outside India, the recipient is located in India and the place of supply is in India, then it's called Import of services. Purchase of goods and/or services from a foreign vendor is subject to reverse charge, that is, the person importing goods or services has to remit tax to the government.

Process for purchase from a foreign vendor is explained in this document.

> [!NOTE]
> The tax rates and amounts below are illustrative. Confirm current import and tax requirements separately.

## Create a purchase invoice

1. [!INCLUDE [open-search](../../includes/open-search.md)] **Purchase Invoices**, and then choose the related link.
1. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Import**.
1. Select **Item** for goods, **G/L Account** for services, or **Fixed Asset** on the invoice line. Check **GST Group Code** and **HSN/SAC Code**. Set **GST Credit** to **Availment** or **Non-Availment**, as appropriate.
1. GST Credit option can be changed in document line.
1. For goods, enter **GST Assessable Value** and **Custom Duty Amount** on the line as applicable. These values aren't allowed for service groups or **Charge (Item)** lines.
1. For goods invoiced with a bill of entry, enter **Bill of Entry No.**, **Bill of Entry Date**, and **Bill of Entry Value** on the header before posting.

For services from an associated enterprise, check **Associated Enterprises** on the header. This setting distinguishes the associated-enterprise examples below from ordinary import service transactions.

In the goods and fixed asset examples below, INR 11,000 is the **GST Assessable Value** before adding INR 1,000 of basic customs duty. The resulting tax calculation base is INR 12,000, even though the supplier's transaction value is INR 10,000.

- In case of import of goods from foreign vendor, IGST is to be calculated on GST Assessable Value + Basic Custom Duty.

  For example, purchase invoice is issued INR 10000, Custom Duty is INR 1000. Therefore, on GST Assessable Value INR 11000,(IGST @18%) has to be charged. Calculation base: (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%).

  - GST calculation appears in the Fact Box as following:

      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Transaction Value**|10000|
      |**GST Assessable Value**|11,000|
      |**Custom Duty (BCD)**|1000|
      |**GST Base Amount**|12,000|
      |**IGST**|2160 (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)|  

  - GL Entries for import of goods from foreign vendor where input tax credit is available are as following:

      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Purchase Account (Transactional Value+ BCD)**|11000|  
      |**IGST Receivable Account (GST on GST Assessable Value + BCD)**|2160| 
      |**Customs House Account (GST Amount + BCD)**|-3160|
      |**Vendor Account (Transaction Value)**|-10000|

  - GL Entries for import of goods from foreign vendor where input tax credit isn't available are as following:

      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Purchase Account (Transactional Value+ BCD + IGST Amount)**|13160|  
      |**Customs House Account (GST Amount + BCD)**|-3160|
      |**Vendor Account (Transaction Value)**|-10000|

- Import of Fixed Asset from foreign vendor, IGST is to be calculated on GST Assessable Value + Basic Custom Duty.

  For example, purchase invoice is issued for INR 10000, Custom Duty INR 1000, GST Assessable Value INR 11000,(IGST @18%) has to be charged. Calculation base: (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%).

  - GST Calculation appears in the Fact Box as following:

      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**Transaction Value**|10000|
      |**GST Assessable Value**|11,000|
      |**Custom Duty (BCD)**|1000|
      |**GST Base Amount**|12,000|
      |**IGST**|2160 (18% on 11,000 GST Assessable Value + 1,000 BCD) (12,000*18%)|  

  - GL Entries for import of goods from foreign vendor where input tax credit is available, will be as following:

      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Fixed Asset Increase During the Year Account (Transactional Value+ BCD)**|11000|  
      |**IGST Receivable Account (GST on GST Assessable Value + BCD)**|2160| 
      |**Customs House Account (GST Amount + BCD)**|-3160|
      |**Vendor Account (Transaction Value)**|-10000|

  - GL Entries for import of goods from foreign vendor where input tax credit isn't available, will be as following:

     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Fixed Asset Increase During the Year Account (Transactional Value+ BCD + IGST Amount)**|13160|  
     |**Customs House Account (GST Amount + BCD)**|-3160|
     |**Vendor Account (Transaction Value)**|-10000|

- Import of services from foreign vendor.

  For example, purchase invoice is issued for INR 10000, (IGST @18%) has to be charged.

  - GST Calculation appears in the Fact Box as following:

     |Component|Amount|
     |----------------------------------|---------------------------------------|  
     |**GST Base Amount**|10000|
     |**IGST**|1800|  

  - GL Entries for import of services from foreign vendor where input tax credit is available are as following:

     |Particulars|Amount|
     |----------------------------------|---------------------------------------|  
     |**Services Account**|10000|  
     |**IGST Receivable (Interim) Account**|1800|
     |**IGST Payable (Interim) Account**|-1800|
     |**Vendor Account (Transaction Value)**|-10000|

  - GL Entries for import of services from foreign vendor where input tax credit isn't available are as following:

      |Particulars|Amount|
      |----------------------------------|---------------------------------------|  
      |**Services Account**|11800|  
      |**IGST Payable (Interim) Account**|-1800|
      |**Vendor Account**|-10000|

- Import of Services from Import Associate Vendor.

  For example, purchase invoice is issued for INR 10000, (IGST @18%) has to be charged.

  - GST Calculation appears in the Fact Box as following:

      |Component|Amount|
      |----------------------------------|---------------------------------------|  
      |**GST Base Amount**|10000|
      |**IGST**|1800|

  - GL Entries for import of services from import associate vendor where input tax credit is available are as following:

      |Particular|Amount|
      |----------------------------------|---------------------------------------|  
      |**Services Account**|10000|  
      |**IGST Receivable Account**|1800|
      |**IGST Payable Account**|-1800|
      |**Vendor Account**|-10000|

  - GL Entries for import of services from import associate vendor where input tax credit isn't available are as following:

      |Particular|Amount|
      |----------------------------------|---------------------------------------|  
      |**Services Account**|11800|  
      |**IGST Payable Account**|-1800|
      |**Vendor Account**|-10000|

> [!NOTE]
>
> For an import in foreign currency, enter the **Currency Code** and check the exchange rate before posting. Posting converts customs duty and tax amounts to local currency.

## Related information

[Purchase from Vendor with Overseas Place of Supply](GST-Service-Purchase-for-Overseas-Place-of-supply-Registered-Vendor.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
