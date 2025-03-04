---
title: Notification and registration for the NemHandelsregisteret in Denmark 
description: This article describes how to handle notification and registration with the NemHandelsregisteret in Denmark. 
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: nemhandel, nemhandelsregisteret, notification, registration, denmark
ms.search.form: 1
ms.date: 03/03/2025
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

# Notification and registration for the NemHandelsregisteret in Denmark

According to the Danish bookkeeping act, as of January 2024, all standard systems must notify users that they can register with the NemHandelsregisteret. They must also provide information about the registration functionality.

In addition, if the company isn't registered with the NemHandelsregisteret, a notification appears at the top of page and provides registration instructions.

## Notification about not being registered

If the company isn't registered with the NemHandelsregisteret, you receive the following notification: "Your accounting software isn't registered in Nemhandelsregisteret." You can complete the registration process directly from the notification, by selecting either the **Register in Nemhandelsregisteret** link or the **Open registration guide** link. Both links direct you to the external Nemhandel content.

If the company is already registered, and if a valid Central Business Register (CVR) number is entered in the **Registration No.** field on the **Company Information** page, the notification doesn't appear.

> [!NOTE]
> A notification appears on the **Company Information** page and on the following role centers: Accountant, Business Manager, Administration of users, security groups and permissions, Sales Order Processor, and Sales and Relationship Manager.

## Registration with the NemHandelsregisteret

> [!IMPORTANT]
> Before you begin registration, you must enter a valid CVR number in the **Registration No.** field on the **Company Information** page.

To start registration, select the **Register in Nemhandelsregisteret** link in the notification. Before the external system calls are made, or before you open the NemHandelsregisteret registration form, you must confirm your consent.

After you complete the registration with the NemHandelsregisteret, the existing notification disappears, because Microsoft Dynamics 365 Business Central confirms that the company's CVR number from the **Registration No.** field on the **Company Information** page is registered with the NemHandelsregisteret through the API call. In Business Central's internal records, the company has a status of **registered in NemHandelsregisteret**.

## Other important facts

If the company is registered with the NemHandelsregisteret, and if it has set the **VAT Registration No.** and **Registration No.** fields on the **Company Information** page, you can't delete the company from the **Companies** page. This limitation exists because the company is a production company in this case, and you can't delete production transactions.

Additionally, when you select **Copy** on the **Companies** page, the new company is created, and the **Registered with Nemhandel** and **Registration No.** fields are left blank.

> [!NOTE]
> These limitations work only if the environment is a production environment. In a sandbox environment, you can delete the company without limitations.
>
> If you don't enter a valid CVR number in the **Registration No.** field, you can't use E-documents in Denmark.

## Related information

- [Financial Management](../../finance.md)  
- [VAT Management Overview](../../finance-manage-vat.md)  
- [E-documents Overview](../../finance-edocuments-overview.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
