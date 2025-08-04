---
title: Specify available languages in your environment
description: Learn how to build a list of the languages that are available in your Business Central environment. 
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.form: 
ms.date: 02/19/2025
ms.custom: bap-template
---

# Specify the languages that are available in your Business Central environment

To let people work in their preferred language, the user interface (UI) in [!INCLUDE [prod_short](includes/prod_short.md)] is translated by apps that Microsoft provides, or by language apps that our partners provide on AppSource. Administrators install the language apps in their [!INCLUDE [prod_short](includes/prod_short.md)] environment. Afterward, on the **My Settings** page, people can choose the language in which they want to use [!INCLUDE [prod_short](includes/prod_short.md)].

The **Languages** page lists all languages that [!INCLUDE [prod_short](includes/prod_short.md)] supports. However, to use [!INCLUDE [prod_short](includes/prod_short.md)] in a selected language, the language app must be installed in the environment. If someone chooses a language that a language app isn't installed for, they might be confused when the UI doesn't change.

To avoid confusion and make it easier for people to select a language they can use, administrators can use the **Allowed Languages** page to list the languages that they installed language apps for. [!INCLUDE [prod_short](includes/prod_short.md)] filters the list of languages on the **My Settings** page to show only the allowed languages.

## Create a list of allowed languages

1. Choose the ![Lightbulb that opens the Tell Me feature.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Allowed Languages**, and choose the related link.
1. In the **Language ID** field, choose the language to allow.
1. Repeat step 2 for each language that you installed a language app for.

## Related information

[Administration Tasks](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
