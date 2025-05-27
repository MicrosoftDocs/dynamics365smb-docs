---
title: Send Fraud Prevention Data (UK)
description: Business Central supports the British requirement to submit fraud prevention data to HMRC as part of Making Tax Digital. This article explains how to set up the headers.
author: brentholtorf
ms.topic: article
ms.search.keywords: fraud prevention, making tax digital, making tax digital software, HMRC, tax
ms.search.form: 10539, 743
ms.date: 02/18/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Send fraud prevention data in the United Kingdom

Communication with His Majesty's Revenue and Customs (HMRC) without fraud prevention headers isn't allowed, starting in 2021. [!INCLUDE [prod_short](../../includes/prod_short.md)] communicates with HMRC through Making Tax Digital and supports the requirement to submit data that can help prevent fraud.  

> [!IMPORTANT]
> Make sure that you have the latest version of the Making Tax Digital app. You can read about Making Tax Digital in the United Kingdom, [here](making-tax-digital-submit-vat-return.md).

The admin of the company that transmits VAT data together with fraud prevention parameters must consent one time for each web application that is used for interoperation with the HMRC VAT APIs. Otherwise, data that is collected from the user devices that are used to submit the VAT requests can't be transmitted.

> [!NOTE]
> We recommend that it's always the same person who submits data to HMRC from the same device. This way, the fraud prevention headers contain consistent information about the device.

## Fraud prevention headers

Fraud prevention headers are sent to HMRC whenever there's communication with the APIs at HMRC. In other words, this information is sent when one of the following actions is chosen in [!INCLUDE [prod_short](../../includes/prod_short.md)]:

* Get VAT return periods
* Submit VAT return
* Get status of submitted VAT return

When you start one of these processes, you're presented with the current header content and asked for consent before any data is sent. If you choose to cancel, no information is sent to HMRC.

### Headers

In this section, we provide a list of fraud prevention headers. The content is intended to help you identify any issues with fraud prevention headers for your company.  

The set of HTTP headers that must be transmitted for fraud prevention varies, depending on the architecture of the environment that is used by the company that is interoperating with MTD for VAT. The **Gov-Client-Connection-Method** header must represent the connection method that is used for the request that the company makes. The assumption is that most companies that use [!INCLUDE [prod_short](../../includes/prod_short.md)] online use the **WEB\_APP\_VIA\_SERVER** connection method.  

The **WEB\_APP\_VIA\_SERVER** connection method assumes transmission of headers as outlined in the following table.

| HTTP header | Description |
|--|--|
| `Gov-Client-Public-IP` | The public IP address (IPv4 or IPv6) that the originating device makes the request from. |
| `Gov-Client-Public-Port` | The public TCP port that the originating device uses when it initiates the request. |
| `Gov-Client-Device-ID` | An identifier that is unique to an originating device. |
| `Gov-Client-User-IDs` | A key-value data structure that contains the user identifiers. |
| `Gov-Client-Timezone` | The local time zone of the originating device. |
| `Gov-Client-Local-IPs` | A list of all local IP addresses (IPv4 and IPv6) that are available to the originating device. |
| `Gov-Client-Screens` | Information that is related to the originating device's screens. The following fields are included:<ul><li> <strong>width</strong> – The reported width of the screen, in pixels</li><li><strong>height</strong> – The reported height of the screen, in pixels</li><li><strong>scaling-factor</strong> – The reported scaling factor of the screen. For example, a high-pixel density screen could have a scaling factor of 2, while a standard definition screen could have a scaling factor of 1.</li><li><strong>color-depth</strong> – The color depth of the screen, in bits.</li></ul> |
| `Gov-Client-Window-Size` | The number of pixels of the window on the originating device where the user initiated (directly or indirectly) the API call to HMRC. |
| `Gov-Client-Browser-Plugins` | A list of browser plug-ins on the originating device. |
| `Gov-Client-Browser-JS-User-Agent` | The JavaScript-reported user agent string from the originating device. |
| `Gov-Client-Browser-Do-Not-Track` | A value that indicates whether the **Do Not Track** option is turned on in the browser. |
| `Gov-Client-Multi-Factor` | A list of key-value data structures that contains details of the multifactor authentication (MFA) statuses that are related to the API call. |
| `Gov-Vendor-Version` | A key-value data structure of the software versions that are involved in handling a request. |
| `Gov-Vendor-License-IDs` | A key-value data structure of hashed license keys that are related to the vendor software that initiated the API request on the originating device. |
| `Gov-Vendor-Public-IP` | The public IP address of the servers that the originating device sent its requests to. |
| `Gov-Vendor-Forwarded` | A list that details the hops over the internet between services that terminate Transport Layer Security (TLS). |

## Populating headers

The following table explains how to identify all automatically populated headers. The guidance is based on an example from one of our reselling partners in the UK. The content is intended to help you set up fraud prevention headers for your company.  

|Header|Description  |Example  |Notes  |
|---------|---------|---------|---------|
|`Gov-Client-Browser-Do-Not-Track` |`true` or `false`, depending on your browser's setting for tracking.         | `Gov-Client-Browser-Do-Not-Track: false`        | `false` by default. Check the value in your browser's settings. You can also search online for *do not track option in (name of browser)*.       |
|`Gov-Client-Browser-JS-User-Agent` | JavaScript-reported user agent string from the originating device. Pass the value as reported by the browser, usually in this format: `product / product-version (system-information) platform (platform-details) extensions`|`Gov-Client-Browser-JS-User-Agent: Mozilla/5.0 (iPad; U; CPU OS 3 2_1 like Mac OS X; en-us) (KHTML, like Gecko) Mobile/7B405`| Search for *device information online* to get the information about the device and the browser. Combine the values using the described format. |
|`Gov-Client-Browser-Plugins`| A list of browser plugins on the originating device. Every value in the list must be percent encoded (opens in a new tab), not percent encode separators (commas).  |`Gov-Client-Browser-P1ugins: Shockwave%20F1ash Chromium%20PDF%20Viewer`| Search for *device information online* to get the information about the device and the browser. Separate all the values with commas. Then search for *encode url online*.        |
|`Gov-Client-Local-Ips` |  IP addresses.       |<ul><li>`Gov-Client-Local-IPs:  10 .1. 2.3`</li><li>`Gov-Client-Local-IPs: 10.1. 2. 3,10.3.4. 2`</li><li>`Gov-Client-Local-IPs: 65f466e3-1f39-4ca5-957f-65e231804f91.local`</li></ul>| If you don't know your IP address, search for *how to identify my local IP*. Alternatively, use a PowerShell command as mentioned in the following table: <br>`Test-Connection -ComputerName (hostname) -Count 1 \| Select IPV4Address`|
|`Gov-Client-Public-Port`|The public TCP port used by the originating device when initiating the request. It must not be a server port, such as 80 for HTTP connections or 443 for HTTPS connections. The valid range is between 0 and 65535.|`57961`|Run ```netstat -a``` and see the TCP connection. For example, if your IP address is 192.168.45.2 and you see an entry for 192.168.45.2:57961, it means that port number 57961 is open and possibly in use. You can choose this value.|
|`Gov-Client-Screens`|Information about the originating device's screen. These fields should be submitted as a list of key-value data structures, and you can see a description of the keys in the table in the [Headers](#headers) section. |`Gov-Client-Screens: width=1920&height=1080&sca1ing-factor=1.25&colour-depth=16`|Find the details about your monitor in the display settings. Combine the values using the format.|
|`Gov-Vendor-Public-IP`|The public IP address of the servers the originating device sent their requests to.|`Gov -Vendor-Public-IP: 203.0.113.6`|Search for *what is my public ip address?*.|
|`Gov-Vendor-Forwarded`|A list that details balance of payments over the internet between services that terminate Transport Layer Security (TLS).|`Gov-vendor-Forwarded:by=203.0.113.6&for=198.51.100.0`|`by` = public ID. `for` = local IP.|

## IP addresses

Starting in 2022, you must specify an endpoint for the service that your company uses to extract and submit the IP address of the user who sends the VAT report. This is a requirement of HMRC so that they can validate the sender. The endpoint must be specified in the **User IP Address Service** field in the **VAT Report Setup** page. Learn about setting up VAT reporting, [here](../../finance-setup-vat.md#set-up-vat-reporting).  

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
