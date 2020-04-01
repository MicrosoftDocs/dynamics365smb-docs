---
    title: How to Set Up PAC Web Services
    description: Before you can send invoices and credit memos electronically, you must specify one or more providers of the electronic stamp that must be included in invoices in Mexico.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Set Up PAC Web Services
Before you can send invoices and credit memos electronically, you must specify one or more providers of the electronic stamp that must be included in invoices in Mexico.  

When you send an electronic document, it must receive a digital stamp by an authorized service provider, PAC, before it can be sent to your customer. The communication between [!INCLUDE[d365fin](../../includes/d365fin_md.md)] and the PAC is managed through web services, and therefore, you must specify technical information about the web services of the PAC that you intend to use.  

To use web services, you must identify the name of the method on the web service that processes requests for digital stamps. Your PAC can give you this information.  

If your PAC offers the service of canceling signed documents, you must specify two web methods: one web method for requesting the digital stamp, and the other for canceling an already signed document.  

## To set up a PAC web service  

1.  Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **PAC Web Services**, and then choose the related link.  
2.  Fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|  
    |**Environment**|Specify if the web service is for a test environment or a production environment.|  
    |**Type**|Specify if the web method is for requesting a digital stamp or for canceling.|  
    |**Method Name**|Specify the name of the web method, such as **GeneraTimbre** or **CancelaTimbre**.|  
    |**Address**|Specify the URL of the web method.|  

    Contact your PAC for this information.  

5.  Repeat the steps for any additional PAC that you want to set up.  

    > [!IMPORTANT]  
    >  SAT has certified more than one PAC in Mexico, and you must obtain the appropriate information for communication with the PAC of your choice.  

## See Also  
 [Electronic Invoicing](electronic-invoicing.md)   
 [Set Up Electronic Invoicing](how-to-set-up-electronic-invoicing.md)  
 [Mexico Local Functionality](mexico-local-functionality.md)
