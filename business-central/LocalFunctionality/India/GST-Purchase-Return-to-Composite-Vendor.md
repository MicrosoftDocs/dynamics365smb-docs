---
    title: Purchase Return of Goods and Services to Composite Vendor or Purchase Return of exempted goods and services with no GST Impact
    description: Purchase Return of Goods and Services to Composite Vendor or Purchase Return of exempted goods and services with no GST Impact

    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 06/16/2020
    ms.author: v-debapd

---
# Purchase Return of Goods and Services to Composite Vendor or Purchase Return of exempted goods and services with no GST Impact

## Create a Purchase Return Order/Credit Memo

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Return Order/Credit Memo**, and then choose the related link.
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Composite** or **Exempted**.
3. Select **Item Code** for goods, **G/L Account** for Service purchase, **Fixed Asset** for Fixed Asset purchase and **Charge (Item)** for Item Charge on **Purchase Credit Memo** line. For example, Purchase Return Order/Credit Memo has been issued for INR 10000 on which no GST is charged.
4. GL Entries will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|
    |**Vendor Account**|10000|
    |**Purchase/Services/Fixed Asset increase during the year Account**|-10000|

> [!NOTE]
>
> All relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































