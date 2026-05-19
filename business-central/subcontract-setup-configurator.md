---
title: Set up purchase provisions and provision wizard
description: Learn how to configure purchase provisions and the provision setup guide for subcontracting operations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: subcontracting, purchase provisions, wizard, setup, BOM, routing
ms.search.form: 99000886
ms.date: 01/15/2026
ms.service: dynamics-365-business-central
ms.custom: bap-template

---

[!INCLUDE [early-access-partners-only](includes/early-access-partners-only.md)]

# Set up purchase provisions and use the provision setup guide

To use purchase provisions, you must configure settings for routing link codes, source warehouse selection, automatic transfers, creation of production orders, and receipt and consumption postings. If the master data you use in the order process, such as items, stockkeeping units, production BOMs, and routings, don't use other values, [!INCLUDE [prod_short](includes/prod_short.md)] applies the setup values for purchase orders.

## Configure purchase provisions settings

The following steps describe how to configure purchase provisions.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Setup**, and then choose the related link.
2. On the **Purchase Provisions** FastTab, fill in the fields as described in the following table. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

|Field|Description|
|-----|----------|
|**Routing Link Code for Purchase Provision**|Specifies which routing link code to use for purchase provisions when you manually enter BOMs and routings. A routing link code connects component lines with routing lines. When an operation finishes, the material with the identical routing link code is consumed with the required quantity.|
|**Default Component Item No.**|Specifies the default component item number for purchase provisions.|
|**Work Center Group No. General**|Specifies the work center group number to use for purchase provisions.|
|**Work Center Put-away**|Specifies the work center for put-away in purchase provisions.|
|**Default Flushing Method**|Specifies the default flushing method to use for purchase provisions. The following options are available:<br><br>**Manual** - You must manually post the consumption of components in the production order after the finished product returns to your warehouse.<br><br>**Forward** - When you register receipt of the finished product, [!INCLUDE [prod_short](includes/prod_short.md)] automatically posts consumption of components with the expected consumption quantity.<br><br>**Backward** - When you register receipt of the finished product, [!INCLUDE [prod_short](includes/prod_short.md)] automatically posts consumption of individual components with the consumption quantity based on the current shipment quantity of the receipt.<br><br>You can enter the same options for the provision BOMs in the item card and the components on the **Replenishment** FastTab.|
|**Direct Transfer for Subcontracting**|Specifies that the transfer of a subcontracting component doesn't use a transit location for transfers. When you turn on direct transfer, the **Qty. to Ship** field of the transfer is filled with the same value as the quantity to be shipped. Transfer and posting automatically occur from a source warehouse to the target warehouse (vendor warehouse).|
|**Components at Location**|Specifies which location to use as the source location when you create a transfer of subcontracting components (provision). [!INCLUDE [prod_short](includes/prod_short.md)] determines the data from the following options:<br>**Purchase Line**<br>**Company Information** (the **Location Code** field on the **Shipping** FastTab)<br>**Manufacturing Setup** (the **Components at Location** field)<br>**Empty** - Specify further details only when ordering.<br><br>The **Subcontracting Location Code** on the vendor card, **Shipping** FastTab, applies to both subcontracting transfer and purchase provision.|
<!-- |**Always Save Changed Versions**|Specifies whether changed BOM and routing versions are always saved in the provision wizard.|
|**Allow Edit UI Selection**|Specifies whether users can edit the UI selection in the provision wizard.| -->

> [!NOTE]
> You can also enter the work center group number on the vendor card in the **Work Center Group No.** field on the **Shipping** FastTab.

Make sure that you set up the data for the work center groups assigned to the provisions, including their work calendars. Learn more in [Set up work and machine centers](production-how-to-set-up-work-and-machine-centers.md).

## Set up default component locations

You can specify which location [!INCLUDE [prod_short](includes/prod_short.md)] uses by default to provide components for subcontracting.

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Subcontracting Setup**, and then choose the related link.
2. On the **Purchase Provisions** FastTab, in the **Components at Location** field, choose one of the following options:

|Option|Description|
|------|----------|
|**Purchase**|Components come from the standard purchase location. [!INCLUDE [prod_short](includes/prod_short.md)] determines the location automatically.|
|**Company**|Components come from the company location specified in the **Location Code** field on the **Company Information** page.|
|**Manufacturing**|Components come from the manufacturing location specified in the **Components at Location** field on the **Manufacturing Setup** page.|

> [!NOTE]
> If you choose **Company** or **Manufacturing**, make sure the location code is specified in the respective setup pages.

### Location assignment scenarios

The following scenarios show how [!INCLUDE [prod_short](includes/prod_short.md)] assigns locations in different situations.

#### Purchase provision without existing data

- **Component location**: From the **Components at Location** field in the setup.
- **Subcontracting location**: From the **Subcontracting Location Code** field on the vendor card.

#### Purchase provision with existing bill of materials

- **Component location**: From the **Components at Location** field on the **Manufacturing Setup** page.
- **Adjustment**: Based on the subcontracting type of the components.

## About the provision setup guide

The provision setup guide helps you create production orders for purchase provisions. It guides you through the selection and configuration of BOMs and routings for production orders.

[!INCLUDE [prod_short](includes/prod_short.md)] automatically starts the wizard when you use the **Create Production Order** action in a purchase order. Depending on your existing data and configuration, different steps are displayed or skipped.

### Wizard steps

The wizard guides you through the following steps:

1. **Welcome** - Overview of the item and general settings.
2. **BOM** - Selection and configuration of the production BOM.
3. **Routing** - Selection and configuration of the routing.
4. **Components** - Preview of production order components.
5. **Operations** - Preview of production order operations.

> [!NOTE]
> Which steps display depends on your configuration in the **Subcontracting Setup**.

### Processing scenarios

The setup guide processes different scenarios depending on which data is stored in the item or in the stockkeeping units.

#### When no BOM or routing is available

When neither a BOM nor a routing is stored in the item or stockkeeping units:

- **BOM** - Created automatically from the setup configuration.
- **Routing** - Created with standard operations (subcontracting, optional put-away).
- **Components** - Use the predefined component item from the setup.
- **Location** - Components are assigned to the subcontracting location.

#### When both BOM and routing are available

When both a BOM and a routing are available from the item or stockkeeping units:

- **BOM** - All existing components are transferred.
- **Routing** - All existing operations are transferred.
- **Components** - Use the actual items and quantities from the BOM.
- **Location** - Components are assigned to the production location.

#### When only a BOM or only a routing is available

When only a BOM or only a routing is available from the item or stockkeeping units:

- **Existing data** - Transferred from the item or stockkeeping units.
- **Missing data** - Created from the setup configuration.
- **Flexibility** - Enables gradual introduction of item-specific data.

> [!NOTE]
> The wizard first checks the stockkeeping units and then uses the item master data as a fallback option.

### Display and edit options

For different scenarios, you can specify what the setup guide does:

|Option|Description|
|------|----------|
|**Hide**|The step is skipped and automatically processed.|
|**Show**|The step is displayed for display or selection only.|
|**Edit**|The step is displayed with full editing available.|

### Scenario-specific configuration

The settings are divided according to the following scenarios:

|Scenario|Description|
|--------|----------|
|**Both Available**|Configuration when both BOM and routing are available.|
|**Partially Available**|Configuration when only BOM or only routing is available.|
|**Nothing Available**|Configuration when neither BOM nor routing is available.|

For each scenario, you can set the following options:

- **Operation/BOM Selection** - How the wizard handles the selection of routing and BOM.
- **Production Operation/Components Selection** - How the wizard handles the preview of components and operations.

### Application scenarios

#### Fully automatic processing

When all wizard steps are configured to **Hide**:

- The wizard doesn't open.
- The production order is automatically created.
- Existing or setup-based BOMs and routings are used.

#### Selection without editing

When the steps are configured to **Show**:

- You can select different BOMs and routings.
- You can't edit lines.
- You can preview generated components and operations.

#### Full editing

When the steps are configured to **Edit**:

- All wizard steps are displayed.
- You can fully edit BOM and routing lines.
- You can create new versions.
- You can save in the item or stockkeeping units.

### Version management

The wizard supports the management of BOM and routing versions:

- Automatic creation of new versions when editing.
- Configurable saving of versions.
- Automatic cleanup of temporary data.

### Save options

You can specify where changes should be saved:

|Option|Description|
|------|----------|
|**Do not save**|Temporary data is deleted after wizard completion.|
|**Save in Item**|BOM and routing are assigned to the item.|
|**Save in Stockkeeping Units**|BOM and routing are assigned to the stockkeeping unit.|


## Related information

[Set up purchase provisions for subcontracting](subcontract-purchase-provisions.md)  
[Set up subcontracting](subcontract-setup.md)  
[Set up work and machine centers](production-how-to-set-up-work-and-machine-centers.md)  
[Manufacturing](production-manage-manufacturing.md)  
[Work with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
