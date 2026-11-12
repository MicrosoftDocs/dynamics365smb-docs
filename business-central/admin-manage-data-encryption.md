---
title: Manage Data Encryption in Business Central
description: Manage application data encryption keys in Business Central on-premises, and understand how this protection differs from database encryption at rest.
author: brentholtorf
ms.topic: concept-article
ms.devlang: al
ms.date: 11/12/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---
# Manage data encryption in Business Central

Application data encryption protects values that an application encrypts through AL encryption methods. This protection isn't the same as encrypting the entire database at rest.

On-premises, you can generate a new encryption key or import an existing key for the [!INCLUDE[prod_short](includes/prod_short.md)] server instance that connects to the database. Learn more in [Encrypting data in Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-encrypting-data).

> [!NOTE]
> Use the **Data Encryption Management** page to manage application encryption keys in [!INCLUDE[prod_short](includes/prod_short.md)] on-premises. For online environments, the service encrypts data at rest and backups. Learn more in [Data encryption at rest](/dynamics365/business-central/dev-itpro/security/transparent-data-encryption).

## Manage on-premises encryption keys

[!INCLUDE[open-search](includes/open-search.md)], enter **Data Encryption Management**, and then choose the related link.

The page provides actions to enable or disable encryption, and to import, change, or export the encryption key. When you export a key, protect it with a password and store it safely. Keep the key and password available for recovery.

## Related information

[Administration](admin-setup-and-administration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
