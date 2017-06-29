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
# eXtensible Business Reporting Language
XBRL \(e **X**tensible **B**usiness **R**eporting **L**anguage\) is an XML\-based language for financial reporting. XBRL provides a standard for uniform reporting for all users of the financial information supply chain; such as public and private companies, the accounting profession, regulators, analysts, the investment community, capital markets and lenders, as well as key third parties such as software developers and data aggregators.  
  
 Taxonomies are maintained by www.xbrl.org. You can download taxonomies or read more detailed information on the XBRL website.  
  
## How to work with XBRL  
 Someone who wants financial information from you, provides you with a taxonomy \(an XML document\) containing one or more schemas, each with one or more lines to fill out. The lines correspond to the individual financial facts required by the sender. You import this taxonomy into the program and then fill out the schema\(s\) by entering which account or accounts correspond to each line, what kind of timeframe to use, for example net change or balance at date. In some cases you can enter a constant instead, for example, number of employees. You are now ready to send the instance document \(an XML document\) to the someone who requests the information. The idea is that this might be a recurring event, so unless changes have been made to the taxonomy, you just export new instance documents for new periods on request.  
  
## XBRL is comprised of the following components  
 The XBRL **Specification** explains what XBRL is, how to build XBRL instance documents and XBRL taxonomies. The XBRL Specification explains XBRL in technical terms and is intended for a technical audience.  
  
 The XBRL **Schema** are the core low\-level components of XBRL. The schema is the physical XSD file which express how instance documents and taxonomies are to be built.  
  
 The XBRL **Linkbases** are the physical XML files which contain various information about the elements defined in the XBRL Schema, such as labels in one or more languages, how they relate to each other, how to sum up elements, etc.  
  
 An XBRL **Taxonomy** is a "vocabulary" or "dictionary" created by a group, compliant with the XBRL Specification, in order to exchange business information.  
  
 An XBRL **Instance document** is a business report, such as a financial statement prepared to the XBRL specification. The meaning of the values in the instance document is explained by the taxonomy. An instance document is somewhat useless unless you know the taxonomy to which it is prepared.  
  
## Layered Taxonomies  
 A taxonomy can consist of a base taxonomy, for example, us\-gaap or IAS, and then have one or more extensions. To reflect this, a taxonomy refers to one or more schemas which all are separate taxonomies. When the additional taxonomies are loaded into the database, the new elements are simply added to the end of the existing elements.  
  
## Linkbases  
 In XBRL Spec. 2, the taxonomy is described in several XML\-files. The primary XML file is the taxonomy schema file itself \(.xsd file\) which only contains an unordered list of elements or facts to be reported. In addition to this, there are usually associated some linkbase files \(.xml\). The linkbase files contain data which is complementary to the raw taxonomy \(.xsd file\). There are six types of linkbases files of which four have relevance for Product Name XBRL. These are:  
  
-   Label linkbase: This linkbase contains labels or names for the elements. The file may contain labels in different languages which are identified with an XML property called 'lang'. The XML language identifier usually contains a two\-letter abbreviation, and although it should be easy to guess what the abbreviation means, there is no connection to the Windows language code or to the language codes defined in the demo data. Therefore, when the user looks up the languages for a specific taxonomy, he will see all the labels for the first element in the taxonomy, meaning that he can then see an example of each language. A taxonomy can have several label linkbases attached to it as long as these linkbases contain different languages.  
  
-   Presentation linkbase: This linkbase contains information about the structure of the elements, or more precisely; how the issuer of the taxonomy suggests that the program presents the taxonomy to the user. The linkbase contains a series of links that each connect two elements as parent and child. When applying all these links, the elements can be shown in a hierarchical way. Note that the presentation linkbase deals with just that: the presentation of elements to the user.  
  
-   Calculation linkbase: This linkbase contains information about which elements roll up to which. The structure is quite similar to the presentation linkbase, except that each link or ‘arc’, as they are called, has a weight property. The weight can be either 1 or –1 indicating whether the element should be added to or subtracted from its parent. Note that the rollups are not necessarily in keeping with the visual presentation.  
  
-   Reference linkbase: This linkbase is an xml file that contains supplementary information about the data that is required by the taxonomy issuer.