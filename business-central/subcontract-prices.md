---
title: Set up subcontractor prices
description: Learn how to set up and maintain subcontractor prices for work center groups, including copying prices between vendors and filtering options.
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
# Subcontractor Prices

Store your subcontractor prices in your master data here and view all prices for each item at a glance. To do this, call up the "Subcontractor Prices" card via the search.
The maintenance of subcontractor prices can be done with assignment to vendors, standard catalog filters, and work center groups.
The subcontractor prices are accessible from the work center group card as well as the vendor card.

## General

In the "Subcontractor Prices" card, under "General", you can use various filters for subcontractor prices to simplify editing. The following filters are available to you:

+ Vendor No. Filter

+ Work Center Group No. Filter

+ Standard Catalog Code Filter

+ Item No. Filter

+ Starting Date Filter

Fill the lines with a "Work Center Group No.", "Vendor No." as well as "Item No.".
Enter specific activities for the respective work center group in the "Standard Catalog Code" within the lines. Then enter the activity-related price under "Purchase Price". This can refer to items, time periods, units of measure, and quantities.

>[!NOTE]
> Required fields to be filled are always "Work Center Group No.", "Vendor No." and "Item No.".

## Define Prices via Work Center Group Card

Analogous to the known purchase price storage, you can store activity-related prices for the individual work center group.

1. Open your work center group and select a group. The work center group card will be displayed.

1. In the ribbon, under "Related", select "Subcontracting", "Subcontractor Prices".

1. In the "Subcontractor Prices" card, the "Work Center Group No." from which you came is already displayed under "Work Center Group No. Filter".

1. Enter specific activities for the respective work center group in the "Standard Catalog Code" within the lines.

1. Enter the activity-related price in the "Purchase Price" column. This refers to items, item variants, time periods, units of measure, and quantities. Information about minimum quantity can also be provided.

1. If you have agreed on a minimum amount per process with your subcontracting vendor for each production order quantity, enter this in the "Minimum Amount" field. The price finding for the production order operation considers this amount and determines the purchase price based on the order quantity.

> [!NOTE]
> Required fields to be filled are always "Work Center Group No.", "Vendor No." and "Item No.".

## Copy Prices

In the "Subcontractor Prices" card, you have the option to copy prices from one vendor to another vendor. Enter the number of the vendor in the "Vendor No. Filter" field and the number of the work center group in the "Work Center Group No. Filter" field for which you want to create new copied prices. Activate the "Copy Subcontractor Prices" action, select and mark the lines to be copied. By clicking "OK", the marked lines are copied for the selected vendor.

## Call Up Prices via a Routing

You can additionally call up the subcontractor prices starting from the routing. First open the corresponding routing and select the subcontracting within the lines. Then navigate via the ribbon to "More Options", "Operation" and "Subcontractor Prices". This way you get to the "Subcontractor Prices" card and can view or edit the appropriate information for the item.