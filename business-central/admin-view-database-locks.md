---
title: "View Database Locks"
description: Learn how you can view information about customer database locks right from the client interface in Business Central.
author: jswymer

ms.topic: concept-article
ms.devlang: al
ms.search.form: 9511
ms.date: 06/14/2021
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Viewing Database Locks

Database locking controls access by multiple users to the same data at the same time. To protect a transaction against other transactions modifying the same data, the first transaction puts a lock on the data. The lock remains until the transaction's done.

Users may be blocked from completing transactions on the locked data. They'll typically get a message that indicates the lock condition.

## To view database locks

Choose the ![Search for Page or Report.](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Database Locks**, and then choose the related link.

The **Database Locks** page gives snapshot of all current database locks.

For more information about database locking, see [Monitoring Database Locks](/dynamics365/business-central/dev-itpro/administration/monitor-database-locks) in the Business Central Developer and IT Pro help.

## Related information

[Monitor Database Locks](/dynamics365/business-central/dev-itpro/administration/monitor-database-locks) 


[!INCLUDE[footer-include](includes/footer-banner.md)]
