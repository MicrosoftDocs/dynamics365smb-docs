---
title: Send Fraud Prevention Data (UK)
description: Business Central supports the British requirement to submit fraud prevention data to HMRC as part of Making Tax Digital. This article describes how to set up the required headers.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: fraud prevention, making tax digital, making tax digital software, hmrc, tax
ms.date: 05/18/2021
ms.author: edupont

---
# Send Fraud Prevention Data in the United Kingdom

Communication with Her Majesty's Revenue and Customs (HMRC) without fraud prevention headers is not allowed. [!INCLUDE [prod_short](../../includes/prod_short.md)] communicates with HMRC through Making Tax Digital and supports the requirement to submit data that can help prevent fraud.  

> [!IMPORTANT]
> Make sure that you have the latest version of the Making Tax Digital app. For more information, see [Making Tax Digital in the United Kingdom](making-tax-digital-submit-vat-return.md).

## Fraud prevention headers

Set up the headers in the **HMRC Fraud Prevention Headers Setup** page. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] Choose the **Get Current Headers** action to see which headers cannot be retrieved automatically.  

Fraud prevention headers are sent to HMRC whenever there is communication with the APIs at HMRC. In other words, this information is sent when one of the following actions are chosen in [!INCLUDE [prod_short](../../includes/prod_short.md)]:

* Get VAT return periods
* Submit VAT return
* Get status of submitted VAT return

When you start one of these processes, you are presented with the current header content and asked for consent before the any data is sent. If you choose to cancel, no information is sent to HMRC.

> [!NOTE]
> The **Get Current Headers** action fetches data based on the current user. That means that if you are not the user who will submit the final data to HMRC, you will see different data for those  headers that include person identifiable information (PII).

## See Also

[Making Tax Digital](making-tax-digital-submit-vat-return.md)  
[United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
[Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
[Working with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
