---
    title: Purchase of Services for Overseas Place of Supply from Registered Vendor
    description: Purchase of Services for Overseas Place of Supply from Registered Vendor

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
# Purchase of Services for Overseas Place of Supply from Registered Vendor

## Create a Purchase Invoice

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Invoice**, and then choose the related link.
2. Select **Vendor** on **Purchase Invoice** header, GST vendor type should be **Registered**.
3. Select **G/L Account** on **Purchase Invoice** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** on the G/L Account. For example, Service Recipient having GSTIN for West Bengal and Vendor having GSTIN for West Bengal, but being service provider and place of supply is outside India. In this case, IGST will be charged as place of supply is outside India. So, invoice will be issued for INR 10,000 on which 18% IGST, will be charged.
4. GST Credit option can be changed on **Purchase Invoice** line.
5. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|

6. GL Entries for purchase of services for overseas place of supply from registered vendor where input tax credit is available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|10000|
    |**IGST Receivable Account**|1800|  
    |**Vendor Account**|-11800|

7. GL Entries for purchase of services for overseas place of supply from registered vendor where input tax credit is not available, will be as following:
    
    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11800|
    |**Vendor Account**|-11800|

> [!NOTE]
>
> All relevant GST attributes are stored along with the GST transactions for GST Settlement and generating GST returns for government authorities.





































