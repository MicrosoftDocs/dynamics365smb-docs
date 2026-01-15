---
title: Purchase provisions for subcontracting
description: Learn how to create and post purchase provisions with linked production orders and transfer orders for subcontracting operations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: 99000886,
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---
# Purchase Provisions

While subcontracting outsources individual production steps/manufacturing work externally, e.g., milling work, cutting, or surface treatments, purchase provisions involve processing individual components by an external service provider into a finished product. With the purchase order, a service from the vendor is invoiced. The purchase order is simultaneously linked to the corresponding production order.

After completion of the product, it returns to your own warehouse. You can individually set up when transfers or receipts and issues are posted.

You can create, edit, and view the production orders required for posting the provision as well as any transfer orders from the purchase order. The required components can be specified order-specifically or taken from existing production BOMs.


## Create Order (incl. Production Order)

Detailed instructions for creating and posting purchase provisions, including linking with production orders and transfer orders.

Depending on the basic setup and (non-)existing BOMs, you create the order and assign the necessary BOM components using a production order. When using the subcontracting type "Transfer", you create the transfer order. You can initiate the postings of inventory changes in the purchase order card or using warehouse functions. How you can proceed in which type of posting situation can be read in the respective chapters of Microsoft's documentation.

1. Create a new purchase order and enter all relevant data.
    > [!NOTE]
    > Note that the "Location Code" for subcontracting is maintained on the vendor card.

1. In the lines, select the item to be procured.

1. In the "Quantity" column, specify how many finished produced items should return.

1. Under "Direct Unit Cost", specify the price of the service. A price may already be preset, read more about this under "Subcontractor Prices".

1. For the purchase line, select "Functions", "Create Production Order". Depending on the previously selected flushing method ("Basic Setup Purchase Provision"), consumption is posted with shipment posting of the subcontracting service using the production order, as well as the receipt of the item produced by the supplier in the warehouse. The details are created in the background via the creation of the production order.

1. The provision wizard starts automatically and guides you through the configuration of BOMs and routings. Depending on the configuration in the "Subcontracting Setup", various steps are displayed or automatically processed. More information about the wizard can be found under **Purchase Provisions Setup**.

1. Back in the purchase order, you can transfer the provision components with subcontracting type "Transfer" into a transfer. On the purchase order page, select "Actions", "Functions", "Create Transfer Order for Subcontracting". With this function, the required BOM component lines are transferred to a transfer order. The location codes "Transfer-from Code" and "Transfer-to Code" are filled based on the basic setup specifications. If an open transfer order exists for the vendor's location code, it is supplemented with the required lines.

Information about the production orders and transfer orders linked to the purchase order can be obtained in the "Lines" tab via the "Production" menu.

Read more about [Transfer](https://learn.microsoft.com/dynamics365/business-central/inventory-how-transfer-between-locations) in Microsoft's documentation.

## Post Orders with Provision

1. **Transfer of BOM Components**
The components transferred to a transfer order are posted with the warehouse functionalities (depending on the setup) of the addressed location codes.

1. **Consumption of Provided BOM Components**
   + **Forward:** The BOM components assigned with the flushing method "Forward" or "Backward" are automatically posted with the entry type "Consumption" via the created production order from the vendor's location when posting the "Qty. to Receive".

    > [!NOTE]
    > Items with assignment of subcontracting type "Purchase with Service" must first be posted in the purchase order with "Qty. to Receive".

    + **Manual:** The BOM components assigned with the flushing method "Manual" must be posted separately after receipt of the produced item. To do this, switch to the production order linked to the purchase line. In the production order, select "Line" and "Production Journal", "Post".

1. **Receiving the Produced Item**
You post the receipt of the produced item in the purchase order. Specify the "Qty. to Receive" and post Receive. The item ledger entry is created with the entry type "Output" with reference to the linked production order. If you work with different bins in your location, you can put away the inventory to the target bin code with bin transfers.

1. **Post Invoice**
The posting of invoicing is done with purchasing functionalities, analogous to other purchase invoices, for received goods. The posted line amount is transferred to the production order for valuation of the produced items and supplemented by the value of the consumed items. Finally, change the status of the production order to "Finished".

Read more about [Working with Production Orders](https://learn.microsoft.com/dynamics365/business-central/production-about-production-orders) in Microsoft's documentation.



## Purchase Provisions Setup

To use purchase provisions, the following basic setups must be made. First, call up the "Subcontracting Setup" via the search and navigate to the Purchase Provisions tab.

Here, among other things, specify the values for routing link code and selection of the source warehouse to be applied. At the same time, make settings here that enable automatic transfers, creation of production orders, and receipt as well as consumption postings.
If the master data used in the order process (items, stockkeeping units, production BOMs, routings) do not use other values, the setup values for purchase orders are applied.

|Field/Switch|Description|
|:--|:--|
|**Routing Link Code for Purchase Provision**|Specifies which routing link code should be used for purchase provisions when manually entering BOMs and routings. A routing link code connects component lines with routing lines. As soon as an operation is finished, the material with the identical routing link code is consumed with the required quantity.|
|**Work Center Group No. General**|Specifies the work center group no. to be used for purchase provisions.|
|**Default Flushing Method**|Specifies the default flushing method to be used for purchase provisions.</br></br>**• Manual:** As soon as the finished product returns to your warehouse, the consumption of components in the production order must be posted manually.</br></br>**• Forward:** As soon as the receipt of the finished product is registered, the consumption of components is automatically posted with the expected consumption quantity of the components.</br></br>**• Backward:** As soon as the receipt of the finished product is registered, the consumption of individual components is automatically posted with the consumption quantity based on the "current shipment quantity" of the receipt.</br></br>**Note:** You can enter the same options for the provision BOMs in the item card and the components under "Replenishment".|
|**Direct Transfer for Subcontracting**|Specifies that the transfer of a subcontracting component does not use a transit location for transfers. If you transfer directly, the "Qty. to Ship" field of the transfer is filled with the same value as the quantity to be shipped. When activated, transfer and posting automatically occurs from a source warehouse to the target warehouse (vendor warehouse).|
|**Components at Location**|Specifies which location should be used as the source location when creating a transfer of subcontracting components (provision). The data is determined from the following options: </br>• **Purchase Line**</br>• **Company Information** (Field "Location Code" in the "Shipping" tab)</br>• **Manufacturing Setup** (Field "Components at Location")</br>• **Empty:** Make further specifications only when ordering.</br></br>**Note:** The "Subcontracting Location Code" on the vendor card, "Shipping" tab, applies to both subcontracting transfer and purchase provision.|

> [!NOTE]
> The work center group no. to be applied can also be entered in the vendor card in the "Work Center Group No." field ("Shipping" tab).

Ensure that you have set up the data for the work center groups assigned to the provisions, including their work calendars.

Read more about [Setting Up Work Centers and Machine Centers](https://learn.microsoft.com/dynamics365/business-central/production-how-to-set-up-work-and-machine-centers) in Microsoft's documentation.




## Provision Wizard

The Provision Wizard is a multi-step assistant for creating production orders within the framework of purchase provisions. It guides you step by step through the selection and configuration of BOMs and routings for production orders.
The wizard is automatically started when you use the "Create Production Order" function in a purchase order. Depending on existing data and your configuration, various steps are displayed or skipped.

## Wizard Steps

The wizard guides you through the following steps:

1. **Welcome:** Overview of the item and general settings
2. **BOM:** Selection and configuration of the production BOM
3. **Routing:** Selection and configuration of the routing
4. **Components:** Preview of production order components
5. **Operations:** Preview of production order operations

> [!NOTE]
> Which steps are displayed depends on your configuration in the "Subcontracting Setup".

## Processing Scenarios

The wizard processes different scenarios depending on which data is already stored in the item or in the stockkeeping units:

### Scenario 1: Nothing Available
When neither a BOM nor a routing is stored in the item or stockkeeping units:
- **BOM:** Is automatically created from the setup configuration
- **Routing:** Is created with standard operations (subcontracting, optional put-away)
- **Components:** Use the predefined component item from the setup
- **Location:** Components are assigned to the subcontracting location

### Scenario 2: Both Available
When both a BOM and a routing are available (from item or stockkeeping units):
- **BOM:** All existing components are transferred
- **Routing:** All existing operations are transferred
- **Components:** Use the actual items and quantities from the BOM
- **Location:** Components are assigned to the production location

### Scenario 3: Partially Available
When only a BOM OR only a routing is available (from item or stockkeeping units):
- **Existing Data:** Is transferred from item or stockkeeping units
- **Missing Data:** Is created from the setup configuration
- **Flexibility:** Enables gradual introduction of item-specific data

> [!NOTE]
> The wizard first checks the stockkeeping units and then uses the item master data as a fallback option.

## Application Scenarios

### Fully Automatic Processing

When all wizard steps are configured to "Hide":
- The wizard does not open
- The production order is automatically created
- Existing or setup-based BOMs/routings are used

### Selection without Editing

When the steps are configured to "Show":
- You can select different BOMs/routings
- Editing of lines is not possible
- Preview of generated components and operations

### Full Editing

When the steps are configured to "Edit":
- All wizard steps are displayed
- Full editing of BOM/routing lines possible
- Creation of new versions possible
- Saving in item or stockkeeping units

## Configuration

The wizard configuration is done in the "Subcontracting Setup" under the "Purchase Provisions" tab.

### Important Setting Fields

|Field|Description|
|:--|:--|
|**Routing Link Code for Purchase Provision**|Routing link code for purchase provision|
|**Default Component Item No.**|Predefined component item number|
|**Work Center Group No. General**|Common work center for purchase provisions|
|**Work Center Put-away**|Work center for put-away|
|**Default Flushing Method**|Standard flushing method for components|
|**Always Save Changed Versions**|Always save changed versions|
|**Allow Edit UI Selection**|User may edit UI selection|

### Display/Edit Options

For different scenarios, you can specify how the wizard should behave:

- **Hide:** Step is skipped, automatic processing
- **Show:** Step is displayed, only display/selection possible
- **Edit:** Step is displayed, full editing possible

### Scenario-specific Configuration

The settings are divided according to the following scenarios:

- **Both Available:** Both BOM and routing are available
- **Partially Available:** Only BOM or only routing is available
- **Nothing Available:** Neither BOM nor routing are available

## Version Management

The wizard supports the management of BOM and routing versions:

- Automatic creation of new versions when editing
- Configurable saving of versions
- Automatic cleanup of temporary data

## Save Options

You can specify where changes should be saved:

- **Do not save:** Temporary data is deleted after wizard completion
- **Save in Item:** BOM/routing are assigned to the item
- **Save in Stockkeeping Units:** BOM/routing are assigned to the stockkeeping unit

## Application

1. Create a new purchase order and enter all relevant data.
    > [!NOTE]
    > Note that the "Location Code" for subcontracting is maintained on the vendor card.

2. In the lines, select the item to be procured.

3. For the purchase line, select "Functions", "Create Production Order".

4. The Provision Wizard starts automatically and guides you through the configured steps:

   + **Welcome:** Check the item information and general settings
   + **BOM:** Select a production BOM or edit it (if configured)
   + **Routing:** Select a routing or edit it (if configured)
   + **Components:** Check the production order components (if configured)
   + **Operations:** Check the production order operations (if configured)

5. After completing the wizard, the production order is created and linked to the purchase line.

> [!NOTE]
> Depending on the configuration in the "Subcontracting Setup", individual steps can be automatically skipped or displayed for editing.