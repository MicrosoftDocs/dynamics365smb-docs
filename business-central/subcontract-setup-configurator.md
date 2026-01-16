---
title: Set up purchase provisions and provision wizard
description: Learn how to configure purchase provisions and the provision wizard for subcontracting operations.
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
# Set Up Purchase Provisions and Provision Wizard

To use purchase provisions, the following basic setups must be made. First, call up the "Subcontracting Setup" via the search and navigate to the Purchase Provisions tab.

Here, among other things, specify the values for routing link code and selection of the source warehouse to be applied. At the same time, make settings here that enable automatic transfers, creation of production orders, and receipt as well as consumption postings.
If the master data used in the order process (items, stockkeeping units, production BOMs, routings) do not use other values, the setup values for purchase orders are applied.

## Purchase Provisions Settings

|Field|Description|
|:--|:--|
|**Routing Link Code for Purchase Provision**|Specifies which routing link code should be used for purchase provisions when manually entering BOMs and routings. A routing link code connects component lines with routing lines. As soon as an operation is finished, the material with the identical routing link code is consumed with the required quantity.|
|**Default Component Item No.**|Specifies the predefined component item number for purchase provisions.|
|**Work Center Group No. General**|Specifies the work center group no. to be used for purchase provisions.|
|**Work Center Put-away**|Specifies the work center for put-away in purchase provisions.|
|**Default Flushing Method**|Specifies the default flushing method to be used for purchase provisions.</br></br>**• Manual:** As soon as the finished product returns to your warehouse, the consumption of components in the production order must be posted manually.</br></br>**• Forward:** As soon as the receipt of the finished product is registered, the consumption of components is automatically posted with the expected consumption quantity of the components.</br></br>**• Backward:** As soon as the receipt of the finished product is registered, the consumption of individual components is automatically posted with the consumption quantity based on the "current shipment quantity" of the receipt.</br></br>**Note:** You can enter the same options for the provision BOMs in the item card and the components under "Replenishment".|
|**Direct Transfer for Subcontracting**|Specifies that the transfer of a subcontracting component does not use a transit location for transfers. If you transfer directly, the "Qty. to Ship" field of the transfer is filled with the same value as the quantity to be shipped. When activated, transfer and posting automatically occurs from a source warehouse to the target warehouse (vendor warehouse).|
|**Components at Location**|Specifies which location should be used as the source location when creating a transfer of subcontracting components (provision). The data is determined from the following options: </br>• **Purchase Line**</br>• **Company Information** (Field "Location Code" in the "Shipping" tab)</br>• **Manufacturing Setup** (Field "Components at Location")</br>• **Empty:** Make further specifications only when ordering.</br></br>**Note:** The "Subcontracting Location Code" on the vendor card, "Shipping" tab, applies to both subcontracting transfer and purchase provision.|
|**Always Save Changed Versions**|Specifies whether changed BOM and routing versions should always be saved in the provision wizard.|
|**Allow Edit UI Selection**|Specifies whether users may edit the UI selection in the provision wizard.|

> [!NOTE]
> The work center group no. to be applied can also be entered in the vendor card in the "Work Center Group No." field ("Shipping" tab).

Ensure that you have set up the data for the work center groups assigned to the provisions, including their work calendars.

Read more about [Setting Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md) in Microsoft's documentation.

## Provision Wizard Configuration

The Provision Wizard is a multi-step assistant for creating production orders within the framework of purchase provisions. It guides you step by step through the selection and configuration of BOMs and routings for production orders.

The wizard is automatically started when you use the "Create Production Order" function in a purchase order. Depending on existing data and your configuration, various steps are displayed or skipped.

### Wizard Steps

The wizard guides you through the following steps:

1. **Welcome:** Overview of the item and general settings
2. **BOM:** Selection and configuration of the production BOM
3. **Routing:** Selection and configuration of the routing
4. **Components:** Preview of production order components
5. **Operations:** Preview of production order operations

> [!NOTE]
> Which steps are displayed depends on your configuration in the "Subcontracting Setup".

### Processing Scenarios

The wizard processes different scenarios depending on which data is already stored in the item or in the stockkeeping units:

#### Scenario 1: Nothing Available
When neither a BOM nor a routing is stored in the item or stockkeeping units:
- **BOM:** Is automatically created from the setup configuration
- **Routing:** Is created with standard operations (subcontracting, optional put-away)
- **Components:** Use the predefined component item from the setup
- **Location:** Components are assigned to the subcontracting location

#### Scenario 2: Both Available
When both a BOM and a routing are available (from item or stockkeeping units):
- **BOM:** All existing components are transferred
- **Routing:** All existing operations are transferred
- **Components:** Use the actual items and quantities from the BOM
- **Location:** Components are assigned to the production location

#### Scenario 3: Partially Available
When only a BOM OR only a routing is available (from item or stockkeeping units):
- **Existing Data:** Is transferred from item or stockkeeping units
- **Missing Data:** Is created from the setup configuration
- **Flexibility:** Enables gradual introduction of item-specific data

> [!NOTE]
> The wizard first checks the stockkeeping units and then uses the item master data as a fallback option.

### Display/Edit Options

For different scenarios, you can specify how the wizard should behave:

|Option|Description|
|:--|:--|
|**Hide**|Step is skipped, automatic processing|
|**Show**|Step is displayed, only display/selection possible|
|**Edit**|Step is displayed, full editing possible|

### Scenario-specific Configuration

The settings are divided according to the following scenarios:

|Scenario|Description|
|:--|:--|
|**Both Available**|Configuration when both BOM and routing are available|
|**Partially Available**|Configuration when only BOM or only routing is available|
|**Nothing Available**|Configuration when neither BOM nor routing is available|

For each scenario, you can set the following options:

- **Operation/BOM Selection:** How the wizard handles the selection of routing and BOM
- **Production Operation/Components Selection:** How the wizard handles the preview of components and operations

### Application Scenarios

#### Fully Automatic Processing

When all wizard steps are configured to "Hide":
- The wizard does not open
- The production order is automatically created
- Existing or setup-based BOMs/routings are used

#### Selection without Editing

When the steps are configured to "Show":
- You can select different BOMs/routings
- Editing of lines is not possible
- Preview of generated components and operations

#### Full Editing

When the steps are configured to "Edit":
- All wizard steps are displayed
- Full editing of BOM/routing lines possible
- Creation of new versions possible
- Saving in item or stockkeeping units

### Version Management

The wizard supports the management of BOM and routing versions:

- Automatic creation of new versions when editing
- Configurable saving of versions
- Automatic cleanup of temporary data

### Save Options

You can specify where changes should be saved:

|Option|Description|
|:--|:--|
|**Do not save**|Temporary data is deleted after wizard completion|
|**Save in Item**|BOM/routing are assigned to the item|
|**Save in Stockkeeping Units**|BOM/routing are assigned to the stockkeeping unit|

## See also

- [Purchase Provisions](subcontract-purchase-provisions.md)
- [Set Up Subcontracting](subcontract-setup.md)
- [Setting Up Work Centers and Machine Centers](production-how-to-set-up-work-and-machine-centers.md)
