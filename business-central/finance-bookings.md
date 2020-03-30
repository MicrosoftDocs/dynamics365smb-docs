---
title: Invoice your bookings in Business Central | Microsoft Docs
description: 'Learn how you can do bulk invoicing from Microsoft Bookings in Business Central .'
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: invoicing, bookings
ms.date: 04/01/2020
ms.author: edupont

---
# Bulk Invoicing for Microsoft Bookings in [!INCLUDE[d365fin](includes/d365fin_md.md)]
If your company uses the Bookings app in Office 365, you can do bulk invoicing for appointments. The **Uninvoiced Bookings** page in [!INCLUDE[d365fin](includes/d365fin_md.md)] provides a list of the company's completed bookings. In this page you can quickly select the appointments that you want to invoice and create draft invoices for the services provided.  

## Connect to Bookings
To connect your [!INCLUDE[d365fin](includes/d365fin_md.md)] with Bookings, you must specify your Bookings company, what to synchronize with Bookings, how often to synchronize, and which templates to use. You set up this information on the **Booking Sync. Setup** page, which you can launch from the **Exchange Sync. Setup** page, which you can find through [Search](ui-search.md).  

For example, if you want to synchronize customers between Bookings and [!INCLUDE[d365fin](includes/d365fin_md.md)], you must specify the default template to use to add new customers in [!INCLUDE[d365fin](includes/d365fin_md.md)] based on the customers in your Bookings company.  

> [!NOTE]
> The Bookings app is designed to book appointments for individual customers rather than companies. The synchronization with [!INCLUDE[d365fin](includes/d365fin_md.md)] will, therefore, only synchronize customer contacts with a Type of "Person". An email address is also required for the contact to synchronize.  

Similarly, if you want to synchronize service items between Bookings and [!INCLUDE[d365fin](includes/d365fin_md.md)], you must specify the default template to use to add new service items in [!INCLUDE[d365fin](includes/d365fin_md.md)] based on the services in our Bookings company.  

> [!NOTE]
> Only items of type *Service* will synchronize between Bookings and [!INCLUDE[d365fin](includes/d365fin_md.md)]. The template that you set up in the **Configuration Templates** page so it can be used for the item synchronization must define the type as *Service*.

## Invoice Appointments
When it is time to send invoices for the completed bookings, you go to the **Uninvoiced Bookings** page. Depending on how often the information is synchronized, the list is long or short. You can create invoices for all bookings in the list or one booking at a time. You can select one or more entries in the list and invoice those only.  

The support for invoicing appointments from Bookings is simpler than the fuller workflow of working with sales quotes, sales orders, and sales invoices. For more information, see [Invoice Sales](sales-how-invoice-sales.md). You can choose to sell your services using [!INCLUDE[d365fin](includes/d365fin_md.md)] or choose to use Bookings, depending on your business needs.  

## See Also
[Finance](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Microsoft Bookings](https://products.office.com/business/scheduling-and-booking-app)  
