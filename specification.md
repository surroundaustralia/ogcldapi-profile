# OGC LD API Specification
This document specifies the rules that [RDF](https://www.w3.org/RDF/) data must adhere to, to be valid according to this profile and thus fit for use with instances of the OGC LD API tool.

This document's persistent identifier is:

* <https://w3id.org/profile/ogcldapi/spec>

## Role
This document is part of the larger OGCLDAPI Profile which contains multiple parts: this specification, validators and so on. The profile is online at:

* <https://w3id.org/profile/ogcldapi>

This document does _not_ profile rules that can be used to validate data. For resources fullfilling that role, see the list of resources in the profile (link above). The validator resources in this profile quote the written rules specificed here in their operations.


## Requirements

The requirements specified by this specification are listed here. The correspond to machine-executable RDF validation tests supplied by this profile in the [Shapes Constraint Language (SHACL)](https://www.w3.org/TR/shacl/).

This specification places requirements on three [OWL](http://www.w3.org/TR/owl2-primer/) classes from two well known ontologies:

* `Dataset` from the [DCAT2](https://www.w3.org/TR/vocab-dcat/) ontology
* `FeatureCollection` & `Feature` from [GeoSPARQL 1.1](https://opengeospatial.github.io/ogc-geosparql/geosparql11/spec.html)

DCAT is identified by the `dcat` prefix and GeoSPARQL by the `geo` prefix.


### For `dcat:Dataset`

* **Requirement D-title****: Each  Dataset _MUST_ have one and only one English title which is an English text literal, indicated using the `dcterms:title` predicate

* **Requirement D-defn**: Each  Dataset _MUST_ have no more than one English definition which is an English text literal, indicated using the `dcterms:description` predicate

* **Requirement D-id**: Each  Dataset _MUST_ have one and only one identifier, an `xsd:token`, indicated using the `dcterms:identifier` predicate. Note: this identifier must be unique within the Dataset it is part of. This uniqueness is not testable in SHACL.

* **Requirement D-part**: If a Dataset has a part, indicated by `dcterms:hasPart`, that part _MUST_ be of type `geo:FeatureCollection`

* **Requirement D-bb**: A Dataset _MAY_ indicate a Bounding Box geometry with a `geo:boundingBox` predicate


### For `geo:FeatureCollection`

* **Requirement FC-title**: Each  Feature Collection _MUST_ have one and only one English title which is an English text literal, indicated using the `dcterms:title` predicate

* **Requirement FC-defn**: Each  Feature Collection _MUST_ have no more than one English definition which is an English text literal, indicated using the `dcterms:description` predicate

* **Requirement FC-id**: Each  Feature Collection _MUST_ have one and only one identifier, an `xsd:token`, indicated using the `dcterms:identifier` predicate. Note: this identifier must be unique within the Dataset it is part of. This uniqueness is not testable in SHACL

* **Requirement FC-part**: Each  Feature Collection _MUST_ indicate that it is part of one and only one `dcat:Dataset` with use of the `dcterms:isPartOf` predicate

* **Requirement FC-part**: If a Feature Collection has a part, indicated by `dcterms:hasPart`, that part _MUST_ be of type `geo:Feature`

* **Requirement FC-bb**: A Feature Collection _MAY_ indicate a Bounding Box geometry with a `geo:boundingBox` predicate


### For `geo:Feature`

* **Requirement F-id**: Each  Feature _MUST_ have one and only one identifier, an `xsd:token`, indicated using the `dcterms:identifier` predicate. Note: this identifier must be unique within the Dataset it is part of. This uniqueness is not testable in SHACL.

* **Requirement F-part**: Each  Feature _MUST_ indicate that it is part of at least one `geo:FeatureCollection` with use of the `dcterms:isPartOf` predicate

* **Requirement F-geometry**: Each  Feature _MUST_ indicate that it has at least one `geo:Geometry` with use of the `geo:hasGeometry` predicate