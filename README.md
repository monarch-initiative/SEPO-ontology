## The SEPIO Ontology
The **Scientific Evidence and Provenance Information Ontology (SEPIO)** was developed to represent evidence and provenance information about scientific assertions (aka 'claims'), in a way that supports critical evaluation of their validity. **Evidence** is defined as information as used to evaluate the validity of a proposition put forth in an assertion. **Provenance** information describes the complete process history behind an assertion. This includes the history of the assertion itself (e.g. who made it how, and when), but also the history of all information used as evidence to support it (e.g. the agents, activities, and resources were used in generating the evidence).
  
SEPIO provides a flexible and generic model that defines a core set of concepts and relationships that capture how evidence is evaluated in the act of making a scientific assertion. The core model is suited to application in any domain, and can support the integration of data across different data models and systems [1]. SEPIO can easily be extended with domain-specific constructs to support focused applications or use cases. For example, we are developing a extensions to support representation of the detailed evidence and provenance information collected in variant interpretation workflows, implemented in tools being developed by the ClinGen consortium [2,3,4]. 

Below we provide a brief summary of the SEPIO data model and its core terms and relationships. The **Concept-Attribute Tables** and **Core Concept Pages** to the right offer more detailed descriptions of these concepts and their key attributes in the SEPIO model, and the **Real Data Example** pages provide a diverse selection of evidence and provenance data from existing databases represented using the SEPIO model.  Please post issues to our [tracker](https://github.com/monarch-initiative/SEPIO-ontology/issues), and contact Matthew Brush with questions at brushm@ohsu.edu.

-----------

## Core Concepts and Relationships
The central axis of SEPIO defines the relationship between **Assertions**, **Evidence Lines**, and **Evidence Items** (i.e. the individual pieces of information that serve as evidence). Around these concepts, SEPIO builds the core model diagrammed below.  

![sepio-wiki_023](https://user-images.githubusercontent.com/5184212/28144547-f004bd46-6720-11e7-887c-f4ad9291d646.jpg)

### (1) [Assertion](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Assertion)
- **Description:** An Assertion is an evidence-based statement made by a particular Agent on particular occasion, often following rules specified in some Assertion Method.  Assertions can be supported or disputed by one or more Evidence Line.
- **Example:** The ENIGMA consortium’s assertion that "The DSC2:c.631-2A>G variant is pathogenic_for arrhythmogenic ventricular cardiomyopathy."
  
### (2) [Evidence Line](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Evidence-Line)
- **Description:** Evidence Lines represent an independent argument relevant to the validity of the proposition it puts forth. Evidence Lines are supported by one or more individual pieces of Information, which in this role serve as Evidence Items.
- **Example:** The argument made for the assertion above by an Agent's interpretation of the prior assertion that "The c.631-2A>G variant impairs DSC2 gene function." 
    
### (3) [Evidence Item](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Evidence-Item)
- **Description**: An Evidence Item is any Information artifact that is interpreted to evaluate the validity of a Proposition put forth by an Assertion. It is shown parenthetically above because it is a 'defined class' in SEPIO, representing any piece of Information bearing an evidence role. SEPIO organizes Evidence Items under Evidence Lines that represent the discrete arguments to which these items contribute. 
- **Example:** Specific measurement data and statistical confidence scores from a study showing that recombinant DSC2 protein with this mutation showed impaired binding of Ca2+ ions in a HeLa cell based assay, that are used to support an Assertion that  the c.631-2A>G variant impairs DSC2 gene function. 
  
### (4) [Activity](https://github.com/monarch-initiative/SEPIO-ontology/wiki/Activity)
- **Description:** In SEPIO we are primarily concerned with Activities that generate information that is used as evidence, such as research studies, assays, or computation. SEPIO supports description of such Activities to capture the provenance of Evidence Items.
- **Example:** An in vitro Ca2+ binding assay
  
### (5) Publications
- **Description:** Publications are the most common form of evidence and provenance metadata provided by curated databases. But Publications are not considered Evidence Items in the SEPIO model, as they are only proxies that point to where actual evidence information is described. 
  
### (6) Shortcut Relations
- **Description:**  Evidence Lines can be directly linked to a supporting Activity or Publication by 'shortcut relations' (dashed lines), enabling description of the provenance of an Evidence Line even when particular Evidence Items are not provided. These relationships can inferred via property chains defined in the SEPIO ontology to enable interoperability of graphs asserting these different patterns (see [5]).


The semantics and structure of the core SEPIO model directly reflect the implicit cognitive tasks that are performed in the process of making evidence-based assertions: (1) the organization of evidence into separate, meaningful arguments; (2) the evaluation of these arguments individually to determine the direction and strength of support they provide for a particular proposition; and (3) the combined assessment of all relevant arguments to make a final assertion expressing belief (or not) in this proposition. SEPIO's organization of metadata around Evidence Lines is critical to representing these perspectives. This enables assessment of the overall **quantity**, **quality**, **diversity**, and **concordance** of evidence for a particular claim - key features that support computational approaches for evidence and provenance-based evaluation [6].

-----

## The SEPIO Framework
SEPIO is an OWL2 ontology developed according to OBO Foundry Principles, and uses the Basic Formal Ontology (BFO) to provide high-level structure. Where possible, it re-uses terms from orthogonal ontologies including the Evidence and Conclusion Ontology (ECO), the Ontology of Biomedical Investigations (OBI), the Information Artifact Ontology (IAO), and the Provenance Ontology (PROV-O).

Development of this core ontology is the first step toward establishing a larger SEPIO Framework comprised of SEPIO-based data models and tools to support implementation of and computation over SEPIO data. The framework will have three components:

1. **Data Models:** A generic semantic data model complemented by 'profiles' that extend the core model to support domain and application- specific use cases.
2. **Supporting Ontologies:** A set of modules from orthogonal ontologies providing standardized terms for the consistent and interoperable collection of semantically enriched metadata.
3. **Supporting Tools:** A suite of tools supporting metadata curation, ontology creation, data integration, and evidence-based evaluation of scientific claims.

Plans for developing such a Framework are further described here [7].

## References

1. Real Data Examples pages
2. ClinGen data example page
3. Community Collaborations and Uses page (and/or ACMG paper)
4. ClinGen page
5. Levels/Shortcuts
6. Evidence Concept page
7. SEPIO Framework page


