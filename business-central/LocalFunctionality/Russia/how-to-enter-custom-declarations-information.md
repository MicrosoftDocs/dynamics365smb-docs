---
title: Entering custom declaration information in Russia
description: Russian localization includes enhancements for managing customs declarations, enabling tracking, and printing of declaration numbers for imported goods.
author: brentholtorf
ms.topic: how-to
ms.search.keywords: custom declarations, item tracking, item tracking codes, Russia
ms.date: 07/15/2025
ms.reviewer: v-soumramani
ms.author: bholtorf
ms.service: dynamics-365-business-central
---

# Custom declaration
Russian legislation requires companies to record and track the customs declaration number for all imported goods. If a company sells imported goods, it must print the customs declaration number and the country/region of origin on invoices.

## Setup

> [!NOTE]
> You may need to enable this capability by going to the **Feature Management** page and enable **Feature Update: Use tracking by package number in reservation and tracking system**.

### Check the format of customs declarations

Custom declarations have a special format. You can verify that your format is correct by choosing **Yes** in the **Check CD No. Format** field on the **Inventory Setup** page.

You must also specify a format on the **CD Number Format** page. The following table describes the symbols you can use.

|Symbol  |Use for|
|---------|---------|
|#|Any number.|
|@|Any Russian or Latin letter.|
|?|Any character|

All other characters are an exact match.

### Set up item tracking codes

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Tracking Codes**, and then choose the related link.
1. Create new item tracking codes that are used for items that require custom declaration tracking.
1. Set the **Package Specific Tracking** to **Yes** for the item tracking code.
1. Choose **CD Tracking Location Setup**, where you can define rules for specific locations. For example, you can configure a foreign location to use temporary customs declaration tracking until the moment the goods cross the border and receive a real customs declaration number.
1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.
1. Assign the item tracking code to all items that require customs declaration tracking.

<!-- 
> [!NOTE]
> Unlike the Serial or Lot number specific tracking, you can add CD specific tracking to items that have open transactions.
-->

### Create a customs declaration

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Custom Declarations**, and then choose the related link.
1. Create a new customs declaration, and fill in the following fields.

   | Field | Description |
   |:-|:-|
   | **No.** | Specifies the custom declaration number. |
   | **Description** | Specifies the description of the custom declaration number. |
   | **Source Type** | Select the source type for the custom declaration. Source types include **Blank**, **Customer**, **Vendor**, and **Item**. |
   | **Source No.** | Specifies the source number from either the **Customer**, **Vendor**, or **Item List** table. |
   | **Country of Origin Code** | Specifies the country/region for the customer if all the items in the customs declaration came from the same country/region. Information from this field is copied to lines on the customs declaration. |
   | **Declaration Date** | Enter the date of the customs declaration. |

1. Create lines with items according to the content of the declaration you received from the customs authority.
1. Choose the **OK** button.

> [!NOTE]
> You may want to create a temporary customer declaration to enable scenarios when goods are first received at a custom location. Set **Temporary CD Number** to **Yes** on the lines of the temporary customs declaration. You'll be able to assign permanent customs declaration number when transferring goods to or from customs and your warehouse.
>
> If you choose **Yes** in the **Check CD No. Format** field on the **Inventory Setup** page, the **Temporary CD Number** field is automatically set based on what you entered in the **CD No** field.

### Purchase and sales

The process of assigning a customs declaration number is similar to assigning lot and serial numbers. For more information, see [Assign Serial and Lot Numbers to Items for Tracking](../../inventory-how-work-item-tracking.md#to-assign-serial-or-lot-numbers-during-an-inbound-transaction)

### Change a customs declaration number

The process of changing customs declaration numbers is similar to changing lot and serial numbers. For more information, see [Reclassify Serial and Lot Numbers](../../inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers)

## Print the factura-invoice

You must print the customs declaration number on Factura-Invoice documents.

### Print the posted factura-invoice

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Invoice**, and then choose the related link.
1. Choose the **Print** action, and then choose **Posted Factura-Invoice**.
1. Choose the **Print** action to print the report, or choose the **Preview** action to view it on the screen. Choose the **Cancel** action to save the information without printing the report.

### Print the factura-invoice before posting

1. Choose the ![ Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoice**, and then choose the related link.
1. Choose the **Print** action, and then choose the **Order Factura-Invoice** action.
1. Choose the **Print** action to print the report, or choose the **Preview** action to view it on the screen. Choose the **Cancel** action to save the information without printing the report.

## Related information

- [Russia Local Functionality](russia-local-functionality.md)  
- [Customizing Business Central Using Extensions](../../ui-extensions.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
