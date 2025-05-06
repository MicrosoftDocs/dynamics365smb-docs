---
title: Sales price calculation
description: You can use sales price calculation in subscription and recurring billing.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.keywords: 
ms.search.form: 
ms.date: 08/14/2024
ms.service: dynamics-365-business-central
---

# Price determination of service commitments

The price of a service commitment is automatically determined based on their setup. To learn more, go to [Service commitments](../masterdata/service-commitments.md). To change a price manually, you can edit the **Calculation Base Amount** and **Calculation Base %** fields.

* **Calculation Base Amount**

   * **Item Price**

   The **Calculation Base Amount** of the service commitments is determined from the item. Customer-side service commitments use the **Unit Price** field. Vendor-side service commitments use the **Last Direct Cost** field. Changes to the sales price and cost price in the sales document have no effect.

   * **Document Price**

   The **Calculation Base Amount** is determined from the **Unit Price** for customer service commitments and from the **Unit Cost** of the sales document line for vendor service commitments. A change to the prices on the document line automatically applies to all service commitments for the sales item.

   * **Document Price And Discount**

   **Calculation Base Amount** is determined in the same way as the Document Price Type (see above). In addition, a discount entered in the sales item for the service commitments is transferred and taken into account when determining the Service Amount. This option is not available for vendor-side service commitments.

   * **Calculation Base Amount**

   **Calculation Base Amount** is the basis for calculating the service amount. When selling a good with an additional recurring service commitment, the calculation base amount is equal to the value of the good.

   * **Calculation Base %**

   **Calculation Base %** is the percentage from the **Calculation Base Amount** which is used to determine the price of the service commitment.

   * **Price**

   The price is calculated from the **Calculation Base Amount** and the **Calculation Base %**. The price is always valid for the entire **Calculation Base Amount**. For it's an annual price if a year (or 12 months) is entered in **Calculation Base Amount** and a monthly price if a month is entered in **Calculation Base Period**.

## Related information

[Service commitments](../masterdata/service-commitments.md)  
[Sales process](sales-service-commitments.md)  
