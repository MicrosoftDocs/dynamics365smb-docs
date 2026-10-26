---
title: E-Way Bill
description: Review e-way bill information and workflows for goods transportation, including document details and related actions in Business Central for India.
author: v-debapd
ms.topic: article
ms.devlang: al
ms.search.keywords: India, local, IN, English, E-Way bill, template generation
ms.date: 10/21/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# E-Way Bill

Use the E-Way Bill template to export transaction information for goods transportation. Confirm the applicable E-Way Bill requirements for your transaction before preparing the submission.

- Business user is able to generate excel file from system, which will be helpful for them to enter data into E-Waybill JSON Preparation tool. Business user can copy and paste data from excel sheet exported from system to preparation tool.
- Transactions posted through Journals aren't a part of E-Waybill template report. User will be able to generate E-Waybill template against transactions posted from documents only.
- User will be able to generate E-Waybill for movement of goods for Transfers (shipment), Sales, and Purchase transactions. System only considers Items and FA with GST Group Type as 'Goods' in this report.

## Generate an E-Way Bill template

- E-Way Bill template feature enables the user to generate excel file from system, which will be helpful for them to enter data into E-Waybill JSON Preparation tool.

  1. Update **GST Registration No.** and **State Code** for the **Shipping Agent**, and specify **Transportation Mode** on the **Transport Method**.
  1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **E-Way Bill File Format**, and then choose the related link.
  1. Fill in the fields on the request page as described in the following table, and then choose **OK**.

     |Field|Description|
     |---------|---------|
     |**Start Date**|Specifies the starting date of the report.|
     |**End Date**|Specifies the ending date of the report.|
     |**Location GST Reg. No.**|Specifies the GST registration number for which the report is generated.|
     |**Transaction Type**|Select the relevant Transaction Type.|
     |**Source Type**|Specify the relevant source type.|
     |**Source No.**|Specify the relevant source number.|

The report requires both dates, a location registration number, and a transaction type. The start date can't be later than the end date. For a transfer, leave **Source No.** blank. The report downloads an Excel workbook; it doesn't submit an E-Way Bill.

## Related information

[GST input credit adjustment](GST-Input-Tax-Credit-Adjustment.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
