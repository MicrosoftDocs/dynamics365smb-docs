---
title: Setting Up Web Sources for Contact Companies | Microsoft Docs
description: Describes how to use web sources for contacts in Financials
services: project-madeira
documentationcenter: ''
author: jswymer

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/01/2016
ms.author: jswymer

---
# Setting Up Web Sources for Contact Companies
You can use web sources with your contact companies to identify, for example, search engines and web sites, on the Internet that you want to use to search for information about the contacts. When assigning web sources, you specify which search engine and search word the application will use to find the requested information.

Using web sources on contacts is a two-step process. First, you define the web source code. You only have to perform this step one time for each web source. Once you have a web source code, you can start to assign the code to contact persons.

## to define a web source code
1. In the top right corner, choose the **Search for Page or Report** icon, enter **Web Sources**, and then choose the related link.
2. Choose the **New** actions.
3. Fill in the **Code**, **Description**, and **URL** fields.
   
    Type %1 in the **URL** field to insert a placeholder for a search word in the URL. When you launch the web source from a contact, the %1 is replaced with the search word, for example, the name of the company that you have entered in the **Contact Web Sources** window.

Repeat these steps to set up as many web sources as you want.

## tp assign web sources to a contact company
When assigning web sources, you specify which search engine and search word that the application will use to find the requested information.

1. Open the contact.
2. Choose the **Company** action, and then choose the **Web Sources** action. The **Contact Web Sources** window opens.
3. In the **Web Source Code** field, choose the web source you want to assign.
4. In the **Search Word** field, enter the search word that you want to use to find the information.

Repeat these steps to assign as many web sources as you want.

You can also assign web sources from the **Contact List** window by following the same procedure.

## See Also
[Creating Contact Companies](marketing-create-contact-companies.md)  
[Working With Financials](ui-work-product.md)

