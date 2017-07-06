---
    title: Scenario Example: Calculating Cash Flow Dates and Amounts for Open Invoices | Microsoft Docs
    description: This topic shows how the cash flow forecast dates and amounts are calculated for an open sales invoice.
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
# Scenario Example: Calculating Cash Flow Dates and Amounts for Open Invoices
This topic shows how the cash flow forecast dates and amounts are calculated for an open sales invoice.  
  
## Calculating Cash Flow Forecast Dates and Amounts  
 If the payment discount terms have not expired, the cash flow forecast assumes that the customer will pay on the date when the terms expire and get a discount. If the payment discount terms have expired, the cash flow forecast assumes that the customer will pay on the payment due date and will not get a discount.  
  
## Scenario Example  
 The following list describes the scenario example that is used to show how the cash flow forecast dates and amounts are calculated.  
  
-   The invoice date is January 1, 2013.  
  
-   The invoice amount is 100.00 local currency (LCY).  
  
-   The invoice payment terms are 14 days/5 days-2%.  
  
-   The cash flow payment terms are 21 days/3 days-4%.  
  
## Results  
 This section uses the setup scenarios that are described in the [Cash Flow Forecast Dates and Amounts](../cash-flow-forecast-dates-and-amounts.md) topic to show the calculation results of the cash flow forecast dates and amounts.  
  
### Results Based on Setup Scenario 1  
 The following table shows the cash flow forecast dates and amounts based on the setup scenario 1.  
  
|Work date|Cash flow forecast date|Cash flow forecast amount|  
|---------------|-----------------------------|-------------------------------|  
|Any work date between January 1, 2013 and January 4, 2013|January 4, 2013|96|  
  
#### Results Based on Setup Scenario 2  
 The following table shows the cash flow forecast dates and amounts based on the setup scenario 2.  
  
|Work date|Cash flow forecast date|Cash flow forecast amount|  
|---------------|-----------------------------|-------------------------------|  
|Any work date after January 5, 2013|January 22, 2013|100|  
  
##### Results Based on Setup Scenario 3  
 The following table shows the cash flow forecast dates and amounts based on the setup scenario 3.  
  
|Work date|Cash flow forecast date|Cash flow forecast amount|  
|---------------|-----------------------------|-------------------------------|  
|Any work date between January 1, 2013 and January 6, 2013|January 6, 2013|98|  
  
###### Results Based on Setup Scenario 4  
 The following table shows the cash flow forecast dates and amounts based on the setup scenario 4.  
  
|Work date|Cash flow forecast date|Cash flow forecast amount|  
|---------------|-----------------------------|-------------------------------|  
|Any work date after January 7, 2013|January 15, 2013|100|  
  
## See Also  
 [Cash Flow Forecast Dates and Amounts](../cash-flow-forecast-dates-and-amounts.md)