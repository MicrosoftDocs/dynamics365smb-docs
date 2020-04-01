---
    title: Receivables Cartera Module
    description: The Receivables Cartera module allows you to manage bills generated from sales invoices.

    services: project-madeira 
    documentationcenter: ''
    author: SorenGP

    ms.service: dynamics365-business-central
    ms.topic: article
    ms.devlang: na
    ms.tgt_pltfrm: na
    ms.workload: na
    ms.search.keywords:
    ms.date: 04/01/2020
    ms.author: sgroespe

---
# Receivables Cartera Module
The Receivables Cartera module allows you to manage bills generated from sales invoices. The documents can be managed by:  

- Due date  
- Bank  
- Value  
- Document type  
- Currency  

You can manually create bills using the **Cartera Journal**. You can also use the Receivables Cartera module to manage all sales invoices that the company yields to a factoring company.  

## Bill Groups  
With the Receivables Cartera module, you can manage bill groups and discount bill groups in your local currency or original currency.  

There are various criteria for grouping documents in a bill group. You can group documents for the same customer, documents with the same due date, documents drawn in the same market, and so on. You can group one or more receivable documents in one bill group.  

A bill group consists of one or more documents grouped together to submit to a bank. A bill group can be submitted for collection or discount.  

If submitted for collection, the bank is only responsible for processing the collection of the documents on the due date.  

If the bill group is submitted for discount, the bank will advance the amount of the bill group (or a portion of it, in the case of factoring) to the company, and will take responsibility for collecting on the due dates of the documents that make up the bill group.  

A bill group of invoices can be submitted to a financial institution (factor) for risked factoring (the risk of insolvency is covered by the company) or unrisked factoring (the risk of insolvency is covered by the factor).  

Bill groups include:  

- Finance charges for collection or discount management  
- Finance charges for returned bills  
- Interest for discounts  

With the Receivables Cartera module, you can yield credits or factoring of sales invoice bill groups, including the finance charge calculation by the factoring company. You can request the anticipated value of the yielded invoices, or only the management of the collection.  

You can use bill groups for the following:  

- Factoring without risk - The factoring company takes on the risks associated with non-payment.  
- Factoring with risk - You take on the risks associated with non-payment.  

## See Also  
 [Cartera Module](cartera-module.md)   
 [Payments Cartera Module](payments-cartera-module.md)
