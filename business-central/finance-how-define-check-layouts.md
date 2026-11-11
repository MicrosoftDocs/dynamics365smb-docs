---
title: Select a Check Layout in Business Central
description: Select a check report and layout in Business Central, compare North American check formats, and learn about MICR and check security fonts.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: print check, customize
ms.search.form: 374, 404
ms.date: 11/11/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Select a check layout in Business Central

You can design your checks to conform with the standards set by the local authorities. The United States and Canadian versions include check reports that can print in English, French, or Spanish.

The North American reports support check/stub/stub, stub/check/stub, stub/stub/check, and three-checks-per-page formats.

## Select the check report

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Report Selection - Bank Account**, and then choose the related link.
1. On the **Report Selection - Bank Account** page, in the **Usage** field, select **Check**.
1. Select one of the following report IDs. Reports in the 10000 range are available in the North American versions.

| Report ID | Report name | Description |
| --- | --- | --- |
| 1401 |Check |This report is the default report. |
| 10401 |Check (Stub/Stub/Check) |This report is designed to print checks in a stub/stub/check format. |
| 10411 |Check (Stub/Check/Stub) |This report is designed to print checks in a stub/check/stub format. |
| 10412 |Check (Check/Stub/Stub) |This report is designed to print checks in a check/stub/stub format. |
| 10413 |Three Checks per Page |This report is designed to print three checks on each page. |

After you set up check layouts, you can print checks from the **Payment Journal** page. Learn more in [Work with Checks](payables-how-work-checks.md).

To change one of these default check layouts, create a user-defined layout. Learn more in [Get started creating report layouts](ui-get-started-layouts.md).

## Use MICR and security fonts

The online version of [!INCLUDE[prod_short](includes/prod_short.md)] contains preinstalled fonts on the servers that can be used when defining check layouts. The following outlines which fonts are available and have links to detailed information by the 3rd-party suppliers of the fonts.

> [!Important]
> MICR and check security fonts in [!INCLUDE[prod_short](includes/prod_short.md)] are licensed in a font package from IDAutomation.com, Inc. These products may only be used as part of and in connection with [!INCLUDE[prod_short](includes/prod_short.md)].

In update 15.3 and later, Magnetic Ink Character Recognition (MICR) fonts are installed and available to use. Both the E-13B and the CMC-7 standards are supported. Special security fonts are also available to generate text, names, amounts, and the currency symbols such as Dollar, Euro, Pound, and Yen, which are hard to tamper with once a check is printed.

> [!NOTE]
> - For security and legal reasons, you cannot upload custom fonts to the [!INCLUDE[prod_short](includes/prod_short.md)] online environment.
> - With [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, the MICR and check security fonts from IDAutomation.com aren't available by default. You must purchase them from IDAutomation.com or another supplier. Once you have the fonts, install them on the computer that runs the [!INCLUDE[server](includes/server.md)]. As a minimum, install the fonts for the user that runs the [!INCLUDE[server](includes/server.md)] instance, that is, the service account. To install the fonts, follow the instructions from the font supplier or refer to [Add a Font](https://support.microsoft.com/en-us/office/add-a-font-b7c5f17c-4426-4b53-967f-455339c564c1).

### MICR E-13B specifications

The following illustration summarizes specifications for the MICR E-13B fonts that can be useful when calibrating fonts to be on check layouts with specific MICR printers.

:::image type="content" source="media/font_MICR_E-13B_Specifications.png" alt-text="Diagram showing MICR E-13B character dimensions for calibrating check layouts.":::

### MICR E-13B delimiter characters

:::image type="content" source="media/font-micr-letters.png" alt-text="Diagram showing the delimiter characters used with MICR E-13B fonts.":::

Learn more in the supplier's [MICR E-13B font specifications](https://www.idautomation.com/micr-fonts/e13b/).

### MICR CMC-7 specifications

The following CMC-7 fonts are available in [!INCLUDE[prod_short](includes/prod_short.md)] online:

- IDAutomationCMC7
- IDAutomationCMC7n10
- IDAutomationCMC7n25
- IDAutomationCMC7n40

The following illustration summarizes specifications for the MICR CMC-7 fonts that can be useful when calibrating fonts to be on check layouts with specific MICR printers.

:::image type="content" source="media/font_MICR_CMC-7_Specifications.png" alt-text="Diagram showing MICR CMC-7 character dimensions for calibrating check layouts.":::

### MICR CMC-7 delimiter characters

:::image type="content" source="media/font-cmc7-letters.png" alt-text="Diagram showing the delimiter characters used with MICR CMC-7 fonts.":::

Learn more in the supplier's [MICR CMC-7 font specifications](https://www.idautomation.com/micr-fonts/cmc7/).

### Secure font specifications

The following illustration summarizes specifications for check security fonts that can be useful when calibrating fonts to be on check layouts with specific MICR printers.

:::image type="content" source="media/font_check-security-font_Specifications.png" alt-text="Diagram showing check security font samples and dimensions for check layouts.":::

Learn more in the supplier's [check security font specifications](https://www.idautomation.com/security-fonts/).

Fonts for other purposes are also available in [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more in [Available fonts](ui-fonts.md).

## Related information

[Get started creating report layouts](ui-get-started-layouts.md)  
[Fonts in Business Central](ui-fonts.md)  
[Managing payables](payables-manage-payables.md)  
[Reconciling bank accounts](bank-manage-bank-accounts.md)  
[Completing period-end processes](year-how-complete-period-end-processes.md)  
[Work with Business Central](ui-work-product.md)  
[General business functionality](ui-across-business-areas.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
