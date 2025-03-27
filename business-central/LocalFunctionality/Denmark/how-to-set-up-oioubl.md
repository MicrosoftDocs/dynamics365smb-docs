---
title: Set Up the OIOUBL Extension for Electronic Invoicing | Microsoft Docs
description: Prepare to submit sales documents in the Offentlig Information Online - Universal Business Language (OIOUBL) format by following the steps outlined in this article.
author: brentholtorf   
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: OIOUBL, Offentlig, Denmark
ms.date: 03/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Set up OIOUBL

You must define a location for storing Offentlig Information Online UBL (OIOUBL) files when you create electronic documents such as invoices or credit memos. You must also define payment methods, payment terms, and item charges, and you must set up relevant customers for OIOUBL.  

* Set up payment terms and item charges.  
* Set up customers for OIOUBL.  

### About OIOUBL profiles

OIOUBL profiles are adaptations of business processes for various types of transactions, and differ depending on the types and contents of the documents that are exchanged. In Denmark, the two profiles that are required are the **Simpel fakturaproces** (Procurement-OrdSim-BilSim-1.0) and **Billing Basic** (urn:www.nesubl.eu:profiles:profile5:ver2.0) profiles. The Billing Basic profile is based on the Northern European Subset (NES). Your customer must be able to receive documents in one of these profiles. If you aren't sure, ask your customer about the profile they require. Refer to the entry on OIOUBL profiles in the frequently asked questions section at [Digitaliseringsstyrelsen](https://aka.ms/Digitaliseringsstyrelsen).  

The default profile for all customers is the Simpel fakturaproces profile, which is chosen on the **Sales & Receivables Setup** page. You specify the profile for a specific customer on the **Customer** card. If you want to use the Billing Basic profile you need to add it. To do so, on the **Sales & Receivables Setup** page, choose the button in the **Default Profile Code** field, and then choose **New**. Enter a name for the code, and then in the **Profile** field, enter **urn:www.nesubl.eu:profiles:profile5:ver2.0**. You can then choose the profile either as the default profile, or for one or more customers.

## Set up payment terms

If you set up payment terms for customers, the electronic documents include discounts you give for early payments.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Terms**, and then choose the related link.  
1. In the **OIOXML Code** field, choose a code for each payment term that you use for electronic invoices.  

### Set up customers for OIOUBL

You can use the **Offentlig kunde (OIOXML)** customer template to apply standard settings for OIOUBL to a new customer, or the **Apply Template** function to apply the settings in the template to an existing customer. The following steps describe how to manually complete the required fields for OIOUBL. <!--need to check whether this overwrites anything for existing customers-->

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
1. Open the customer that you want to enable for OIOUBL.  
1. Enter the customer's address. Make sure that you specify a country/region code, and the contact information for the sell-to contact.  
1. In the **Document Sending Profile** field, choose the **OIOUBL** profile.
1. On the **Invoicing** FastTab, fill in the fields as described in the following table.  

    > [!Tip]
    > To display all of the fields, you need to choose the **Show more** for the **Invoicing** FastTab.

    |Field|Description|  
    |---------------------------------|---------------------------------------|
    |**GLN**|Enter the Global Location Number for the customer. |  
    |**Account Code**|Enter the account code for the customer.<br><br/> Customers in the public sector provide an account code when they place an order or requisition. Based on the value of this field, the account code is included in the OIOUBL documents that you create in [!INCLUDE[prod_short](../../includes/prod_short.md)]. In accordance with **Lov om Offentlige Betalinger** and related statutes, the customer is entitled to withhold payment until they receive an invoice with the relevant account code. |  
    |**Profile Code**|Specifies the profile that this customer requires for electronic documents if this is different from the default profile that you specified on the **Sales & Receivables Setup** page.|  
    |**Profile Code Required**|Specifies if this customer requires a profile code for electronic documents.<br><br/> **Tip** <br/> If the **Profile Code Required** field is selected, you can't post a sales document for this customer unless you specified a profile.|  

1. In the **Payment Terms** field, choose the terms under which you expect the customer to pay.

Learn more in [Register New Customers](../../sales-how-register-new-customers.md), which provides information on setting up a customer in Business Central.

## Set up item charges

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Charges**, and then choose the related link.  
1. For each item charge, in the **Charge Category** field, select a category.  

Finally, you must specify EAN numbers and account codes for the relevant customers. Learn more in [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md).  

## Related information

- [Denmark Local Functionality](denmark-local-functionality.md)  
- [OIOUBL Electronic Invoicing Overview](oioubl-electronic-invoicing-overview.md)
- [Set Up Customers for OIOUBL](how-to-set-up-customers-for-oioubl.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
