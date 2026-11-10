---
title: "View Database Locks"
description: View a snapshot of database locks in Business Central to identify affected tables, sessions, users, and available details about the executing AL code.
author: jswymer

ms.topic: how-to
ms.devlang: al
ms.search.form: 9511
ms.date: 11/10/2026
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
ai-usage: ai-assisted
---
# View database locks

Database locking controls access by multiple users to the same data at the same time. To protect a transaction against other transactions modifying the same data, the first transaction puts a lock on the data. The lock remains until the transaction's done.

Other transactions might have to wait to access the locked data. If a transaction waits too long, the user can get a lock timeout message.

## View current database locks

[!INCLUDE[open-search](includes/open-search.md)], enter **Database Locks**, and then choose the related link.

The **Database Locks** page gives a snapshot of current database lock requests, including granted requests and requests that are waiting for a lock. Where available, it also shows the user, session, and executing AL code for each lock request.

For more information about database locking, see [Monitoring Database Locks](/dynamics365/business-central/dev-itpro/administration/monitor-database-locks) in the Business Central Developer and IT Pro help.

## Related information

[Monitor Database Locks](/dynamics365/business-central/dev-itpro/administration/monitor-database-locks) 


[!INCLUDE[footer-include](includes/footer-banner.md)]
