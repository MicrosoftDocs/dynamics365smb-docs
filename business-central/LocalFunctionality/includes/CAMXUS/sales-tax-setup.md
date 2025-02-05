---
author: brentholtorf
ms.topic: include
ms.date: 02/04/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: v-soumramani
---

When you first start using [!INCLUDE[prod_short](../../../includes/prod_short.md)], you can run an assisted setup guide to quickly and easily set up sales tax information for your company, customers, and vendors. 

In a matter of minutes, you're ready to create sales documents and purchase documents with sales tax calculated correctly. Just search for the **Set Up Sales Tax** assisted setup guide and then follow the steps in the guide. This includes specifying the accounts that you want to use for sales tax for sales and purchases.  

We recommend that you choose to apply the new tax area to your own company information. If you also choose to apply it to customers or vendors, you'll be asked if you want to set a filter. This filter determines which customers or vendors you want to apply the information to. For example, you can choose to apply the tax area to those customers that are in your own city or county, or to all customers.

Who you assign the tax area codes to will determine the taxes that are calculated on your sales and purchasing transactions.

If you move to the empty *My Company*, we recommend that you start by using each of the assisted setup guides, including the one for sales tax. If you prefer to set up sales tax yourself, this article explains what you have to take into consideration. But we recommend that you work closely with your tax advisor.  

## Tax groups, tax areas, and tax jurisdictions

In [!INCLUDE[prod_short](../../../includes/prod_short.md)], a tax group represents a group of inventory items or resources that are subject to identical tax terms. For example, you can set up a tax group for taxable items and another for nontaxable items. You must assign tax group codes to inventory items and general ledger accounts. Similarly, you must assign tax area codes to customers, locations, and to your own company settings. The assisted setup guide helps you do this.  

Each tax area is a grouping of sales tax jurisdictions based on a particular geographic location. For example, the tax area for Miami, Florida, includes three sales tax jurisdictions: city (Miami), county (Dade), and state (Florida). [!INCLUDE[prod_short](../../../includes/prod_short.md)] includes a limited set of tax areas with a default configuration, but you can change them and add new tax areas.  
