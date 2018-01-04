---
    title: Set Up the OIOUBL Extension for Electronic Invoicing | Microsoft Docs
    description: Describes what you need to do to get ready to submit sales documents in a Offentlig Information Online - Universal Business Language (OIOUBL) format.
    services: project-madeira
    documentationcenter: ''
    author: bholtorf

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 01/04/2017
    ms.author: bholtorf

---
# How to: Set Up OIOUBL Electronic Invoicing
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use the OIOUBL extension to create electronic documents in the OIOUBL format for invoices, credit memos, and reminders (which include finance charge memos). This topic describes what you need to set up beforehand but mentions only the fields that apply to the OIOUBL extension.  

By default, the OIOUBL extension is installed in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. However, there are a few things to do before you can use the extension:

* Set up customers for OIOUBL
* Specify the file locations for the XML documents you generate
* Set up payment methods and payment terms
* Set up item charges

### About OIOUBL Profiles  
OIOUBL profiles are adaptations of business processes for various types of transactions and differ depending on the types and contents of the documents that are exchanged. In [!INCLUDE[d365fin](../../includes/d365fin_md.md)] you can specify the profile that you want to use by default for all customers, but you can also specify the profile to use for a specific customer if needed. In Denmark, the two profiles that are required are the Simpel fakturaproces (Procurement-OrdSim-BilSim-1.0) and Billing Basic (urn:www.nesubl.eu:profiles:profile5:ver2.0) profiles. The Billing Basic profile is based on the Northern European Subset (NES). 

By default, the Simpel fakturaproces is chosen in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. If you want to use the Billing Basic profile, you will need to set that up. You specify the default profile to use for all customers on the **Sales & Receivables Setup** page. You specify the profile for a specific customer on the **Customer** card. <!--To use the Billing Basic profile, copy the following >

For more information, see the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](http://go.microsoft.com/fwlink/?LinkId=267236).  

### To set up customers for OIOUBL  
You must add OIOUBL information to the relevant customers. Additionally, your customer must be able to receive documents in either the **Billing Basic** or **Simpel fakturaprocess** profiles. For more information, see [The OIOUBL Extension for Electronic Invoicing in Denmark](ui-extensions-oioubl.md).

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.  
2.  Open the customer that you want to enable for OIOUBL.  
3.  Enter the customer's address. Make sure that you specify a country/region code.  
4.  On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**GLN**|Enter the Global Location Number for the customer. |  
    |**Account Code**|Enter the account code for the customer.<br /><br /> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the OIOUBL documents that you create in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. In accordance with **Lov om Offentlige Betalinger** and related statutes, the customer is entitled to withhold payment until they receive an invoice with the relevant account code. |  
    |**Profile Code**|Specifies the profile that this customer requires for electronic documents if this is different from the default profile that you specified in the **Sales & Receivables Setup** window.|  
    |**Profile Code Required**|Specifies if this customer requires a profile code for electronic documents.<br /><br /> **Tip** <br /> If the **Profile Code Required** field is selected, you cannot post a sales document for this customer unless you have specified a profile.|  

For more information about how to set up a customer, see [How to: Register New Customers](../../sales-how-register-new-customers.md).

### To specify where to store OIOUBL files  
1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2. On the **OIOUBL** FastTab, fill in the fields as required.  
3. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link.  
4. In the **Service Invoice Path** and **Service Cr. Memo Path** fields, provide the path and name of the folder where you want to store OIOUBL files.  
5. Choose the **OK** button.  
  
    > [!IMPORTANT]  
    > External document numbers are required for OIOUBL documents. This is true even if you did not select the **Ext. Doc. No. Mandatory** field on the **General** FastTab. If the document does not have an external document number, you will receive an error message.  

## To set up payment methods and payment terms  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Methods**, and then choose the related link.  
2.  In the **Payment Channel** field, choose a payment channel for each payment method that you will use for electronic invoices. The following table describes the options.  

    |Option|Description|  
    |-------------------------------------|---------------------------------------|  
    |**Payment Slip**|The payment is made by using a payment slip, such as giro or an FI card (Fællesindbetalingskort).<br /><br /> > **Note** <br /> This payment channel is not supported in the standard version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
    |**Account Transfer**|The payment is made by transfer from the customer’s bank account.|  
    |**National Clearing**|The payment is made by transfer from the customer’s bank account and is processed by a clearing house.|  
    |**Direct Debit**|The payment is made by using the unified bank payment service (PBS).|  

3.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Terms**, and then choose the related link.  
4.  In the **OIOXML Code** field, choose a code for each payment term that you will use for electronic invoices.  

For more information about how to set up payment methods, see [Defining Payment Methods](../../finance-payment-methods.md). 

## To set up item charges  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Charges**, and then choose the related link.  
2.  For each item charge, in the **Charge Category** field, select a category.  

For more information about how to set up item charges, see [How to: Use Item Charges to Account for Additional Trade Costs](../../payables-how-assign-item-charges.md).

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[The OIOUBL Extension for Electronic Invoicing in Denmark](ui-extensions-oioubl.md)  
[Create an Electronic Document in a OIOUBL Format](how-to-create-electronic-documents-by-using-oioubl.md)  
 
