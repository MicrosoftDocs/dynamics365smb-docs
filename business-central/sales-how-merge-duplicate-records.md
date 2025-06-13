---
title: Merge duplicate customer or vendor records
description: Describes how to consolidate information about customers or vendors when you have duplicate entries about some of them.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: client
ms.date: 06/13/2025vir
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Merge duplicate records

As different users create new customer, vendor, or contact cards over time, or the new records are created automatically during migration, a customer, vendor, or contact might be represented in the system with more than one record. In this case, you can use the **Merge Duplicate** page from the card of the record that you want to keep. The page gives you an overview of duplicated field values and lets you select which values to keep or discard when you merge two records into one.

> [!NOTE]
> Only users with the MERGE DUPLICATES permission set can use this functionality.

> [!TIP]
> The **Merge Duplicate** page shows all fields where the values are different for the two records being compared. Therefore, a duplicate is indicated by the page showing very few fields. Whereas, if the page shows many fields, then the suspected record is probably not a duplicate.

The following procedure is based on a customer card. The steps are similar for a vendor  and contact cards.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Select the customer that you know or suspect that a duplicate record exists for, and then choose the **Edit** action.
3. On the **Customer Card** page, choose the **Merge With** action.
4. On the **Merge Duplicate** page, in the **Merge With** field, select the customer that you believe is a duplicate of the one you have opened, indicated in the **Current** field.

    The **Fields** FastTab lists fields where the values are different for the two customers. This means that if the selected customer is really a duplicate, then only few fields should be listed, such as typing errors and other data entry mistakes.

    The **Related Tables** FastTab lists tables where there are fields with a relation to both customers. The **Current Count** and **Duplicate Count** fields show the number of fields in related tables where the **No.** value of both the current and the duplicate customer is used. On the **Merge Duplicate** page, this section is informational only, however, if merge conflicts exist, you'll resolve them on the **Merge Duplicate Conflicts** page. Refer to steps 8 through 12.

5. For each field where you want to use another value than the current one, select the **Override** checkbox. The value in the **Alternate Value** field will then be transferred to the current record when you complete the process.
6. When you have finished selecting which values to keep or override, choose the **Merge** action.

    The system checks if the merge of values for the duplicate customer into the current customer causes any conflicts. A conflict exists if a value in at least one primary-key field is the same for both customers while the value in the **No** field is different for the two customers.

7. If no conflicts are found, choose the **Yes** button in the confirmation message box.

    The duplicate customer is renamed so that all usage of its **No.** value in all fields with relations to the customer table will be replaced with the **No.** value of the current customer.
8. If conflicts exist, choose the **Resolve (xx) conflicts before merge.** action on the **Conflicts** FastTab, which will appear if conflicts exist.
9. On the **Merge Duplicate Conflicts** page, select the line for a related table with a conflict, and then choose the **View Details** action.

    The **Merge Duplicate** page now shows the fields in the selected table that cause a merge conflict between the two customer records. Notice in both the summarized values in the **Current** and **Conflicts With** fields and on the lines that at least one primary-key field is the same for both customers and the value of the **No.** field is different for the two customers.   
10. If you don't want to keep the duplicate customer record, choose the **Remove Duplicate** action, and then choose the **Close** button.

    Identical field values, other than the value in the **No.** field, are removed from the duplicate record and inserted on the current record.
11. If you want to keep the duplicate customer record after the merge,  choose the **Rename Duplicate**.
12. On lines, not for the **No.** field, where the field has the same value on both records, change the value in the **Alternate Value** field, and then choose the **Close** button.

    The conflicting field value is updated on the duplicate record so that it can be merged with the current record. The duplicate record continues to exist after the merge.
13. Repeat steps 8 through 12 until all conflicts are resolved. The **Conflicts** FastTab disappears.
14. On the **Merge Duplicate** page, choose the **Merge** action again, and then select the **Yes** button in the confirmation message box.

> [!NOTE]
> For contacts, you can use functionality to find duplicate contacts before you use the **Merge Duplicate** page. For more information, see [Search for duplicate contacts](marketing-setup-contacts.md#search-for-duplicate-contacts).

## Related information

[Sales](sales-manage-sales.md)  
[Set Up Contacts](marketing-setup-contacts.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
