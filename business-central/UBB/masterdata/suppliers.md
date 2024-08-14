---
title: Suppliers
hide_title: true
sidebar_label: Suppliers
slug: /ubb/masterdata/suppliers
---

# Usage data suppliers
A **Usage Data Supplier** is the business partner who provides the usage data for subsequent processing. This is usually the provider of the services for subsequent processing. <br/>
In the page of the same name new suppliers can be created or already created suppliers can be adapted. In addition to a unique, self-assigned **No.** an explanatory **Description** can be entered. <br/>
The **Vendor Name** can be used to connect to a vendor. This is especially relevant for the [import and processing](/docs/pli/price-list.md#supplier-reference-for-usage-data) of CSP/NCE price lists. <br/>
In the field **Type** only the selection *Generic* is currently available. This means that the data to be imported is not imported via a specific interface (API). Instead, CSV files can be imported. An API page is also provided as an interface for the generic import. <br/>
The **Unit Price from Import** field influences the customer pricing of the usage data and specifies whether the sales price from the usage data should be used. If a supplier is flagged this way, pricing based on the Service Commitments will be overridden. In this case, the import file must contain the customer pricing and the related [Data Exchange Definitions](/docs/ubb/masterdata/dataexchangedefinitions.md) ([see below](#settings-on-the-supplier)) must be set to process this information. <br/>
The **Vendor Invoice per** field specifies whether vendor invoices are created as a collective invoice per import or as one invoice per customer / end user.


## Settings on the supplier
In the **Settings** further connector specific defaults can be made. In addition to the **[Data Exchange Definitions](/docs/ubb/masterdata/dataexchangedefinitions.md)** to be used for the import, the **[Create Customers](/docs/ubb/masterdata/customers-subscriptions.md#usage-data-customers)** and **[Create Subscriptions](/docs/ubb/masterdata/customers-subscriptions.md#usage-data-subscriptions)** fields control whether this data is automatically created during usage data processing. In addition, the **Process without Usage Data Blobs** field indicates that no data from the related blob field is used as the basis for processing the usage data. This is the case, for example, if the usage data is imported via [API](/docs/ubb/processing-usage-data/imports-processing.md#import-usage-data-via-api). If the field is set to *YES*, the first step in usage data processing is skipped. It is not needed in this case or it is a hindrance, because it leads to the Imported Lines being overwritten with *empty* and thus de facto deleted.


### Custom processing of usage data
If it is necessary to use custom usage data processing (e.g. because the usage data is only available in a non-standard structure), this can be selected in the **Additional Processing** field, if implemented. Therefore, although the field is hidden by default, it can be shown via *Personalize*.


:::note
The **Settings** page displays different content depending on **Type**. All other fields in the **Usage Data Supplier** page are generic.
:::