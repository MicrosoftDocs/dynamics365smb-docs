---
ms.service: dynamics-365-business-central
---

## Use Edit in Excel on output, consumption, and item journals

One reason the Edit in Excel feature in is so popular is that it provides a fast way to enter data. For example, you can use templates for journals, quickly do bulk edits, and so on. You can use the feature to speed up data entry on item journals to include item tracking details such as lot, serial, package number, warranty, and expiration dates. You can also edit item tracking details in consumption and output journals.

To let users enter serial, lot, and package data directly on journal lines, you must enable the capability on item journal batches. To set that up, follow these steps:

1. Open the **Item Journal Templates** page.
1. Select a template of the type Item, Consumption or Output.
1. Choose the **Batches** action to open a list of item journal batches.
1. Choose **New** to create a new batch, and then turn on the **Item Tracking on Lines** toggle.

Repeat these steps for all templates for which you want to use the capability.

After you set the feature up, you can start using it right away.

1. Depending on what you want to do, open the **Item Journals**, **Consumption Journals**, or **Output Journals** pages.
1. In the **Batch Name** field, select the batch for which you enabled the **Item Tracking on Lines** toggle.
1. Choose the **Edit in Excel** action.
1. In Excel, you can now fill in columns, including **Serial No.**, **Lot No.**, **Package No.**, **Expiration Date**, and **Warranty Date**.
1. When you're done, choose **Publish** to send changes to Business Central.