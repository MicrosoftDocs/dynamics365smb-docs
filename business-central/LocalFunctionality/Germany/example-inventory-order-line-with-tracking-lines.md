---
    title: Example - Inventory Order Line with Tracking Lines
    description: The physical inventory order line must contain certain data.
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

---
# Example - Inventory Order Line with Tracking Lines
The physical inventory order line should contain the following data:  

- Item No.: 80216-V  
- Location Code: BLUE  
- The fields Variant Code and Bin Code may be blank.  

There is a check mark in the field Use Tracking Lines on the physical inventory order line and the item 80216-V should be posted all time with lot nos. according to the item tracking code.  

The posting date on the physical inventory order header should be 12/31/2002.  

The expected quantity of the item 80216-V at the location BLUE on 12/31/2001 should be 120 pieces.  

The quantity on stock consists of the following lots:  

## The expected Item Tracking Lines:  

|**Lot No.**|**Quantity**|  
|-----------------|------------------|  
|CH1001|80|  
|CH1003|30|  
|CH1006|10|  
|**Total**|**120**|  

There had been recorded the following physical inventory recording lines for the item 80216-V, location code BLUE:  

## Recorded Lot Nos. on the Physical Inventory Recording Lines:  

|**Lot No.**|**Quantity**|  
|-----------------|------------------|  
|CH1001|80|  
|CH1002|12|  
|CH1003|20|  
|**Total**|**112**|  

When finishing the physical inventory order the program will calculate for the item 80216-V at the location BLUE a negative adjustment of 8 pieces and will create the following entries:  

## Item Tracking lines to post:  

|**Lot No.**|**Expected Quantity**|**Recorded Quantity**|**Quantity to post**|  
|-----------------|---------------------------|---------------------------|--------------------------|  
|CH1001|80|80|0|  
|CH1002|0|12|+ 12|  
|CH1003|30|20|- 10|  
|CH1006|10|0|- 10|  
|**Total**|**120**|**112**|**- 8**|  

## See Also  
 [Physical Inventory Order Lines With Item Tracking Lines](physical-inventory-order-lines-with-item-tracking-lines.md)  
 [Work with Serial and Lot Numbers](../../inventory-how-work-item-tracking.md)
