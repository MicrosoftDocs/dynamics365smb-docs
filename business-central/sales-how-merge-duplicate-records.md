---
title: Merge Duplicate Customers, Vendors, or Contacts
description: Merge duplicate customer, vendor, or contact records in Business Central, choose which field values to keep, and resolve conflicts in related records.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: client
ms.date: 10/22/2026
ai-usage: ai-assisted
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Merge duplicate records

Over time, as different people create new customers, vendors, or contacts, or you create new records during data migration, there's a risk that you duplicate records. If you find a duplicate, you can use the **Merge Duplicate** page from the card of the record that you want to keep. The page gives you an overview of duplicated field values and lets you select which values to keep or discard when you merge two records into one.

> [!NOTE]
> Only users with the MERGE DUPLICATES permission set can use this functionality.

> [!WARNING]
> Merging records can't be undone. Review the records and the values to keep before you choose **Merge**.

> [!TIP]
> The **Merge Duplicate** page shows all fields where the values are different for the two records being compared. Therefore, if the page shows only a few fields, it might indicate a duplicate. If the page shows many fields, the record probably isn't a duplicate.

The following procedure is based on a customer card. The steps are similar for a vendor and contact cards.

1. [!INCLUDE[open-search](includes/open-search.md)], enter **Customers**, and then choose the related link.
1. Select the customer that you know or suspect that a duplicate record exists for, and then choose the **Edit** action.
1. On the **Customer Card** page, choose the **Merge With** action.
1. On the **Merge Duplicate** page, in the **Merge With** field, select the customer that you believe is a duplicate of the one you opened, which shows in the **Current** field.

    The **Fields** FastTab lists fields where the values are different for the two customers. This means that if the selected customer is really a duplicate, then only few fields should be listed, such as typing errors and other data entry mistakes.

    The **Related Tables** FastTab lists tables with fields related to the customer records. The **Current Count** and **Duplicate Count** fields show how many records in each related table refer to each customer. On the **Merge Duplicate** page, this section is informational only. Resolve any merge conflicts as described in the following steps.

1. For each field where you want to use another value than the current one, select the **Override** checkbox. The value in the **Alternate Value** field transfers to the current record when you complete the process.
1. After you specify the values to keep or override, choose the **Merge** action.

    [!INCLUDE [prod_short](includes/prod_short.md)] checks whether the merge of values for the duplicate customer into the current customer causes conflicts. A conflict exists if a value in at least one primary-key field is the same for both customers while the value in the **No** field is different for the two customers.

1. If no conflicts are found, choose the **Yes** button in the confirmation message.

    The duplicate customer is renamed so that all use of its **No.** value in all fields with relations to the customer table are replaced with the **No.** value of the current customer.
1. If conflicts exist, choose the **Resolve (xx) conflicts before merge** action on the **Conflicts** FastTab, which displays if conflicts exist.
1. On the **Merge Duplicate Conflicts** page, select the line for a related table with a conflict, and then choose the **View Details** action.

    The **Merge Duplicate** page now shows the fields in the selected table that cause a merge conflict between the two customer records. Notice in both the summarized values in the **Current** and **Conflicts With** fields and on the lines that at least one primary-key field is the same for both customers and the value of the **No.** field is different for the two customers.   
1. If you don't want to keep the conflicting related record, select **Override** for any nonkey fields whose values you want to keep. Choose **Remove Duplicate**, confirm the deletion, and then choose **Close**.

    The conflicting related record is deleted. The selected nonkey field values are copied to the current related record.
1. To keep the conflicting related record, change the **Alternate Value** of another primary-key field so that the key is unique, and then choose **Rename Duplicate**.

    The conflicting related record is renamed and retained. The duplicate customer record is still merged into the current customer.

1. Repeat the conflict-resolution steps until the **Conflicts** FastTab disappears. On the **Merge Duplicate** page, choose **Merge** again, and then choose **Yes** to confirm.

> [!NOTE]
> For contacts, you can use functionality to find duplicate contacts before you use the **Merge Duplicate** page. For more information, see [Search for duplicate contacts](marketing-setup-contacts.md#search-for-duplicate-contacts).

## Related information

[Sales](sales-manage-sales.md)  
[Set Up Contacts](marketing-setup-contacts.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
