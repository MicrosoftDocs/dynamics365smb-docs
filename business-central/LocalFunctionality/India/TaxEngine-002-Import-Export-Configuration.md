---
    title: Tax Engine - Import/Export Configuration
    description: Tax Engine - Import/Export Configuration
    author: v-debapd

    ms.service: dynamics365-business-central
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords: India, local, IN, English
    ms.date: 10/01/2020
    ms.author: v-debapd
   
---
# Tax Engine - Import/Export Configuration

[!INCLUDE[vnext_preview](../../includes/vnext_preview.md)]

Json Exchange extension is used to import or export the configuration data of tax engine in json format.

There are two options available for importing and exporting tax configuration:

- **Import or Export from Tax Type**

This option is used when all configuration pertaining to a tax type is to be imported or exported. It contains entities, components, input parameter, rate setup and use cases.

- **Import or Export for a specific Use Case**

This option is used when configuration pertaining to one or more-use cases is to be imported or exported. It contains use case related information.

- **Importing Use Cases in a new company**

This is required to import the use cases in a new company.
1. Go to **Setting** -> **Assisted Setup** -> **Setup Tax Engine**, a **Tax Engine Setup* wizard will be opened.
2. Select **Append** and click on **Next**.
3. Click on **Finish** and system will import all the pre-configured use cases from the configuration file in the new company.















































[!INCLUDE[footer-include](../../includes/footer-banner.md)]