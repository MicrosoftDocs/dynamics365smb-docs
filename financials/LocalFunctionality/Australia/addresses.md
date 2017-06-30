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
# Addresses
A single postal code can include multiple cities in the same region.  
  
 At the same time, cities with the same name are sometimes located in different states.  
  
 For example, Australian postal code 4069 covers the cities of Chapel Hill and Kenmore in the state of Queensland. However, there is also a city named Chapel Hill in the state of South Australia, located in postal code 5153.  
  
 To avoid confusion and improve address accuracy, available options display when you enter data in address fields. For example, when you enter a postal code on a customer card, you can select from a list of all available cities for that postal code in the **City** field drop-down list. Likewise, when you enter a city name, you can select from a list of all available states in the **State** field drop-down list.  
  
 To enable this functionality, you must enter the data into the **Post Code** table. You can do this manually, or you can download a copy of the Australian postal codes from the Australian Post Office website. Downloadable postal codes are not available for New Zealand.  
  
 To increase postal efficiency in Australia, the postal department has introduced an address bar coding system in which every address is assigned a unique identifier called a Delivery Point Identifier \(DPID\). From the DPID, a bar code is generated and printed for each address. Companies can receive discounts on bulk mailings if they use these bar codes. To retrieve a DPID, you must connect to the local postal database that uses authorized Address Matching Approval System \(AMAS\) software. You can reduce your number of postal returns by validating customer addresses using the AMAS database.  
  
 When you print an address that has a DPID, a bar code will be printed together with the address. If you cannot print bar codes, the DPID will be printed together with the address.  
  
 Contact your vendor for information on how to obtain AMAS software.  
  
## See Also  
 Post Code   
 [Australia Local Functionality](australia-local-functionality.md)   
 [New Zealand Local Functionality](new-zealand-local-functionality.md)