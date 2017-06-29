---
    title: Insert topic title| Microsoft Docs
    description: Insert description
    services: project-madeira
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-financials
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 07/01/2017
    ms.author: sgroespe

    ---
# How to: Import XBRLTaxonomies
The first step in working with the XBRL functionality is to import the taxonomy into your company database. A taxonomy consists of one or more schemas and some linkbases. After you have completed the import of both schemas and linkbases and have applied the linkbases to the schema, you can set up the lines and map the general ledger accounts in the chart of accounts to the appropriate taxonomy lines.  
  
### To import taxonomies  
  
1.  In the **Search** box, enter **XBRL Taxonomies**, and then choose the related link.  
  
2.  In the **XBRL Taxonomies** window, create a new line and enter the name and description of the taxonomy.  
  
3.  On the **Navigate** tab, in the **Taxonomy** group, choose **Schemas** and insert the description of the schema.  
  
4.  To import the schema, in the **XBRL Schemas** window, on the **Home** tab, in the **Process** group, choose **Import** and then select a folder and an XSD file. Choose the **Open** button.  
  
5.  To import the linkbase, in the **XBRL Schemas** window, on the **Home** tab, in the **Process** group, choose **Linkbases** and then select a folder and an XML file. Choose the **Open** button..  
  
6.  You can now choose to apply the linkbase to the schema. Repeat until you have imported all linkbases.  
  
7.  On the **Actions** tab, in the **Functions** group, choose **Apply to Taxonomy** to apply the linkbase to the schema.  
  
> [!IMPORTANT]  
>  Instead of individually applying the linkbases after the import, you can wait until you have imported all linkbases and then apply them at the same time. To do this, choose the **NO** button when you are prompted to apply the newly imported linkbase to the schema. Then select the lines with the linkbases that you want to apply.  
  
## See Also  
 [How to: Set Up XBRL Lines](../BusinessIntelligence/how-to-set-up-xbrl-lines.md)   
 XBRL Export Instance - Spec. 2   
 [How to: Update XBRL Taxonomies](../BusinessIntelligence/how-to-update-xbrl-taxonomies.md)   
 [eXtensible Business Reporting Language](../BusinessIntelligence/extensible-business-reporting-language.md)