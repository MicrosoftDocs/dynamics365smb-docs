---
    title: How to Set Up Customers for OIOUBL | Microsoft Docs
    description: To create Offentlig Information Online UBL (OIOUBL) documents for customers in the public sector, you must add OIOUBL information to the relevant customers.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up Customers for OIOUBL
To create Offentlig Information Online UBL (OIOUBL) documents for customers in the public sector, you must add OIOUBL information to the relevant customers.  

 This topic only describes fields that apply to OIOUBL. For more information, see [Register New Customers](../../sales-how-register-new-customers.md).  

### To set up customers for OIOUBL  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Open the customer that you want to enable for OIOUBL.  
3.  On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|  
    |**GLN**|Enter the customer's Global Location Number, which uniquely identifies the billing address. A GLN has a fixed length of 13 digits. It includes an assigned company prefix, a location reference, and a check digit.|  
    |**Account Code**|Enter the account code for the customer.<br /><br /> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the OIOUBL documents that you create in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. In accordance with **Lov om Offentlige Betalinger** and related statutes, the customer is entitled to withhold payment until they receive an invoice with the relevant account code.|  
    |**OIOUBL Profile Code**|Specifies the profile that this customer requires for electronic documents if this is different from the default profile that you specified on the **Sales & Receivables Setup** page.|  
    |**OIOUBL Profile Code Required**|Specifies if this customer requires a profile code for electronic documents. **Tip:**  If the **OIOUBL Profile Code Required** field is selected, you cannot post a sales document for this customer unless you have specified a profile.|  

 These fields are specific to OIOUBL. The values are used in all OIOUBL documents that you create for this customer. For more information, see [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md).  

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[Register New Customers](../../sales-how-register-new-customers.md)   
[Set Up OIOUBL](how-to-set-up-oioubl.md)   
[Create Electronic Documents by Using OIOUBL](how-to-create-electronic-documents-by-using-oioubl.md)   
[OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)  
