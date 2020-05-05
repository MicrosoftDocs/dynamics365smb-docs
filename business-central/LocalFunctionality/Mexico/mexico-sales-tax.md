---
title: Setting Up Tax Groups, Areas, and Jurisdictions in Mexico
description: Learn about how sales tax is set up, and how tax groups, tax areas (states, counties, cities, and localities), tax jurisdictions, and tax details work.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: local
ms.date: 04/01/2020
ms.author: edupont

---
# Reporting Sales Tax in the Mexico
When you first start using [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can run an assisted setup guide to quickly and easily set up sales tax information for your company, customers, and vendors. In a matter of minutes, you are ready to create sales documents and purchase documents with sales tax calculated correctly. 
If you move to the empty My Company, we recommend that you start by using each of the assisted setup guides, including the one for sales tax. If you prefer to set up sales tax yourself, this article explains what you have to take into consideration.  

## Tax Groups, Tax Areas, and Tax Jurisdictions
In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], a tax group represents a group of inventory items or resources that are subject to identical tax terms. For example, you can set up a tax group for taxable items and another for nontaxable items. You must assign tax group codes to inventory items and general ledger accounts. Similarly, you must assign tax area codes to customers, locations, and to your own company settings. The assisted setup guide helps you do this.  

If you set up new tax areas and tax jurisdictions, you must make sure that you fill in the fields correctly. In Mexico, states, counties, cities, and localities can charge sales tax. Companies collect and remit sales tax to these government authorities for products sold to end users. Sales tax can also be charged to existing sales tax. For example, tax can be calculated on a sales invoice amount that already includes the tax from other jurisdictions.  

## Tax Details
The **Tax Details** page shows different combinations of sales tax jurisdictions and sales tax groups to establish sales tax rates. For each tax jurisdiction, we recommend that you set up one tax group for normal sales tax, another tax group for items or services that are not taxed, and an additional tax group for every type of item or service that is handled with a different sales tax rate in that jurisdiction.  

In Mexico, when you sell to a customer at a location where you do not have a *situs*—or a legal location in that state, you do not collect sales tax. For locations in which you do not have a situs, ensure that both the **Tax Below Minimum** and **Tax Above Maximum** fields are 0.00.  

## See Also
[Mexico Local Functionality](mexico-local-functionality.md)  
[Finance](../../finance.md)  
[Setting Up Finance](../../finance.md)  
[Set Up Sales Tax - Watch a Video](https://www.youtube.com/watch?v=qMs4BoSytN8&index=13&list=PLcakwueIHoT8K1m148oMqo7amR2a7Bz-8)  
[Working with [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)  
