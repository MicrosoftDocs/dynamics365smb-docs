---
author: brentholtorf
ms.topic: include
ms.date: 05/28/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
You might see other users in the **Users** list apart from those from your own company. When a delegated admin from a reselling partner company logs into a [!INCLUDE [prod_short](prod_short.md)] environment on behalf of their customer, they are automatically created as a user inside [!INCLUDE [prod_short](prod_short.md)]. This way, the actions performed by a delegated admin are logged in [!INCLUDE [prod_short](prod_short.md)], such as posting documents, and associated with their user ID.  

With *granular delegated admin privileges (GDAP)*, the user is shown in the **Users** list and can be assigned any permissions. They are not shown with name and other personal information but with their company name and a unique ID. Both internal and external admins can see these users in the **Users** list, and they have full transparency into what these users do through the [change log](../across-log-changes.md), for example. But they can't see the actual name of these users. GDAP users are listed with user names in the following format: `User123456@partnerdomain.com`. They might have a user name that reflects the partner's company name, and the email address is not the person's actual email address. This way, the GDAP user accounts do not reveal personal information. If you need to find out who the person behind such a pseudonym is, you'll have to reach out to the company that this user works or worked for.  

Learn more in [Delegated administrator access to Business Central Online](/dynamics365/business-central/dev-itpro/administration/delegated-admin).