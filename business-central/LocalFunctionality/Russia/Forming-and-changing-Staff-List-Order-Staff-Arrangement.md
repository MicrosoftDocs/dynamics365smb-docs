---
title: Forming and changing staff in Russia
description: Russian enhancements include forming and changing staff.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---
# Forming and Changing the Staff List Order

### Changing of Staff List

To make changes in the Staff List  go to **Human Resources > Organization > Staff list Order**

1. In the header of the order, fill the fields:

| Field                       | Description                                                  |
| --------------------------- | ------------------------------------------------------------ |
| No.                         | Specifies the number of the involved entry or record, according to the specified number series. |
| Document Date               | Specifies the date when the related document was created.    |
| Posting date                | Specifies the entry's posting date.                          |
| HR Order No., HR Order Date | The number and date specified in the fields are used to form the printed form of the order to make changes to the staff List |
| Description                 | Specifies the description associated with this line.         |

The HR Manager No. and Chief Accountant No. fields are filled automatically according to the organization settings.

2. The fields must be filled on the lines:

| Field  | Description                                                  |
| ------ | ------------------------------------------------------------ |
| Type   | Position/Org. Unit                                           |
| Code   | Code of position or Org. Unit                                |
| Action | Approve/Reopen/Close/Rename – type of action to be performed on this staffing item |

3. Post order.

> [!NOTE]
> Only an unoccupied position that is not the highest for any other position can be closed.
>
> A unit can be closed if all positions in it are closed.

### Forming of staff list

In [!INCLUDE[prodshort](../../includes/prodshort.md)], there is a concept of archive staffing. Archive staffing allows you to save the status of the staff list at the time of its creation.

Staff list for any date you can see: **Human Resources > Organization > Staff List**.

By default, the staff list displays only the actual (approved) positions on the working date set in the system. The necessary data can be obtained by setting special filters on the form.

To create an archive, click the **Archive** button.

The formed staff list for the specified date is transferred to the list of posted documents. **Human Resources > Archive > Archived Staff List**

### Staff Arrangement

Staff list is document impersonal, it indicates the number of posts in the organization and salaries for them. However, some companies print a special form that is not regulated by the legislation – Staff Arrangement.

Staff Arrangement – a document that indicates which units approved in the staff list are occupied, indicating the name of the employee, his salary and allowances, and which are still vacant.

The form of  Staff Arrangement is formed on the basis of the archived staff list.

To create a printed form of Staff Arrangement, find (or form) an archive form of staff list and click the **Print** button.

When you run the report, check the box **Staff Arrangement** and select the desired mode of report generation in the field **Show Staff**.

Click OK to generate the report.

## See Also

[Human Resources](Human-Resources.md)
