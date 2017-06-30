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
# How to: Prepare Shipments

When your warehouse is set up to require warehouse shipment processing, you can ship items only on the basis of source documents that other company units have released to the warehouse for action. Source documents for shipments include sales orders, service orders, purchase return orders, and outbound transfers.

Before you can ship any items, you must either open a shipment document that is waiting for action or create a new shipment from orders that have been released to the warehouse and that probably require only the usual rate of expedition.


**Note**: If your warehouse uses cross-docking and bins, for each line, you can view the quantity of items that have been placed in the cross-dock bins. The program calculates these quantities automatically whenever the fields on the shipment are updated. If they are the items that apply to the shipment you are preparing, you can create a pick for all the lines and then complete the shipment.

## To create a shipment


1.In the Search box, enter Warehouse Shipments, and then choose the related link.


2.Fill in the fields on each journal line.


3.Fill in the shipment header. Press Ctrl+N for a blank header, fill in the location code, and if you are using bins, fill in the bin. If you are using directed put-away and pick, fill in the zone code.

If you are using directed put-away and pick and want to ship items with warehouse class codes other than the class code of the bin in the Bin Code field on the document header, you must delete the contents of the Bin Code field on the header before you retrieve source document lines for the items.


4.On the Actions tab, choose Get Source Documents and select one or several source documents. Or, choose Use Filters to Get Src. Docs. if you want to get particular shipment lines, for example, for a particular customer or shipping agent. You can create a shipment document with lines from several sales orders.

If you deleted the contents of the Bin Code field on the header before getting the lines, you must fill in an appropriate bin code on each shipment line.


When you have the lines you want to ship, you can start the process that sends the lines to warehouse employees to pick.

**Note**: The following procedure requires that the warehouse is set up to require warehouse pick processing as well as warehouse shipment processing.

## To pick and ship


1.In the Search box, enter Warehouse Shipments, and then choose the related link. Select the warehouse shipment that you want to work on.


2.In the Warehouse Shipment window, choose Create Pick.


3.Fill in the fields in the request window and then choose the OK button. All the fields are optional.


4.In the Search box, enter Picks, and then choose the related link. Select the warehouse pick that you want to work on.

If the warehouse is set up to use bins, then the pick lines have been converted to Take and Place action lines.

You can sort the lines, assign an employee to the pick, set a break-bulk filter, if you are using directed put-away and pick, and print the pick instructions.


5.Perform the actual picking of items and place them in the specified shipping bin, or in the shipping area, if you do not have bins.


6.Choose the  Register Pick button.

The Qty. to Ship field and the Document Status field on the header of the shipment document are updated. The items you have picked are no longer available for picking for other shipments or for internal operations.


7.Print your shipping documents, prepare the shipment packages, and post the shipment.


For more information about picking for warehouse shipments, see How to: Pick Items for Warehouse Shipment.

**Note**: You can also use the pick worksheet to make several pick instructions into one instruction (for several shipments) and thereby improve the efficiency of picking in the warehouse. For more information, see the Pick Worksheet window. If you are waiting for particular items to arrive at the warehouse, and you use cross-dock functionality, then Microsoft Dynamics NAV calculates on each shipment or pick worksheet line the quantity of the item that is in the cross-dock bin. It updates this field each time you leave and open the shipment document or worksheet.