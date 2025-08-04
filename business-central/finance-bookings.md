---
title: Invoice your bookings in Business Central
description: This topic explains learning how you can perform bulk invoicing from Microsoft Bookings in Business Central.
author: brentholtorf
ms.topic: reference
ms.devlang: al
ms.search.keywords: invoicing, bookings
ms.search.form: 1638, 6702, 6704
ms.date: 05/20/2022
ms.author: bholtorf

ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Bulk Invoicing for Microsoft Bookings in [!INCLUDE[prod_short](includes/prod_short.md)]

If your company uses the Bookings app in Microsoft 365, you can do bulk invoicing for appointments. The **Bookings Not Invoiced** page in [!INCLUDE[prod_short](includes/prod_short.md)] provides a list of the company's completed bookings. In this page you can quickly select the appointments that you want to invoice and create draft invoices for the services provided.  

## Connect to Bookings

To connect your [!INCLUDE[prod_short](includes/prod_short.md)] with Bookings, you must specify your Bookings company, what to synchronize with Bookings, how often to synchronize, and which templates to use. You set up this information on the **Booking Sync. Setup** page, which you can launch from the **Exchange Sync. Setup** page, which you can find through [Search](ui-search.md).  

For example, if you want to synchronize customers between Bookings and [!INCLUDE[prod_short](includes/prod_short.md)], you must specify the default template to use to add new customers in [!INCLUDE[prod_short](includes/prod_short.md)] based on the customers in your Bookings company.  

> [!NOTE]
> The Bookings app is designed to book appointments for individual customers rather than companies. The synchronization with [!INCLUDE[prod_short](includes/prod_short.md)] will, therefore, only synchronize customer contacts with a Type of *Person*. An email address is also required for the contact to synchronize.  

Similarly, if you want to synchronize service items between Bookings and [!INCLUDE[prod_short](includes/prod_short.md)], you must specify the default template to use to add new service items in [!INCLUDE[prod_short](includes/prod_short.md)] based on the services in our Bookings company.  

> [!NOTE]
> Only items of type *Service* will synchronize between Bookings and [!INCLUDE[prod_short](includes/prod_short.md)]. The template that you set up in the **Configuration Templates** page so it can be used for the item synchronization must define the type as *Service*.

## Invoice Appointments

When it is time to send invoices for the completed bookings, you go to the **Bookings Not Invoiced** page. Depending on how often the information is synchronized, the list is long or short. You can create invoices for all bookings in the list or one booking at a time. You can select one or more entries in the list and invoice those only.  

The support for invoicing appointments from Bookings is simpler than the fuller workflow of working with sales quotes, sales orders, and sales invoices. For more information, see [Invoice Sales](sales-how-invoice-sales.md). You can choose to sell your services using [!INCLUDE[prod_short](includes/prod_short.md)] or choose to use Bookings, depending on your business needs.  

> [!NOTE]
> In May 2022, we discovered an issue in the integration with Bookings. Currently, the sync from Bookings to [!INCLUDE [prod_short](includes/prod_short.md)] requires you to manually associate the invoices with customers in [!INCLUDE [prod_short](includes/prod_short.md)].

## Related information

[Finance](finance.md)  
[Invoice Sales](sales-how-invoice-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Microsoft Bookings](https://products.office.com/business/scheduling-and-booking-app)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
