---
title: Items
hide_title: true
sidebar_label: Items
slug: /srb/masterdata/items
---

# Service Commitments at Items
Items can be set when being used they either bring additional service commitments with them or they represent service commitments themselves. The setting for this can be made via the **Service Commitment Option** field (in the *Prices and Sales* fast tab). Basically, four options are available:

|Option|Meaning|
|:--|:--|
|Sales without Service Commitment|This selection means that the item is for sale only and not for Service Commitments or contracts. This setting is typically used for trade-only items. <br/> For items with this setting, *no Service Object* will be created upon delivery. This is also not possible manually.|
|Sales with Service Commitment|This selection means that this item can be sold with additional service commitments. If additional service commitments are stored, these are used either automatically (**Default**=*Yes* in assigned Service Commitment Package) or on request in the sales process. <br/> For items with this setting, a *Service Object is created automatically* upon delivery.
|Service Commitment Item|This selection means that this item can be used in a sales document, but Invoicing is done exclusively (in the form of Service Commitments) via the contract. When a Sales Order line is delivered, it will automatically be set as *Invoiced*. This option can only be selected if **Type**=*No Inventory*. <br/> For items with this setting, a *Service Object is created automatically* upon delivery.
|Invoicing Item|This selection means that this item will be used for billing additional service commitments sold for another item. This option can be selected only if **Type**=*Non-Inventory*. This item cannot be used in document lines (Sales Quote / Sales Order / Sales Invoice / Purchase Invoice). <br/> No Service Object *can* be created for items with this setting.


## Service Commitments (Infobox)
The Service Commitments stored on an item are displayed in the infobox area via the infobox of the same name. This infobox is available in the Item list as well as in the Item card. <br/>
In addition to the name of the Service Commitment Package, the infobox also shows whether the respective Service Commitment Package is marked as *Standard*. If an item set in this way is used in the sales process, all the services from the corresponding Service Commitments Packages are transferred to the sales item in the document (see [Assign Services](/docs/srb/sales/sales-service-commitments.md)).
Clicking on the header of the infobox opens the **Service Commitment Packages per Item** page. Here, the overview of all Service Commitment Packages stored for the item (upper part) including the respective details (Service Commitment Package Lines, lower part) is displayed. For visual assignment, the Service Commitment Package Lines for the currently selected package are displayed in bold. This is particularly helpful if several Service Commitment Packages are stored for the item. Insert the Service Commitment Package in a new line to add it to the item. If a line is deleted, the Service Commitments will not be available in Sales Orders or Quotes anymore.


## Service Commitments (Action)
Analogous to the Infobox, the Service Commitments stored on the item can also be called up via the **Service Commitments** action. The call is located in the **Item** action group and is available both in the Item list and in the Item card.