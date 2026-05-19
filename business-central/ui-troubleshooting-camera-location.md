---
title: Troubleshooting - Accessing camera and location
description: This article describes how to troubleshoot access to camera and location information in Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.date: 04/07/2026
ms.topic: troubleshooting-general
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Troubleshooting: accessing camera and location

You might come across some issues when trying to access the camera and location information of a device from [!INCLUDE[prod_short](includes/prod_short.md)]. This article lists some possible causes and how to work around them.

## Device must have camera and location capabilities

To access the camera or a user's location from a device, the device must have a physical camera or the capability to retrieve location information, respectively.

If your device has camera and location capabilities but problems continue, you might need to update or reinstall some drivers. We always recommend that you update your device operating system, drivers, and browser to the latest version.

## Access permissions not enabled

You must enable general access to camera and location from your device's privacy settings and explicitly give permission to  [!INCLUDE[prod_short](includes/prod_short.md)] to access them. For example, to see or change permissions for a device running on Windows, go to **Settings**, choose **Privacy**, and then **App permissions**. 

For mobile devices, you must give camera and location access permissions to the [!INCLUDE[prod_short](includes/prod_short.md)] Mobile App. To do so for an iOS device, go to **Settings**, choose **Privacy**, and then **Camera** or **Location**. For Android devices go to **Settings**, choose **Apps & Notifications**, **Advanced**, **Permission Manager**, and then **Camera** or **Location**.

In addition, if you're using [!INCLUDE[prod_short](includes/prod_short.md)] in a browser, you must also grant the [!INCLUDE[prod_short](includes/prod_short.md)] site permission to access the camera or location information. To access or change a site's permissions in the Microsoft Edge browser, go to **Settings**, choose **Site Permissions**, and then **Camera** or **Location**. These steps might differ for other browsers.

By default, the device or browser shows a request to access these capabilities when you activate them for the first time.

> [!NOTE]  
> Some older browsers don't grant access to camera and location. For example, camera isn't available in Internet Explorer or the legacy Microsoft Edge browser.

## Web client connections not secure

The camera and location capabilities are only available when accessing the Web Client through SSL secured HTTP connections, using the `https://` URI scheme. 

The only exception is connecting to `http://localhost`, used for development and test purposes.

## Work with virtualization technologies

When connecting to [!INCLUDE[prod_short](includes/prod_short.md)] through Remote Desktop or another virtualization, access to camera or location might not be available. Use the physical system instead.

## Antivirus software

Some antivirus software blocks access to camera and location by default. Remember to check your antivirus software settings.

## Related information

[Implementing the Camera in AL](/dynamics365/business-central/dev-itpro/developer/devenv-implement-camera-al)  
[Implementing the Location in AL](/dynamics365/business-central/dev-itpro/developer/devenv-implement-location-al)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
