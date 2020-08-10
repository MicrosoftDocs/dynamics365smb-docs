---
    title: GST Exempted Sales
    description: GST Exempted Sales

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
# GST Exempted Sales

Sales made to an exempted customer are known as Exempted Sales. No GST will be computed on such transactions.

## Create a Sales Invoice or Credit Memo

1. Choose the ![img](image/search.jpg)icon, enter **Sales Invoice** or **Sales Credit Memo**, and then choose the related link.
2. Select **Customer** on **Sales Invoice** or **Sales Credit Memo** header, GST customer type should be **Exempted**.
3. Select **G/L Account** or **Item Code** on **Sales Invoice** or **Sales Credit Memo** line. For example, there is a sales invoice and a sales credit memo for INR 10,000.

6. GL Entries for Exempted Sales, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|10,000|  
    |**Sales or Services Account**|-10,000| 

6. GL Entries for Sales Credit Memo for Exempted Sales, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Customer Account**|-10,000|  
    |**Sales or Services Account**|10,000| 








































