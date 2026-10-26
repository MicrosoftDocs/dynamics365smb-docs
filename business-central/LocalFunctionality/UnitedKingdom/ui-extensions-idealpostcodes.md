---
title: Ideal Postcodes extension [UK]
description: Retrieve addresses for entities like customers, vendors, employees, and banks in the United Kingdom from the Ideal Postcodes service.
author: brentholtorf
ms.topic: get-started
ms.search.keywords: postcodes, postal, address, extension
ms.search.form: 9142,
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ms.custom: bap-template
ai-usage: ai-assisted
---

# Ideal Postcodes extension in the British version

The Ideal Postcodes extension saves time and prevents mistakes when you enter addresses for customers, vendors, bank accounts, and employees. Enter a postcode, and [!INCLUDE[prod_short](../../includes/prod_short.md)] shows a list of addresses. Select an address to fill in the address fields.

Before you start, [set up and enable the Ideal Postcodes provider](ui-extensions-setup-idealpostcodes-service.md).

## Use the Ideal Postcodes extension when you enter an address

1. Open the card page for editing, and enter a postcode in **Post Code**. The address lookup opens automatically when you validate the postcode. To open it again, choose **Lookup address from postcode** or the **Lookup Address** action.

   > [!NOTE]
   > Address lookup is available only when the provider is configured and enabled, the card is editable, and **Country/Region Code** is either empty or contains **GB**, **UK**, **NL**, **SG**, or **IE**.

1. On the **Select Address** page, select the address and confirm your selection.

   The address, city, postcode, county, and country/region fields on the card page fill in with the selected address.

## Related information

[Set up the Ideal Postcodes extension](ui-extensions-setup-idealpostcodes-service.md)  
[United Kingdom local functionality in the British version](united-kingdom-local-functionality.md)  

[!INCLUDE [footer-banner](../../includes/footer-banner.md)]