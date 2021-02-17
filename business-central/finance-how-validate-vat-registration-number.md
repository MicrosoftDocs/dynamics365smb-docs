---
title: Validate VAT Registration Numbers
description: Let Business Central use the VIES service to validate VAT registration numbers for you automatically.
author: kielkenny
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.reviewer: edupont
ms.search.keywords: VAT, posting, tax, value-added tax
ms.date: 10/01/2020
ms.author: andregu

---

# Validate VAT Registration Numbers

It is important that the VAT registration numbers you have for customers, vendors, and contacts are valid. For example, companies sometimes change their tax liability status, and in some countries tax authorities might ask you to provide reports, such as the EC Sales List report, that list the VAT registration numbers you use when you do business.

The European Commission provides the VIES VAT Number Validation service on its website, which is public and free. [!INCLUDE[prod_short](includes/prod_short.md)] can save you a step and let you use the VIES service to validate and track VAT numbers for customers, vendors, and contacts straight from the customer, vendor, and contact cards. The service in [!INCLUDE[prod_short](includes/prod_short.md)] is named **EU VAT Reg. No. Validation Service**. The service is available on the **Service Connections** page, and you can start using it right away. The service connection is free, and sign-up is not required.

## To verify VAT registration numbers

In order to enable the **EU VAT Reg. No. Validation Service** open the entry in the **Service Connection** page. The **Service Endpoint** field should already be populated. If not, you can use the **Set Default Endpoint** action. Then set the **Enabled** field and you are good to go.

> [!NOTE]
> To enable the EU VAT Reg. No. Validation Service, you must have administrator permissions.

When you use our service connection, we record a history of VAT numbers and verifications for each customer, vendor, or contact, in the **VAT Registration Log**, so you can easily track them. The log is specific to each customer. For example, the log is useful for proving that you have verified that the current VAT number is correct. When you verify a VAT number, the **Request Identifier** column in the log will reflect that you have taken action.

You can view the VAT Registration log on the Customer, Vendor, or Contact cards, on the **Invoicing** FastTab, by choosing the lookup button in the **VAT Registration No.** field.  

There are a couple of things to note about the VIES VAT Number Validation service:

* The service uses the http protocol, which means that data transferred through the service is not encrypted.  
* You may experience downtime for this service for which Microsoft is not responsible. The service is part of a broad EU network of national VAT registers.

> [!IMPORTANT]
> It is your responsibility to check that the data is valid. On occasion, data with errors is returned by the VIES VAT Number Validation service. If validation fails, validate the VAT registration numbers on the [web site](https://ec.europa.eu/taxation_customs/vies/), print the result or save it to a shared location, and then add the link to the record for your customer, vendor, or contact. For more information, see [Manage Attachments, Links, and Notes on Cards and Documents](ui-how-add-link-to-record.md).

## See Also

[Set Up Value-Added Tax](finance-setup-vat.md)  
[Setting Up Unrealized Value Added Tax](finance-setup-unrealized-vat.md)  
[Report VAT to a Tax Authority](finance-how-report-vat.md)  
[Work with VAT on Sales and Purchases](finance-work-with-vat.md)  
[Local functionality in Business Central](about-localization.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
