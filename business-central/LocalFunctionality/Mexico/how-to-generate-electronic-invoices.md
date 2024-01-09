---

title: Generate electronic invoices [MX]
description: After you post a sales invoice in the Mexican version, you must generate an electronic invoice that will be sent to the customer.
author: altotovi
ms.author: altotovi
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 12/12/2023
ms.custom: bap-template
ms.search.form: 132, 25
---
# Generate electronic invoices in the Mexican version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], after you post a sales invoice you must generate an electronic invoice that is sent to the customer. You can also export the electronic invoice as an XML file, which you can save to a specified location.  

The following procedure describes how to generate electronic invoices for sales invoices, but the same steps also apply the following documents:

* Sales credit memos  
* Sales shipments  
* Transfer shipments  
* Service invoices  
* Service credit memos  

## To generate electronic invoices for sales invoices  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoice**, and then choose the related link.  
2. Select the posted invoice.  

    > [!NOTE]
    > If you're canceling the posted document, you must specify a reason for the cancellation in the **CFDI Cancellation Reason** field, and you must specify which document substitutes the canceled document in the **Substitution Document No.** field. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]
3. Choose the **Send Electronic Document** action, and then specify if you want to also request a digital stamp for the document.  

    If you choose **Request Stamp**, the posted invoice is digitally signed by your PAC, and you can then send the posted invoice afterwards. If you choose **Request Stamp and Send**, the posted invoice is digitally signed and sent in one step.

    An email is sent to the customer with the electronic invoice attached as an XML file. If you selected the **Send PDF Report** field on the **General Ledger Setup** page, a PDF is included with the XML file.  

    You can view of the status of the electronic invoice on the **Shipping & Billing** FastTab.
4. Optionally, choose the **Export E-Document as XML** action. Select the location where you want to save the electronic invoice as an XML file.  

To verify the electronic invoice activity, on the **Posted Sales Invoice** page, on the **Invoicing** FastTab, the **Electronic Document Sent** and **No. of E-Document Submissions** fields are updated.  

> [!NOTE]  
> [!INCLUDE[bp_refimplementation](../../includes/bp_refimplementation.md)]  

## Receive payments

Mexican companies must be able to receive payments in accordance with CFDI Withholdings and Payment Information version 2.0. To receive payment in accordance with CFDI version 2.0, you don't need extra settings because the required data will already have been included for the customer invoices. You can't stamp a payment that is applied to an invoice that doesn't have a stamp.

> [!IMPORTANT]  
> The current version of [!INCLUDE [prod_short](../../includes/prod_short.md)] supports receipt of *customer payment information* in accordance with CFDI version 2.0. However, *withholding receipt* is currently not supported in the default version of [!INCLUDE [prod_short](../../includes/prod_short.md)].  

### To stamp the payment  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Ledger Entries**, and then choose the related link.  
2. Find a payment that you applied to the electronic invoice, and then select this line.
3. Choose the **Send** action, and then specify if you want to also request a digital stamp for the payment.

## Register export (Comercio Exterior Complement)

The Comercio Exterior Complement is an annex to the electronic invoice. It identifies importers and exporters and improves the description of the merchandise that is traded. The Comercio Exterior Complement is a key obligation for taxpayers who export merchandise.

To set up Comercio Exterior Complement, follow these steps:  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **Electronic Invoice** FastTab, in the **USD Currency Code** field, choose the USD currency you want to use. It can be different than *USD*. For example, it might be *USD-CFDI*.  
3. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Units of Measure**, and then choose the related link.
4. In the **SAT Customs Unit** field, choose the unit of measure from the **SAT Custom Units** table for foreign trade operations.

To create Comercio Exterior Complement:

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices**, and then choose the related link.
2. Create a sales invoice with all details ready for export.
3. In the **CFDI Export Code** field, choose a value related to your type of export. Validation of this field sets values on the **Foreign Trade** FastTab, but you can change it. For example, if the **CFDI Export Code** contains **04** as a value. The **Foreign Trade** is also used for **Carta Porte Complement**.
4. If you configure a foreign trade invoice, you must fill in the following fields.

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    |**Transit-to Location**|Specifies the customer’s location with their address and postal code.|
    |**SAT International Trade Terms (Incoterms)**|You can specify one of the options from the new Incoterms catalog.|
    |**Exchange Rate USD (reversed value for Currency Factor)**|This value is assigned from the **USD Currency Code** exchange rates. You can change this value if needed.|

5. After posting the document and getting a stamp, you'll get an XML file with the Comercio Exterior Complement.

> [!NOTE]  
> If you want to create an invoice for foreign trade, the **CFDI Export Code** field must be different from **01** because that value is used for domestic invoices only.  

## See also

[Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
[Electronic Invoicing](electronic-invoicing.md)  
[Mexico Local Functionality](mexico-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
