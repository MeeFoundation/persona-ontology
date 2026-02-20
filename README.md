# persona-ontology

The persona ontology is an application profile over existing OWL ontologies. It models the domain of natural people in the Mee Identity Agent. It documents in SHACL which classes and properties from other ontologies are used to describe a person. 

## Purpose

It defines a formal, machine-readable model of a real-world person's identity data — names, addresses, phone numbers, SSNs, height, email, etc. — by reusing and constraining existing well-known ontologies rather than inventing new ones.

## Key components

- **`persona.ttl`** — The core ontology file. It imports the IEEE Person Ontology (PO) and serves as the entry point.

- **`persona-shacl.ttl`** — SHACL (Shapes Constraint Language) rules that define *which* classes and properties are valid and *how* data must be structured. For example:
  - A `Person` must have designators (name, SSN, phone, email, address)
  - A `PersonName` must have at least one `GivenName` and exactly one `FamilyName`
  - An `SSN` must match the pattern `\d{3}-\d{2}-\d{4}`
  - A `TemporalRegion` must have a start date

- **`example.ttl`** — A concrete RDF instance of a person ("Margery Elizabeth Trevithick", who goes by "Elizabeth Trevithick") showing how the ontology is used in practice, with her name, SSN, phone, email, home address, height, and address tenure.

- **`Person-Ontology-dev.ttl`** — A local copy of the upstream IEEE Person Ontology.

## Ontologies used

| Prefix | Namespace                                                | Notes                         | Local file with link to source                                                                                                                                                     |
|--------|----------------------------------------------------------|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| bfo    | http://purl.obolibrary.org/obo/BFO_                      | Basic Formal Ontology         | |
| cco    | http://www.ontologyrepository.com/CommonCoreOntologies/  | Common Core Ontologies        | | 
| uo     | http://purl.obolibrary.org/obo/UO_                       | Units Ontology                | |
| po     | https://purl.org/efo/domains/PersonOntology              | Person Ontology               | [PersonOntology-dev.ttl](https://opensource.ieee.org/po/person-ontology-project/-/raw/master/dev/Person-Ontology-dev.ttl?ref_type=heads)                                     |
| iao    | http://purl.obolibrary.org/obo/IAO_                      | Information Artifact Ontology | | 
| dct    | http://purl.org/dc/terms/                                | Metadata only                 | | 
| sh     | http://www.w3.org/ns/schacl#                             | Metadata only                 | | 
| p      | http://www.mee.foundation/ontologies/persona#            | Not yet used                  | [persona.ttl](https://raw.githubusercontent.com/MeeFoundation/persona-ontology/refs/heads/main/persona.ttl)                                                                  | 
   
