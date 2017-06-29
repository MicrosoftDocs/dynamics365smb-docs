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
# How to: Process Certificates of Supply
When you sell goods to a customer in another EU country\/region, you must send the customer a certificate of supply that the customer must sign and return to you.  
  
 The following procedures are for processing certificates of supply for sales shipments, but the same steps apply for service shipments of items, and return shipments to vendors.  
  
### To view certificate of supply details  
  
1.  In the **Search** box, enter **Posted Sales Shipments**, and then choose the related link.  
  
2.  Choose the relevant sales shipment to a customer in another EU country\/region.  
  
3.  On the **Home** tab, in the **Shipment** group, choose **Certificate of Supply Details**.  
  
4.  By default, if the VAT Posting Group setup for the customer has the **Certificate of Supply Required** check box selected, then the **Status** field is set to **Required**. You can update the field to indicate whether the certificate has been received back from the customer.  
  
     If the VAT Posting Group setup does not have the **Certificate of Supply Required** check box selected, then a record is created and the **Status** field is set to **Not Applicable**. You can update the field to reflect the correct status information. You can manually change the status from **Not Applicable** to **Required**, and from **Required** to **Not Applicable** as needed.  
  
     When you update the **Status** field to **Required**, **Received**, or **Not Received**, a certificate is created.  
  
    > [!TIP]  
    >  You can use the **Certificates of Supply** window to get a view of the status of all posted shipments for which a certificate of supply has been created.  
  
5.  On the **Home** tab, in the **Process** group, choose **Print Certificate of Supply**.  
  
     You can preview or print the document. When you choose **Print Certificate of Supply** and print the document, the **Printed** check box is automatically selected. In addition, if not already specified, the status of the certificate is updated to **Required**.  
  
 You include the printed certificate with the shipment.  
  
### To print a certificate of supply  
  
1.  In the **Search** box, enter **Posted Sales Shipments**, and then choose the related link.  
  
2.  Choose the relevant sales shipment to a customer in another EU country\/region.  
  
3.  On the **Home** tab, in the **Shipment** group, choose **Print Certificate of Supply**.  
  
    > [!NOTE]  
    >  Alternatively, you can print a certificate from the  **Certificate of Supply** window.  
  
4.  To include information from the lines on the shipment document in the certificate, select the **Print Line Details** check box.  
  
5.  Select the **Create Certificates of Supply if Not Already Created** check box to have ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> create certificates for posted shipments that do not have one at the moment of execution. When you select the check box, new certificates will be created for all posted shipments that do not have certificates within the selected range  
  
6.  By default, the filter settings are for the shipment document that you have selected. Fill in the filter information to select a specific certificate of supply that you want to print.  
  
7.  In the **Certificate of Supply** window, choose the **Print** button to print the report or choose the **Preview** button to view it on the screen.  
  
     The **Certificate of Supply Status** field and the **Printed** field are updated for the shipment in the **Certificates of Supply** window.  
  
 You must send the printed certificate of supply to the customer for signature.  
  
### To update the status of a certificate of supply for a shipment  
  
1.  In the **Search** box, enter **Posted Sales Shipments**, and then choose the related link.  
  
2.  Choose the relevant sales shipment to a customer in another EU country\/region.  
  
3.  In the **Status** field, choose the relevant option.  
  
     If the customer has returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  
  
     You can modify the date to reflect the date that you received the customer's signed certificate of supply. You can also add a link to the signed certificate using standard ADD INCLUDE<!--[!INCLUDE[navnow](../../includes/navnow_md.md)]--> linking.  
  
     If the customer does not return the signed certificate of supply, choose **Not Received**. You must then send the customer a new invoice that includes VAT, because the original invoice will not be accepted by the tax authority.  
  
 To view a group of certificates, you start from the **Certificates of Supply** window, and then update the information about the status of outstanding certificates as you receive them back from your customers. This can be useful when you want to search for all certificates that have a certain status, for example, **Required**, for which you want to update their status to **Not Received**.  
  
### To update the status of a group of certificates of supply  
  
1.  In the **Search** box, enter **Certificates of Supply**, and choose the related link.  
  
2.  Filter the **Status** field to the value that you want in order to create the list of certificates that you want to manage.  
  
3.  To update the status information, on the **Home** tab, in the **Manage** group, choose **Edit List**.  
  
4.  In the **Status** field, choose the relevant option.  
  
     If the customer has returned the signed certificate of supply, choose **Received**. The **Receipt Date** field is updated. By default, the receipt date is set to the current work date.  
  
     You can modify the date to reflect the date that you received the signed the certificate of supply. You can also add a link to the signed certificate using standard Microsoft Dynamics NAV document linking.  
  
    > [!NOTE]  
    >  You cannot create a new certificate of supply in the **Certificate of Supply** window when you navigate to it using this procedure. To create a certificate for a shipment that was not set up to require one, open the posted sales shipment, and use either of two procedures described above:  
    >   
    >  -   To manually create a certificate of supply certificate  
    > -   To print a certificate of supply.  
  
## See Also  
 [Certificates of Supply](../certificates-of-supply.md)   
 [How to: Create Certificates of Supply](../how-to-create-certificates-of-supply.md)