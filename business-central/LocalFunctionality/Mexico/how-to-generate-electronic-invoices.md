---
    title: Generate Electronic Invoices [MX]
    description: After you post a sales invoice in the Mexican version, you must generate an electronic invoice that will be sent to the customer.
    author: edupont04

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.search.form: 132, 25
    ms.date: 05/18/2022
    ms.author: edupont

---
# Generate Electronic Invoices in the Mexican Version

In [!INCLUDE[prod_short](../../includes/prod_short.md)], after you post a sales invoice you must generate an electronic invoice that will be sent to the customer. You can also export the electronic invoice as an XML file, which you can save to a specified location.  

The following procedure describes how to generate electronic invoices for sales invoices, but the same steps also apply to service invoices and credit memos.  

## To generate electronic invoices for sales invoices  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoice**, and then choose the related link.  
2. Select the posted invoice.  
3. Choose the **Send Electronic Document** action, and then specify if you want to also request a digital stamp for the document.  

    If you choose **Request Stamp**, the posted invoice will be digitally signed by your PAC, and you can then send the posted invoice afterwards. if you choose **Request Stamp and Send**, the posted invoice is digitally signed and sent in one step.

    An email will be sent to the customer with the electronic invoice attached as an XML file. If you selected the **Send PDF Report** field on the **General Ledger Setup** page, a PDF will be included with the XML file.  

    You can view of the status of the electronic invoice on the **Shipping & Billing** FastTab.
4. Optionally, choose the **Export E-Document as XML** action. Select the location where you want to save the electronic invoice as an XML file.  

To verify the electronic invoice activity, on the **Posted Sales Invoice** page, on the **Invoicing** FastTab, the **Electronic Document Sent** and **No. of E-Document Submissions** fields will be updated.  

> [!NOTE]  
> [!INCLUDE[bp_refimplementation](../../includes/bp_refimplementation.md)]  

# Receiving payments

Mexican companies must be able to receive payments in accordance with CFDI withholdings and Payment Information version 2.0.

To receive payment in accordance with CFDI version 2.0, users don’t need additional settings because required data will be prepared for customer invoices first. You cannot stamp payments without applied invoice having a stamp.

> [!IMPORTANT]  
> Current version of [!INCLUDE [prod_short](../../includes/prod_short.md)] supports receiving **customer payment information** related with the CFDI version 2.0, but **withholding receipt is currently out of scope**.  

## To stamp the payment  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Ledger Entries**, and then choose the related link.  
2. Find a payment you applied the invoice and select this line.
3. Choose the **Send** action, and then specify if you want to also request a digital stamp for the payment.

## See Also

[Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
[Electronic Invoicing](electronic-invoicing.md)  
[Mexico Local Functionality](mexico-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
