---
title: Addresses in Australia
description: Use the Post Code feature to improve accuracy for cases in which a single postal code can include multiple cities in the same region.
ms.custom: en-AU
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.search.keywords: post code feature, address accuracy, delivery point identifier, DPID, address matching approval system, AMAS, Australian version
ms.date: 03/25/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# About addresses in the Australian version

A single postal code can include multiple cities in the same region. At the same time, cities with the same name are sometimes located in different states.  

For example, Australian postal code 4069 covers the cities of Chapel Hill and Kenmore in the state of Queensland. However, there's also a city named Chapel Hill in the state of South Australia, located in postal code 5153.

To avoid confusion and improve address accuracy, available options display when you enter data in address fields. For example, when you enter a postal code on a customer card, you can select from a list of all available cities for that postal code in the **City** field dropdown list. Likewise, when you enter a city name, you can select from a list of all available states in the **State** field dropdown list.  

To enable this functionality, you must enter the data into the **Post Code** table. You can do this manually, or you can download a copy of the Australian postal codes from the Australian Post Office website.  

To increase postal efficiency in Australia, the postal department introduced an address bar coding system in which every address is assigned a unique identifier called a Delivery Point Identifier (DPID). From the DPID, a bar code is generated and printed for each address. Companies can receive discounts on bulk mailings if they use these bar codes. To retrieve a DPID, you must connect to the local postal database that uses authorized Address Matching Approval System (AMAS) software. You can reduce your number of postal returns by validating customer addresses using the AMAS database.  

When you print an address that has a DPID, a bar code is printed together with the address. If you can't print bar codes, the DPID is printed together with the address.  

Contact your Microsoft partner for information on how to obtain AMAS software.  

## Related information

[Australia Local Functionality](australia-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
