---
title: "Using Common Data Service"
description: Introduction to Common Data Service and its components.
author: bholtorf

ms.author: bholtorf
ms.custom: na
ms.reviewer: na
ms.service: dynamics365-business-central
ms.topic: article
ms.date: 10/01/2019
---

# About Common Data Service
Common Data Service lets you securely store and manage data that's used by business applications. Data is stored in a set of entities, which are sets of records similar to how a table stores data within a database. Common Data Service includes a base set of standard entities that cover typical scenarios, but you can also create custom entities specific to your organization. For more information, see [Standard and Custom Entities](admin-common-data-service.md#standard-and-custom-entities).

In addition to [!INCLUDE[d365fin_md](includes/d365fin_md.md)], other Dynamics 365 applications, such as Dynamics 365 Sales, Dynamics 365 Customer Service or Dynamics 365 Talent,also use Common Data Service. That means that you can build your apps and use Common Data Service directly against your core business data without the need for integration.

## Integrating Data into the Common Data Service
Apps often use data from more than one source. By combining data in a common store, Common Data Service makes it easier to develop apps, and provides a single set of logic to maintain and operate over data from other Dynamics 365 applications.  

* **Scheduled integration with other systems** – Regularly synchronize data from other applications.  
* **Transform and import data** – Transform data when importing to the Common Data Service can be done through from many online data sources.  
* **One time import of data** – Simple import and export of Excel and CSV files can be used for a one time or infrequent import of data into the Common Data Service.  

## Standard and Custom Entities
You can use the standard entities that Common Data Service provides, or build your own, or both. The standard entities are designed to cover typical business concepts and scenarios based on best practices.



