---
title: FAQ for technical details
description: Implementation details related to the Shopify connector.
ms.date: 03/30/2026
ms.topic: faq
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template

---

# FAQ for technical details

This article answers frequently asked questions about the Shopify Connector.

## Which Microsoft products work with the Shopify Connector?

The connector is available only for [!INCLUDE[prod_short](../includes/prod_short.md)] online. The connector is preinstalled for new environments. Organizations with existing environments can download and install the connector from Marketplace. The organization must have both a [!INCLUDE [prod_short](../includes/prod_short.md)] license and a Shopify license to use the connector. To learn more about supported countries/regions, languages, and editions of [!INCLUDE[prod_short](../includes/prod_short.md)], go to [Shopify Connector on the Marketplace](https://go.microsoft.com/fwlink/?linkid=2196238).

It isn't available for on-premises deployments.

The Shopify connector doesn't work for [Embed App](/dynamics365/business-central/dev-itpro/deployment/embed-app-overview), where the client URL has the `https://[application name].bc.dynamics.com` format.

The Shopify connector doesn't work with other Dynamics 365 applications, like Dynamics 365 Sales or Dynamics 365 Supply Chain Management.

## What Shopify API is used

The Shopify Connector primarily uses the Shopify GraphQL Admin API for all integration calls, with the exception of operations related to sold gift cards. For consistency, all interactions with Shopify use the same API version.

Shopify releases a new API version every three months at the beginning of each quarter, and supports each version for 12 months. These updates often include important changes, such as enhanced stability, improved security, and new features. To reduce impact on your environment, adoption of the latest released Shopify API version happens in major releases of [!INCLUDE[prod_short](../includes/prod_short.md)]. For example, the Shopify Connector released in April 2025 uses the Admin API version from January 2025, while the October release uses the API version released in July.

### Impact on integration

If you're using [!INCLUDE[prod_short](../includes/prod_short.md)] with the Shopify Connector released in 2025 release wave 2 (October 2025), your integration relies on API version 2025-07, which is supported until July 1, 2026. To ensure uninterrupted synchronization and data exchange with Shopify, you must upgrade to the latest major version of [!INCLUDE [prod_short](../includes/prod_short.md)] (2026 release wave 1) before this end-of-support date. If you don't upgrade, API calls might be blocked, which means you can't synchronize data between [!INCLUDE [prod_short](../includes/prod_short.md)] and Shopify.

> [!NOTE]
> The Shopify API version support timeline doesn't align with the [!INCLUDE [prod_short](../includes/prod_short.md)] update period, which allows you to remain on the previous version for up to five months after a major update is released.

## What support is offered for the Shopify Connector?

To learn more, go to [Support for the Shopify Connector](shopify-support.md).

## Why does the connector have so many internal (non-public) codeunits?

The Shopify Connector is built on the [Shopify GraphQL Admin API](https://shopify.dev/docs/api/admin-graphql), which Shopify versions every three months and aggressively deprecates fields between versions. The connector pins a specific API version (adopted at each [!INCLUDE[prod_short](../includes/prod_short.md)] major release) and must uptake to the next version before support ends—fall behind and the integration stops working.

If internal helpers, staging tables, and communication codeunits were all part of a public surface, every upstream API change would land as a breaking change in your extensions on a quarterly cadence. The design trade-off is deliberate: keep internals private so the connector can keep pace with Shopify without breaking the partners building on top.

For the operations partners need most often, we publish stable, public façade codeunits. To learn more, go to [Extend the Shopify Connector](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify).

## Currently unsupported features; however, we're tracking them and may consider adding them

- Draft orders

## Is the Shopify Connector extensible?

Yes. The connector exposes a substantial extensibility surface while keeping internal communication and staging logic private to absorb Shopify's quarterly API changes without breaking partner extensions. The current surface includes:

- **Integration events** across dedicated event codeunits covering orders, products, customers, inventory, shipping, and return/refund processing.
- **Public façade codeunits** for common operations without subscribing to events:
  - **Shpfy Orders** (codeunit 30409) — `MarkAsPaid`, `CancelOrder`
  - **Shpfy Metafields** (codeunit 30418) — `GetMetafieldDefinitions`, `SyncMetafieldToShopify`, `SyncMetafieldsToShopify`
  - **Shpfy Product** (codeunit 30234) — `AddItemToShopify`, `GetProductUrl`, `GetProductsOverview`
- **Extensible enums** with interface implementations for stock calculation, customer mapping, company mapping, return/refund processing, and more.

These façade codeunits are stable and intended to grow. If you need a specific method exposed, you can open a pull request to add it to the relevant façade — that's a small, low-risk change.

The connector is open source and welcomes contributions from partners, including new events, façade methods, bug fixes, and feature work. You can find the [source code](https://github.com/microsoft/BCApps/tree/main/src/Apps/W1/Shopify) in the *BCApps* repository.

To learn more and explore extensibility examples, go to [Extend the Shopify Connector](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify).

## Building your version of the Shopify Connector

According to Shopify, if you want to build and publish a connector app on Shopify marketplace that has the primary purpose of transferring or sharing merchant data to a third party ([!INCLUDE [prod_short](../includes/prod_short.md)]), you must have written consent from Shopify. As part of this process, you must get consent from Microsoft in the "End Recipient Data Acknowledgement Form". We need to ask you to handle the matter with Shopify because Microsoft can't sign third-party agreements.

### What to do

Check the Shopify requirements because you still might be able to have an unlisted app.

Alternatively, the Shopify Connector for [!INCLUDE [prod_short](../includes/prod_short.md)] constantly gets new features and new customers. If you discover a specific gap, consider [submitting a product suggestion](https://aka.ms/bcideas) or a code contribution to [!INCLUDE [prod_short](../includes/prod_short.md)]. For requirements that might not be relevant for a majority of customers, and can't be easily addressed by the current extensibility model, please reach out to the [!INCLUDE [prod_short](../includes/prod_short.md)] development team to discuss the use case. We should be able to find a feasible solution.

## Related information

[Shopify Connector overview](shopify-connector-overview.md)  
[FAQ for the Shopify connector](shopify-faq.md)  
[Troubleshoot the Shopify Connector](troubleshoot.md)  
[Walkthrough: Setting Up and Using Shopify Connector](walkthrough-setting-up-and-using-shopify.md)  

## [!INCLUDE[prod_short](../includes/free_trial_md.md)]  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
