---
title: Notification and registration for the Nemhandelsregisteret in Denmark 
description: This article describes how to handle notification and registration with the Nemhandelsregisteret in Denmark. 
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

# Notification and registration for the Nemhandelsregisteret  

Based on the Danish bookkeeping act, starting January 2024 all standard systems must notify users that they can register in the NemHandelsregisteret, and provide information about the registration functionality.  

In addition, if the company isn't registered with the NemHandelsregisteret, a notification appears at the top of screen with registration instructions.   

## Notification for not being registered  

If the company isn't registered with the NemHandelsregisteret, you will receive a notification with the following text, _Your accounting software is not registered in Nemhandelsregisteret_. This notification allows you to finish the registration process. That means you can choose to **Register in Nemhandelsregisteret** or to **Open registration guide** directly from the notification. Both of options direct you to the external Nemhadel content.  

If the company is registered, and if the valid CVR number is populated in the **Registration No.** field on the **Company Information** page, this notification won't appear.  

> [!NOTE]
> A notification will appear on the **Company Information** page and on the following role-centers: Accountant, Business Manager, Administration of users, security groups and permissions, Sales Order Processor, and Sales and Relationship Manager.  

## Registration with the NemHandelsregisteret 

> [!IMPORTANT]
> Before you begin registration, you must populate the **Registration No.** field on the **Company Information** page with the valid CVR number.

To start registration, select the **Register in Nemhandelsregisteret** link in the notification. Before the external system calls or before you open the NemHandelsregisteret registration form, you must confirm the offered consent.   

After you finish the registration with the NemHandelsregisteret, the existing notification disappears as Dynamics 365 Business Central confirms that the company’s CVR number from the **Registration No.** field on the **Company Information** page has been registered in NemHandelsregisteret through the API call. In Business Central's internal records, this company has the status of **registered in NemHandelsregisteret**.  

## Other important facts   

If the company is registered in NemHandelsregisteret and has populated the **VAT Registration No.** and **Registration No.** fields on the **Company Information** page, you can't delete this company from the **Companies** page. This is because it's a production company, and you can't delete production transactions.  

Also, when you select **Copy** on the **Companies** page, the new company is created and the **Registered with Nemhandel** field and **Registration No.** are left blank.    

> [!NOTE]
> These limitations only work if the environment is in Production. In a sandbox environment, you can delete the company without limitations. 
>
> If you don’t populate the **Registration No.** with the valid CVR number, it's possible to use e-documents in Denmark.  


## See also  

[Financial Management](../../finance.md)  
[VAT Management Overview](../../finance-manage-vat.md)  
[E-documents Overview](../../finance-edocuments-overview.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
