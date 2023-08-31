---
title: Set Up Electronic Invoicing [MX]
description: Before you can send electronic documents in Mexico, you must set up Business Central to ensure that the required identification numbers are in place for CFDI.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 05/19/2022
ms.author: bholtorf
---

# Set up Electronic invoicing - Mexico

Before you can send electronic documents, you must set up [!INCLUDE[prod_short](../../includes/prod_short.md)] to ensure that the tax identification number (RFC), personal identification number (CURP), and state inscription IDs are available for your company and all your customers and vendors. You also need to set up the parameters that are needed for sending electronic invoices to customers and vendors. These parameters include the certificate thumbprint, which is the certificate that you received from the Mexico tax authority (SAT).  

> [!IMPORTANT]  
> The certificate that you received from the Mexico tax authority must be installed for each user who sends electronic invoices. For more information, see the [Servicio de Administracíon Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website.  
>
> Your company must also have SMTP mail set up for emailing electronic invoices. Depending on the configuration in your company, you may need to grant explicit SMTP permissions to each relevant user and computer. The documents will be sent from the address that is specified on the **Company Information** page.  

## Set up company information  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
2. On the **Company Information** page, fill in the relevant fields. For more information, see [Company Information Quick Start](../../quick-start-company-information.md).

    > [!NOTE]
    > You must fill in the **SAT Postal Code** field. If you cannot see the field on the **General** Fast Tab, choose the **More** action to show more fields.
3. On the **Shipping** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    |**SCT Permission Type** and **SCT Permission Name**|These fields specify a permission that has been provided by the Secretaría de Comunicaciones y Transportes. The permission must correspond to the type of motor transport that the company uses for the transfer of goods or merchandise if you transport goods and merchandise in the national/regional territory.|
4. On the **Tax** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    |**Tax Scheme**|Enter the tax scheme that your company uses complies with. Commonly used tax schemes are Régimen General, Régimen intermedio, and Régimen de pequeños contribuyentes (REPECOS).|
    |**SAT Tax Regime Classification**|Specify the tax scheme required for reporting to the Mexican tax authorities (SAT).|
    |**RFC No.**|Enter the federal registration number for taxpayers. The Registro Federal de Contribuyentes (RFC) tax identification type can be applied to companies and to people. An RFC number for a company is 12 characters, while an RFC number for a person is 13 characters. However, since [!INCLUDE [prod_short](../../includes/prod_short.md)] targets businesses, only 12 digit RFC numbers are currently supported.|
    |**CURP No.**|Enter the unique fiscal card identification number. The Cédula de identification fiscal con clave única de registro de población (CURP) tax identification type can only be applied to people. A CURP number is 18 characters.|
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|

## Set up general ledger information  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, on the **Electronic Invoice** FastTab, fill in the fields as described in the following table.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**Enabled**|Choose this field to switch to use digitally signed documents, and then fill in the remaining fields on this FastTab.|
    |**SAT Certificate**|Specify the SAT certificate. For more information, see the [To add the certificates](how-to-set-up-pac-web-services.md#to-add-the-certificates) section.|
    |**Send PDF Report**|Choose this field to include a PDF when you email electronic invoices to customers or vendors. Electronic invoices are always sent as an XML file, this option allows you to include a PDF with the XML file.|  
    |**PAC Code**|Specify the authorized service provider, PAC, that you want apply digital stamps to your electronic invoices. For more information, see [Set Up PAC Web Services](how-to-set-up-pac-web-services.md).|
    |**PAC Environment**|Specify if your company is using the web services of your authorized service provider, PAC, in a test environment or a production environment.|

Optionally, you can ask your Microsoft Certified Partner to modify the text that is included in the email that is sent when you send electronic invoices. The text is stored as text variables in codeunit 10145, which can be [extended by a developer](/dynamics365/business-central/dev-itpro/developer/devenv-dev-overview).  

## Set up customer and vendor information

You also must add information about your customers and vendors. The following section describes how to specify this information to customers and vendors.

### Set up customer information

1. Choose the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.  
2. For each customer in the **Customers** list, open the customer card, and then fill in the fields on the **General** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**CFDI Purpose**|Enter the CFDI purpose required for reporting to the Mexican tax authorities (SAT).|
    |**CFDI Relation**|Enter the relation of the CFDI document.|
    |**CFDI Export Code**|Enter a code to indicate if the customer is typically used for exports to other countries/regions.|
    |**SAT Tax Regime Classification**|Enter the tax scheme required for reporting to the Mexican tax authorities (SAT).|

3. On the **Invoicing** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 digits.|
    |**CURP No.**|Enter the unique fiscal card identification number. The CURP number must contain 18 digits.|
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|

    > [!NOTE]
    > If you select the **Prices Including VAT** field for a customer, the electronic documents will include VAT in all amounts, including unit prices. The electronic documents will also contain a separate element for VAT. If you want to avoid any possible confusion about the amounts including VAT, you can choose to not select the **Prices Including VAT** field.

4. On the **Payments** FastTab, in the **Payment Method Code** field, specify the payment method that you want to use for this customer.  
5. Repeat steps 2-4 for all other customers.  

### Set up vendor information

1. Choose the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendors**, and then choose the related link.
2. For each vendor in the **Vendors** list, open the vendor card, and then fill in the fields on the **General** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  
3. On the **Payments** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 digits.|
    |**CURP No.**|Enter the unique fiscal card identification number. The CURP number must contain 18 digits.|
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|
4. Repeat steps 2-3 for all other vendors.  

## Set up location information

Finally, you must add information about locations you use. The following section describes how to specify this information to locations.

1. Choose the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.
2. For each location in the **Locations** list, open the location card, and then, on the **Address & Contact** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**SAT State Code**|Enter the state, entity, region, community, or similar definitions where the domicile of the origin and / or destination of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Municipality Code**|Enter the municipality, delegation or mayoralty, county, or similar definitions where the destination address of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Locality Code**|Enter the city, town, district, or similar definition where the domicile of origin and / or destination of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Suburb Code**|Enter the SAT suburb code where the domicile of the origin or destination of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Postal Code**|Enter the SAT postal code where the domicile of the origin or destination of the goods or merchandise that are moved in the different means of transport is located.|
3. Repeat step 2 for all other locations.  

## Set up cancellation reasons

1. Select the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **CFDI Cancellation Reasons**, and then select the related link.  
2. Select **New** to create new cancellation reason or select **Edit** to make changes an existing one.
3. In the **Code** field, enter a value that corresponds to the SAT cancellation reason definition.
4. In the **Description** field enter a brief summary according to the SAT cancellation reason definition.
5. In the **Substitution Number Required** field, specify whether a substitution number is required for the entry according to the SAT cancellation reason definition. If you choose code 01, specify the document that substitutes the canceled document in the **Substitution Document No.** field.
6. Close the page.

## Map key data to the CFDI fields

You can let [!INCLUDE [prod_short](../../includes/prod_short.md)] map relevant fields to the data structure that is required by CFDI by using the **Set up Mexican CFDI information** assisted setup guide, or you can map the fields manually.  

### Assisted setup

1. Choose the ![A fourth lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Mexican CFDI information**, and then choose the related link.
2. Follow the steps in the **Set up Mexican CFDI information** assisted setup guide to map information about your company and how you use [!INCLUDE [prod_short](../../includes/prod_short.md)] to the various fields in the CFDI files.

### Manual setup

If you prefer to map the fields yourself, then you must update the following pages:

- **Countries/Regions**  
- **Units of Measure**  
- **SAT Tax Schemas**  
- **Payment Methods**  
- **Payment Terms**  

#### Map your country codes to the values that SAT requires

1. Choose the ![A fifth lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Countries/Regions**, and then choose the related link.
2. In the **SAT Country Code** field, specify the country code required for reporting to the Mexican tax authorities (SAT).
3. Repeat steps 1-2 for all country codes.

#### Map your units of measure to the values that SAT requires

1. Choose the ![A sixth lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Units of Measure**, and then choose the related link.
2. In the **SAT UofM Classification** field, specify the unit of measure required for reporting to the Mexican tax authorities (SAT).
3. Repeat steps 1-2 for all units of measure.

#### Configure SAT Tax Regime Classification

1. Choose the ![A seventh lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **SAT Tax Schemas**, and then choose the related link.
2. Fill in the fields as appropriate. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

#### Map your payment methods to the values that SAT requires

1. Choose the ![An eight lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Methods**, and then choose the related link.
2. In the **SAT Method of Payment** field, specify the payment method for paying the Mexican tax authorities (SAT).
3. Repeat steps 1-2 for all payment methods.

#### Map your payment terms to the values that SAT requires

1. Choose the ![A ninth lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Payment Terms**, and then choose the related link.
2. In the **SAT Payment Form** field, specify the number of the SAT payment form.
3. Repeat steps 1-2 for all payment terms.

## See Also

[Electronic Invoicing](electronic-invoicing.md)  
[Generate Electronic Invoices](how-to-generate-electronic-invoices.md)  
[Mexico Local Functionality](mexico-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
