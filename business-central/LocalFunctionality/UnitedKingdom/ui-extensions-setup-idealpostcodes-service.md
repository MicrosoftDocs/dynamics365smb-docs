---
title: Set up the Ideal Postcodes Extension [UK]
description: Learn how to configure the Ideal Postcodes extension in the British version of Business Central.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: idealpostcodes, postcodes, extension
ms.search.form: 9142,
ms.date: 10/19/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up the Ideal Postcodes extension

This extension makes it easy to enter addresses in the United Kingdom (UK) for customers, contacts, employees, vendors, and bank accounts.

The Ideal Postcodes extension uses the **Ideal Postcodes** API to find addresses in postcodes in the UK. To use the extension, you need an Ideal Postcodes account, a plan, and an API Key for the Ideal Postcodes API. We help you access the latest plans when you set up the Ideal Postcodes extension in [!INCLUDE [prod_short](../../includes/prod_short.md)].

Plans are based on use, or what are sometimes referred to as "calls." A call, in this case, is when [!INCLUDE [prod_short](../../includes/prod_short.md)] displays a list of addresses in a postcode. Depending on how often you add addresses, choose the plan that's best for you.

To learn more, visit the [Ideal Postcodes website](https://ideal-postcodes.co.uk/).

## Get started

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Service Connections**, and then choose the related link.
1. On the **Service Connections** page, choose **Postcode Service**.
1. Open the **Address Provider** lookup, and choose **IdealPostcodes**.
1. On the **IdealPostcodes Provider Setup** page, choose **Get API Key** to open the provider's pricing page.

   > [!NOTE]
   > You might need to allow pop-ups in your browser.

1. Create an Ideal Postcodes account, and purchase a plan.
1. Get the API key from your Ideal Postcodes account.
1. On the **IdealPostcodes Provider Setup** page, enter the key in **API Key**.
1. Open and read **Terms and conditions**, and then select **Enabled**. You must provide an API key and open the terms before you can enable the provider.
1. Optionally, turn on **Remove the organisation name from address** to remove an organisation name when it appears as the first address line.
1. Choose **Test Connection**. A successful test displays the message "Connection test was successful."
1. Choose **OK** to close the setup page and confirm your provider selection.

> [!IMPORTANT]
> The extension must be allowed to make outbound HTTP requests. On **Extension Management**, select **IdealPostcodes**, open its configuration, and turn on **Allow HttpClient Requests**. This requirement also applies in sandbox environments. If a connection test fails, check this setting and your API key, and then test again. A response code of 0 alone doesn't identify the cause of the failure.

## Related information

[Ideal Postcodes extension in the British version](ui-extensions-idealpostcodes.md)  
[United Kingdom local functionality in the British version](united-kingdom-local-functionality.md)  

[!INCLUDE [footer-banner](../../includes/footer-banner.md)]
