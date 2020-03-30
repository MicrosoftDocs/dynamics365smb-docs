---
title: Expose objects as web services | Microsoft Docs
description: Publish objects as web services to make them immediately available for your Business Central solution.
author: edupont04

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 04/01/2020
ms.author: edupont

---
# Publish a Web Service

Web services are a lightweight way to make application functionality available to a variety of external systems and users. [!INCLUDE[d365fin](includes/d365fin_md.md)] includes an number of objects that are exposed as web services by default due to integration with other Microsoft services, but you can also add other web services.  

You set up a web service in the [!INCLUDE[d365fin](includes/d365fin_md.md)] client. You must then publish the web service so that it is available to service requests over the network. Users can discover web services by pointing a browser at the server location and requesting a list of available services. When you publish a web service, it is immediately available over the network for authenticated users. All authorized users can access metadata for web services, but only users who have sufficient permissions can access actual data.

## Creating and Publishing a Web Service  
The following steps explain how to create and publish a web service.  

### To create and publish a web service  

1. Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Web Services**, and then choose the related link.  
2. On the **Web Services** page, choose **New**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]  
    > **Codeunit** and **Page** are valid types for SOAP web services. **Page** and **Query** are valid types for OData web services.  
    > Also, if the database contains multiple companies, you can choose an object ID that is specific to one of the companies.  
    > Finally, the service name is visible to consumers of your web service and is the basis for identifying and distinguishing web services, so you should make the name meaningful.

3. Select the check box in the **Published** column.  

When you publish the web service, in the **OData URL** and **SOAP URL** fields, you can see the URLs that are generated for the web service. You can test the web service immediately by choosing the links in the **OData URL** and **SOAP URL** fields. Optionally, you can copy the value of the field and save it for later use.  

> [!IMPORTANT]
> For codeunits that are published as a SOAP web service, the methods exposed in the codeunit must be marked as `[External]` in the code.

After you publish a web service, it is available to external parties. You can verify the availability of that web service by using a browser, or you can choose the link in the **OData URL** and **SOAP URL** fields on the **Web Services** page. The following procedure illustrates how you can verify the availability of the web service for later use.  

### To verify the availability of a web service  

1. In your browser, enter the relevant URL. The following table illustrates the types of URLs that you can enter for different web service types.  

    > [!div class="mx-tdBreakAll"]
    > |Type|Syntax|Example|
    > |----------------|------|-------|
    > |SOAP|https://api.businesscentral.dynamics.com/*version*/*tenant*/Production/WS/*CompanyName*/*entity*/ |https://api.businesscentral.dynamics.com/v2.0/7acc9d3d-d354-4616-8bbd-c4fc9f2b15b3/Production/WS/CRONUS%20USA%2C%20Inc./Page/InvoiceDocument|
    > |OData V4|https://api.businesscentral.dynamics.com/*version*/*tenant*/Production/ODataV4/Company('*CompanyName*')/*entity*|https://api.businesscentral.dynamics.com/v2.0/7acc9d3d-d354-4616-8bbd-c4fc9f2b15b3/Production/ODataV4/Company('CRONUS%20USA%2C%20Inc.')/InvoiceDocument<br/>    The company name is case-sensitive.|

2. Review the information that is displayed in the browser. Verify that you can see the name of the web service that you have created.  

When you access a web service, and you want to write data back to [!INCLUDE[d365fin](includes/d365fin_md.md)], you must specify the company name. You can specify the company as part of the URI as shown in the examples, or you can specify the company as part of the query parameters. For example, the following URIs point to the same OData web service and are both valid URIs.  

```
https://api.businesscentral.dynamics.com/v1.0/OData/Company('CRONUS International Ltd.')/Customer  
```

```
https://api.businesscentral.dynamics.com/v1.0/OData/Customer?company='CRONUS International Ltd.'  
```

## See Also

[Administration](admin-setup-and-administration.md)  
[Business Central Web Services for developers](/dynamics365/business-central/dev-itpro/webservices/web-services)  
