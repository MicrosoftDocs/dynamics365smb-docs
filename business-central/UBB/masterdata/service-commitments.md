---
title: Service Commitments
hide_title: true
sidebar_label: Service Commitments
slug: /ubb/masterdata/service-commitments
---

# Extension of Service Commitments
Since **DYCE Usage Based Billing** is an [extension](/docs/ubb/purpose.md) of **[DYCE Subscription & Recurring Billing](/docs/srb/welcome.md)**, only the differences are discussed here. For more information on Service Commitments and how to set them up, please see [this](/docs/srb/masterdata/service-commitments.md) part of the DYCE documentation.


## Service Commitment Templates
Since Service Commitment Templates can be optionally created, the additional fields are explained within the [Service Commitment Packages](#service-commitment-packages).


## Service Commitment Packages
Both Service Commitment Templates and Service Commitment Package lines can be used to create defaults that are necessary for subsequent processing of usage data. <br/>
* Via **Usage Based Billing**, it is specified that the Service Commitments arising from this package line are generally billed based on the underlying usage. This is done in the form of usage data that is [imported and processed](/docs/ubb/processing-usage-data/imports-processing.md). Therefore, the field of the same name in the Service Commitment is used to determine the Service Object. The **Usage Based Pricing** is only relevant on the sales side and is decisive for the subsequent billing towards the customers. On the purchasing side, the (purchase) prices from the usage data are used for the contract invoices on the vendor or supplier side.
* The **Usage Based Pricing** field defines how the prices are determined. The following options are available for this purpose:
    * If **Usage Based Billing** is set, but the **Usage Based Pricing** field is blank, no pricing is determined for the related usage data.
    * **Usage Quantity** <br/>
    This option is used when the customer is charges for the actual used quantity. This can be per billing period, for example, licenses (software), consumption minutes (car sharing) or the number of transactions. Therefore, only integer quantities (without decimal places) can be processed. The sales price (per unit) is determined on the basis of the related item, depending on the quantity.
    * **Fixed Quantity** <br/>
    With this option, the original quantity remains fixed when the usage data is imported. Thus, the Customer will always be charged for the quantity entered in the Service Object. An adjustment of the quantities based on the usage data does not take place. This pricing thus serves the flat-rate billing of Service Commitments, which, however, only takes place if usage data is actually available.
    * **Unit Cost Surcharge** <br/>
    With the option *Unit Cost Surcharge* the imported consumption quantity is also disregarded. However, the unit cost plus the specified surcharge is passed on to the customer. This option is usually used for consumption-based (or volume-based) billing. In this case, all unit costs belonging to the subscription are added up and the surcharge is then calculated on the total.
    * **Consumption Quantity** <br/>
    This pricing option also leaves the quantity in the Service Object unaffected. This means that - in contrast to the *Used Quantity* option - non-integer consumption quantities (with decimal places) can also be processed. However, there is no aggregation of all usage data to one single Service Commitment (as with the *Unit Cost Surcharge* option). Here, too, the sales price (per unit) is determined on a quantity-dependent basis using the related item.
* If you select the *Unit Cost Surcharge* option in the **Usage Based Pricing** field, the percentage value for the surcharge is stored in **Pricing Unit Cost Surcharge %**. For all other options this field is not editable.