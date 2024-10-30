---
title: Multi-language Power BI apps for Business Central
description: Learn how to test and use multi-language capabilities in the Power BI apps for Business Central. 
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.date: 05/28/2024
ms.author: kepontop
ms.service: dynamics-365-business-central
---

# Multi-language [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]

In this article, you learn how to test and use multi-language capabilities in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)]. 


## How to try a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app in your language/locales

To try an app in a language, simply add `language = <culture name>` to the url parameters. For example, this URL will show an app in German:
* https://<your domain>.powerbi.com/groups/a1d27337-134a-4326-99ed-9e68a1485679/reports/3173137b-a485-42e2-a3df-8f3acd7640a6/ReportSection2fa580b0181e8c981cdc?experience=power-bi&language=de-DE


## Languages and locales 

A culture name is usually a lower-case language identifier and an upper-case locale identifier separated by a hyphen. The culture name `en-US` identifies a user in the United States who speaks English. A culture name of `es-ES` identifies a user in Spain who speaks Spanish. A culture name of `fr-FR` identifies a user in France who speaks French. A culture name of `de-DE` identifies a user in Germany who speaks German.

| language parameter | Language | Locale        |
|--------------------|----------|---------------|
| en-US              | English  | United States |
| es-ES              | Spanish  | Spain         |
| fr-FR              | French   | France        |
| de-DE              | German   | Germany       |


## See also

[Installing Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)   
[Introduction to Business Central and Power BI](admin-powerbi.md)   
[Work with Power BI reports](across-working-with-powerbi.md)   
