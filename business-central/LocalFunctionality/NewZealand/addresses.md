---
title: Addresses in New Zealand
description: Learn how to use the address bar coding system, where each address is assigned a unique Delivery Point Identifier (DPID) to improve postal efficiency.
author: brentholtorf
ms.topic: article
ms.devlang: al
ms.search.keywords: address bar coding, DPID, delivery point identifier, New Zealand version
ms.date: 05/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Addresses in the New Zealand version

A single postal code can include multiple cities in the same region.  

At the same time, cities with the same name are sometimes located in different regions.  

To avoid confusion and improve address accuracy, available options display when you enter data in address fields. For example, when you enter a postal code on a customer card, you can select from a list of all available cities for that postal code in the **City** field drop-down list. Likewise, when you enter a city name, you can select from a list of all available regions in the **Region** field drop-down list.  

To enable this functionality, you must enter the data into the **Post Code** table. You can do this manually, or you can download a copy of the New Zealand postal codes for New Zealand.  
  
To increase postal efficiency in New Zealand, the postal department introduces an address bar coding system in which every address is assigned a unique identifier called a Delivery Point Identifier (DPID). From the DPID, a bar code is generated and printed for each address. Companies can receive discounts on bulk mailings if they use these bar codes. To retrieve a DPID, you must connect to the local postal database that uses authorized Address Matching Approval System (AMAS) software. You can reduce your number of postal returns by validating customer addresses using the AMAS database.  

When you print an address that has a DPID, a bar code is printed together with the address. If you can't print bar codes, the DPID is printed together with the address.  

Contact your Microsoft partner for information on how to obtain AMAS software.  

## Related information

[New Zealand Local Functionality](new-zealand-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
