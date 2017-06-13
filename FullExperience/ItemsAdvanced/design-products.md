---
title: "Design Products"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "product design"
  - "items, about"
ms.assetid: 66e3f3fd-ba41-4cbd-8de0-59086726e957
caps.latest.revision: 9
ms.author: "sgroespe"
manager: "terryaus"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# Design Products
The starting point for any business that deals with physical goods is to establish the item. First, you must create a database record for the item, an item card. The item card is a placeholder for critical master data that is used throughout the supply chain as the item is processed. All the rules and values, such as costing method, dimension codes, and substitutions that apply to the item are entered on the item card. After you create the item card, this record controls how the item is processed in business documents by providing information, such as price, sales terms, availability, and planning parameters.  
  
 When the item card is completed, you can proceed to other product design tasks, such as defining cross\-reference descriptions or substitution items and creating stockkeeping units for items stored in multiple locations.  
  
 Items that are assembled or produced within a company require additional product design tasks, which are described in [Define Material and Process Structure](../DesignAndEngineering/define-material-and-process-structure.md).  
  
 The following table describes a sequence of tasks with links to the topics that describe them. These tasks are listed in the order in which they are generally performed.  
  
|**To**|**See**|  
|------------|-------------|  
|Create an item card for each inventory item or service that you trade in.|[How to: Register New Products](../DesignAndEngineering/how-to-register-new-products.md)|  
|Initiate a new item card based on a company\-specific data template.|[How to: Create Cards by Using Data Templates](../WorkingWithDynamics/how-to-create-cards-by-using-data-templates.md)|  
|Enable electronic document sending by filling various fields on item cards that identify the item when mapping data to the external file.|[How to: Set Up Electronic Document Sending and Receiving](../BusinessFunctionality/DataExchange/how-to-set-up-electronic-document-sending-and-receiving.md)|  
|Define how the planning system calculates replenishment of the item.|[Reordering Policy](../DesignAndEngineering/-$-t_27_5440-reordering-policy-$-.md)|  
|Define if the planning system must calculate production need for lower production BOM levels of the item.|[Manufacturing Policy](../DesignAndEngineering/-$-t_27_5442-manufacturing-policy-$-.md)|  
|Define how the outbound unit cost of the item is applied to inbound transactions for inventory valuation.|[Design Details: Costing Methods](../ApplicationDesign/design-details-costing-methods.md)|  
|Specify in which unit of measure the item is handled by default and which alternate units of measure exist.|[How to: Set Up Item Units of Measure](../DesignAndEngineering/how-to-set-up-item-units-of-measure.md)|  
|Write a comment that can be shown on all documents where the item is handled.|[Comment Line](assetId:///bb1ef791-1617-440b-8b07-1884e1fff62d)|  
|Assign one or more default dimensions to the item card that will be included on related document lines and eventually work as a source of analysis of historic transactions.|[Default Dimension](assetId:///bd021a4a-f67d-44ca-9e6a-4b54cf91e710)|  
|Attach a picture \(.bmp file\) of the item.|[How to: Insert Pictures](../DesignAndEngineering/how-to-insert-pictures.md)|  
|Define one or more variations of the item that customers may choose from.|[Item Variant](../DesignAndEngineering/-$-t_5401-item-variant-$-.md)|  
|Make a cross\-reference between the item's number and another item code, such as a barcode.|[Item Cross Reference](../DesignAndEngineering/-$-t_5717-item-cross-reference-$-.md)|  
|Specify which other items can be offered to customers if the first item choice is not available.|[Item Substitution](../DesignAndEngineering/-$-t_5715-item-substitution-$-.md)|  
|Create a simplified item card for items that need not be managed as inventory items, such as drop\-shipment items, special order items, or internal office supplies.|[How to: Create Nonstock Items](../DesignAndEngineering/how-to-create-nonstock-items.md)|  
|List codes for product groups to group items by product type, such as chairs.|[Product Group](../Topic/\($%20T_5723%20Product%20Group%20$\).md)|  
|List codes for item categories, to group items or product groups, such as furniture.|[Item Category](../Topic/\($%20T_5722%20Item%20Category%20$\).md)|  
|Set up language translations for item descriptions so that foreign vendors and customers can get printed documents in their own language.|[How to: Set Up and Use Item Translations](../DesignAndEngineering/how-to-set-up-and-use-item-translations.md)|  
|Write additional text that can be shown in separate document lines in addition to the item description.|[How to: Set Up Extended Text](../DesignAndEngineering/how-to-set-up-extended-text.md)|  
|Set up number series and rules for serial\/lot numbers and assign item tracking codes to items for item tracking.|[How to: Set Up Item Tracking Codes](../DesignAndEngineering/how-to-set-up-item-tracking-codes.md)|  
|Create a hierarchy of items that are sold together as one item, such as a kit.|[Assembly BOM](../Topic/\($%20N_36%20Assembly%20BOM%20$\).md)|  
|Define an additional item record that reflects unique rules and values for the item at one location.|[Create Stockkeeping Unit](../DesignAndEngineering/-$-b_5706-create-stockkeeping-unit-$-.md)|  
  
## See Also  
 [Create New Vendor Accounts](../Purchasing/create-new-vendor-accounts.md)   
 [Purchase Goods](../Purchasing/purchase-goods.md)   
 [Create New Customer Accounts](../Sales/create-new-customer-accounts.md)   
 [Sell Goods](../Sales/sell-goods.md)   
 [Execute Production](../Production/execute-production.md)