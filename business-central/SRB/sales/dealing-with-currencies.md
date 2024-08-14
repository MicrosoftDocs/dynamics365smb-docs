---
title: Currencies
description: You can use currencies in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Dealing with currencies
# Currencies
In Business Central, transactions can be performed taking into account a foreign currency. The currency code is entered in the respective transaction. This can be done, for example, in the Sales Order or in the Customer/Vendor Contract. <br/>
For more details on handling currencies, please refer to <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/finance-how-update-currencies" title="Foreign currencies">this part</a> of the Microsoft documentation.


## Foreign Currency in Service Commitments
If a currency code is entered, e.g. in a sales order (or this is stored at the customer), a corresponding conversion of the prices into the currency of the customer takes place. This is done in the same way for **Sales Service Commitments**. In the Service Commitments for the Service Object, the **Currency Code** field also indicates the currency to which the **Service Amount** refers.
When manually creating a Service Object with Service Commitments, the **Currency Code** and the corresponding fields in the Service initially remain empty, even if a currency code has been defined in the Customer. The currency code can remain blank because the contract that the service is billed via later *decides* which currency will be used. <br/>
When the Service Object and Service Commitments are created via Sales Shipment, the currency code from the Sales Order is automatically transferred to the Service.


## Convert Service Amounts
When assigning Service Commitments to a contract, the system checks if the amounts need to be converted. If the currency code in the contract is the same as the currency code in the Service Commitments, no conversion is required. Otherwise the conversion is done by a query in which the last conversion factor is suggested to the user (based on the work date). Clicking *OK* will recalculate the fields relevant to the currency, update the Service Commitment and then add it to the contract. <br/>
When changing the currency code in the contract, the dialog is also displayed.

:::note Same currency code
When assigning Service Commitments to a contract for which a conversion of the amounts are to be made, the same currency code must be stored in all selected services.
:::


## Update exchange rates on Service Object
The method described here ensures that the agreed price for Service Commitments in a foreign currency does not automatically change as a result of a change in the exchange rate. However, it may be necessary to adjust the exchange rate manually. The action **Update exchange rates** can be used for this purpose. It is available in the Service Object as well as in the Customer and Vendor Contracts (under *Process*).

:::info Manual price change
A manual change by the user to one of the fields
* Calculation Base Amount
* Calculation Base %
* Price
* Discount %
* Discount Amount
* Service Amount

leads to a corresponding update of the fields
* Price (LCY)
* Discount Amount (LCY)
* Service Amount (LCY)

based on the stored exchange rate.
:::


## Update exchange rates for currencies automatically
In Business Central, it is possible to automatically update exchange rates using **[Job Queue](/docs/srb/setup/job-queue.md)**. For more details, please see <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/finance-how-update-currencies" title="Update Currency Exchange Rates">this</a> and <a href="https://learn.microsoft.com/en-us/dynamics365/business-central/admin-job-queues-schedule-tasks" title="Job Queue">this</a> Microsoft documentation.