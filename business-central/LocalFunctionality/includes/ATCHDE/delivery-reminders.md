---
author: brentholtorf
ms.topic: include
ms.date: 03/05/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

Delivery reminders are used to track overdue vendor shipments and to remind vendors about overdue deliveries. To create delivery reminders, you must set up the following items:

- **Delivery reminder terms**  

    Delivery reminder terms are identified by a code that must be assigned to vendors. To use more than one combination of settings, you must set up a code for each setting separately. You can set up any number of delivery reminder terms.  

- **Delivery reminder levels**  

    For every delivery reminder term, you must set up delivery reminder levels. These levels determine how often delivery reminders can be created for a specific term. Level 1 is the first delivery reminder that you create for an overdue delivery. Level 2 is the second delivery reminder, and so on. When delivery reminders are created, the number of reminders that were created previously is considered, and the current number is used to apply terms.  

- **Delivery reminder texts messages**  

    You must set up delivery reminder text messages for every delivery reminder level. There are two types of delivery reminder text messages: beginning and ending. The beginning text message is printed under the header section, before the list of entries that are marked for reminder. The ending text message is printed after this list.  

After you set up the delivery terms, levels, and texts, you must assign the relevant delivery reminder codes to your vendors.  

You can create delivery reminders manually or automatically. You can use the **Create Delivery Reminder** batch job to create delivery reminders automatically so that you can select the purchase orders for which delivery reminders must be created.  

You can also track documents in relation to purchase order lines and sales order lines.  

[!INCLUDE[prod_short](../../../includes/prod_short.md)] provides the following reports:  

- **Issued Delivery Reminder** - To view the delivery reminders for vendors.  
- **Delivery Reminder - Test** - To verify the delivery reminders before you issue them.  
