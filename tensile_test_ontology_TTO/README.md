# Tensile Test Ontology (TTO)

This repository comprises supplementary information on the tensile test ontology (TTO) that was developed within the frame of the joint project 
Platform MaterialDigital (PMD): [PMD website](https://materialdigital.de/). 
It is designed as a module of the PMD Core Ontology (PMDco) and therefore, part of the [PMDco repository](https://github.com/materialdigital/core-ontology/tree/main). 
However, some information on the TTO is also given in this [PMD application ontology (PMDao) repository](https://github.com/materialdigital/application-ontologies/tree/main/tensile_test_ontology_TTO).

<!-- TOC -->
1. [Abstract](#Abstract)
2. [Documents | Links](#Documents-|-Links)
3. [Documentation](#Documentation)
   1. [Ontology Development Steps](#Ontology-Development-Steps)
   2. [Design Principles | Decision log](#Design-Principles-|-Decision-log)
      1. [Fundamentals](#Fundamentals)
      2. [Case decisions | Specific issues](#Case-decisions-|-Specific-issues)
      3. [Namespaces](#Namespaces)
<!-- TOC -->

## Abstract
This document is supposed to provide general information on the development of an 
ontology in the field of materials sciences and engineering (MSE) that was 
realized within [PMD](https://materialdigital.de) as a first best practice example. 
Accordingly, it is supposed to give specifically documentation on the development of the tensile test ontology (TTO). 
Hence, besides its informative character, this document may allow the 
developers to explain, register and secure distinct decisions made during 
the ontology development process. As such, it serves as a kind of log book.

The material's characterization process of the tensile test on 
metallic materials at room temperature (henceforth simply referred 
to as 'tensile test') was semantically described in accordance with the 
standard DIN EN ISO 6892-1:2019-11. In particular, terms, definitions and 
symbols given in the standard are used in the TTO. Furthermore, a 'preferable data structure' (cf. section [Documents | Links](#Documents-|-Links)) in terms of the categorization
of typical data resulting from a tensile test was developed in an ad-hoc group formed by experts of the DIN standardization
committee being in charge of the corresponding DIN EN ISO 6892-1. This data structure depicts the MSE experts' view on how tensile
test data is supposed to be categorized and, in particular, which data may be recorded and provided by test operators 
to obtain a comprehensive tensile test dataset.


The resulting [TTO](https://github.com/materialdigital/application-ontologies/blob/main/tensile_test_ontology_TTO/pmdao_TTO.ttl) is supposed to be publicly available on the 
[PMD website](https://materialdigital.de/download/) (download section, available after free registration), the PMD GitHub repositories of the [PMD Core Ontology](https://github.com/materialdigital/core-ontology/tree/main) and [PMD application ontologies](https://github.com/materialdigital/application-ontologies/tree/main/tensile_test_ontology_TTO) 
as well as on [MatPortal.org](https://matportal.org/ontologies). 
An HTML documentation of the TTO that was auto-generated using pyLODE ([online tool](http://pylode.surroundaustralia.com/)) 
can be found at the gh-pages: [TTO pyLODE documentation](https://markusschilling.github.io/application-ontologies/).

Moreover, an [exemplary TTL file](https://github.com/materialdigital/application-ontologies/blob/main/tensile_test_ontology_TTO/pmdao_TTO_data_mapping_example.ttl) is given in this repository which resulted from data mapping of typical
tensile test data that was published on an open access [Zenodo repository](https://zenodo.org/record/6778336)
to the TTO. 
As it is the case for the plain TTO, an HTML documentation of the TTO mapped with exemplary data 
that was auto-generated using pyLODE ([online tool](http://pylode.surroundaustralia.com/)) can be found at this gh-pages: [TTO data mapped pyLODE documentation](https://markusschilling.github.io/application-ontologies/index-mapped).

The TTO was strongly designed on the basis of the PMD Core Ontology ([PMDco](https://github.com/materialdigital/core-ontology)). 
Accordingly, PMDco concepts are re-used. Thus, the TTO is contained in its entirety in PMDco (being an importable module of PMDco), since the consideration of 
the tensile test was used as a first example to define classic concepts from the field of materials sciences and engineering (MSE).
As a result, TTO concepts are all referring to the PMDco namespace (cf. [Namespaces](#Namespaces)).

Moreover, PMDco is connected to other (higher-level) ontologies (cf. section [Documents | Links](#Documents-|-Links)).
Therefore, a consideration of the PMDco and its documentation is recommended.

*Furthermore, there is an earlier version of the TTO that was developed as first
approach to provide an example for the creation of an application ontology.
The result of this development is also given in this repository in a separate
branch ([TTO_0.1](https://github.com/materialdigital/application-ontologies/tree/main/tensile_test_ontology_TTO)).* 

## Documents | Links
In this section, some documents and tools are listed (and linked, if applicable) that 
supported the ontology creation or provide some additional information.

+ [Repository of TTO](https://github.com/materialdigital/application-ontologies/tree/main/tensile_test_ontology_TTO) | Files will be stored here, e.g., TTL file of TTO or exemplary RDF files
+ [Tensile Test Ontology (TTO) module](https://github.com/materialdigital/application-ontologies/blob/main/tensile_test_ontology_TTO/pmdao_TTO.ttl) | TTL file of the TTO in PMDco repository
+ [TTO pyLODE documentation](https://markusschilling.github.io/application-ontologies/) | A documentation of the TTO auto-generated by pyLODE
+ [Standard ISO 6892-1:2019-11](https://www.beuth.de/de/norm/iso-6892-1/316885984) | The ISO standard the TTO development is based on
+ [Visualization of preferable tensile test data structure](https://github.com/materialdigital/application-ontologies/blob/main/tensile_test_ontology_TTO/Tensile_Test_Data_Structure_DIN_ad-hoc.pdf) | Visualization of a preferable tensile test data structure, which is the result of an ad-hoc group of the DIN EN ISO 6892-1 standardization committee; basis for TTO development
+ [PMD Core Ontology (PMDco)](https://github.com/materialdigital/core-ontology) | The mid-level ontology in the field of materials sciences and engineering (MSE) the TTO is based on
+ [Ontopanel tool](https://yuechenbam.github.io/src/main/webapp/index.html) | A tool created for domain experts based on [diagrams.net](https://www.diagrams.net/) that facilitates visual ontology development and mapping for FAIR data sharing in materials testing (more information in open access [scientific paper](https://link.springer.com/article/10.1007/s40192-022-00279-y))
+ [Protégé tool](https://protege.stanford.edu/) | A tool used for the creation of ontologies; especially, annotations and relations were included in the ontology by applying the Protégé tool
+ [Tensile Test Ontology (TTO) data mapping example](https://github.com/materialdigital/application-ontologies/blob/main/tensile_test_ontology_TTO/pmd_tto_data_mapping_example.ttl) | An example on how a TTL file may look like after actual tensile test data was mapped to TTO
+ [TTO data mapped pyLODE documentation](https://markusschilling.github.io/application-ontologies/index-mapped) | A documentation of the TTO mapped with tensile test data auto-generated by pyLODE
+ [Zenodo repository for tensile test data](https://zenodo.org/record/6778336) | In this open access Zenodo repository, typical tensile test data can be found which may be used for digitalization efforts 

Furthermore, other (higher-level) ontologies are used in TTO since their 
concepts are partly included in PMDco. Such are
+ Basic Formal Ontology ([BFO](https://basic-formal-ontology.org/)),
+ The PROV Ontology ([PROV-O](https://www.w3.org/TR/prov-o/)),
+ European Materials Modelling Ontology ([EMMO](https://github.com/emmo-repo/EMMO)),
+ Chemical Entities of Biological Interest Ontology ([ChEBI](https://www.ebi.ac.uk/chebi/)). 
+ Quantities, Units, Dimensions, and Types Ontology ([QUDT](https://qudt.org/))



## Documentation
This section provides information on the TTO development process and fundamental
design principles used in TTO. Most basic design principles are already given
in the PMDco the TTO is based on.

### Ontology Development Steps
During the development of TTO, the following steps were taken:
1. Usage of all necessary and supporting information, e.g., ISO standard(s) and preferable data structure(s) created therefrom
2. Creation of concepts and plausible relations (T-Box) between them on a visual basis using Ontopanel tool (possibility to use direct conversion) or a concept board (conversion needs to be done with an appropriate tool) 
3. Conversion into OWL / TTL by using the built-in conversion plugin of Ontopanel or Protégé
4. Annotation and curation of concepts using Protégé tool, including definitions of concepts, classes, object properties, entities using annotation functionality and adding relations between concepts
5. Verification in Protégé (as appropriate, by using reasoning)

Since the development of ontologies is an iterative process that might 
include both, the possibility and the demand to adjust and extend the 
ontology, the development steps presented above are also iterative and were 
used in repeated sequence. In particular, steps 2 and 3 were repeated 
numerously after findings in step 5 and also possible changes concerning 
implemented content. Likewise, steps 4 and 5 were repeatedly taken when new 
relations between concepts were introduced.

### Design Principles | Decision log
In this section, **design principles** used to model the TTO and, 
especially, underlying modelling decisions are logged and explained with 
a focus on modelling goals.

#### Fundamentals
Some basic ideas and conceptual approaches that were kept in mind when creating TTO are given in note form (most ideas also affected PMDco creation and are therefore also realized in PMDco):
+ include many classes that allow interconnection / interoperability / reuse
+ object properties defined are condensed to a lower number to reach clarity (re-use generic object properties partly given in higher-level ontologies as much as possible)
+ re-usage of known and well-established concepts / schema is preferred (usage of higher-level ontologies), such as in the field of datatype definitions
+ including labels using *rdfs:label*, *skos:preflabel*, *skos:altlabel* and definitions as *skos:definition* (using Protégé tool) for human readability
+ if applicable, usage examples are provided via *skos:example*
+ MSE (domain) knowledge is included in class definitions - by including human-readable definitions given in natural-language (using skos:definition) as well as by implementing class relations
+ human-readable identifiers for better understanding - labels as well as class / object property designation lead to enhanced query-ability 
+ PMDco (core ontology = mid-level ontology) is used as basis for ontology development, i.e. basic classes and properties, which are partly related to higher-level ontologies, are frequently used

#### Case decisions | Specific issues

| Aim / modelling goal                                                                                                                                                        | Decision / modelling approach                                                                                                               | Remarks / Explanation                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Integration of generic terms and definitions from the field of MSE                                                                                                          | Usage of higher-level ontologies, if possible; add own definitions.                                                                         | Since basic MSE concepts are to be included, concepts already given in other ontologies are used to avoid doubled work. If there are no concepts that fit the specific need, such are simply created.                                                                                                                                     |
| Include concepts of (characteristic) parameters to the characterization method description. Q: Where to put such parameters conceptually - to TT process or the test piece? | Due to the general modelling approach using the mid-level ontology PMDco, such parameters are connected as 'characteristic' to the process. | In general, this modelling is process-centered as the ontology is supposed to focus the tensile test process and respective data originating therefrom. Therefore, especially, characteristic values are semantically connected to the process. Data distinctly referring to the test piece are connected to the test piece, accordingly. |
| Include expressivity for the description of the material used, e.g., 'steel'.                                                                                               | The possibility to name the material used was inherited from the PMDco using the class *'MaterialDesignation'*                              | The material tested in a tensile test has to be named, for sure. This is possible using the *'MaterialDesignation'* class. Some more expressivity can be included by using the classes given by PMDco to describe chemical compositions.                                                                                                  |

#### Axioms

To achieve more expressivity, some logic relations and interdependencies between concepts created were asserted.
Some of these are given in the following table.

| Axiom                                                                                                              | Description                                                                                                                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| :relatesToExtension some ('has value' value 0.1f)                                                                  | **_Rp0.1_** depends on the value of the _Percentage Extension_, which has to be exactly 0.1%.                                                                                                                                                                                           |
| :relatesToExtension some ('has value' value 0.2f)                                                                  | **_Rp0.2_** depends on the value of the _Percentage Extension_, which has to be exactly 0.2%.                                                                                                                                                                                           |
| :relatesTo some :PercentageExtension                                                                               | **_Proof Strength Total Extension_** depends on _Percentage Extension_. It has to be the value of the stress measured at the highest measured percentage extension value.                                                                                                               |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Elongation_** refers to _Original Gauge Length_, because it is measured as the elongation of the original gauge length in mm.                                                                                                                                                        |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Percentage Elongation_** refers to _Original Gauge Length_, because it is measured as the elongation of the original gauge length in %.                                                                                                                                              |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Percentage Permanent Elongation_** relates to _Original Gauge Length_, because it is measured as the elongation of the original gauge length in %.                                                                                                                                   |
| :relatesTo some :ExtensometerGaugeLength                                                                           | **_Percentage Extension_** refers to _Extensometer Gauge Length_, because it is measured in reference to the extensometer gauge length.                                                                                                                                                 |
| (:relatesTo some :Stress) and (:relatesTo some :MaximumForce)                                                      | **_Tensile Strength_** relates to the _Stress_ measured at _Maximum Force_.                                                                                                                                                                                                             |
| :relatesTo some :Stress                                                                                            | **_Yield Strength_** relates to _Stress_ because it is measured in reference to a specific stress value.                                                                                                                                                                                |
| :relatesTo some :Stress                                                                                            | **_Lower Yield Strength_** relates to _Stress_ because it is measured in reference to a specific stress value.                                                                                                                                                                          |
| :relatesTo some :Stress                                                                                            | **_Upper Yield Strength_** relates to _Stress_ because it is measured in reference to a specific stress value.                                                                                                                                                                          |
| (:relatesTo some :OriginalDiameter) or ((:relatesTo some :OriginalThickness) and (:relatesTo some :OriginalWidth)) | **_Percentage Reduction of Area_** relates to the _Cross-sectional Area_ of the test piece which is defined by the test piece dimensions such as diameter, thickness, and width, depending on test piece type                                                                           |
| :relatesTo some :ExtensometerGaugeLength                                                                           | **_Percentage Extension_** relates to the _Extensometer Gauge Length_ because the extension is expressed as a percentage value referring to the extensometer gauge length                                                                                                               |
| :relatesTo some :ExtensometerGaugeLength                                                                           | **_Percentage Permanent Extension_** relates to the _Extensometer Gauge Length_ because the extension is expressed as a percentage value referring to the extensometer gauge length                                                                                                     |
| (:relatesTo some :ExtensometerGaugeLength) and (:relatesTo some :MaximumForce)                                     | **_Percentage Plastic Extension at Maximum Force_** related to the _Extensometer Gauge Length_ (equivalent to 'percentage extension') and the maximum force because it is the plastic proportion of the percentage extension value measured at maximum force                            |
| (:relatesTo some :ExtensometerGaugeLength) and (:relatesTo some :MaximumForce)                                     | **_Percentage Total Extension at Maximum Force_** related to the _Extensometer Gauge Length_ (equivalent to 'percentage extension') and the maximum force because it is the total percentage extension value measured at maximum force                                                  |
| :relatesTo some :ExtensometerGaugeLength                                                                           | **_Extension_** relates to the _Extensometer Gauge Length_ because the extension is measured referring to the extensometer gauge length                                                                                                                                                 |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Elongation_** relates to the _Original Gauge Length_ because the elongation is measured referring to the original gauge length                                                                                                                                                       |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Percentage Elongation_** relates to the _Original Gauge Length_ because the elongation is measured as a percentage value referring to the original gauge length                                                                                                                      |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Percentage Elongation after fracture_** relates to the _Original Gauge Length_ because the elongation is measured as a percentage value referring to the original gauge length, however, the moment of fracture is not further defined as a concept and depends on the test operator |
| :relatesTo some :OriginalGaugeLength                                                                               | **_Percentage Permanent Elongation_** relates to the _Original Gauge Length_ because it describes the increase in the original gauge length of a test piece after removal of a specified stress, expressed as a percentage of the original gauge length                                 |
| :participant some :TestPiece AND :participant some :TensileTestingMachine                                          | **_Tensile Test_** (process) has to have the participants (tensile) _Test Piece_ and _Tensile Testing Machine_; without these participants, no tensile tests can be performed                                                                                                           |

#### Namespaces
In this section, the namespaces used in TTO are listed. These can also be found in the [pmd_tto.ttl file](https://github.com/materialdigital/core-ontology/blob/main/pmd_tto.ttl).
Since TTO is a module of the PMDco, PMDco namespace (https://w3id.org/pmd/co/) is used for ontological concepts.
The base of the TTO itself (IRI of the ontology) is https://w3id.org/pmd/tto. 

| Prefix | Namespace / URI                             |
|:-------|---------------------------------------------|
| :      | https://w3id.org/pmd/co/                    |
| owl    | http://www.w3.org/2002/07/owl#              |
| rdf    | http://www.w3.org/1999/02/22-rdf-syntax-ns# |
| xml    | http://www.w3.org/XML/1998/namespace        |
| xsd    | http://www.w3.org/2001/XMLSchema#           |
| rdfs   | http://www.w3.org/2000/01/rdf-schema#       |
| base   | https://w3id.org/pmd/tto                    |