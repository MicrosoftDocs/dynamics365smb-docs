---
title: 
description: 
ms.date: 03/21/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
manager: 
---



# Troubleshooting

## Logs

-   Activate the log.   //TBD: to be moved to "other, part trouleshouting. 

When a synchronization task from / to Shopify fails, you can activate logging on the tab 'General' in the Shopify Shop Card:

![](media/image119.png)

After you start the synchronization task again, you can check the Scaptify Log Entries for any errors / information:

![](media/image120.png)

![](media/image121.png)

![](media/image122.png)

Make sure to disable the logging when not needed, or to delete the entries periodically.

![](media/image123.png)


## Reset sync

On the Shopify Shop card, there are functions available to reset the sync. This function ensures that when the sync is executed, all data is synced and not just the changes that have happened compared to the previous sync.

This function only applies to syncs from Shopify to [!INCLUDE[prod_short](../includes/prod_short.md)].

![](media/image111.png)
