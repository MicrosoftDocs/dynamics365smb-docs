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
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can use the OIOUBL extension to create electronic documents in an OIOUBL format for invoices, credit memos, and reminders (which include finance charge memos). By default, the OIOUBL extension is installed in [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. However, there are a few things to do before you can use it:

* Set up payment methods, payment terms, and item charges.  
* Set up customers for OIOUBL.  
* If you are using the Windows client, specify the file locations for the XML documents you generate. If you are using a browser version, by default the files save to your Downloads folder.  

### About OIOUBL Profiles  
OIOUBL profiles are adaptations of business processes for various types of transactions, and differ depending on the types and contents of the documents that are exchanged. In Denmark, the two profiles that are required are the **Simpel fakturaproces** (Procurement-OrdSim-BilSim-1.0) and **Billing Basic** (urn:www.nesubl.eu:profiles:profile5:ver2.0) profiles. The Billing Basic profile is based on the Northern European Subset (NES). Your customer must be able to receive documents in one of these profiles. If you are not sure, ask your customer about the profile they require. For more information, see the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](http://go.microsoft.com/fwlink/?LinkId=267236).  

The default profile for all customers is the Simpel fakturaproces profile, which is chosen on the **Sales & Receivables Setup** page. You specify the profile for a specific customer on the **Customer** card. If you want to use the Billing Basic profile you will need to add it. To do so, on the **Sales & Receivables Setup** page, choose the button in the **Default Profile Code** field, and then choose **New**. Enter a name for the code, and then in the **Profile** field, enter **urn:www.nesubl.eu:profiles:profile5:ver2.0**. You can then choose the profile either as the default profile, or for one or more customers.

## To set up payment methods
Setting up payment methods and assigning them to customers lets you avoid having to specify a payment channel on each document.

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Methods**, and then choose the related link.  
2.  In the **Payment Channel** field, choose a payment channel for each payment method that you will use for electronic invoices. The following table describes the options.  

    |Option|Description|  
    |-------------------------------------|---------------------------------------|  
    |**Payment Slip**|The payment is made by using a payment slip, such as giro or an FI card (Fællesindbetalingskort).<br /><br /> **Note** <br /> This payment channel is not supported in the standard version of [!INCLUDE[d365fin](../../includes/d365fin_md.md)].|  
    |**Account Transfer**|The payment is made by transfer from the customer’s bank account.|  
    |**National Clearing**|The payment is made by transfer from the customer’s bank account and is processed by a clearing house.|  
    |**Direct Debit**|The payment is made by using the unified bank payment service (PBS).|  

##To set up payment terms
If you set up payment terms for customers, the electronic documents will include discounts you give for early payments. 

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Terms**, and then choose the related link.  
2.  In the **OIOXML Code** field, choose a code for each payment term that you will use for electronic invoices.  

For more information about how to set up payment methods, see [Defining Payment Methods](../../finance-payment-methods.md). 

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
    |**Profile Code**|Specifies the profile that this customer requires for electronic documents if this is different from the default profile that you specified in the **Sales & Receivables Setup** window.|  
    |**Profile Code Required**|Specifies if this customer requires a profile code for electronic documents.<br /><br /> **Tip** <br /> If the **Profile Code Required** field is selected, you cannot post a sales document for this customer unless you have specified a profile.|  
  
6. In the **Payment Method** field, choose the payment method you set up for OIOUBL.
7. In the **Payment Terms** field, choose the terms under which you expect the customer to pay.

For more information about how to set up a customer, see [How to: Register New Customers](../../sales-how-register-new-customers.md).

## To specify where to store OIOUBL files  
> [!Note]
> This process is required only if you are using the Windows client. If you are using a browser version, such as the web client, by default the files for all documents save to your **Downloads** folder.

1. Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup**, and then choose the related link.  
2. On the **OIOUBL** FastTab, fill in the fields as required.  
  
    > [!IMPORTANT]  
    > External document numbers are required for OIOUBL documents. This is true even if you did not select the **Ext. Doc. No. Mandatory** field on the **General** FastTab. If the document does not have an external document number, you will receive an error message.  
  
3. For service documents, choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Setup**, and then choose the related link. 
4. In the **Service Invoice Path** and **Service Cr. Memo Path** fields, enter paths to the locations where you want to store the XML files.

## To set up item charges  
1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Charges**, and then choose the related link.  
2.  For each item charge, in the **Charge Category** field, select a category.  

For more information about how to set up item charges, see [How to: Use Item Charges to Account for Additional Trade Costs](../../payables-how-assign-item-charges.md).

## See Also  
[Denmark Local Functionality](denmark-local-functionality.md)  
[The OIOUBL Extension for Electronic Invoicing in Denmark](ui-extensions-oioubl.md)  
[Create an Electronic Document in a OIOUBL Format](how-to-create-electronic-documents-by-using-oioubl.md)  
 
