---
title: Service Commitments in Service Objects
hide_title: true
sidebar_label: Service Commitments in Service Objects
slug: /srb/working-with-contracts/so-service-commitments
---

# Service Commitments
Service Commitments describe the monetary content of agreements with customers and suppliers as well as termination dates. In order for a Service Commitments to be billed recurrently, it must be assigned to a contract.

A Service Commitment is valid if **Invoicing via** is set to *Contract* and the **Service End Date** is either blank or the **Next Billing Date** has not reached the Service End Date. Service Commitments with Invoicing via *Sales* are used to store information and are not billed on a recurring basis.
If a Service Commitments is assigned to a contract, almost all changes can be made in the contract. The quantity of Service Commitments cannot be changed in the contract.

:::info
* If the **Next Billing Date** reaches the **Service End Date**, it will be grayed out. These Service Commitments are considered ended and can no longer be billed.
* An example of a service that should not be billed recurringly but store information about the sale is a warranty extension. It is billed once through the sales order. The information about how long the extension is valid is stored in the Service Commitments.
:::


## Editing Service Commitments
### Log changes to Services Commitments
Service Commitments can be edited as lines in the **[Service Objects](/docs/srb/working-with-contracts/service-objects.md)** and contracts. If any of the following fields are edited, the Service Commitments will be archived before the change is made:
* Calculation Base Amount
* Calculation Base %
* Price
* Discount % 
* Discount Amount 
* Service Amount
* Billing Base Period
* Billing Rhythm

If the Service Amount changes due to quantity changes, the Service Commitment is also archived. In addition, changing the serial number will result in archiving, as the serial number is also present in the **Archived Service Commitments**.

If archived Service Commitments exist, the field **Archived Service Commitments** in the Service Object shows *Yes*. By clicking on *Yes* the Archived Service Commitments are displayed (incl. the corresponding quantity of the Service Object). The timestamp and user who made the change can be viewed via the Page Inspector.

:::info
If several changes are made in quick succession to the same Service Commitment, only the "original" version will be archived.
:::


### Delete Service Commitments
Service Commitments can be deleted if they have not yet been invoiced and are not yet assigned to a contract. If they are assigned to a contract, the contract line can be deleted to remove the assignment. If the Service Commitments have already been invoiced, they must first be terminated by setting a Service End Date before the Service Commitments can be deleted.

:::tip Tip
Contract lines and Service Commitments are always identical. If a contract line is edited, the change is automatically applied to the Service Commitments.
:::