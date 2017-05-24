---
title: "Item Documents"
ms.custom: na
ms.date: "06-05-2016"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "receiving, official reports"
  - "inventory, item reciept reports"
ms.assetid: 7d4295fc-79f5-4e2d-9eb8-6517cf9f089c
caps.latest.revision: 2
ms.author: "edupont"
translation.priority.ht: 
  - "ru-ru"
---
# Item Documents
[!INCLUDE[navnow](../../ApplicationDesign/includes/navnow_md.md)] includes several documents that you can use to manage your warehouse. This also includes reports that you must submit for official reporting, such as the [\($ R\_14919 Item Report TORG\-29 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_14919-item-report-torg-29-$-.md), [\($ B\_14918 Items Receipt Act TORG\-1 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-b_14918-items-receipt-act-torg-1-$-.md), and [\($ B\_14925 Receipt Deviations TORG\-2 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-b_14925-receipt-deviations-torg-2-$-.md) reports.  
  
 The following types of documents are useful for managing your warehouse:  
  
-   Item receipt act without the vendor invoice \- This is applied to the account receipt of items based on the quality, quantity, and cost.  
  
-   Item writing\-off act – This is applied to register damage for reasons such as the loss of quality of items that will no longer be sold.  
  
-   Item transfer – This is applied to receipt and delivery shipments for transfer of items within the organization.  
  
## Setting Up Warehouse Document Numbering  
 The following procedure shows how to set up warehouse document numbering.  
  
1.  In the **Search** box, enter **Inventory Setup**, and then choose the related link.  
  
2.  On the **Numbering** FastTab, specify in the following fields the series of numbers for documents:  
  
    -   **Item Receipt Nos**  
  
    -   **Posted Item receipt Nos**  
  
    -   **Item Shipment Nos**  
  
    -   **Posted Item Shipment Nos**  
  
## Creating an Item Receipt Act Without a Vendor  
 The following procedure shows how to create an item receipt act without a vendor.  
  
1.  In the **Search** box, enter **Item Receipts**, and then choose the related link.  
  
2.  In the header of the **\($ N\_12450 Item Receipt $\)** window, enter the fields described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12451\_2 No. $\)**|Specifies the warehouse document header number.|  
    |**\($ T\_12451\_3 Posting Description $\)**|Specifies the posting description.|  
    |**\($ T\_12451\_7 Location Code $\)**|Specifies the value code that is filled in from the Location list.|  
    |**\($ T\_12451\_23 Gen. Bus. Posting Group $\)**|Specifies the code of the general business posting group.|  
    |**\($ T\_12451\_3 Posting Date $\)**<br /><br /> **\($ T\_12451\_5 Document Date $\)**|Specifies the working date that is filled in by default.|  
    |**\($ T\_12451\_16 External Document No. $\)**|Enter the primary document number.|  
    |**\($ T\_12451\_11 Purchaser Code $\)**|Specifies the value code that is selected from salespeople or purchasers.|  
    |**\($ T\_12450\_30 Correction $\)**|Specifies if the entry is a correction.|  
    |**\($ T\_12450\_21 Status $\)**|Specifies if the document is Open or Released.|  
  
3.  In the document lines of the **\($ N\_12450 Item Receipt $\)** window, enter the fields described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12452\_3 Item No. $\)**|Specifies the item number from the Item List table.|  
    |**\($ T\_12452\_8 Description $\)**|Specifies the item description.|  
    |**\($ T\_12452\_13 Quantity $\)**|Specifies the number of item units.|  
    |**\($ T\_12452\_5413 Reserve Quantity Inbnd $\)**|Specifies the item quantity reserved at the warehouse of the receiver.|  
    |**\($ T\_12452\_16 Unit Amount $\)**|Specifies the price of a unit item.|  
    |**\($ T\_12452\_37 Indirect Cost % $\)**|Specifies the indirect cost percent.|  
    |**\($ T\_12452\_17 Unit Cost $\)**|Specifies the item unit cost of the receipt shipment line.|  
    |**\($ T\_12452\_18 Amount $\)**|Specifies the transaction amount.|  
    |**\($ T\_12452\_5407 Unit of Measure Code $\)**|Specifies the unit of measure code for the received items.|  
  
4.  In the **\($ N\_12450 Item Receipt $\)** window, on the **Navigate** tab, in the **Receipt** group, choose **Employee Signatures** to specify the signature of the person in charge.  
  
5.  Enter the fields described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12420\_4 Employee Type $\)**|Specifies the type of the employee.|  
    |**\($ T\_12420\_5 Employee No. $\)**|Specifies the employee number of the employee who must sign.|  
    |**\($ T\_12420\_6 Employee Name $\)**|Specifies the values that are retrieved from the standard fields of the selected **\($ N\_5200 Employee Card $\)**.|  
  
6.  To print an **Item Receipt** report from the **\($ N\_12450 Item Receipt $\)** window, on the **Report** tab, in the **General** group, choose **Item Document**.  
  
7.  Choose the **Print** button.  
  
 The following functions are available in the Item Receipt document.  
  
|Function|Description|  
|--------------|-----------------|  
|Changing document status|Documents can be open or released for the next processing stage. Click **Functions**, click **Release** or **Functions**, and then click **Reopen**.|  
|Reservation of document lines|Items can be reserved from the document line. Click **Functions**, and then click **Reserve.**|  
|Warehouse adjustment calculation|Refers only to item quantity corrections in the warehouse bins. This is accessible only if advanced picking and placing is used in the warehouse.|  
|Document posting|Click **Posting** to perform the following:<br /><br /> -   **Post \-** Post the Item Receipt document. The posted item receipt is created.<br />-   **Post and Print \-** Post the document and print the test report.|  
  
## Analysis of a Posted Document Item Receipt Without a Vendor  
 The following procedure shows how to analyze a posted document item receipt without a vendor.  
  
1.  In the **Search** box, enter **Posted Item Receipts**, and then choose the related link.  
  
    > [!NOTE]  
    >  The posted item receipt displays all the information from the item receipt.  
  
2.  Choose **Sort** to sort the list of documents selected for printing in ascending or descending order.  
  
3.  Choose the **Print** button.  
  
## Creating an Item Writing\-Off Act  
 The following procedure shows how to create an item writing\-off act.  
  
1.  In the **Search** box, enter **Item Shipments**, and then choose the related link.  
  
2.  On the header of the **\($ N\_12452 Item Shipment $\)** window, enter the fields. These fields are the same as those on the **\($ N\_12450 Item Receipt $\)** window.  
  
3.  In the document lines of the **\($ N\_12452 Item Shipment $\)** window, enter the fields. These fields are the same as those on the **\($ N\_12450 Item Receipt $\)** form except for the following:  
  
    -   The **Indirect Cost** field is available only in the **\($ N\_12450 Item Receipt $\)** window.  
  
    -   The fields in the following table are available only in the **\($ N\_12452 Item Shipment $\)** form.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12455\_12450 FA No. $\)**|Specifies the fixed asset to write off items and materials.|  
    |**\($ T\_12455\_12452 Depreciation Book Code $\)**|Specifies the fixed asset depreciation book to which the additional cost will be added.|  
  
4.  In the **\($ N\_12452 Item Shipment $\)** window on the **Navigate** tab, in the **Receipt** group, choose **Employee Signatures** to specify the signature of the person in charge.  
  
5.  Enter the fields described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**\($ T\_12420\_4 Employee Type $\)**|Specifies the type of the employee.|  
    |**\($ T\_12420\_5 Employee No. $\)**|Specifies the employee number of the employee who must sign.|  
    |**\($ T\_12420\_6 Employee Name $\)**|Specifies the values that are retrieved from the standard fields of the selected **\($ N\_5200 Employee Card $\)**.|  
  
6.  Choose the **Print** button.  
  
 The functions available in the Item Shipment document are same as those in the Item Receipt document.  
  
## Analysis of a Posted Document Item Writing\-Off Act  
 The following procedure shows how to analyze a posted document item writing\-off act.  
  
1.  In the **Search** box, enter **Posted Item Shipments**, and then choose the related link.  
  
    > [!NOTE]  
    >  The posted item shipment displays all the information from the item shipment.  
  
2.  Choose **Sort** to sort the list of documents selected for printing in ascending or descending order.  
  
3.  Choose **Print**.  
  
## Report Transfer Order TORG\-13 Based on an Unposted Transfer Document  
 The following procedure shows how to create a Transfer Order TORG\-13 report based on transfer documents that are not posted.  
  
1.  In the **Search** box, enter **Transfer Orders**, and then choose the related link.  
  
     On the **Actions** tab, in the **General** group, choose **Print**.  
  
## Report Transfer Order TORG\-13 Based on a Posted Transfer Document \- Transfer Receipt  
 The following procedure shows how to create a report based on a posted transfer document called a transfer receipt.  
  
1.  In the **Search** box, enter **Posted Transfer Receipt**, and then choose the related link.  
  
2.  On the **Home** tab, in the **Print** group, choose **Print**.  
  
## Report Transfer Order TORG\-13 Based on a Posted Transfer Document \- Transfer Shipment  
 The following procedure shows how to create a report based on a posted transfer document called a transfer shipment.  
  
1.  In the **Search** box, enter **Posted Transfer Shipments**, and then choose the related link.  
  
     On the **Home** tab, in the **Print** group, choose **Print**.  
  
## See Also  
 [Inventory Setup](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/inventory-setup.md)   
 [Item Obligatory Acts](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/item-obligatory-acts.md)   
 [Item General Ledger Turnover](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/item-general-ledger-turnover.md)   
 [\($ R\_14919 Item Report TORG\-29 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_14919-item-report-torg-29-$-.md)   
 [\($ B\_14918 Items Receipt Act TORG\-1 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-b_14918-items-receipt-act-torg-1-$-.md)   
 [\($ B\_14925 Receipt Deviations TORG\-2 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-b_14925-receipt-deviations-torg-2-$-.md)   
 [\($ R\_14976 Transfer Order TORG\-13 $\)](../../LocalFunctionalityForMicrosoftDynamicsNav2016/Russia/-$-r_14976-transfer-order-torg-13-$-.md)