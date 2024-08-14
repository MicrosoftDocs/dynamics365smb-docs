---
title: Customers & Subscriptions
hide_title: true
sidebar_label: Customers & Subscriptions
slug: /ubb/masterdata/customers-subscriptions
---

# Customers & Subscriptions
In addition to the usage data that changes per import, there is also data that has more the character of master data, since it does not change. This includes both the customers for whom the usage data is imported and the subscriptions on the basis of which the link to the Service Commitments to be billed is established. In the case of the customers, this is supporting but not necessary data, whereas without a subscription, no billing of usage data is possible.


## Usage data customers
The **Usage Data Customers** page displays the records of customers for which usage data is provided for processing. At the [supplier](/docs/ubb/masterdata/suppliers.md), the **Create customers** field can be used to set whether an entry should be created automatically in this overview when usage data is imported ([see below](#create-customers-based-on-usage-data)). Since these entries are based on usage data and thus represent the supplier's data, they may differ from the master data in Business Central. Therefore, a link can be created based on the Customer. This data is not required for processing and billing of usage data. The page is for clarity reasons only. <br/>
Records are identified by the **Supplier No.** field to which supplier they belong. Via the **Customer No.** a link to the master data can be established. **Usage Data Customers** not yet linked to a Customer will be displayed in blue-green to indicate that the assignment has not yet been made. For the entries colored in black, the link has already been made. The **Supplier Reference** field contains the unique ID of the customer at the supplier. This value contains a link to the [central references](/docs/ubb/masterdata/references.md) (type=*Customer*) that is automatically created when usage data is processed.


### Create customers based on usage data
If it is specified at the supplier that the customers belonging to the usage data are to be created ([see above](#usage-data-customers)), the information from the usage data is used as far as possible to create the data records:
* Supplier No.
* Supplier description
* Customer ID as supplier reference


## Usage data subscriptions
The **Usage Data Subscriptions** page displays the subscriptions that belong to the usage data to be processed. On the [supplier](/docs/ubb/masterdata/suppliers.md), the **Create Subscriptions** field can be used to set whether an entry should be created automatically in this overview when usage data is imported or during its processing ([see below](#create-subscriptions-based-on-usage-data)). These entries represent the supplier's data regarding the customer's subscriptions. For processing and billing usage data this data is *required*. If the data is not created via the above-mentioned indicator at the supplier in advance or during the processing of usage data, this must therefore be done manually or by another means. It is therefore recommended to let the system create the **Usage Data Subscriptions** via this way. In addition, this page serves general clarity. <br/>
The records are identified by **Supplier No.** to which supplier they belong. Via the functionalities **[Extend Contract](/docs/ubb/processing-usage-data/extend-contract.md)** and **[Connect Subscription with Service Object](/docs/ubb/processing-usage-data/connect-subscription-service-object.md)** links to the Customer (**Customer No.**) and to the related [Service Object](/docs/srb/working-with-contracts/service-objects.md) are established. Subscriptions not yet associated with a Service Object are shown colored blue-green to indicate that the association has not yet been made. For the entries colored in black, the linking has already been done. The **Supplier Reference** field contains the unique ID of the subscription at the supplier. This value contains a link to the [central references](/docs/ubb/masterdata/references.md) (type=*Subscription*) that is automatically created when usage data is processed.


### Create subscriptions based on usage data
If it is specified at the supplier that the subscriptions belonging to the usage data are to be created ([see above](#usage-data-subscriptions)), the information from the usage data is used as far as possible to create the data records:
* Supplier No.
* Customer ID
* Supplier reference (as ID of the subscription)
* Subscription Name
* Subscription Description
* Subscription Start Date
* Subscription End Date
* Product ID
* Product Name
* Unit of Measure
* Quantity