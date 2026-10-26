---
title: Send Fraud Prevention Data in the UK
description: Learn how Business Central collects fraud prevention data for Making Tax Digital in the United Kingdom and how to set up the IP address service.
author: brentholtorf
ms.topic: concept-article
ms.search.keywords: fraud prevention, making tax digital, making tax digital software, HMRC, tax
ms.search.form: 10539, 743
ms.date: 10/19/2026
ai-usage: ai-assisted
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# Send fraud prevention data in the United Kingdom

Communication with His Majesty's Revenue and Customs (HMRC) without fraud prevention headers isn't allowed, starting in 2021. [!INCLUDE [prod_short](../../includes/prod_short.md)] communicates with HMRC through Making Tax Digital and supports the requirement to submit data that can help prevent fraud.  

> [!IMPORTANT]
> Make sure that you have the latest version of the Making Tax Digital app. You can read about Making Tax Digital in the United Kingdom, [here](making-tax-digital-submit-vat-return.md).

Before you communicate with HMRC, turn on **Enabled** on the **Making Tax Digital** FastTab of the **VAT Report Setup** page and accept the consent prompt. [!INCLUDE [prod_short](../../includes/prod_short.md)] blocks MTD requests if you turn off this setting. This consent is separate from granting the application authority to interact with HMRC.

> [!NOTE]
> We recommend that it's always the same person who submits data to HMRC from the same device. This way, the fraud prevention headers contain consistent information about the device.

## Fraud prevention headers

Fraud prevention headers accompany MTD API requests to HMRC. For example, [!INCLUDE [prod_short](../../includes/prod_short.md)] sends these headers when you:

* Retrieve VAT return periods.
* Submit a VAT return.
* Retrieve submitted VAT returns, VAT liabilities, or VAT payments.
* Request or refresh an access token.

The **Communicating with HMRC** window collects the browser information needed for the headers. Keep this window open until collection finishes. It doesn't display a header preview or ask for consent for each request.

### Headers

In this section, we provide a list of fraud prevention headers. The content is intended to help you identify any issues with fraud prevention headers for your company.  

The set of HTTP headers that you must transmit for fraud prevention varies, depending on the architecture of the environment that your company uses to interoperate with MTD for VAT. The MTD app sets the `Gov-Client-Connection-Method` header to `WEB_APP_VIA_SERVER`.

The current MTD app generates the headers in the following table. It doesn't generate `Gov-Client-Public-Port`, `Gov-Client-Local-IPs`, `Gov-Client-Browser-Plugins`, or `Gov-Client-Multi-Factor`.

| HTTP header | Description |
|--|--|
| `Gov-Client-Public-IP` | The public IP address (IPv4 or IPv6) that the originating device makes the request from. |
| `Gov-Client-Public-IP-Timestamp` | The timestamp captured by the browser when it starts collecting fraud prevention data. |
| `Gov-Client-Device-ID` | An identifier that is unique to an originating device. |
| `Gov-Client-User-IDs` | A key-value data structure that contains the user identifiers. |
| `Gov-Client-Timezone` | The local time zone of the originating device. |
| `Gov-Client-Screens` | Screen information returned by the browser: `width` and `height` in pixels, and `colour-depth` in bits. The app sets `scaling-factor` to `1`. |
| `Gov-Client-Window-Size` | The number of pixels of the window on the originating device where the user initiated (directly or indirectly) the API call to HMRC. |
| `Gov-Client-Browser-JS-User-Agent` | The JavaScript-reported user agent string from the originating device. |
| `Gov-Client-Browser-Do-Not-Track` | A value that indicates whether the **Do Not Track** option is turned on in the browser. |
| `Gov-Vendor-Product-Name` | The Business Central product name, with an on-premises suffix for on-premises installations. |
| `Gov-Vendor-Version` | A key-value data structure of the software versions that are involved in handling a request. |
| `Gov-Vendor-License-IDs` | A key-value data structure containing a hash derived from tenant identifiers and license dates. |
| `Gov-Vendor-Public-IP` | The public IP address of the servers that the originating device sent its requests to. |
| `Gov-Vendor-Forwarded` | A list that details the hops over the internet between services that terminate Transport Layer Security (TLS). |

## How headers are populated

[!INCLUDE [prod_short](../../includes/prod_short.md)] automatically generates the headers. You don't need to assemble browser information, choose a TCP port, or enter header values manually.

The app collects browser and device information through the **Communicating with HMRC** window. It derives user identifiers, license identifiers, and product information in Business Central. For `Gov-Vendor-Forwarded`, `by` is the server's public IP address and `for` is the client's public IP address.

The following table helps you identify header values when troubleshooting. Examples illustrate the formats, not values to copy into your configuration. The table describes the current app's behavior, rather than the complete HMRC header requirements.

| Header | Description | Example | Notes |
|--|--|--|--|
| `Gov-Client-Browser-Do-Not-Track` | A Boolean value derived from the browser's tracking preferences. | `Gov-Client-Browser-Do-Not-Track: false` | The app reads the browser's Do Not Track properties automatically. Check the browser's tracking preferences when investigating this value. Don't assume every browser has the same default. |
| `Gov-Client-Browser-JS-User-Agent` | The user agent string reported by the browser. | `Gov-Client-Browser-JS-User-Agent: Mozilla/5.0 (iPad; U; CPU OS 3_2_1 like Mac OS X; en-us) AppleWebKit/531.21.10 (KHTML, like Gecko) Mobile/7B405` | This illustrative string identifies an older browser. The app uses the current browser's `navigator.userAgent` value without asking you to assemble device information. |
| `Gov-Client-Browser-Plugins` | Information about browser plugins. | Not generated by the current app. | The current app doesn't collect a plugin list. You don't need to assemble or encode a list for its standard workflow. |
| `Gov-Client-Local-IPs` | Local IP addresses of the originating device. | Not generated by the current app. | A local IP address isn't the same as the public address in `Gov-Client-Public-IP`. Running a local IP lookup doesn't populate this header in the current app. |
| `Gov-Client-Public-Port` | The public TCP source port used for the request. | Not generated by the current app. | Don't choose an arbitrary port from `netstat` output. The current app doesn't provide a setting for this header. |
| `Gov-Client-Screens` | Screen width, height, scaling factor, and colour depth. | `Gov-Client-Screens: width=1920&height=1080&scaling-factor=1&colour-depth=24` | The app reads `window.screen.width`, `window.screen.height`, and `window.screen.colorDepth`. It sets `scaling-factor` to `1`, rather than reading the display scaling setting. |
| `Gov-Vendor-Public-IP` | The public IP address of the server handling the request. | `Gov-Vendor-Public-IP: 203.0.113.6` | Online environments get this value from tenant settings. On-premises environments use the configured IP address service. A public IP lookup on your own device might return a different address. |
| `Gov-Vendor-Forwarded` | The server and client public IP addresses for the request. | `Gov-Vendor-Forwarded: by=203.0.113.6&for=198.51.100.10` | The app generates `by` from the server's public IP and `for` from the client's public IP. It adds a value only when both addresses are available. |

## IP addresses

Starting in 2022, you must specify an endpoint for the service that your company uses to extract and submit the IP address of the user who sends the VAT report. This requirement comes from HMRC so that they can validate the sender. Specify the endpoint in the **User IP Address Service** field on the **Making Tax Digital** FastTab of the **VAT Report Setup** page. Learn more in [Set up VAT reporting](../../finance-setup-vat.md#set-up-vat-reporting).

When you enter or test a nonblank endpoint, Business Central checks that the service returns a public IP address for both the server and the client. On-premises installations require this field to be filled in before the app generates fraud prevention headers. For online environments, the app gets the server's public IP address from tenant settings.

Your company can sign up for any of the following endpoints:

* [https://api.db-ip.com/v2/free/self](https://api.db-ip.com/v2/free/self)  
* [https://www.cloudflare.com/cdn-cgi/trace](https://www.cloudflare.com/cdn-cgi/trace)  
* [https://api.ipify.org](https://api.ipify.org)  
* [https://jsonip.com](https://jsonip.com)  

> [!IMPORTANT]
> The **User IP Address Service** field is available in version 20.1 and later. Your admin can manage your organization's version of [!INCLUDE [prod_short](../../includes/prod_short.md)] in the admin center.

## Related information

- [Making Tax Digital](making-tax-digital-submit-vat-return.md)  
- [United Kingdom Local Functionality](united-kingdom-local-functionality.md)  
- [Customizing [!INCLUDE[prod_short](../../includes/prod_short.md)] Using Extensions](../../ui-extensions.md)  
- [Work with [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
