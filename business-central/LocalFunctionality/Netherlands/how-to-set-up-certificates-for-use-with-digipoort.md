---
title: How to Set Up Certificates for use with Digipoort
description: Information about Digipoort certificates.
author: SorenGP

ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords:
ms.date: 07/01/2017
ms.author: sgroespe

---

# Set Up Certificates for use with Digipoort
The following procedure assumes that you have obtained the certificates from the government. If you have not, take the following steps to obtain the certificates.  

- Obtain a PKIoverheid certificate for the company if you do not have one already. A list of certificate providers can be found here: [http://www.logius.nl/producten/toegang/pkioverheid/aansluiten/toegetreden-csps](http://www.logius.nl/producten/toegang/pkioverheid/aansluiten/toegetreden-csps).  

- Obtain a **Digipoort Service certificate**, which can be obtained at the Dutch Tax Administration website: [https://aansluiten.procesinfrastructuur.nl](https://aansluiten.procesinfrastructuur.nl).  

- Register a user of Digipoort, which can be done here: [https://aansluiten.procesinfrastructuur.nl/site/registratie/nieuw](https://aansluiten.procesinfrastructuur.nl/site/registratie/nieuw).  

After you register and log on to the official site, you can download the digiport server certificates from this site: [https://aansluiten.procesinfrastructuur.nl/site/documentatie/certificaten](https://aansluiten.procesinfrastructuur.nl/site/documentatie/certificaten).  

Next, you have to install the certificates. The certificates have to be installed on the server. Later, you will use the common name (CN) of the certificates in [!INCLUDE[d365fin](../../includes/d365fin_md.md)].  

> [!NOTE]  
>  In the Digipoort implementation you install certificates on the server. Users who need to be able to communicate with tax authorities via Digipoort will need access to the private key of the personal certificate on the server.  

## To install the certificates  

1.  Open the **Windows Certificate Console** to import the certificates that you have obtained from the government. For more information, see [Use the Certificates Console](http://social.technet.microsoft.com/wiki/contents/articles/2167.how-to-use-the-certificates-console.aspx).  
2.  Import the two certificates. For more information, [To import a certificate](http://social.technet.microsoft.com/wiki/contents/articles/2167.how-to-use-the-certificates-console.aspx#To_import_certificates).  

    **Personal Certificate**  

    1.  In the **Personal** section, choose the **Import** action. Make sure to set proper permissions to the private key.  
    2.  Complete the **Certificate Import Wizard**.  

    **Service Certificate**  

    1.  In the **Trusted Publishers** section, choose the **Import** action  
    2.  Complete the **Certificate Import Wizard**.  

3.  Grant read permissions to the certificate for the user who is doing the submission.  

    Right-click the certificate, choose the **All Tasks** action, and then choose the **Manage Private Keys** action. Select the user and in the **Permissions** box, select the **Allow Read** check box.  

4.  Close the **Console** window.  

## See Also  
 [Digipoort Overview](digipoort-overview.md)
