---
title: Sales Price Calculation
hide_title: true
sidebar_label: Sales Price Calculation
slug: /srb/sales/price-calculation
---

# Price determination of Service Commitments
The price of a Service Commitment is automatically determined based on [Setup](/docs/srb/masterdata/service-commitments.md). Editing **Calculation Base Amount** and **Calculation Base %** is possible to change the price manually.

* **Calculation Base Amount**.
    * **Item Price** <br />
    The **Calculation Base Amount** of the Service Commitments is determined from the master data (Item card). For customer-side Service Commitments the **Unit Price** and for vendor-side Service Commitments the field **Last Direct Cost** is used. Changes to the sales price and cost price in the sales document have no effect.
    * **Document Price** <br />
    The **Calculation Base Amount** is determined from the **Unit Price** for Customer Service Commitments and from the **Unit Cost** of the sales document line for Vendor Service Commitments. A change to the prices in the document line is automatically applied to all Service Commitments for the sales item.
    * **Document Price And Discount** <br />
    The **Calculation Base Amount** is determined in the same way as the Document Price Type (see above). In addition, a discount entered in the sales item for the Service Commitments is transferred and taken into account when determining the Service Amount. This option is not available for vendor-side Service Commitments.
* **Calculation Base Amount**
    * Calculation Base Amount is the basis for calculating the Service Amount. When selling a good with an additional recurring Service Commitment, the Calculation Base Amount is equal to the value of the good.
* **Calculation Base %**
    * Calculation Base Amount % is the percentage from the **Calculation Base Amount** which is used to determine the price of the Service Commitment.
* **Price**
    * The price is calculated from the **Calculation Base Amount** and the **Calculation Base %**
    * The price is always valid for the entire **Calculation Base Amount**. I.e. it is an annual price if a year (or 12 months) is entered in **Calculation Base Amount** and a monthly price if a month is entered in **Calculation Base Period**.