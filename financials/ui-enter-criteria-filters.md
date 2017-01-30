---
title: Entering Criteria in Filters | Microsoft Docs
description: Learn how filters work in Financials.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen

ms.service: project-madeira
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/12/2016
ms.author: solsen

---
# Entering Criteria in Filters
When you want to search for data, such as customer names, addresses, or product groups, you enter criteria. In search criteria you can use all the numbers and letters that you normally use in the specific field. In addition, you can use special symbols to further filter the results.

## Searching using the Quick Filter
You can add filters to all pages by using the Quick Filter. The Quick Filter is enabled by choosing the magnifier icon in the top right corner of a page. This filtering type is used for a fast entry of criteria.

**Important**: The Quick Filter provides an easy access to filter data by entering plain text, but does also provide a lot of search criteria options. Depending on whether you enter plain text or text including symbols, the Quick Filter behaves differently.  

* If you enter plain text in the search criteria, the search criteria is interpreted as a case insensitive search that contains certain text.  
* If you enter text including symbols in the search criteria, the search criteria is interpreted exactly as you entered it, and the search is case sensitive.

### Quick filter criteria
<!-- html syntax because symbols conflict with MarkDown syntax -->
<TABLE>
  <TR>
    <TH>Search Criteria</TH>
    <TH>Interpreted as...</TH>
    <TH>Returns...</TH>
  </TR>
  <TR>
    <TD>>man</TD>
    <TD>@*man*</TD>
    <TD>All records that contain the text man and case insensitive.</TD>
  </TR>
  <TR>
    <TD>>se</TD>
    <TD>@*se*</TD>
    <TD>All records that contain the text se and case insensitive.</TD>
  </TR>
  <TR>
    <TD>>Man*</TD>
    <TD>Starts with Man and case sensitive.</TD>
    <TD>All records that start with the text Man.</TD>
  </TR>
  <TR>
    <TD>'man'</TD>
    <TD>An exact text and case sensitive.</TD>
    <TD>All records that match man exactly.</TD>
  </TR>
  <TR>
    <TD>@*man</TD>
    <TD>Ends with and case insensitive.</TD>
    <TD>All records that end with man.</TD>
  </TR>
  <TR>
    <TD>@man*</TD>
    <TD>Starts with and case insensitive.</TD>
    <TD>All records that start with man.</TD>
  </TR>
</TABLE>

**Note**: You cannot use a wildcard when filtering on enumeration fields, such as the **Status** field on sales orders. To enter a filter for this type of field, you can enter the numeric value as a filtering parameter. For example, in the **Status** field on a sales order that has the values **Open**, **Released**, **Pending Approval**, and **Pending Prepayment**, use the values **0**, **1**, **2**, and **3** to filter for these options.  

## See Also
[Working With Financials](ui-work-product.md)

