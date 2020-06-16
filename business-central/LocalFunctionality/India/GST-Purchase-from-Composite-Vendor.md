---
    title: Purchase from Composite Vendor or Purchase of exempted goods and services with no GST Impact
    description: Purchase from Composite Vendor or Purchase of exempted goods and services with no GST Impact

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 06/15/2020
    ms.author: v-debapd

---
# Purchase from Composite Vendor or Purchase of exempted goods and services with no GST Impact

## Create a Purchase Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link.
2. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Composite** or **Exempted**.
3. Select **G/L Account**, **Item Code**, **Fixed Asset** or **Charge (Item)** on **Purchase Invoice** line.
For example, invoice will be issued for INR 10000 on which there is no GST will be charged.

6. GL Entries will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Purchase/Services Account**|10000|  
    |**Vendor Account**|-10000|

> [!NOTE]
>
> All relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































