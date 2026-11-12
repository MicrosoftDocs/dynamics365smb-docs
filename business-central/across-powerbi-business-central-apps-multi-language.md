---
title: Multilanguage Power BI Apps for Business Central
description: Test the Business Central Power BI apps in another language by adding a locale parameter to the report URL, such as de-DE for German.
author: kennieNP
ms.topic: get-started
ms.devlang: al
ms.search.keywords: analysis, reporting, business intelligence, KPI, installation, administration
ms.search.forms: 36951,
ms.date: 11/11/2026
ms.author: kepontop
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Use [!INCLUDE [prod_short](includes/prod_short.md)] Power BI apps in another language

This article describes how to test and use multilanguage capabilities in the [!INCLUDE [powerbi-name](includes/powerbi-name.md)] apps for [!INCLUDE [prod_short](includes/prod_short.md)].

## Try a [!INCLUDE [powerbi-name](includes/powerbi-name.md)] app in your language/locale

To try an app in a language, add `language=<CultureName>` to the report URL's query parameters, without spaces. Use `?language=de-DE` if the URL has no query parameters, or `&language=de-DE` if it already has parameters. For example, this URL requests German. Replace the example workspace ID, report ID, and `<ReportPage>` with the values from your report URL.

``` link
https://app.powerbi.com/groups/aaaaaaaa-0000-1111-2222-bbbbbbbbbbbb/reports/bbbbbbbb-1111-2222-3333-cccccccccccc/<ReportPage>?experience=power-bi&language=de-DE
```

## Languages and locales

A culture name is usually a lower-case language identifier and an upper-case locale identifier separated by a hyphen. Here are some examples of culture names:

- **en-US** identifies a user in the United States who speaks English.
- **es-ES** identifies a user in Spain who speaks Spanish.
- **fr-FR** identifies a user in France who speaks French.
- **de-DE** identifies a user in Germany who speaks German.

| language parameter | Language | Locale        |
|--------------------|----------|---------------|
| en-US              | English  | United States |
| es-ES              | Spanish  | Spain         |
| fr-FR              | French   | France        |
| de-DE              | German   | Germany       |

## Related information

[Install Power BI apps for Business Central](across-powerbi-install-business-central-apps.md)  
[Introduction to Business Central and Power BI](admin-powerbi.md)  
[Work with Power BI reports](across-working-with-powerbi.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
