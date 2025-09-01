---
title: Sustainability certificates
description: Learn how to set up and use sustainability certificates.
author: altotovi
ms.topic: article
ms.devlang: al
ms.search.keywords: Sustainability, ESG, emission, GHG, certificate, green
ms.search.form: 
ms.date: 09/10/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Sustainability certificates

In today’s business landscape, sustainability is more than a trend - it’s a necessity. As companies strive to reduce their environmental impact and meet growing consumer demand for responsible practices, sustainability certificates are now an essential tool for validating these efforts. These certificates serve as an independent verification that a company or its products meet specific environmental, social, and governance (ESG) standards, fostering trust and transparency in the marketplace.  

Sustainability certificates offer a clear and measurable way to assess the environmental and ethical credentials of both companies and their products. By prioritizing vendors who hold recognized sustainability certifications, businesses can enhance their supply chain integrity, reduce risks, and contribute to a more sustainable future.

Sustainability certificates for companies cover a wide range of criteria, including resource efficiency, waste management, emissions reduction, and social responsibility. Similarly for products, these certifications ensure that items meet stringent environmental standards, from raw material sourcing to manufacturing processes and end-of-life disposal.

## Sustainability certificate area

The *sustainability certificate area* refers to the specific area covered by a particular certificate. Generally, this method is used to categorize similar certificates based on distinct characteristics. To create new sustainability certificate area, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sust. Certificate Areas**, and then select the related link.
2. On the **Sust. Certificate Areas** page, select **New**, and enter the **Number** and **Name** fields for new certificate area.
3. Close the page.

## Sustainability certificate standards

The *Sustainability certificate standard* refers to the specific standard for a particular certificate. Generally, it should provide third-party verified, transparent, and measurable criteria aligned with international ESG frameworks to promote responsible business practices.

To create a new sustainability certificate standard, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sust. Certificate Standards**, and then select the related link.
2. On the **Sust. Certificate Standards** page, select **New**, and enter the **Number** and **Name** fields for new certificate standard.
3. Close the page.  

## Create a sustainability certificate

To create a new sustainability certificate, follow these steps:  

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Sustainability Certificates**, and then select the related link.
2. On the **Sustainability Certificates** page, select **New**.
3. In the **Type** field, choose if this certificate is related to vendors or items, and enter the **No.** and **Name** fields.
4. In the **Area** field, choose specific **Sust. Certificate Area** option and in the **Standard** field, choose adequate **Sust. Certificate Standard**.
5. In the **Issuer** field, specify the issuer name.
Sustainability certificates are typically issued by independent third-party organizations, which can include non-profit certifying bodies, industry associations, standards organizations, or specialized sustainability certification firms. The issuers are responsible for assessing compliance with established sustainability standards.
6. If this certificate has a measurable value, enable the **Has Value** field and then fill in the **Value** field. 

> [!NOTE]
> You can also create a new sustainabilty certificate directly from the vendor or item card. In this case, the **Type** field is automatically filled in with **Item** or **Vendor** based on where you create the certificate.

### Add the sustainability certificate for vendors

To add the sustainability certificate to the vendor, follow these steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then select the related link.
2. Choose the vendor you want to work with.
3. In the **General** FastTab, select the certificate in the **Sust. Certificate No.** field. If the field doesn't display by default, select **Show more** on the **General** FastTab.
4. Close the page.  

### Add a sustainability certificate to an item

To add a sustainability certificate to an item, follow the steps:

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then select the related link.
2. Choose the item you want to work with.
3. In the **Sustainability** FastTab, select the certificate in the **Sust. Certificate No.** field. 
4. Close the page.

## Meet Digital Product Passport reporting requirements

Support for Digital Product Passport (DPP) reporting requirements empowers businesses to meet European Union sustainability regulations by capturing key environmental data in [!INCLUDE [prod_short](includes/prod_short.md)]. Structured reporting on recyclability, energy efficiency, and end-of-life handling can help enhance product transparency, support circular economy goals, and build trust with eco-conscious customers and partners. To learn more about DPP, go to the [European Union website](https://go.microsoft.com/fwlink/?linkid=2334243).

To support DPP initiatives, there are sustainability-related fields on the **Sustainability** FastTab of the **Item Card** page. The following fields are specifically related to DPP:

- **Recyclability Percentage**: Indicates the percentage of recyclable content in the product.
- **Energy Efficiency Ratings**: Captures standardized energy efficiency information, such as the product category or label (for example, A–G rating).
- **End-of-Life Information**: Provides disposal instructions, recycling options, return schemes, or environmental impact notes.

> [!NOTE]
> [!INCLUDE [prod_short](includes/prod_short.md)] doesn't generate embedded QR codes for DPP. However, it does provide data that an external QR code tool can use.

## Related information

[Sustainability management overview](finance-manage-sustainability.md)  
[Sustainability setup](finance-sustainability-setup.md)  
[Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)  
[Sustainability reports and analytics in Business Central](sustainability-reports.md)  
[Finance](finance.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[!INCLUDE[footer-include](includes/footer-banner.md)]
