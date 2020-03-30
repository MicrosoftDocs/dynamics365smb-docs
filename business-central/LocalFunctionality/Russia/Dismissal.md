---
title: Dismissal in Russia
description: Russian enhancements include dismissal of employees.
author: DianaMalina

ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords:
ms.date: 04/01/2020
ms.reviewer: edupont
ms.author: soalex
---

# Dismissal

For the dismissed is created additional line of the employment contract with **Operation type** *Dismissal*. 

Registration of the order on dismissal is carried out in the following sequence. 

1. For indefinite employment contracts, fill the **end date** field in the employment contract header. The field must contain the employee's dismissal date.
2. Create a new line and specify *Dismissal* in the **Operation Type** field.
3. Fill the contract fields:

| Field              | Description                                                  |
| ------------------ | ------------------------------------------------------------ |
| Dismissal Reason   | Code of  Dismissal Reason                                    |
| Dismissal Document | In the field, you can enter a document of reason for dismissal, if necessary |

If the employee at dismissal rely compensation payments, they should be specified in the terms of the contract.

The code of obligatory compensation payment is also linked to the reason of termination of the employment contract.

4. Approve the contract line (Function – **Approve line**). 

5. The following sequence of actions will be performed during the approval of the employment contract line with the type dismissal. 

- The employment contract will be assigned the closed status.
- Creates a new record of dismissal in the history of the employee at the enterprise. 

6. The employee card contains information about the dismissal (in the field **Status** set the value *Dismissed*, filled in the fields **date of dismissal** and **Code of the reason for dismissal**.

## See Also

[Human Resources](Human-Resources.md)
