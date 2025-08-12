---
title: Dismissal in Russia
description: Russian localization includes features for managing employee dismissals.
author: DianaMalina
ms.topic: article
ms.search.keywords: dismissal, employee dismissal, Russia
ms.date: 07/11/2025
ms.reviewer: v-soumramani
ms.author: soalex
ms.service: dynamics-365-business-central
---

# Dismissal

For the dismissed is created additional line of the employment contract with **Operation type** *Dismissal*.

Registration of the order on dismissal is carried out in the following sequence.

1. For indefinite employment contracts, fill the **end date** field in the employment contract header. The field must contain the employee's dismissal date.
1. Create a new line and specify *Dismissal* in the **Operation Type** field.
1. Fill the contract fields:

   | Field | Description |
   |--|--|
   | Dismissal Reason | Code of  Dismissal Reason |
   | Dismissal Document | In the field, you can enter a document of reason for dismissal, if necessary |

   If the employees at dismissal rely compensation payments, they should be specified in the terms of the contract.

   The code of obligatory compensation payment is also linked to the reason of termination of the employment contract.

1. Approve the contract line (Function – **Approve line**).
1. The following sequence of actions is performed during the approval of the employment contract line with the type dismissal.

   - The employment contract is assigned the closed status.
   - Creates a new record of dismissal in the history of the employee at the enterprise.

1. The employee card contains information about the dismissal (in the field **Status** set the value *Dismissed*, filled in the fields **date of dismissal** and **Code of the reason for dismissal**.

## Related information

[Human Resources](Human-Resources.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
