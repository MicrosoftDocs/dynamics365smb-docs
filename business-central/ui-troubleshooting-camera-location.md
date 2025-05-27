---
title: "Troubleshooting: Accessing Camera and Location"
description: "This article describes how to troubleshoot access to camera and location information in Business Central."
author: brentholtorf
ms.author: bholtorf
ms.date: 04/01/2021
ms.topic: troubleshooting-general

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Troubleshooting: Accessing Camera and Location

You might come across some issues when trying to access the camera and location information of a device from [!INCLUDE[prod_short](includes/prod_short.md)]. You can find the possible causes behind these problems and how to work around them listed below.

## Device must have Camera and Location Capabilities

In order to access the camera or a user's location from a device, the device must have a physical camera or the capability to retrieve location information, respectively.

If your device has camera and location capabilities but you still encounter problems, it is possible that some drivers need updating or reinstalling. Even if you are unsure, we always recommend you update your device operating system, drivers, and browser to the latest version for the best experience.

## Access Permissions not Enabled

You must enable general access to camera and location from your device's privacy settings and explicitly give permission to  [!INCLUDE[prod_short](includes/prod_short.md)] to access them. For example, to see or change permissions for a device running on Windows, go to **Settings**, choose **Privacy**, and then **App permissions**. 

For mobile devices, you must give camera and location access permissions to the [!INCLUDE[prod_short](includes/prod_short.md)] Mobile App. To do so for an iOS device, go to **Settings**, choose **Privacy**, and then **Camera** or **Location**. For Android devices go to **Settings**, choose **Apps & Notifications**, **Advanced**, **Permission Manager**, and then **Camera** or **Location**.

In addition, if you are using [!INCLUDE[prod_short](includes/prod_short.md)] in a browser, you must also grant the [!INCLUDE[prod_short](includes/prod_short.md)] site permission to access the camera or location information. To see or change a site's permissions in the Microsoft Edge browser, go to **Settings**, choose **Site Permissions**, and then **Camera** or **Location**. Note that this might be different for other browsers.

By default, the device or browser will pop up a request to access these capabilities when the user activates them for the first time.

> [!NOTE]  
> Some old browsers do not grant access to camera and location. For example, camera is not available in Internet Explorer or the legacy Edge browser.

## Web Client Connection not Secure

The camera and location capabilities are only available when accessing the Web Client through SSL secured HTTP connections, using the `https://` URI scheme. 

The only exception is connecting to `http://localhost`, used for development and test purposes.


## Work with Virtualization Technologies

When connecting to [!INCLUDE[prod_short](includes/prod_short.md)] through Remote Desktop or another virtualization, the access to camera or location might not be available. If this is the case, use the physical system instead.

## Antivirus Software
Some antivirus software block access to camera and location by default. Remember to check your antivirus software settings.

## Related information
[Implementing the Camera in AL](/dynamics365/business-central/dev-itpro/developer/devenv-implement-camera-al)  
[Implementing the Location in AL](/dynamics365/business-central/dev-itpro/developer/devenv-implement-location-al)


[!INCLUDE[footer-include](includes/footer-banner.md)]
