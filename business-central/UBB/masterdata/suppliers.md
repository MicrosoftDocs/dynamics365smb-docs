---
title: Usage data suppliers
description: You can use suppliers in usage-based billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 8044_Primary, 8041, 8038
ms.date: 07/11/2025
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Usage data suppliers

Use the **Usage Data Supplier** page to manage information about the business partners who provide usage data for processing. A supplier is usually the provider of a service.

In addition to a unique **No.**, you can enter an explanatory **Description**.

Use the **Vendor Name** field to connect the supplier to a vendor. To learn more, go to [Methods for pricing](../processing-usage-data/imports-processing.md#methods-for-pricing).

The **Type** field only offers the **Generic** option, which means that the data isn't imported through an interface, such as an API. Instead, you import data in CSV files. An API page is also provided as an interface for the generic import.

The **Unit Price from Import** checkbox affects the customer pricing of the usage data and specifies whether to use the sales price from the usage data. If you select the checkbox, pricing based on subscription lines is overwritten. In this case, the import file must contain the customer pricing and the data exchange definition. To learn more, go to [Data exchange definitions](dataexchangedefinitions.md) and [Settings on the supplier](#settings-on-the-supplier).

The **Vendor Invoice per** field specifies whether to create vendor invoices as a collective invoice per import, or as one invoice per customer/end user.

## Settings on the supplier

On the **Usage Data Suppliers** page, use the **Settings** action to open the **Generic Import Settings page**, where you can specify various setting for data import. In addition to the [Data exchange definitions](dataexchangedefinitions.md) to use to import data, the [Usage data customers and suppliers](customers-subscriptions.md#usage-data-customers-and-suppliers) and [Create Subscriptions](customers-subscriptions.md#usage-data-subscriptions) toggles control whether you automatically create this data when you process usage data. In addition, the **Process without Usage Data Blobs** toggle indicates that data from the related blob field isn't used as the basis for processing the usage data. This is the case, for example, if you import usage data using an API. To learn more, go to [Import usage data via API](../processing-usage-data/imports-processing.md#import-usage-data-via-an-api). If you turn on the toggle, the first step in processing usage data is skipped because it leads to the imported lines being overwritten with **Empty** and thus deleted.

### Custom processing of usage data

You can use custom usage data processing, for example, if the usage data is only available in a non-standard structure. Use the **Additional Processing** field, if it's implemented. If it is, you might need to personalize the page to add it. To learn more, go to [Personalize your workspace](../../ui-personalization-user.md).

## Related information

[Overview of usage-based billing](../welcome.md)  
[Import data in usage-based billing](../processing-usage-data/imports-processing.md)  
