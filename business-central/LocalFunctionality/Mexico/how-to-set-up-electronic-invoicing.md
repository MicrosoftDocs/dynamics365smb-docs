---
    title: Set Up Electronic Invoicing [MX]
    description: Before you can send electronic documents in Mexico, you must set up Business Central to ensure that the required identification numbers are in place for CFDI.
    author: edupont04

    
    ms.topic: conceptual
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 02/17/2022
    ms.author: edupont

---
# Set Up Electronic Invoicing in the Mexican Version

Before you can send electronic documents, you must set up [!INCLUDE[prod_short](../../includes/prod_short.md)] to ensure that the tax identification number (RFC), personal identification number (CURP), and state inscription IDs are available for your company and all your customers and vendors. You also need to set up the parameters that are needed for sending electronic invoices to customers and vendors. These parameters include the certificate thumbprint, which is the certificate that you received from the Mexico tax authority (SAT).  

> [!IMPORTANT]  
> The certificate that you received from the Mexico tax authority must be installed for each user who sends electronic invoices. For more information, see the [Servicio de Administracíon Tributaria](https://go.microsoft.com/fwlink/?LinkId=242772) website.  
>
> Your company must also have SMTP mail set up for emailing electronic invoices. Depending on the configuration in your company, you may need to grant explicit SMTP permissions to each relevant user and computer. The documents will be sent from the address that is specified on the **Company Information** page.  

## To set up company information  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Company Information**, and then choose the related link.  
2. On the **Company Information** page, fill in the relevant fields. For more information, see [Company Information Quick Start](../../quick-start-company-information.md).

    > [!NOTE]
    > You must fill in the **SAT Postal Code** field. If you cannot see the field on the **General** Fast Tab, choose the **More** action to show more fields.
3. On the **Tax** FastTab, fill in the fields as described in the following table.  

    |Field|Description|  
    |------------------------------------|---------------------------------------|
    |**Tax Scheme**|Enter the tax scheme that your company uses complies with. Commonly used tax schemes are Régimen General, Régimen intermedio, and Régimen de pequeños contribuyentes (REPECOS).|
    |**SAT Tax Regime Classification**|Specify the tax scheme required for reporting to the Mexican tax authorities (SAT).|
    |**RFC No.**|Enter the federal registration number for taxpayers. The Registro Federal de Contribuyentes (RFC) tax identification type can be applied to companies and to people. An RFC number for a company is 12 characters, while an RFC number for a person is 13 characters. However, since [!INCLUDE [prod_short](../../includes/prod_short.md)] targets businesses, only 12 digit RFC numbers are currently supported.|
    |**CURP No.**|Enter the unique fiscal card identification number. The Cédula de identification fiscal con clave única de registro de población (CURP) tax identification type can only be applied to people. A CURP number is 18 characters.|
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|
    |**SCT Permission Type** and **SCT Permission Name**|These fields specify a permission that has been provided by the Secretaría de Comunicaciones y Transportes. The permission must correspond to the type of motor transport that the company uses for the transfer of goods or merchandise if you transport goods and merchandise in the national territory.|

    Fill in the remaining fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]

## To set up general ledger information  

1. Choose the ![Lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Setup**, and then choose the related link.  
2. On the **General Ledger Setup** page, on the **Electronic Invoice** FastTab, fill in the fields as described in the following table.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**Enabled**|Choose this field to switch to use digitally signed documents, and then fill in the remaining fields on this FastTab.|
    |**SAT Certificate**|Specify the SAT certificate. For more information, see the [To add the certificates](how-to-set-up-pac-web-services.md#to-add-the-certificates) section.|
    |**Send PDF Report**|Select to include a PDF when you email electronic invoices to customers or vendors. Electronic invoices are always sent as an XML file, this option allows you to include a PDF with the XML file.|  
    |**PAC Code**|Specify the authorized service provider, PAC, that you want apply digital stamps to your electronic invoices. For more information, see [Set Up PAC Web Services](how-to-set-up-pac-web-services.md).|
    |**PAC Environment**|Specify if your company is using the web services of your authorized service provider, PAC, in a test environment or a production environment.|

Optionally, you can ask your Microsoft Certified Partner to modify the text that is included in the email that is sent when you send electronic invoices. The text is stored as text variables in codeunit 10145, which can be [extended by a developer](/dynamics365/business-central/dev-itpro/developer/devenv-dev-overview).  

## To set up customer and vendor information

You also must add information about your customers and vendors. The following section section describes how to specify this information to customers and vendors.

### Set up customer information

1. Choose the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Card**, and then choose the related link.
2. In the **Customer Card** window, on the **General** FastTab, fill in the fields. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]. The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**CFDI Purpose**|Enter the CFDI purpose required for reporting to the Mexican tax authorities (SAT).|
    |**CFDI Relation**|Enter the relation of the CFDI document.|
    |**CFDI Export Code**|Enter a code to indicate if the customer is typically used for exports to other countries.|
    |**SAT Tax Regime Classification**|Enter the tax scheme required for reporting to the Mexican tax authorities (SAT).|

3. In the **Customer Card** window, on the **Invoicing** FastTab, fill in the fields [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]. The following table describes some of the complex CFDI-related fields.  

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 digits.|
    |**CURP No.**|Enter the unique fiscal card identification number. The CURP number must contain 18 digits.|
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|
    |**CFDI Export Code**| Enter the relevant code to indicate if the customer is typically used for exports to other countries. Use 01 no export, 02 for exported goods, and 03 for temporary exports, such as services or assembly.|

    > [!NOTE]
    > If you select the **Prices Including VAT** field for a customer, the electronic documents will include VAT in all amounts, including unit prices. The electronic documents will also contain a separate element for VAT. If you want to avoid any possible confusion about the amounts including VAT, you can choose to not select the **Prices Including VAT** field.

4. On the **Payments** FastTab, in the **Payment Method Code** field, specify the payment method that you want to use for this customer.

### Set up vendor information

1. Choose the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Card**, and then choose the related link.
2. In the **Vendor Card** window, on the **Payments** FastTab, fill in the fields as described in the following table.

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**RFC No.**|Enter the federal registration number for taxpayers. The RFC number must contain 12 digits.|
    |**CURP No.**|Enter the unique fiscal card identification number. The CURP number must contain 18 digits.|
    |**State Inscription**|Enter the tax ID number that is assigned by state tax authorities to every person or corporation.|

## To set up location information

Finally, you must add information about locations you use. The following section section describes how to specify this information to locations.

1. Choose the ![A third lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Location Card**, and then choose the related link.
2. In the **Location Card** window, on the **Address & Contact** FastTab, fill in the fields as described in the following table.

    |Field|Description|
    |------------------------------------|---------------------------------------|
    |**SAT State Code**|Enter the state, entity, region, community, or similar definitions where the domicile of the origin and / or destination of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Municipality Code**|Enter the municipality, delegation or mayoralty, county, or similar definitions where the destination address of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Locality Code**|Enter the city, town, district, or similar definition where the domicile of origin and / or destination of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Suburb Code**|Enter the SAT suburb code where the domicile of the origin or destination of the goods or merchandise that are moved in the different means of transport is located.|
    |**SAT Postal Code**|Enter the SAT postal code where the domicile of the origin or destination of the goods or merchandise that are moved in the different means of transport is located.|

## To map key data to the CFDI fields

1. Choose the ![A fourth lightbulb that opens the Tell Me feature.](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Mexican CFDI information**, and then choose the related link.
2. Follow the steps in the **Set up Mexican CFDI information** assisted setup guide to map information about your company and how you use [!INCLUDE [prod_short](../../includes/prod_short.md)] to the various fields in the CFDI files.

## See Also

[Electronic Invoicing](electronic-invoicing.md)  
[Generate Electronic Invoices](how-to-generate-electronic-invoices.md)  
[Mexico Local Functionality](mexico-local-functionality.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
