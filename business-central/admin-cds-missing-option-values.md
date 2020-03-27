---
title: "Handling Missing Option Values"
description: Learn how to prevent full synchronization from failing because the options differ in mapped fields.
author: bholtorf

ms.author: bholtorf
ms.custom: na
ms.reviewer: na
ms.service: dynamics365-business-central
ms.topic: article
ms.date: 02/03/2020
---

# Handling Missing Option Values
[!INCLUDE[d365fin](includes/cds_long_md.md)] contains only three option set fields that contain option values that you can map to [!INCLUDE[d365fin](includes/d365fin_md.md)] fields of Option type<!-- Option type, not enum? @Onat can you vertify this? --> for automatic synchronization. During synchronization, non-mapped options are ignored and the missing options are appended to the related [!INCLUDE[d365fin](includes/d365fin_md.md)] table and added to the **CDS Option Mapping** system table to handle manually later. For example, by adding the missing options in either product and then updating the mapping. This section describes how that works.

The **Integration Table Mapping** page contains three maps for fields that contain one or more mapped option values. After a full synchronization, the **CDS Option Mapping** page contains the non-mapped options in the three fields respectively.

|         Record             | Option Value | Option Value Caption |
|----------------------------|--------------|----------------------|
| Payment Terms: NET30	     | 1            | Net 30	           |
| Payment Terms: 2%10NET30   | 2            | 2% 10; Net 30        |
| Payment Terms: NET45	     | 3            | Net 45               |
| Payment Terms: NET60	     | 4            | Net 60               |
| Shipment Method: FOB	     | 1            | FOB                  |
| Shipment Method: NOCHARGE  | 2            | No Charge            |
| Shipping Agent: AIRBORNE   | 1            | Airborne             |
| Shipping Agent: DHL        | 2            | DHL                  |
| Shipping Agent: FEDEX      | 3            | FedEx                |
| Shipping Agent: UPS        | 4            | UPS                  |
| Shipping Agent: POSTALMAIL | 5            | Postal Mail          |
| Shipping Agent: FULLLOAD   | 6            | Full Load            |
| Shipping Agent: WILLCALL   | 7            | Will Call            |

The content of the **CDS Option Mapping** page is based on enum values in the **CDS Account** table. In [!INCLUDE[d365fin](includes/cds_long_md.md)], the following fields on the account entity are mapped to fields on the customer and vendor records:

- **Address 1: Freight Terms** of data type Enum, where values are defined as follow:

```
enum 5335 "CDS Shipment Method Code"
{
    Extensible = true;
    value(0; " ") { Caption = ' '; }
    value(1; "FOB") { Caption = 'FOB'; }
    value(2; "NoCharge") { Caption = 'No Charge'; }
}
```

- **Address 1: Shipping Method** of data type Enum, where values are defined as follows:

```
enum 5336 "CDS Shipping Agent Code"
enum 5336 "CDS Shipping Agent Code"
{
    Extensible = true;
    value(0; " ") { Caption = ' '; }
    value(1; "Airborne") { Caption = 'Airborne'; }
    value(2; "DHL") { Caption = 'DHL'; }
    value(3; "FedEx") { Caption = 'FedEx'; }
    value(4; "UPS") { Caption = 'UPS'; }
    value(5; "PostalMail") { Caption = 'Postal Mail'; }
    value(6; "FullLoad") { Caption = 'Full Load'; }
    value(7; "WillCall") { Caption = 'Will Call'; }
}
```

- **Payment Terms** of data type Enum, where values are defined as follows:

```
enum 5334 "CDS Payment Terms Code"
{
    Extensible = true;
    value(0; " ") { Caption = ' '; }
    value(1; "Net30") { Caption = 'Net 30'; }
    value(2; "2%10Net30") { Caption = '2% 10; Net 30'; }
    value(3; "Net45") { Caption = 'Net 45'; }
    value(4; "Net60") { Caption = 'Net 60'; }
}
```

All of the [!INCLUDE[d365fin](includes/d365fin_md.md)] enums above are mapped to option sets in [!INCLUDE[d365fin](includes/cds_long_md.md)].

### Extending Option Sets in [!INCLUDE[d365fin](includes/d365fin_md.md)]
1. Create a new AL extension.

2. Add an Enum extension for the options that you want to extend. Be sure that you use the same value. 

```
enumextension 50100 "CDS Payment Terms Code Extension" extends "CDS Payment Terms Code"
{
    value(779800001; "Cash Payment") { Caption = 'Cash Payment'; }
    value(779800002; "Transfer") { Caption = 'Transfer'; }
}
```

> [!IMPORTANT]  
> You must use the same option ID values from [!INCLUDE[d365fin](includes/cds_long_md.md)] when you extend the [!INCLUDE[d365fin](includes/d365fin_md.md)] enum. Otherwise synchronization will fail.

> [!NOTE]
> The first ten characters of the new option value names and captions must be unique. For example, two options named "Transfer 20 working days" and "Transfer 20 calendar days" will cause an error because both have the same first 10 characters, "Transfer 2". Name them, for example, "TRF20 WD" and "TRF20 CD."

### Update [!INCLUDE[d365fin](includes/cds_long_md.md)] Option Mapping
Now you can recreate the mapping between [!INCLUDE[d365fin](includes/cds_long_md.md)] options and [!INCLUDE[d365fin](includes/d365fin_md.md)] records.

On the **Integration Table Mapping** page, choose the line for the **Payment Terms** map, and then choose the **Synchronize Modified Records** action. The **CDS Option Mapping** page is updated with the additional records below.

|         Record                 | Option Value   | Option Value Caption |
|--------------------------------|----------------|----------------------|
| Payment Terms: NET30	         | 1              | Net 30	             |
| Payment Terms: 2%10NET30       | 2              | 2% 10; Net 30        |
| Payment Terms: NET45 	         | 3              | Net 45               |
| Payment Terms: NET60	         | 4              | Net 60               | 
| **Payment Terms: CASH PAYME**  | **779800001**  | **Cash Payment**     |
| **Payment Terms: TRANSFER**    | **779800002**  | **Transfer**         |

The **Payment Terms** table in [!INCLUDE[d365fin](includes/d365fin_md.md)] will then have new records for the [!INCLUDE[d365fin](includes/cds_long_md.md)] options. In the following table new options are in bold font . Italic rows represent all options that can now be synchronized. Remaining rows represent options are not in use and will be ignored during synchronization. You can remove them or extend CDS options with the same names.)

| Code       | Due Date Calculation | Discount Date Calculation | Discount % | Calc. Pmt. Disc. on Cr. Memos | Description       |
|------------|----------------------|---------------------------|------------|-------------------------------|-------------------|
| 10 DAYS    | 10D                  |                           | 0.         | FALSE                         | Net 10 days       |
| 14 DAYS    | 14D                  |                           | 0.         | FALSE                         | Net 14 days       |
| 15 DAYS    | 15D                  |                           | 0.         | FALSE                         | Net 15 days       |
| 1M(8D)     | 1M                   | 8D                        | 2.         | FALSE                         | 1 Month/2% 8 days |
| 2 DAYS     | 2D                   |                           | 0.         | FALSE                         | Net 2 days        |
| *2%10NET30* |                      |                           | 0.         | FALSE                         |                   |
| 21 DAYS    | 21D                  |                           | 0.         | FALSE                         | Net 21 days       |
| 30 DAYS    | 30D                  |                           | 0.         | FALSE                         | Net 30 days       |
| 60 DAYS    | 60D                  |                           | 0.         | FALSE                         | Net 60 days       |
| 7 DAYS     | 7D                   |                           | 0.         | FALSE                         | Net 7 days        |
| ***CASH PAYME*** |                      |                           | 0.         | FALSE                         |                   |
| CM         | CM                   |                           | 0.         | FALSE                         | Current Month     |
| COD        | 0D                   |                           | 0.         | FALSE                         | Cash on delivery  |
| *NET30*      |                      |                           | 0.         | FALSE                         |                   |
| *NET45*      |                      |                           | 0.         | FALSE                         |                   |
| *NET60*      |                      |                           | 0.         | FALSE                         |                   |
| ***TRANSFER*** |                      |                           | 0.         | FALSE                         |                   |

## See Also
