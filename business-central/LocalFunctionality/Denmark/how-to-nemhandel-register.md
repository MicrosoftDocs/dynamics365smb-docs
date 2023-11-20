---
title: Notification and Registration for the Nemhandelsregisteret in Denmark 
description: This article describes how to handle with the notification and registration with the Nemhandelsregisteret in Denmark. 
author: altotovi
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: nemhandel, nemhandelsregisteret, notification, registration, denmark
ms.search.form:  1
ms.date: 11/17/2023
ms.author: altotovi

---

# Notification and Registration for the Nemhandelsregisteret  

Based on Danish bookkeeping act, from January 2024, all standard systems must provide a message to the users, alerting them to the possibility to be registered in the NemHandelsregisteret, and display information about and registration functionality.  

Related with this requirement, if the company is not registered with the NemHandelsregisteret, notification about that will appear at the top of screen, together with instructions on how to register.   

## Notification for not being registered  

Notification should appear if the company is not registered with the NemHandelsregisteret with the following text: _Your accounting software is not registered in Nemhandelsregisteret_. In this case, it should allow users to finish the registration process. That means users can choose if they want to **Register in Nemhandelsregisteret** or to **Open registration guide** directly from the notification. Both of options will lead user to the external Nemhadel content.  

But if the company is registered and if the valid CVR number is populated in the **Registration No.** field on the **Company Information** page, this notification will not appear.  

> [!NOTE]
> Notification will appear on the **Company Information** page and on the following role-centers: Accountant, Business Manager, Administration of users, security groups and permissions, Sales Order Processor, and Sales and Relationship Manager.  

## Registration with the NemHandelsregisteret 

> [!IMPORTANT]
> Before starting registration, users must have populated the **Registration No.** field on the **Company Information** page with the valid CVR number.

To start registration, the user needs to click on the **Register in Nemhandelsregisteret** link in the notification. Before external system calls or opening NemHandelsregisteret registration form, the consent will be presented to a user and user must confirm it.   

Once the user finishes the registration with the NemHandelsregisteret, the existing notification will disappear as Business Central will confirm that the company’s CVR number from the **Registration No.** field in the **Company Information** page has been registered in NemHandelsregisteret through the API call, and in Business Central's internal records, this company will have the status of 'registered in NemHandelsregisteret’.  

## Other important facts   

If the company is registered in NemHandelsregisteret and has populated the **VAT Registration No.** and **Registration No.** fields in the **Company Information**, deleting this company from the **Companies** page will be prevented as a production company as by law it is not allowed to delete production transactions.  

Also, when users use the **Copy** action from the **Companies** page, the new company will be created without marked the **Registered with Nemhandel** field and populated **Registration No.**   

> [!NOTE]
> These limitations will work only if the environment is Production. In a sandbox environment, users can delete the company without limitations. 

> [!NOTE]
> If user doesn’t populate the **Registration No.** with the valid CVR number, it will not be possible to use e-documents in Denmark.  


## See also  

[Financial Management](../../finance.md)  
[VAT Management Overview](../../finance-manage-vat.md)  
[E-documents Overview](../../finance-edocuments-overview.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
