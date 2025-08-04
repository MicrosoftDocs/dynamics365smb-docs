---
title: "Handling missing option values"
description: Learn how to prevent full synchronization from failing because the options differ in mapped fields. This process requires help from a developer.
author: brentholtorf
ms.author: bholtorf
ms.topic: how-to
ms.date: 09/16/2024
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Handling missing option values

This article is intended for a technical audience. The processes it describes require the help of a developer.

[!INCLUDE[prod_short](includes/cds_long_md.md)] contains three option set fields that contain values that you can map to [!INCLUDE[prod_short](includes/prod_short.md)] fields of the Option type for automated synchronization. During synchronization, nonmapped options are ignored and the missing options are appended to the related [!INCLUDE[prod_short](includes/prod_short.md)] table and added to the **Dataverse Option Mapping** system table to handle manually later. For example, by adding the missing options in either product and then updating the mapping.

The **Integration Table Mapping** page contains three fields that contain one or more mapped option values. After a full synchronization, the **Dataverse Option Mapping** page contains the nonmapped options in the three fields.

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

The content of the **Dataverse Option Mapping** page is based on enum values in the **CRM Account** table. In [!INCLUDE[prod_short](includes/cds_long_md.md)], the following fields on the account table are mapped to fields on the customer and vendor records:

- **Address 1: Freight Terms** of data type Enum, where values are defined as follows:

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

All of the [!INCLUDE[prod_short](includes/prod_short.md)] enums are mapped to option sets in [!INCLUDE[prod_short](includes/cds_long_md.md)].

## Extending option sets in [!INCLUDE[prod_short](includes/prod_short.md)]
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
> You must use the same option ID values from [!INCLUDE[prod_short](includes/cds_long_md.md)] when you extend the [!INCLUDE[prod_short](includes/prod_short.md)] enum. Otherwise synchronization will fail.

> [!IMPORTANT]  
> Do not use the ","  character in the enum values and captions. This is currently not supported by the [!INCLUDE[prod_short](includes/prod_short.md)] runtime.

> [!NOTE]
> The first ten characters of the new option value names and captions must be unique. For example, two options named "Transfer 20 working days" and "Transfer 20 calendar days" will cause an error because both have the same first 10 characters, "Transfer 2". Name them, for example, "TRF20 WD" and "TRF20 CD."

## Update [!INCLUDE[prod_short](includes/cds_long_md.md)] option mapping
Now you can recreate the mapping between [!INCLUDE[prod_short](includes/cds_long_md.md)] options and [!INCLUDE[prod_short](includes/prod_short.md)] records.

On the **Integration Table Mapping** page, choose the line for the **Payment Terms** map, and then choose the **Synchronize Modified Records** action. The **Dataverse Option Mapping** page is updated with the following records.

|         Record                 | Option Value   | Option Value Caption |
|--------------------------------|----------------|----------------------|
| Payment Terms: NET30	         | 1              | Net 30	             |
| Payment Terms: 2%10NET30       | 2              | 2% 10; Net 30        |
| Payment Terms: NET45 	         | 3              | Net 45               |
| Payment Terms: NET60	         | 4              | Net 60               | 
| **Payment Terms: CASH PAYME**  | **779800001**  | **Cash Payment**     |
| **Payment Terms: TRANSFER**    | **779800002**  | **Transfer**         |

The **Payment Terms** table in [!INCLUDE[prod_short](includes/prod_short.md)] has new records for the [!INCLUDE[prod_short](includes/cds_long_md.md)] options. In the following table, new options are in bold font. Italic rows represent all options that can now be synchronized. Remaining rows represent options aren't in use and are ignored during synchronization. You can remove them or extend Dataverse options with the same names.

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

## Related information
[Mapping the Tables and Fields to Synchronize](admin-how-to-modify-table-mappings-for-synchronization.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
