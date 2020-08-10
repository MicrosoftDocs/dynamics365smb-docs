---
    title: Purchase Return of Services for Overseas Place of Supply to Registered Vendor
    description: Purchase Return of Services for Overseas Place of Supply to Registered Vendor

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
# Purchase Return of Services for Overseas Place of Supply to Registered Vendor

## Create a Purchase Return Order or Purchase Credit

1. Choose the ![img](image/search.jpg)icon, enter **Purchase Return Order** or **Purchase Credit Memo**, and then choose the related link.
2. Select **Vendor** on **Purchase Credit Memo** header, GST vendor type should be **Registered**.
3. Select **G/L Account** on **Purchase Credit Memo** line. GST Group Code, HSN/SAC Code and GST Credit value should be selected as **Availment** if the tax input credit is available or else **Non-Availment** in the G/L Account. For example, Service Recipient having GSTIN for West Bengal and Vendor having GSTIN for West Bengal, but being service provider and place of supply is outside India. In this case, IGST will be charged as place of supply is outside India. So, return order or credit memo will be issued for INR 10,000 on which 18% IGST, will be charged.
5. GST Credit option can be changed on **Purchase Credit Memo** line.
6. GST calculation will appear in the Fact Box, as following:
    
    |Component|Amount|
    |----------------------------------|---------------------------------------|  
    |**GST Base Amount**|10,000|  
    |**IGST**|1800|  

6. GL Entries for Return or Credit Note of services for overseas place of supply from registered vendor where input tax credit is available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|11800|  
    |**IGST Receivable Account**|-1800|  
    |**Vendor Account**|-10000|

7. GL Entries for Return or Credit Note of services for overseas place of supply from registered vendor where input tax credit is not available, will be as following:

    |Particulars|Amount|
    |----------------------------------|---------------------------------------|  
    |**Services Account**|-11800|  
    |**Vendor Account**|11800|







































