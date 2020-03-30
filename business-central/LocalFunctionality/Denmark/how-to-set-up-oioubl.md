---
    title: Set Up the OIOUBL Extension for Electronic Invoicing | Microsoft Docs
    description: Describes what you need to do to get ready to submit sales documents in a Offentlig Information Online - Universal Business Language (OIOUBL) format.
    author: bholtorf

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: bholtorf

---
# Set Up OIOUBL
You must define a location for storing Offentlig Information Online UBL (OIOUBL) files when you create electronic documents such as invoices or credit memos. You must also define payment methods, payment terms, and item charges, and you must set up relevant customers for OIOUBL.  

* Set up payment terms and item charges.  
* Set up customers for OIOUBL.  

### About OIOUBL Profiles  
OIOUBL profiles are adaptations of business processes for various types of transactions, and differ depending on the types and contents of the documents that are exchanged. In Denmark, the two profiles that are required are the **Simpel fakturaproces** (Procurement-OrdSim-BilSim-1.0) and **Billing Basic** (urn:www.nesubl.eu:profiles:profile5:ver2.0) profiles. The Billing Basic profile is based on the Northern European Subset (NES). Your customer must be able to receive documents in one of these profiles. If you are not sure, ask your customer about the profile they require. For more information, see the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](https://aka.ms/Digitaliseringsstyrelsen).  

The default profile for all customers is the Simpel fakturaproces profile, which is chosen on the **Sales & Receivables Setup** page. You specify the profile for a specific customer on the **Customer** card. If you want to use the Billing Basic profile you will need to add it. To do so, on the **Sales & Receivables Setup** page, choose the button in the **Default Profile Code** field, and then choose **New**. Enter a name for the code, and then in the **Profile** field, enter **urn:www.nesubl.eu:profiles:profile5:ver2.0**. You can then choose the profile either as the default profile, or for one or more customers.

##To set up payment terms
If you set up payment terms for customers, the electronic documents will include discounts you give for early payments.

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Terms**, and then choose the related link.  
2.  In the **OIOXML Code** field, choose a code for each payment term that you will use for electronic invoices.  

### To set up customers for OIOUBL  
You can use the **Offentlig kunde (OIOXML)** customer template to apply standard settings for OIOUBL to a new customer, or the **Apply Template** function to apply the settings in the template to an existing customer. The following steps describe how to manually complete the required fields for OIOUBL. <!--need to check whether this overwrites anything for existing customers-->

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Open the customer that you want to enable for OIOUBL.  
3.  Enter the customer's address. Make sure that you specify a country/region code, and the contact information for the sell-to contact.  
4.  In the **Document Sending Profile** field, choose the **OIOUBL** profile.
5.  On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    > [!Tip]
    > To display all of the fields, you might need to choose the **Show more** for the **Invoicing** FastTab.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**GLN**|Enter the Global Location Number for the customer. |  
    |**Account Code**|Enter the account code for the customer.<br /><br /> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the OIOUBL documents that you create in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. In accordance with **Lov om Offentlige Betalinger** and related statutes, the customer is entitled to withhold payment until they receive an invoice with the relevant account code. |  
    |**Profile Code**|Specifies the profile that this customer requires for electronic documents if this is different from the default profile that you specified on the **Sales & Receivables Setup** page.|  
    |**Profile Code Required**|Specifies if this customer requires a profile code for electronic documents.<br /><br /> **Tip** <br /> If the **Profile Code Required** field is selected, you cannot post a sales document for this customer unless you have specified a profile.|  

6. In the **Payment Terms** field, choose the terms under which you expect the customer to pay.

For more information about how to set up a customer, see [Register New Customers](../../sales-how-register-new-customers.md).

## To set up item charges  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Charges**, and then choose the related link.  
2.  For each item charge, in the **Charge Category** field, select a category.  

Finally, you must specify EAN numbers and account codes for the relevant customers. For more information, see [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md).  

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)   
[Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)   
