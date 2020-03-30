---
title: Releasing, tracking, and writing off fixed assets in Russia
description: You can manage your fixed assets utilizing the fixed assets acts features in [!INCLUDE[prodshort](../../includes/prodshort.md)]. Fixed assets acts allow you to release, track, and write-off the fixed assets of your organization.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Release, Track, and Write off Fixed Assets

You can manage your fixed assets utilizing the fixed assets acts features in [!INCLUDE[prodshort](../../includes/prodshort.md)]. Fixed assets acts allow you to release, track, and write-off the fixed assets of your organization.

The first step to managing your fixed assets is to set up fixed assets numbering and source codes.

## To set up fixed asset numbering

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset Setup**, and then choose the related link.
2. On the **Numbering** FastTab, select a number series for each type of fixed asset transaction.
3. Choose the **OK** button to close the window and save your entries.

## To set up fixed asset source codes

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Source Code Setup**, and then choose the related link.
2. On the **Fixed Assets** FastTab, select a source code for each type of fixed asset.
3. Choose the **OK** button to close the window and save your entries.

## Releasing Fixed Assets into Service

An asset is recognized as a fixed asset after it is released into service for the organization. You can use the **FA Release Act** window to release fixed assets into service.

### To release fixed assets into service

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Release Act**, and then choose the related link.

2. On the **General** FastTab, fill in the fields as described in the following table.

   | Field                         | Description                                                  |
   | ----------------------------- | ------------------------------------------------------------ |
   | **No.**                       | Enter the identification number that is assigned to the fixed asset release. |
   | **Posting Description**       | Enter a description for the fixed asset release. A description is automatically created from the document type and release number. |
   | **Reason Document No.**       | Enter the identification number of the source document that is the reason for the fixed asset release. |
   | **Reason Document Date**      | Enter the date of the source document that is the reason for the fixed asset release. This information is used in fixed asset reports and entries. |
   | **FA Posting Date**           | Enter the date on which the fixed asset release is posted. This information is used in fixed asset reports and entries. |
   | **External Document No.**     | Enter the number of the external document that relates to this fixed asset release. |
   | **Posting No.**               | Enter an identifying posting number to use for the fixed asset release entry. |
   | **Shortcut Dimension 1 Code** | Enter the department code that is associated with the fixed asset. |
   | **Shortcut Dimension 2 Code** | Enter the incexp code that is associated with the fixed asset. |

3. On the **Lines** FastTab, fill in the fields as described in the following table.

   | Field                          | Description                                                  |
   | ------------------------------ | ------------------------------------------------------------ |
   | **FA No.**                     | Enter the identification number that is assigned to the fixed asset to be released. |
   | **Description**                | Enter a description for the fixed asset.                     |
   | **Depreciation Book Code**     | Enter the code for the depreciation book that is used to post depreciation for the fixed asset. The value is set using information from the **Fixed Asset Setup** window. |
   | **New Depreciation Book Code** | Enter an alternative depreciation book code that is used to post depreciation for the released fixed asset entry. |

4. Choose the **OK** button to post your entries and release the fixed assets into service.

## Tracking the Movement of Fixed Assets

Tracking the location and status of fixed assets is an important function within most organizations. For example, you may want to record the movement of office equipment from a previous location to a new location. You can use the **FA Movement Act** window to track the movement of fixed assets and record the status of your fixed assets.

### To track the movement of fixed assets

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Movement Act**, and then choose the related link.

2. On the **General** FastTab, fill in the fields as described in the following table.

   | Field                         | Description                                                  |
   | ----------------------------- | ------------------------------------------------------------ |
   | **No.**                       | Enter an identification number that is assigned to the fixed asset movement entry. |
   | **Posting Description**       | Enter a description for the fixed asset movement entry. A description is automatically created from the document type and movement number. |
   | **Reason Document No.**       | Enter the identification number of the source document that is the reason for the fixed asset movement. |
   | **Reason Document Date**      | Enter the date of the source document that is the reason for the fixed asset movement. This information is used in fixed asset reports and entries. |
   | **FA Location Code**          | Specifies the location of the fixed asset before it being moved. |
   | **New FA Location Code**      | Enter the new location for the fixed asset.                  |
   | **FA Posting Date**           | Enter the date on which the fixed asset movement entry is posted. This information is used in fixed asset reports and entries. |
   | **External Document No.**     | Enter the number of the external document that relates to this fixed asset movement entry. |
   | **Posting No.**               | Enter an identifying posting number to use for the fixed asset movement entry. |
   | **Shortcut Dimension 1 Code** | Enter the department code that is associated with the fixed asset. |
   | **Shortcut Dimension 2 Code** | Enter the incexp code that is associated with the fixed asset. |

3. On the **Lines** FastTab, fill in the fields as described in the following table.

   | Field                          | Description                                                  |
   | ------------------------------ | ------------------------------------------------------------ |
   | **FA No.**                     | Enter an identification number that is assigned to the fixed asset movement line entry. |
   | **Description**                | Enter a description for the fixed asset movement line entry. |
   | **Status**                     | Enter the status of the fixed asset. The options include **Inventory**, **Montage**, **Operation**, **Maintenance**, **Repair**, **Disposed**, and **Written Off**. |
   | **Depreciation Book Code**     | Enter the code for the depreciation book that is used to post depreciation for the fixed asset. The value is set using information from the **Fixed Asset Setup** window. |
   | **New Depreciation Book Code** | Enter a new depreciation book code that is used to post depreciation after the fixed asset movement entry is posted. |
   | **Reason Code**                | Enter a reason code fixed asset movement entry.              |

4. Choose the **OK** button to post your entries and record the movement of the fixed asset.

## Writing Off the Value of a Fixed Asset

During the sale or disposal of a fixed asset, you may want to write-off the remaining book value of the asset that has not been depreciated. You can use the **FA Writeoff Act** window to write-off the remaining value of a fixed assets.

### To write-off the value of a fixed asset

1. Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **FA Writeoff Act**, and then choose the related link.

2. On the **General** FastTab, fill in the fields as described in the following table.

   | Field                         | Description                                                  |
   | ----------------------------- | ------------------------------------------------------------ |
   | **No.**                       | Enter an identification number that is assigned to the fixed asset write-off entry. |
   | **Posting Description**       | Enter a description for the fixed asset write-off entry. A description is automatically created from the document type and write-off number. |
   | **Reason Document No.**       | Enter the identification number of the source document that is the reason for the fixed asset write-off. |
   | **Reason Document Date**      | Enter the date of the source document that is the reason for the fixed asset write-off. This information is used in fixed asset reports and entries. |
   | **FA Location Code**          | Specifies the location of the fixed asset.                   |
   | **FA Employee No.**           | Enter the employee number of the person who maintains possession of the fixed asset. |
   | **FA Posting Date**           | Enter the date on which the fixed asset write-off entry is posted. This information is used in fixed asset reports and entries. |
   | **External Document No.**     | Enter the number of the external document that relates to this fixed asset write-off entry. |
   | **Posting No.**               | Enter an identifying posting number to use for the fixed asset write-off entry. |
   | **Shortcut Dimension 1 Code** | Enter the department code that is associated with the fixed asset. |
   | **Shortcut Dimension 2 Code** | Enter the incexp code that is associated with the fixed asset. |

3. On the **Lines** FastTab, fill in the fields as described in the following table.

   | Field                      | Description                                                  |
   | -------------------------- | ------------------------------------------------------------ |
   | **FA No.**                 | Enter an identification number that is assigned to the fixed asset write-off line entry. |
   | **Description**            | Enter a description for the fixed asset write-off line entry. |
   | **Depreciation Book Code** | Enter the code for the depreciation book that is used to post depreciation for the fixed asset. The value is set using information from the **Fixed Asset Setup** window. |
   | **Item Receipt No.**       | Enter the receipt number from the item sale or disposal document. |
   | **Reason Code**            | Enter a reason code for the fixed asset write-off entry.     |

4. Choose the **OK** button  to post your entries and record the write-off of the fixed asset.

## See Also

[Fixed Assets](../../fa-manage.md)  
