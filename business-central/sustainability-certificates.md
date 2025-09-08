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

The *Sustainability certificate standard* refers to the specific standard for a particular certificate. Generally, it should provide third-party verified, transparent, and measurable criteria aligned with international ESG frameworks to promote responsible business practices. To create new sustainability certificate standard, follow these steps: 

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
1. If this certificate has a measurable value, enable the **Has Value** field and enter the **Value**.   

> [!NOTE]
> You can also create a new sustainabilty directly from the vendor or item card. In this case, the **Type** field is automatically prepopulated as an Item or Vendor based on where you create the certificate.   
 
### Add the sustainability certificate for vendors

To add the sustainability certificate to the vendor follow the next steps:   

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Vendors**, and then select the related link.
2. Choose the vendor you want to work with.
3. In the **General** FastTab, select the certificate in the **Sust. Certificate No.** field. If you don't see the field by default, select the **Show more** for the **General** FastTab.
4. Close the page.  

### Add the sustainability certificate for items

To add the sustainability certificate to the item follow the steps:   

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Items**, and then select the related link.
2. Choose the item you want to work with.
3. In the **Sustainability** FastTab, select the certificate in the **Sust. Certificate No.** field. 
4. Close the page.

## Related information

- [Sustainability management overview](finance-manage-sustainability.md)  
- [Sustainability setup](finance-sustainability-setup.md)    
- [Ad-hoc analysis of sustainability data](ad-hoc-analysis-sustainability.md)    
- [Sustainability reports and analytics in Business Central](sustainability-reports.md)   
- [Finance](finance.md)    
- [Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   
[!INCLUDE[footer-include](includes/footer-banner.md)]
