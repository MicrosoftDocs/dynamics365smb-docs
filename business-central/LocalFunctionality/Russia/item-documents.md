---
title: Inventory documents in Russia
description: Russian enhancements for inventory documents.
author: DianaMalina
ms.topic: how-to
ms.search.keywords: inventory, inventory documents, report act items, report items, items receipt, Russia
ms.search.form: 6774, 6775, 6776
ms.date: 10/23/2026
ms.reviewer: jswymer
ms.author: jswymer
ms.service: dynamics-365-business-central
ai-usage: ai-assisted
---

# Inventory documents

[!INCLUDE[prod_short](../../includes/prod_short.md)] includes inventory document reports such as Write-off act TORG-16, Items Receipt Act TORG-1, and Receipt Deviations TORG-2. Confirm which forms your organization must use under current requirements.

Configure the corresponding report templates before you generate these reports. For receipt reports, use **Purchases & Payables Setup**, including **M-7 Template Code** and **TORG-1 Template Code**. Configure inventory shipment templates in **Inventory Setup**. If **Report Selection - Print** opens after you choose **Print**, select **Print Report** for the report that you need, and then choose **OK**. Complete the report options and choose **OK** to export the report to Excel.

## Report Act Items Receipt M-7, Items Receipt Act TORG-1, and Receipt Deviations TORG-2 based on an unposted inventory receipt

The following procedure shows how to create the following reports based on inventory receipt documents that aren't posted.
- Act Items Receipt M-7
- Items Receipt Act TORG-1
- Receipt Deviations TORG-2

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Receipt**, and then choose the related link.
1. Fill in the fields. For more information, see [Count and Adjust Inventory Using Documents](../../inventory-how-count-inventory-with-documents.md).
1. Choose the **Employee Signatures** action to specify the signature of the person in charge.
1. Enter the fields described in the following table.

   | Field | Description |
   |--|--|
   | **Employee Type** | Specifies the type of the employee. |
   | **Employee No.** | Specifies the employee number of the employee who must sign. |
   | **Employee Name** | Specifies the values that are retrieved from the standard fields of the selected **Employee Card**. |

1. Choose the **Print** action.

## Report Act Items Receipt M-7, Items Receipt Act TORG-1, and Receipt Deviations TORG-2 based on a posted inventory receipt

The following procedure shows how to create the following reports based on posted inventory receipt.

- Act Items Receipt M-7
- Items Receipt Act TORG-1
- Receipt Deviations TORG-2

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Inventory Receipts**, and then choose the related link.
1. Choose the **Print** action.

## Report Item Write-off act TORG-16 based on an unposted inventory shipment

The following procedure shows how to create an Item Write-off act TORG-16 report based on inventory shipment documents that aren't posted.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Shipment**, and then choose the related link.
1. Fill in the fields. For more information, see [Count and Adjust Inventory Using Documents](../../inventory-how-count-inventory-with-documents.md).
1. Choose the **Employee Signatures** action to specify the signature of the person in charge.
1. Enter the fields described in the following table.

   | Field | Description |
   |--|--|
   | **Employee Type** | Specifies the type of the employee. |
   | **Employee No.** | Specifies the employee number of the employee who must sign. |
   | **Employee Name** | Specifies the values that are retrieved from the standard fields of the selected **Employee Card**. |

1. Choose the **Print** action.

## Report Item Write-off act TORG-16 based on a posted inventory shipment

The following procedure shows how to create an Item Write-off act TORG-16 report based on posted inventory shipments.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Inventory Shipments**, and then choose the related link.
1. Choose the **Print** action.

The **Item Shipment** window and **Item Receipt** window have the same functions.

## Report Transfer Order TORG-13 based on an unposted transfer document

The following procedure shows how to create a Transfer Order TORG-13 report based on transfer documents that aren't posted.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Orders**, and then choose the related link.
1. Fill in the fields. For more information, see [Transfer Inventory Between Locations](../../inventory-how-transfer-between-locations.md).
1. Choose the **Employee Signatures** action to specify the signature of the person in charge.
1. Enter the fields described in the following table.

   | Field | Description |
   |--|--|
   | **Employee Type** | Specifies the type of the employee. |
   | **Employee No.** | Specifies the employee number of the employee who must sign. |
   | **Employee Name** | Specifies the values that are retrieved from the standard fields of the selected **Employee Card**. |

1. Choose the **Print** action.

## Report Transfer Order TORG-13 based on a posted transfer document - transfer receipt

The following procedure shows how to create a report based on a posted transfer document called a transfer receipt.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Transfer Receipt**, and then choose the related link.
1. Choose the **Print** action.

## Report Transfer Order TORG-13 based on a posted transfer document - transfer shipment

The following procedure shows how to create a report based on a posted transfer document called a transfer shipment.

1. Choose the ![Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Transfer Shipments**, and then choose the related link.
1. Choose the **Print** action.

## Related information

- [Inventory Setup](inventory-setup.md)  
- [Item Obligatory Acts](item-obligatory-acts.md)  
- [Item General Ledger Turnover](item-general-ledger-turnover.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
