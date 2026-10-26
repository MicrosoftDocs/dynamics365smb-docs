---
title: Set Up Electronic Invoicing - Mexico [MX]
description: To send electronic documents in Mexico, it's necessary to set up Business Central to include the required identification numbers for CFDI.
author: brentholtorf
ms.topic: how-to
ms.devlang: al
ms.search.keywords: identification numbers, CFDI
ms.date: 10/20/2026
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
ai-usage: ai-assisted
---

# Set up electronic invoicing - Mexico

Before you can send electronic documents, set up the tax identification information for your company, customers, and vendors in [!INCLUDE[prod_short](../../includes/prod_short.md)]. This information includes the applicable RFC, CURP, and state inscription IDs. You also need to upload the SAT certificate and configure the PAC web services used to stamp electronic documents.

> [!IMPORTANT]  
> Upload the certificate to [!INCLUDE[prod_short](../../includes/prod_short.md)] and select an **Available To** value that gives the relevant users access. You don't need to install the certificate on each user's computer. Learn more about SAT certificates and keys on the [Servicio de Administración Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website.
>
> To email electronic invoices, set up an email account for the **Default** email scenario. This account sends the documents. Learn more in [Set up email](../../admin-how-setup-email.md).

## Set up company information  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Company Information**, and then choose the related link.  
1. On the **Company Information** page, fill in the relevant fields. More information is available in the [Company Information Quick Start](../../quick-start-company-information.md) article.

    > [!NOTE]
    > You must fill in the **SAT Postal Code** field. If you can't see the field on the **General** FastTab, choose **Show more**.
1. On the **Tax** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    |**Tax Scheme**|Enter the tax scheme that your company complies with.|
    |**SAT Tax Regime Classification**|Specify the tax scheme required for reporting to the Mexican tax authorities (SAT).|
    |**RFC Number**|Enter the federal registration number for taxpayers. The field supports 12-character and 13-character RFC numbers.|
    |**CURP No.**|Enter the 18-character Clave Única de Registro de Población for a person, where applicable.|
    |**State Inscription**|Enter the tax ID number that the state tax authorities assign to every person or corporation.|

For Carta de Porte, specify SCT permissions on the vehicle's **Fixed Asset Card**, not on **Company Information**. Learn more in [Set up vehicles for transportation](packing-slips-transfer-orders.md#set-up-vehicles-for-transportation).

## Set up general ledger information  

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **General Ledger Setup**, and then choose the related link.  
1. On the **General Ledger Setup** page, on the **Electronic Invoice** FastTab, fill in the fields as described in the following table.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**Enabled**|Choose this field to switch to use digitally signed documents, and then fill in the remaining fields on this FastTab.|
    |**SAT Certificate**|Specify the SAT certificate. The section on [adding certificates](how-to-set-up-pac-web-services.md#add-the-certificates) provides information on how to add certificates.|
    |**Multiple SAT Certificates**|Enable this option to be able to assign other SAT certificates to locations associated with company branches.|
    |**Send PDF Report**|Select this field to include a PDF when you email electronic invoices to customers. The XML file is always attached.|
    |**PAC Code**|Specify the authorized service provider, PAC, that you want to apply digital stamps to your electronic invoices. Learn more in [Set up PAC web services](how-to-set-up-pac-web-services.md).|
    |**PAC Environment**|Specify if your company is using the web services of your authorized service provider, PAC, in a test environment or a production environment.|

Optionally, you can ask your Microsoft Certified Partner to modify the text that is included in the email that is sent when you send electronic invoices. The text is stored as text variables in codeunit 10145, which [a developer can extend](/dynamics365/business-central/dev-itpro/developer/devenv-dev-overview).  

## Set up customer and vendor information

You also must add information about your customers and vendors. The following section describes how to specify this information to customers and vendors.

### Set up customer information

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Customers**, and then choose the related link.  
1. For each customer in the **Customers** list, open the customer card, and then fill in the fields on the **General** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**CFDI Purpose**|Enter the CFDI purpose required for reporting to the Mexican tax authorities (SAT).|
    |**CFDI Relation**|Enter the relation of the CFDI document.|
    |**CFDI Export Code**|Enter a code to indicate if the customer is typically used for exports to other countries/regions.|
    |**SAT Tax Regime Classification**|Enter the tax scheme required for reporting to the Mexican tax authorities (SAT).|

1. On the **Invoicing** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**Tax Identification Type**|Select **Legal Entity** for a company or **Natural Person** for a person before entering the RFC number.|
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 characters for a legal entity or 13 characters for a natural person.|
    |**CURP No.**|Enter the unique personal identification number. The CURP number must contain 18 characters.|
    |**State Inscription**|Enter the tax ID number that the state tax authorities assign to every person or corporation.|

    > [!NOTE]
    > If the posted document uses **Prices Including VAT**, the CFDI export converts the unit prices and discounts to VAT-exclusive values. VAT is reported separately in the electronic document.

1. On the **Payments** FastTab, in the **Payment Method Code** field, specify the payment method that you want to use for this customer.  
1. Repeat steps 2-4 for all other customers.  

### Set up vendor information

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Vendors**, and then choose the related link.
1. For each vendor in the **Vendors** list, open the vendor card, and then fill in the fields on the **General** FastTab. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  
1. On the **Payments** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)] The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**Tax Identification Type**|Select **Legal Entity** for a company or **Natural Person** for a person before entering the RFC number.|
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 characters for a legal entity or 13 characters for a natural person.|
    |**CURP No.**|Enter the unique personal identification number. The CURP number must contain 18 characters.|
    |**State Inscription**|Enter the tax ID number that the state tax authorities assign to every person or corporation.|
1. Repeat steps 2-3 for all other vendors.  

## Set up location information

Use SAT address records to specify the geographic codes for your locations.

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SAT Addresses**, and then choose the related link.
1. Create or edit an address and fill in **Country/Region Code** and the relevant SAT codes.

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**SAT State Code**|Select the state or region for the address.|
    |**SAT Municipality Code**|Select the municipality for the address.|
    |**SAT Locality Code**|Select the city, town, or district for the address.|
    |**SAT Suburb Code**|Use the assist-edit button to select the suburb.|
    |**SAT Postal Code**|Review the postal code from the selected suburb. You can't edit this field directly.|

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Locations**, and then choose the related link.
1. Open the location card and fill in the following fields in the **Electronic Document** section of the **Address & Contact** FastTab.

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**SAT Address ID**|Select the SAT address for the location.|
    |**SAT Certificate**|Specify the SAT certificate issued by the tax authority to the company branch at this location. To enable this field, set the **Multiple SAT Certificates** option on the **General Ledger Setup** page. If a document is posted with a location that has an assigned SAT certificate, that certificate is used to sign the electronic document. Otherwise, the certificate from the **General Ledger Setup** page is applied.|

1. Repeat the location setup for each location used for electronic documents.

## Set up cancellation reasons

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **CFDI Cancellation Reasons**, and then select the related link.  
1. Select **New** to create new cancellation reason or select **Edit** to make changes to an existing one.
1. In the **Code** field, enter a value that corresponds to the SAT cancellation reason definition.
1. In the **Description** field, enter a brief summary according to the SAT cancellation reason definition.
1. In the **Substitution Number Required** field, specify whether a substitution number is required according to the SAT cancellation reason definition.
1. Close the page.

When you cancel a posted document with reason **01**, specify the replacement document in the **Substitution Document No.** field on that document, not on the cancellation reason.

## Map key data to the CFDI fields

You can let [!INCLUDE [prod_short](../../includes/prod_short.md)] map relevant fields to the data structure that is required by CFDI by using the **Set up Mexican CFDI information** assisted setup guide, or you can map the fields manually.  

### Use assisted setup

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Mexican CFDI information**, and then choose the related link.
1. Follow the steps in the **Set up Mexican CFDI information** assisted setup guide to map information about your company and how you use [!INCLUDE [prod_short](../../includes/prod_short.md)] to the various fields in the CFDI files.

### Map fields manually

If you prefer to map the fields yourself, then you must update the following pages:

- **Countries/Regions**  
- **Units of Measure**  
- **SAT Tax Schemas**  
- **Payment Methods**  
- **Payment Terms**  

#### Map your country codes to the values that SAT requires

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Countries/Regions**, and then choose the related link.
1. In the **SAT Country Code** field, specify the country code required for reporting to the Mexican tax authorities (SAT).
1. Repeat steps 1-2 for all country codes.

#### Map your units of measure to the values that SAT requires

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Units of Measure**, and then choose the related link.
1. In the **SAT UofM Classification** field, specify the unit of measure required for reporting to the Mexican tax authorities (SAT).
1. Repeat steps 1-2 for all units of measure.

#### Configure SAT tax regime classification

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **SAT Tax Schemas**, and then choose the related link.
1. Fill in the fields as appropriate. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

#### Map your payment methods to the values that SAT requires

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Methods**, and then choose the related link.
1. In the **SAT Method of Payment** field, specify the SAT code that describes how the customer pays the invoice.
1. Repeat steps 1-2 for all payment methods.

#### Map your payment terms to the values that SAT requires

1. [!INCLUDE [open-search](../../includes/open-search.md)], enter **Payment Terms**, and then choose the related link.
1. In the **SAT Payment Form** field, specify the number of the SAT payment form.
1. Repeat steps 1-2 for all payment terms.

## Related information

[Electronic Invoicing](electronic-invoicing.md)  
[Generate Electronic Invoices](how-to-generate-electronic-invoices.md)  
[Mexico Local Functionality](mexico-local-functionality.md)  

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
