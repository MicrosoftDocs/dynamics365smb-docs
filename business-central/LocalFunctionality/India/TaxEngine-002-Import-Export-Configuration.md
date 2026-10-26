---
title: Tax Engine - Import/Export Configuration
description: Import and export tax engine configuration in JSON format, and review configuration setup and file handling in Business Central for India.
author: v-debapd
ms.topic: how-to
ms.devlang: al
ms.search.keywords: India, local, IN, English, tax engine, tax engine configuration, json exchange
ms.date: 10/21/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# Tax engine - Import/Export configuration

The JSON Exchange module imports and exports tax engine configuration data in JSON format. You can transfer configuration for a tax type or for selected use cases.

## Import or export a tax type

Use this option to transfer tax type configuration, including entities, components, input parameters, and rate column setup. You can also include use cases.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Tax Types**, and then choose the related link.
1. To export, select the tax types and choose **Export Tax Type(s)**. Confirm whether to include use cases, and then save the JSON file.
1. To import, choose **Import Tax Type(s)**, select the JSON file, and confirm whether to import use cases.

## Import or export selected use cases

Use this option to transfer configuration for one or more use cases.

1. On the **Tax Types** page, select the tax type and choose **Use Cases**.
1. To export, select the use cases and choose **Export Use Case**, and then save the JSON file.
1. To import, choose **Import Use Case** and select the JSON file.

## Set up tax configuration in a company

Use assisted setup to import the tax configuration supplied by the installed tax extensions.

1. [!INCLUDE [open-search](../../includes/open-search.md)] Enter **Assisted Setup**, and then choose the related link.
1. Choose **Set up Tax Engine** to open the **Tax Engine Setup** wizard.
1. Choose **Next**.
1. If tax types already exist, choose **Append** to update the existing configuration, and then choose **Next**. This step isn't shown when the company has no tax types.
1. Choose **Finish** to apply the configuration.

> [!IMPORTANT]
> The **Replace** option deletes existing tax types before importing the supplied configuration. Export any custom configuration that you need to keep before replacing it. Importing use cases sets them to **Released** and enables them. Review the enabled use cases after the import.

## Related information

[Tax Engine Configuration of Tax Type and Tax Rate](TaxEngine-003-Tax-Configuration.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
