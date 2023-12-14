# FNS-Harmony

## Summary information
Application ontology for the H2020 FNS-Cloud project (https://www.fns-cloud.eu/)

Current ontology version: 1.3

Ontology PURL: https://purl.org/fns-h
 
Ontology modules
* Microbiome module: https://purl.org/fns-h/microbiome
* Bioactives module: https://purl.org/fns-h/bioactives
* Interventions module: https://purl.org/fns-h/interventions
* Food components module: https://purl.org/fns-h/foodComponents
* CLAS module: https://purl.org/fns-h/CLAS
* GS1 terms module: https://purl.org/fns-h/GS1Terms
* GS1 GPC Food and beverages module: https://purl.org/fns-h/GS1gpc

Food Nutrition Security Cloud (FNS-Cloud) has received funding from the European Union’s Horizon 2020 Research and Innovation programme (H2020-EU.3.2.2.3. – sustainable and competitive agri-food industry) under Grant Agreement No. 863059.

## Background
To provide harmonisation of data within the project as well as to support the development of different software services together with the help of partners involved in the applications and demonstrators, we developed the FNS Harmony Ontology (FNS-H).  The motivation for developing an ontology for harmonisation of data in food, nutrition, and security stems from the urgent need to address complex challenges and foster collaboration in these critical domains. 

An ontology is a structured representation of knowledge that defines and organises the concepts, relationships, and properties within a specific domain. An ontology serves as a standardised framework that enables seamless integration and interpretation of diverse data sources, ranging from agricultural production and food processing to dietary patterns and nutritional outcomes. By establishing a common language and shared understanding, this ontology promotes interoperability, facilitates data exchange, and empowers researchers, policymakers, and stakeholders to gain comprehensive insights into the intricate relationships between food systems, nutrition, and security.

## Ontology design
Ontology design is a crucial aspect of knowledge representation and organisation, aiming to create a structured framework that captures the concepts, relationships, and properties within a specific domain. Developing ontologies from scratch can be time-consuming and resource-intensive. Hence, the importance of reusing already developed resources becomes evident. By leveraging existing ontologies and reusing well-established concepts and relationships, researchers and practitioners can save valuable time, effort, and resources. Reuse enables the integration of knowledge from multiple domains, promotes interoperability, and facilitates data sharing and collaboration across different disciplines. Moreover, it fosters consistency, standardisation, and semantic clarity, ensuring that information is accurately interpreted and effectively communicated.

In the development of FNS-H, we aimed at reusing and linking to already established reference ontologies that tackle the domains of food, nutrition and security from different viewpoints and are needed by the different services or applications. These include the following popular ontologies: OBI (Ontology of biomedical investigations), DOID (Human Disease ontology), ONS (Ontology for Nutritional Studies), UO (Units of measurements ontology), ENVO (The environment ontology), UBERON (Uber-anatomy ontology), ChEBI (Chemical Entities of Biological Interest) and others. In the cases where existing terms were not defined in other ontologies or the definition of terms were not adequate for our use cases, we defined the term directly in our ontology.

In FNS-H, we used the MIREOT principle when reusing terms from other ontologies. Extracting external ontology terms with the MIREOT (Minimum Information to Reference an External Ontology Term) principle involves selectively importing or referencing relevant terms from external ontologies into a target ontology. The MIREOT principle aims to avoid unnecessary duplication of terms and ensure a modular and interoperable ontology design. By following this principle, ontology developers can extract only the necessary subset of terms from external ontologies that are required to describe specific domain concepts in the target ontology.
One of the most important aspects to consider when defining terms in an ontology is to establish a format for the identification of each new term. Term identifiers in ontologies are unique identifiers assigned to individual terms or concepts within the ontology. These identifiers serve as stable references to ensure consistency, precision, and interoperability in knowledge representation. Best practices for term identifiers include using globally unique identifiers (such as URIs) to avoid conflicts with other ontologies or vocabularies. The identifiers should be persistent, meaning they remain unchanged even if the term's label or definition is modified.
For the FNS-H each term has been identified with:
*	Unique ID in form of an IRI (Internationalized Resource Identifier), composed of the base ontology IRI (http://www.fns-cloud.eu/) and term ID composed of the prefix FNS_H and a ten digits number; and
*	Term label, which is the language-based representation of the term understandable by humans. 

In order to provide more information about the represented terms in the ontology, we reused metadata annotation properties defined by the Dublin Core metadata standards (https://www.dublincore.org/) as well as ontology metadata defined by the OBO foundry (https://github.com/information-artifact-ontology/ontology-metadata). Annotation properties in ontologies are used to annotate metadata about terms, providing additional descriptive information that helps to enrich their meaning and context. These properties serve as a means to add informative annotations that are not directly related to the formal semantics of the ontology but are valuable for documentation, interpretation, and discovery purposes. Annotation properties can be used to provide textual definitions, synonyms, examples, version information, authors, and other relevant metadata about terms.

## Ontology structure
The development of the FNS-Harmony ontology started with the need of standardisation across different databases that contain microbiome datasets. The idea was to harmonise the metadata about microbiome studies in order to enable meta-analysis as well as allow researchers to enhance the metadata about their studies. This conceptualisation formed the first ontology module. Further on in the ontology development, we also included other ontology modules. Ontology modularisation brings numerous benefits that make it highly advantageous in knowledge representation and management. Firstly, modularisation allows for the decomposition of complex ontologies into smaller, more manageable parts. Furthermore, ontology modularisation promotes reusability by creating a repository of standardised, self-contained modules that can be easily shared and integrated into different applications and domains. Another advantage of ontology modularisation is its ability to enhance scalability and performance.

The current development version of FNS-Harmony is composed of six modules. Each model contains the conceptualisation of a certain part of the food, nutrition and security domain. The ontology modules can be used separately or combined depending on the use-case needs. Here we briefly describe the different modules.

### Microbiome data module
In the initial phase, we started with a collection of metadata terms from ENA database checklists (https://www.ebi.ac.uk/ena/browser/checklists). For the representation of the metadata terms, we imported and mapped to terms from existing ontologies. If a term does not exist in any relevant external ontology, we modelled it inside FNS-Harmony. This ontology module was used by ScaleFocus as a base for the metadata submission form and service that was designed to support study metadata enrichment.

The core FNS-Harmony entities in this module are study, sample, attribute, experiment and run. Supporting entities are platform, file, spot descriptor and resource reference. we represent the different biological metadata that characterise the samples. In addition, we represent the different biological metadata that characterize the samples. This is done by employing the attribute class. FNS-Harmony includes several different types of attributes: general sample attributes, host sample attributes, material sample attributes, sampling attributes and sequencing sample attributes. It is important to note that the list of attributes can be easily extended with new attributes.

To have reusable and interoperable metadata we align the FNS attribute terms to terms from state-of-the-art domain ontologies. Currently, this module imports terms from OBI (Ontology of biomedical investigations), DOID (Human Disease ontology), ONS (Ontology for Nutritional Studies), UO (Units of measurements ontology), ENVO (The environment ontology), and UBERON (Uber-anatomy ontology). 

### Food components module
The food components module contains conceptualisation and taxonomy of food components that are standardised according to EuroFIR. Each food component contains a mapping to the appropriate EuroFIR code, has component names in English and Slovenian, has label mappings to different national food components databases (France, UK, Australia, Danmark, Netherlands and US). In addition, we also represented the taxonomy of food components. For some food components, we also provide a mapping to the ChEBI ontology using the ChEBI ID. The first level of the taxonomy distinguishes between ten major categories, which include:
* Carbohydrate components;
* Food additives;
* Food properties and measures;
*	Lipid components;
* Minerals and inorganic components;
* Nitrogen components;
* Organic acids;
* Phenolic components;
* Proximates; and
* Vitamins.

### Bioactives module
The bioactives module contains representations of different groups of bioactive components that are especially important for the project demonstrators. The bioactive components were extracted from the e-BASIS (Bioactive Substances in Food Information Systems) EuroFIR (https://www.eurofir.org/our-tools/ebasis/) resource. For terms representing bioactive components, we provide a mapping to adequate ChEBI terms where available. The terms are organised in five major groups:
*	Polyphenols;
*	Sulphur compounds;
*	Phytosterols;
*	Antioxidant compound group; and
*	Others.

### Dietary interventions module
The dietary intervention module contains terms that denote different dietary interventions that are used in nutritional intervention studies. For this purpose, we extracted a list of interventions from studies represented in the Phenotype Database  (dBNP). The preliminary list from dBNP was cleaned from ambiguous entries and duplicates were removed. Where possible, we provide mappings of intervention terms from other ontologies. The terms in this module are used by ScaleFocus in the metadata submission form.

### Branded food module

The branded food module contains the initial conceptualisation of branded food products. The conceptualisation is based on the processes of collecting and organising data about branded food products such as the CLAS database (Composition and Labelling Information System) (https://www.frontiersin.org/articles/10.3389/fnut.2021.798576/full), developed by the project partner NUTRIS. We believe that this ontology module has large potential for further development and consequently to be reused by various institutions and companies working with such data. 

### Product identifiers module
The product identifiers module contains the conceptualisation of the different GS1 identifiers (https://www.gs1.org/) which are used for identification of products. Here, in collaboration with the project partner GS1 Slovenia we performed initial conceptualisation of the different identifiers such as GTIN (GTIN8, GTIN12, GTIN13), and others. We also represented part of the Global Product Classification (GPC) that contains the Food/Beverage/Tobacco segment in an ontological form. We believe that this module can be used together with the branded food module to provide more in-depth representation of branded food products and their characteristics.

## Ontology Versions and Implementation
The FNS-H ontology has been developed by using the Protégé ontology editor (https://protege.stanford.edu/). Classes from external ontologies were extracted using the OntoFox tool (https://ontofox.hegroup.org/) using the MIREOT principle (Minimal Informa). For the transformation of information from spreadsheets to ontology, we used the Celfie plug-in for Protégé (https://github.com/protegeproject/cellfie-plugin) as well as the ROBOT OBO tool (http://robot.obolibrary.org/). The ontology is expressed in the OWL2 language (https://www.w3.org/TR/owl2-overview/), which is a standard language for knowledge representation recommended by the W3C (https://www.w3.org/).

The ontology has been released in three versions (1.0, 1.1 and 1.2) and the final version 1.3 will be released before the project ends. Versions 1.0 – 1.2 are focused mostly on the microbiome use case, while version 1.3 contains also other modules: food components, bio-actives, dietary intervention, branded food and product identifiers.

##	Availability
The developed ontology is available via several sources:
*	GitHub repository: https://github.com/panovp/FNS-Harmony
*	Ontology PURL: https://purl.org/fns-h
*	BioPortal Ontology Repository: https://bioportal.bioontology.org/ontologies/FNS-H

The GitHub repository contains the raw ontology source files and allows collaborative development of the ontology. The repository contains all released versions of the ontology. In addition, the git repository contains an issue tracker where collaborators can post requests for new terms to be added to the ontology as well as to post questions and open discussion points. The ontology permanent identifier PURL uses https://purl.archive.org/ service to always resolve and redirect to the last published version of the ontology. This PURL can be used from any ontology editor to directly load, explore and use the last version of the ontology. Finally, the ontology is also indexed and available through the BioPortal ontology repository (https://bioportal.bioontology.org/) which is one of the largest repositories of ontologies for the domain of biomedicine and wider. With this we are increasing the possibility of potential users to find the ontology and reuse it for their use cases.

