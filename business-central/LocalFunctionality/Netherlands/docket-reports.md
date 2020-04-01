---
    title: Docket Reports
    description: The Dutch telebanking application allows you to combine ledger entries for the same customer or vendor, having the same transaction mode, into one payment or collection order to the bank.
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Docket Reports
The Dutch telebanking application allows you to combine ledger entries for the same customer or vendor, having the same transaction mode, into one payment or collection order to the bank. As such one total amount will be paid to or collected from the vendor or customer involved. Possibly this combined payment could lack all detail information about the individual payments or collections. Telebanking offers you the possibility to inform your vendor or customer in detail by generating a docket report that describes the individual payments that constitute the total amount paid or collected.  

When generating payment proposals using the **Get Proposal Entries** batch job the system will select the **Docket** check box on the proposal in case that:  

- The resulting combined payment includes too many invoice numbers to list them in the available four description fields of the new proposal line: **Description 1** field, **Description 2** field, **Description 3** field, and **Description 4** field.  

- The payment is not based upon an invoice.  

## See Also  
 [Telebanking](telebanking.md)
