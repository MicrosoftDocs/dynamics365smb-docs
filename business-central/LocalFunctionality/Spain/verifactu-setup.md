---
title: VERI*FACTU with External Service Integration [ES]
description: Configure the B2Brouter connector for external VERIFACTU integration in Business Central, including API credentials, project settings, and sandbox mode.
author: altotovi
ms.topic: how-to
ms.devlang: al
ms.search.keywords: Verifactu, SFI, e-invoice, Spanish version, b2brouter connector
ms.date: 10/20/2026
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---

# VERI\*FACTU with external service integration

VERI\*FACTU is a regulatory framework introduced by the Spanish government to modernize and secure electronic invoicing systems. Its primary goal is to combat tax fraud and enhance transparency in business transactions. The framework is governed by Royal Decree 1007/2023, later amended by Royal Decree 254/2025, and forms part of Spain’s broader Anti-Fraud Law 11/2021.

VERI\*FACTU refers to a "verifiable invoicing system"—a type of computerized invoicing system (SIF) that can optionally send invoice records in real time to the Spanish Tax Agency (AEAT).

Under the Spanish regulatory framework, companies must adopt a compliant invoicing approach; however, the setup itself is optional, and each company can choose the approach that applies to them. Depending on company size and applicable requirements, businesses can either use the **SII** (Immediate Information Supply) system or **VERI\*FACTU**, but not both at the same time. While one of these approaches is mandatory for compliance, it's up to each company to decide which one to adopt.

Businesses in Spain may choose to use the [SII system for VAT reporting](sii-setup.md), in which case VERI\*FACTU (SIF) rules don't apply to them. SII can be enforced for large companies with an annual turnover exceeding defined thresholds, although businesses may also opt in voluntarily. In all other cases, companies are required to comply with the SIF framework through VERI\*FACTU. Learn more about how to enable embedded VERI\*FACTU mode in [Enable real-time invoice reporting with embedded VERI\*FACTU](enable-real-time-invoice-reporting.md).

## Set up VERI\*FACTU

Dynamics 365 Business Central supports VERI\*FACTU frameworks using integration with the B2Brouter API through our default connector. To set up this mode, follow these steps:

### Disable SII module

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SII Setup**, and then select the related link.  
1. On the **General** FastTab, be sure the **Enabled** field isn't selected.  

Learn more in [SII setup](sii-setup.md), which provides more information about how to set up the SII.

### Enable B2BRouter connector

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **E-Document Services**, and then select the related link.
1. Choose the **Install E-Documents integration from Marketplace** action to open the **Microsoft Marketplace apps** page.  
1. Choose the **B2BRouter** connector, and then select the **View on Marketplace** action.  
1. Install the app from the Marketplace.
1. On the **E-Document Service** page, change the **Service Integration** to **B2BRouter**.  
1. On the **E-Document Service** page, select the **Setup Service Integration** action.
1. On the **B2Brouter Setup** page, select **Staging Mode** if you want to use the sandbox environment.
1. Enter the **API Key** and **Project** for the selected environment. The connector stores separate credentials and project settings for production and sandbox.
1. Continue with the [nonservice provider setup steps](../../finance-how-setup-edocuments-external.md).

> [!NOTE]
> Before you enable the B2BRouter connection, you must obtain credentials directly from B2BRouter. Note that this service may be subject to charges.

> [!IMPORTANT]
> Business Central also provides an embedded VERI\*FACTU integration that sends invoice records directly to AEAT. For that setup, see [Enable embedded VERI\*FACTU mode](enable-real-time-invoice-reporting.md). The B2Brouter setup in this article is for external service integration.

## Related information

- [SII - Invoice and Credit Memo Types in Sales and Purchase Documents](SII-invoice-types-sales-purchase-documents.md)
- [Enable embedded VERI\*FACTU mode](enable-real-time-invoice-reporting.md)
- [Spain Local Functionality](spain-local-functionality.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
