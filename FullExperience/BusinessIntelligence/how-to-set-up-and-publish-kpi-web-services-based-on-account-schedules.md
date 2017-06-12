---
title: "How to: Set Up and Publish KPI Web Services Based on Account Schedules"
ms.custom: na
ms.date: "03-03-2017"
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "account schedules, setting up KPI web services"
  - "account schedules, publishing KPI web services"
  - "KPI web services"
ms.assetid: 07e5afc2-18a0-4e31-9a78-24b94a36a358
caps.latest.revision: 3
ms.author: "sgroespe"
translation.priority.ht: 
  - "da-dk"
  - "de-at"
  - "de-ch"
  - "de-de"
  - "en-au"
  - "en-ca"
  - "en-gb"
  - "en-in"
  - "en-nz"
  - "es-es"
  - "es-mx"
  - "fi-fi"
  - "fr-be"
  - "fr-ca"
  - "fr-ch"
  - "fr-fr"
  - "is-is"
  - "it-ch"
  - "it-it"
  - "nb-no"
  - "nl-be"
  - "nl-nl"
  - "ru-ru"
  - "sv-se"
---
# How to: Set Up and Publish KPI Web Services Based on Account Schedules
In the **Account Schedule KPI Web Service Setup** window, you set up how to show the account\-schedule KPI data and which specific account schedules to base the KPIs on. When you choose the **Publish Web Service** button, the specified account\-schedule KPI data is added to the list of published web services in the **Web Services** window.  
  
### To set up and publish a KPI web service that is based on account schedules  
  
1.  In the **Search** box, enter **Account Schedule KPI Web Service Setup**, and then choose the related link.  
  
2.  On the **General** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Forecasted Values Start**|Specify at what point in time forecasted values are shown on the account\-schedule KPI graphic.<br /><br /> The forecasted values are retrieved from the general ledger budget that you select in the **G\/L Budget Name** field. **Note:**  To obtain KPIs that show forecasted figures after a certain date and actual figures before the date, you can change the **Allow Posting From** field in the **General Ledger Setup** window. For more information, see [Allow Posting From](assetId:///efa2e448-f340-42e8-ba93-f17f183dde40).|  
    |**G\/L Budget Name**|Specify the name of the general ledger budget that provides forecasted values to the account\-schedule KPI web service.|  
    |**Period**|Specify the period that the account\-schedule KPI web service is based on.|  
    |**View By**|Specify which time interval the account\-schedule KPI is shown in.|  
    |**Web Service Name**|Specify the name of the account\-schedule KPI web service.<br /><br /> This name will appear in the **Service Name** field in the **Web Services** window.|  
  
     Proceed to specify one or more account schedules that you want to publish as a KPI web service according to the setup that you made in the previous table.  
  
3.  On the **Account Schedules** FastTab, fill in the fields as described in the following table.  
  
    |[!INCLUDE[bp_tablefield](../ApplicationDesign/includes/bp_tablefield_md.md)]|[!INCLUDE[bp_tabledescription](../ApplicationDesign/includes/bp_tabledescription_md.md)]|  
    |---------------------------------|---------------------------------------|  
    |**Acc. Schedule Name**|Specify the account schedule that the KPI web service is based on.|  
    |**Acc. Schedule Description**|Specify the description of the account schedule that the KPI web service is based on.|  
  
4.  Repeat step 3 for all the account schedules that you want to base the account\-schedule KPI web service on.  
  
5.  To view or edit the selected account schedule, on the **Account Schedule** FastTab, choose **Edit Account Schedule**.  
  
6.  To view the account\-schedule KPI data that you have set up, on the **Navigate** tab, in the **General** group, choose **Account Schedule KPI Web Service**.  
  
7.  To publish the account\-schedule KPI web service, on the **Home** tab, in the **Process** group, choose **Publish Web Service**. The web service is added to the list of published web services in the **Web Services** window.  
  
    > [!NOTE]  
    >  You can also publish the KPI web service by pointing to the **Account Schedule KPI Web Service Setup** page object from the **Web Services** window. For more information, see [How to: Publish a Web Service](../SetupAndAdministration/how-to-publish-a-web-service.md).  
  
## See Also  
 [Account Schedule KPI Web Service Setup](../Topic/\($%20N_195%20Account%20Schedule%20KPI%20Web%20Service%20Setup%20$\).md)   
 [Account Schedule KPI Web Service](../Topic/\($%20N_197%20Account%20Schedule%20KPI%20Web%20Service%20$\).md)   
 [Web Services](../Topic/\($%20N_810%20Web%20Services%20$\).md)   
 [How to: Publish a Web Service](../SetupAndAdministration/how-to-publish-a-web-service.md)