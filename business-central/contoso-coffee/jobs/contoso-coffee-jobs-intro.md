---
title: Introduction to Contoso Coffee Project Management
description: Set up Contoso Coffee project demo data to explore installation, recurring maintenance, resources, and project planning in Business Central.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 11/12/2026
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Introduction to Contoso Coffee project management

Contoso Coffee is a fictitious company that produces consumer and commercial coffee makers. The **Contoso Coffee** apps for [!INCLUDE [prod_short](../../includes/prod_short.md)] add demo data that you can use to learn how to use the Project Management capabilities.

This app provides several elements that are used for the main walkthroughs:

- An installer resource for project tasks.
- Machine, consumable, supply, and service-type items for project planning lines.
- Projects for installation, recurring maintenance, and a software update.

> [!IMPORTANT]
> Generate the **Job** module before you start the walkthrough. Generation creates the projects and planning lines and posts opening stock for the machine item. Installing the apps or generating only setup data doesn't create these records.

## Set up Contoso Coffee project management data

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Once the relevant apps are installed, open the [Contoso Demo Tool](https://businesscentral.dynamics.com/?page=5194) page, select **Job**, and choose **Configure**. This action opens **Contoso Coffee Project Demo Data**. The following table describes the settings:

|Field  |Description  |
|---------|---------|
|**Customer No.**|Specifies the customer for the generated projects. The default is **10000**.|
|**Item Machine No.**|Specifies the machine used on project planning lines. The default is **S-210, S-210 Semi-Automatic**.|
|**Item Consumable No.**|Specifies the consumable used in the installation project. The default is **F-100, Remote pump**.|
|**Item Service No.**|Specifies the service-type item used for project fees. The default is **SER203, Project Fee**.|
|**Item Supply No.**|Specifies the supply item for project scenarios. The default is **F-101, Paper Coffee Cups**.|
|**Resource No.**|Specifies the installer resource used on project tasks. The default is **RESOURCE3**.|
|**Job Posting Group**|Specifies the posting group used on the generated projects.|
|**Project Location**|Specifies the location for project items and planning lines. The default is **MAIN**.|

For shared settings such as the starting year, price factor, and rounding precision, configure the **Common** module. Learn more in [Set up Contoso Coffee data](../contoso-coffee-intro.md#set-up-contoso-coffee-data).

When you're ready, return to **Contoso Demo Tool**, select **Job**, and choose **Generate**. Required dependency modules are generated automatically. The walkthrough uses the default identifiers. If you configure different identifiers, use your values instead.

## Related information

[Walkthrough of projects and project management](contoso-coffee-jobs-basic.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
