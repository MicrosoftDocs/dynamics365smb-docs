---
title: Set up the Ideal Postcodes Extension [UK]
description: Learn how to configure the Ideal Postcodes extension in the British version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: idealpostcodes, postcodes, extension
ms.search.form: 9142,
ms.date: 04/09/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Set up the Ideal Postcodes extension

This extension makes it easy to enter addresses in the United Kingdom (UK) for entities like customers, contacts, employees, vendors, bank accounts, and so on.

The Ideal Postcodes extension uses the **Ideal Postcodes** API to find addresses in postcodes in the UK. To use the extension, you need a an Ideal Postcodes account, a plan, and an API Key for the Ideal Postcodes API. We help you access the latest plans when you set up the Ideal Postcodes extension in [!INCLUDE [prod_short](../../includes/prod_short.md)].

Plans are based on use, or what are sometimes referred to as "calls." A call, in this case, is when [!INCLUDE [prod_short](../../includes/prod_short.md)] displays a list of addresses in a postcode. Depending on how often you add addresses, choose the plan that's best for you.

To learn more about Ideal Postcodes, visit their [website](https://ideal-postcodes.co.uk/?_gl=1*fgtk99*_gcl_au*MTM5OTA3OTA0My4xNzc1NzIyOTg2*_ga*MTQxNjg3NjMxMi4xNzc1NzIyOTg2).

## Get started

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Connections**, and then choose the related link.
1. On the **Service Connections** page, choose **UK Postcode Service**.
1. On the **Postcode provider configuration page**, choose **Disabled**.
1. On the **Postal code service selection** page, choose **IdealPostcodes**.
1. On the **Ideal Postcodes Provider Setup** page, choose **Get API Key** to open the **Plans** page on the website for the **IdealPostcodes** API.

   > [!NOTE]
   > You might need to allow pop-ups in your browser.

1. Create an Ideal Postcodes account, and purchase a plan.
1. Open the Ideal Postcodes account dashboard, and copy the API key.
1. On the **Ideal Postcodes Provider Setup** page:

   1. In the **API Key** field, enter the API key.
   1. Read the **Terms & Conditions**.
   1. Select the **Enabled** checkbox, and then choose **OK**.

1. To verify that your API key works, choose **Test Connection**.

   > [!NOTE]
   > If you're working in a sandbox environment, your Ideal Postcodes extension must allow HTTPClient requests. To verify that setting, open the **Extension Management** page, find the Ideal Postcodes extension, and then make sure that the **Allow HttpClient Requests** toggle is turned on.

1. On the **Service Connections** page, verify that the **Address Provider** field contains **Ideal Postcodes**. If it does, the service is ready to use.

## Related information

[Ideal Postcodes extension in the British version](ui-extensions-idealpostcodes.md)  
[United Kingdom local functionality in the British version](united-kingdom-local-functionality.md)  

[!INCLUDE [footer-banner](../../includes/footer-banner.md)]
