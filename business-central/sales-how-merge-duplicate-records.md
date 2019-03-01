---
title: Merge Duplicate Customer or Vendor Records | Microsoft Docs
description: Describes how to create a customer card to register information about each new customer or client that you sell to.
services: project-madeira
documentationcenter: ''
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: client
ms.date: 02/28/2019
ms.author: sgroespe

---
# Merge Duplicate Customer or Vendor Records
As different users create new customer or vendor cards over time, or the records are created automatically, for example, in data migration, a customer or vendor may be represented in the system with more than one record. In this case, you can use the **Merge Duplicate** page from the card of the record that you want to keep. The page gives you an overview of duplicated field values and provides functions to decide which values to keep or discard when merging two records into one.

The following procedure is based on a customer card. The steps are similar for a vendor card.

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Select the customer where you know or suspect that duplicate records exist, and then choose the **Edit** action.
3. On the **Customer Card** page, choose the **Merge With** action.
4. On the **Merge Duplicate** page, in the **Merge with** field, select the customer that you believe is a duplicate of the one you have opened, indicated in the **Current** field.

    On the A list of fields shows the fields where values are different. , i.e. if it is really a duplicate there should be no much difference and maybe just typos. Here user can define what values should be copied from the duplicate record by setting “Override” to Yes.
-	The list of tables includes tables where there are fields with relation to both customers. “Current count” and “Duplicate Count” show number of records where the current and the duplicate customer code is used. If a field that contains the customer code has no relation to the customer table this table will not appear in the list.
-	Action “Merge” starts from the check if the rename of the duplicate customer causes a conflict. It happens if app value in primary key fields are the same except the only one – customer code.
-	If conflicts are not found the user is asked for confirmation and the duplicate customer renamed so all usage of its customer code in all fields with relation to the customer table will be replaced with the code of the current customer. The end.
-	if conflicts are found there is a tab Conflicts with number of found conflicts. They are also marked with color in the list of tables. Drill down on the conflicts opens the page that shows pairs of records that will conflict on rename. Action “View Details” opens the page with the list of fields – members of the primary key, where user can chose two actions:
o	Remove duplicate – the duplicate record will be removed. It makes sense when the second record is a pure duplicate, maybe a  technical record, in some supplementary table.
o	Rename duplicate – the duplicate record will be updated to avoid the conflict. User must modify one of the fields in the primary key of the duplicate record. It makes sense when this record should exist after merge.
-	When all conflicts are resolved the Conflict tab disappears so user can run “Merge” action again and answer Yes to the confirmation to finish the process.


## See Also
[Sales](sales-manage-sales.md)    
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
