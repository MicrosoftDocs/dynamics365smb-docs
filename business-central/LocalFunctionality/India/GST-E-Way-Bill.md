---
title: E-Way Bill
description: Learn how to generate and manage E-Way Bills for goods transportation in India using Business Central.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, E-Way bill, template generation
ms.date: 19/06/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# E-Way Bill

An electronic way bill or E-Way Bill is essential for the transport of goods that are worth more than INR 50,000. There are also some goods for which an E-Way bill is essential even if the amount doesn't exceed INR 50,000. E-Way Bill Template is designed to meet the formats or requirements provided by government.

- Business user is able to generate excel file from system, which will be helpful for them to enter data into E-Waybill JSON Preparation tool. Business user can copy and paste data from excel sheet exported from system to preparation tool.
- Transactions posted through Journals aren't a part of E-Waybill template report. User will be able to generate E-Waybill template against transactions posted from documents only.
- User will be able to generate E-Waybill for movement of goods for Transfers (shipment), Sales, and Purchase transactions. System only considers Items and FA with GST Group Type as 'Goods' in this report.

## E-Way Bill template generation

- E-Way Bill template feature enables the user to generate excel file from system, which will be helpful for them to enter data into E-Waybill JSON Preparation tool.

  1. Choose the ![Search for Page or Report.](image/search_small.png "Search for Page or Report icon") icon, enter **E-Way Bill File Format**, and then choose the related link.
  1. GST Registration No. and State Code should be updated for **Shipping Agent**.
  1. Transportation Mode field shouldn't be blank in **Transport Method**
  1. Select the following information in the request page and select OK to generate the report

     |Field|Description|
     |---------|---------|
     |**Start Date**|Specifies the starting date of the report.|
     |**End Date**|Specifies the ending date of the report.|
     |**Location Registration No.**|Specifies the GST registration number for which report is generated.|
     |**Transaction Type**|Select the relevant Transaction Type.|
     |**Source Type**|Specify the relevant source type.|
     |**Source No.**|Specify the relevant source number.|

## Related information

[GST Input Cedit Adjustment](GST-Input-Tax-Credit-Adjustment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
