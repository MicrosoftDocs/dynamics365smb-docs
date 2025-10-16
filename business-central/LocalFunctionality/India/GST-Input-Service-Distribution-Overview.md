---
title: GST Input Service Distribution Overview
description: Overview of GST Input Service Distribution functionality in Business Central for India, including setup steps and configuration requirements.
author: v-debapd
ms.topic: overview
ms.devlang: al
ms.search.keywords: India, local, IN, English, input service distribution, ISD on location, ISD on general ledger setup, ISD on source code setup, ISD on GST posting setup
ms.date: 10/16/2025
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: soumramani
---

# GST input service distribution overview

## Overview

Input Service Distributor (ISD) is an office of the supplier, which distributes credit pertaining to Input Services (CGST, SGST and/IGST) to various locations of the supplier. The recipient locations can be inter-state or intra-state, but they should have the same PAN as that of the distributing location. GST Input Service Distribution functionality can be used to distribute CGST & SGST/IGST paid on Input services (Input Tax Credit) to other locations. This functionality is applicable only for Services.

System doesn't allow posting any sales transactions for a location if it contains a registration number, which has **GST Input Service Distribution** activated.

### Lists of setups that are required to be configured

- Locations
- General Ledger Setup
- Source Code Setup
- GST Posting Setup
- GST Component Distribution
- GST Posting No. Series Setup

## Set up ISD on location

This setup is required to identify that this location is applicable for Input Service Distribution.

1. Choose the ![img.](image/search.jpg)icon, enter **Location**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------| 
    |**GST Registration No.**|Select the relevant GST registration number, which should be marked true as **Input Service Distributor**.|

## Set up ISD on general ledger setup

This setup is required to define the number series for distribution.

1. Choose the ![img.](image/search.jpg)icon, enter **General Ledger Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**GST Distribution Nos.**|Specify the number series code for GST Distribution.|

## Set up ISD on source code setup

This setup is required to define the source code for distribution.

1. Choose the ![img.](image/search.jpg)icon, enter **Source Code Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**GST Distribution**|Specify the relevant source code for GST Distribution.|

## Set up ISD on GST posting setup

This setup is required to define the general ledger accounts for distribution.

1. Choose the ![img.](image/search.jpg)icon, enter **GST Posting Setup**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**Receivable Acc. Interim (Dist)**|Specify the relevant general ledger account.|
    |**Receivable Acc. (Dist)**|Specify the relevant general ledger account.|

## Set up ISD on GST component dist. list

This setup is required to define the GST components for distribution functionality.

1. Choose the ![img.](image/search.jpg)icon, enter **GST Component Dist. List**, and then choose the related link.
1. Fill in the fields as described in the following table.

    |Field|Description|
    |---------------------------------|  ---------------------------------------|
    |**GST Component Code**|Specify the relevant component code.|
    |**Distribution Component Code**|Specify the relevant distribution component.|
    |**Intrastate Distribution**|Specify whether this is applicable for intrastate distribution or not.|
    |**Interstate Distribution**|Specify whether this is applicable for interstate distribution or not.|

## Set up Posting No. Series

This setup is required to define the Posting No. Series for distribution.

|Field|Required/Optional|Description|
|-----|-----------|------|
|GST Distribution| Always |Specifies the posting no. series for different documents type.|
|GST Distribution Line| Specify location Code| Specifies the posting no. series for different documents type and location-wise|

## Related information

[GST Input Service Distribution Process](GST-Input-Service-Distribution-Process.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]  
