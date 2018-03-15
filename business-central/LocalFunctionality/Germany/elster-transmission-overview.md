---
    title: ELSTER Transmission Overview
    description: When a user submits a sales VAT advance notification from Business Central to the Elektronische Steuererklärungen (ELSTER) online portal, the Microsoft.Dynamics.ElsterTransferHandler assembly processes the document and then transmits it to ELSTER.

    services: project-madeira
    documentationcenter: ''
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
# ELSTER Transmission Overview
When a user submits a sales VAT advance notification from [!INCLUDE[d365fin](../../includes/d365fin_md.md)] to the Elektronische Steuererklärungen (ELSTER) online portal, the Microsoft.Dynamics.ElsterTransferHandler assembly processes the document and then transmits it to ELSTER. The following section describes technical aspects of submitting documents to ELSTER.  

## Process Overview  

1.  Within the program all relevant data is collected and written into an XML document which follows a schema as prescribed by the Oberfinanzdirektion (OFD). This document contains tax information as well as information about the company and person who submits this tax information.  
2.  After this document has been created successfully it is extended with configuration information (proxy server, certificates, and so forth) which is needed by Microsoft.Dynamics.ElsterTransferHandler.  
3.  The complete document is handed over to Microsoft.Dynamics.ElsterTransferHandler. The assembly further processes the data (encryption, compression, signature) and sends it to one of the servers of the OFD.  

    You can specify the servers of the OFD in the **Electronic VAT Decl. Setup** window. For more information, see [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md)  

4.  The data is received and processed by the server of the OFD and a response document is sent back.  
5.  The response document is received, decrypted, and decompressed by Microsoft.Dynamics.ElsterTransferHandler and returned as an XML document to [!INCLUDE[d365fin](../../includes/d365fin_md.md)]. You can then view the responses in the **VAT Transmission Log Entries** window.  

## Process Details  
The Microsoft.Dynamics.ElsterTransferHandler assembly is responsible for preparation before the transmission to the OFD and the processing of the response document before it is returned to the program.  

## Compression  
The used method for compression is GZIP. A compression method which assures data integrity using a redundancy check. For more information, see [System.IO.Compression.GZipStream](http://go.microsoft.com/fwlink/?LinkId=200710) on the MSDN Library. Certain parts of the documents are compressed with the GZIP method.  

The response document is also compressed using this method. The Handler has to decompress the data before it is returned to the program.  

## Encryption  
The standard which is used for encryption is PKCS#7v1.5. For more information, see [System.Security.Cryptography.Pkcs.EnvelopedCms](http://go.microsoft.com/fwlink/?LinkId=200708) on the MSDN Library. This method not only encrypts the data but also encrypts a recipient information in terms of a certificate from the OFD. This encryption is based upon an asymmetric method which ensures that the data can only be decrypted by the recipient. The data is encrypted with a part of the certificate which is publicly accessible (PublicKey) and can be decrypted exclusively with the non public part of the certificate (PrivateKey). Additionally, the recipient information from the encryption has to match the recipient certificate. This ensures that the data only can be decrypted by the OFD.  

The response uses the same method. With the transmission the OFD receives the public part of the user certificate which is used to encrypt the response document. This ensures that the response document can be decrypted by the recipient only.  

In order to transfer the encrypted data in a text based XML file it has to be Base64 coded. This is a method which is used to present binary data in a textual form.  

## Signature  
For the signature of the data a method following the standard XML-DSig is used. For more information, see [System.Security.Cryptography.Xml.SignedXml](http://go.microsoft.com/fwlink/?LinkId=200709) on the MSDN Library. This method applies a signature to the whole document or a part of the document which is encrypted with a certificate. Using this encryption (also with an asymmetric method) allows the mapping to a certain registered user by the OFD. Thus the integrity of the data can be assured and the identity of the sender can be determined by means of the signature.  

The integrity is assured by the fact that if the document is changed after it has been signed the signature will become invalid and the OFD rejects the data.  

The identity of the sender is determined by mapping the certificate to a registered user. It is checked if the certificate is valid, if it is locked or if other conspicuities have been noticed.  

## See Also  
 [Error Messages of the ElsterTransferHandler](error-messages-of-the-elstertransferhandler.md)   
 [Electronic Submission of Sales VAT Advance Notifications to ELSTER](electronic-submission-of-sales-vat-advance-notifications-to-elster.md)   
 [Set Up Sales VAT Advance Notifications for ELSTER](how-to-set-up-sales-vat-advance-notifications-for-elster.md)
