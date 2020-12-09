# OBO Foundry Principles

## Openness (principle 1): 

The ontology MUST be openly available to be used by all without any constraint other than (a) its origin must be acknowledged and (b) it is not to be altered and subsequently redistributed in altered form under the original name or with the same identifiers. OBO Foundry ontologies are resources for the entire biological and biomedical community. Furthermore, in order to realize the OBO Foundry vision of a suite of interoperable ontologies, ontology developers must be free to re-use terms from any OBO Foundry ontology. For these reasons, the ontologies must be available to all without any constraint on their use or redistribution. Nonetheless, it is proper that their original source is always credited and that after any external alterations, ontologies must never be redistributed under the same name or with the same identifiers.
Recommendations: For ontology providers: OBO Foundry Ontologies MUST EITHER be released under a Creative Commons CC-BY license version 3.0 or later, OR released into the public domain under CC0 (which is not a license). Regardless of which is chosen, it should be clearly stated in the ontology file.
Note: CC-BY licenses allow others to distribute, remix, tweak, and build upon the work, even commercially, as long as they credit the creators for the original creation. CC0 specifies that the creators of an ontology waive, to the extent that they legally can be, all rights and place the ontology in the public domain. It does not prevent them from requesting that the ontology be properly credited and cited, but prevents any legal recourse if it is not credited. Many pros and cons of CC-BY versus CC0 are laid out in this discussion. It is important to note that one can move from CC-BY to CC0 but not the other way around.

### For ontology re-use:

The original source of an ontology must be credited according to the terms specified in the comment annotation of the ontology.
Altered versions of an ontology that are not part of an official release (that is, by the ontology developers) must not be redistributed under the same name or with the same ontology IRI.
If an individual term is reused without change to the definition, the original term IRI should be used. If the definition of a term (either text or logical) is changed, the original term IRI should not be reused. Suggestions for changes or improvements to term definitions should be submitted to the appropriate ontology issue tracker.
Regardless of which license an ontology uses, we strongly request and recommend that any reuse of an ontology attributes the source in accordance with scientific norms and the OBO Citation and Attribution Policy.

### For Ontology Providers: 

1. .owl files
OBO Foundry Ontologies MUST specify the reuse constraints using the following annotations in any publically released OWL version of the ontology:
dcterms:license - specifies the license - see Example 1 (below)
rdfs:comment - specifies terms of reuse - see Example 1 (below)
OBO Foundry Ontologies that host terms developed by an external group (but which are not part of an existing ontology) must credit the external group - see Examples (below)
See below under ontology re-use for guidelines on importing individual terms from external ontologies.

2. .obo files
OBO Foundry Ontologies must specify the reuse constraints using the following annotations in any publically released OBO version of the ontology:
the license in a separate property annotation, which can be converted to a dc:license statement if the ontology is converted to OWL - see Example 2 (below)
the reuse constraints using a comment in the official OBO version of the ontology - see Example 2 (below)

### For Ontology re-use:

The attribution method for individual terms reused in another ontology (e.g., by MIREOT) is via use of their original IRI or ID - see Examples (below).

1. In OWL - Any ontology re-using individual terms from another ontology should:
re-use the original term IRI (which for OBO Foundry ontologies is generally in the form of an OBO Foundry PURL)
use an IAO:imported from annotation http://purl.obolibrary.org/obo/IAO_0000412 on each imported term to link back to the group (i.e. ontology) maintaining it, where more information would be available about the license
include any annotations for term or definition editors from the original ontology

2. In OBO - Any ontology re-using individual terms from another ontology should:
re-use the original term ID (of the form <GO:0000001>)
include any XREFs to the original term editor(s) from the original ontology

### Full ontologies:

The attribution method for importing an entire ontology in OWL is simply to import the ontology without modification. The attribution method for using an ontology for an analysis is to cite the ontology as requested by the ontology developers. If the developers have not specified how to cite their ontology, use the ontology IRI, a publication if available, and the ontology website if available. 

## Common Format (principle 2):

The ontology is made available in a common formal language in an accepted concrete syntax. A common format allows the maximum number of people to access and reuse an ontology. Here there is a distinction between how an ontology is developed and how it is presented for release. Developers are free to use whatever combination of technologies and formats is appropriate for development. However, the official owl PURL for the ontology must resolve to a syntactically valid OWL file in an RDF in RDF-XML syntax.
Note: some groups publish an .obo version, and the OBO Foundry pipeline takes care of making the valid .owl file. See the FAQ for details. You may also submit the ontology for review as OBO. Note also that previously the recommendation was that ontologies may be available in Manchester syntax or OWL-XML, but since has been revised in order to make the official OWL release consumable by a wider variety of tools.
Criteria for review: The ontology is available in at least one of the following formats: OBO Format, OWL or OWL2 RDF/XML.

## URI/Identifier Space (principle 3): 

Each class and relation (property) in the ontology must have a unique URI identifier. The URI should be constructed from a base URI, a prefix that is unique within the Foundry (e.g. GO, CHEBI, CL) and a local identifier (e.g. 0000001). The local identifier should not consist of labels or mnemonics meaningful to humans. Additional information is available at http://www.obofoundry.org/id-policy
The ID-space / prefix must be registered with the OBO library in advance.
OBO-Format Ontologies: If the source ontology is in OBO-Format, then this is automatically satisfied so long as all IDs are of the form <IDSPACE> : <NUMBER>

## Versioning (principle 4):

The ontology provider has documented procedures for versioning the ontology, and different versions of the ontology are marked, stored, and officially released. OBO projects share their ontologies using files in OWL or OBO format (see OBO Principle 2). Ontologies are expected to change over time as they are developed and refined (see OBO Principle 16 on maintenance). This will lead to a series of different files. Consumers of ontologies must be able to specify exactly which ontology files they used to encode their data or build their applications, and be able to retrieve unaltered copies of those files in perpetuity. Note that this applies only to those versions which have been officially released.
Each official release MUST have a unique version identifier. Version identifiers for the ontology artifacts themselves may be of the form “YYYY-MM-DD” (that is, a date), or use a numbering system (such as semantic versioning, i.e, of the form “NN.n”), but in any case each MUST associate with a distinct official release. The date versioning system is preferred, as it meshes with the requirement that version IRIs be specified using dated PURLs (see below).
All OBO projects MUST also have PURLs that resolve to specific official releases of their ontology, in perpetuity. If the files are moved, the PURL MUST be updated to resolve to the new location. Consumers can then use the version IRI to uniquely identify which official release of the ontology they used, and to retrieve unaltered copies of the file(s). Note that the content of official release files MUST NOT be changed. For example, if a bug is found in some official released file for some ontology, the bug MUST NOT be fixed by changing the file(s) for that official release. Instead the bug fixes should be included in a new official release, with new files, and consumers can switch to the new release. If terms are imported from an external ontology, the “IAO:imported from” annotation (see Principle 1) may specify a dated version of the ontology from which they are imported.
Regardless of the versioning system used for the ontology artifact, the version IRI SHOULD use an ISO-8601 dated PURL. In cases where there are multiple releases on the same day, the PURL points to the newest, and the previous release stays in the same folder or a subfolder, named in such a way as to distinguish the releases. Specifications for version IRIs are fully described in the OBO Foundry ID policy document. In short:
For a given version of an ontology, the ontology should be accessible at the following URL, where ‘idspace’ is replaced by the IDSPACE in lower case:

OWL: http://purl.obolibrary.org/obo/idspace/YYYY-MM-DD/idspace.owl
OBO: http://purl.obolibrary.org/obo/idspace/YYYY-MM-DD/idspace.obo
For example, for the version of OBI released 2009-11-06, the OWL document is accessible at http://purl.obolibrary.org/obo/obi/2009-11-06/obi.owl.

An accepted alternative to the above scheme is to include /releases/ in the PURL, as follows:

OWL: http://purl.obolibrary.org/obo/idspace/releases/YYYY-MM-DD/idspace.owl
OBO: http://purl.obolibrary.org/obo/idspace/releases/YYYY-MM-DD/idspace.obo
Examples
For an OBO format ontology use the metadata tag:

data-version: 2015-03-31
data-version: 44.0
For an OWL format ontology, owl:versionInfo identifies the version and versionIRI identifies the resource:

<owl:versionInfo rdf:datatype="http://www.w3.org/2001/XMLSchema#string">2014-12-03</owl:versionInfo>
<owl:versionIRI rdf:resource="http://purl.obolibrary.org/obo/obi/2014-12-03/obi.owl"/>

## Scope (principle 5):

The scope of an ontology is the extent of the domain or subject matter it intends to cover. The ontology must have a clearly specified scope and content that adheres to that scope. An in-scope ontology prevents overlaps between ontologies (duplication of terms), facilitates user searches for specific content, and enables quick selection of ontologies of interest, yet still allows for new terms to be created via combination of existing terms (cross-products).
The domain (scope) covered by the ontology should be clearly stated. The statement should be brief and free of jargon; a few sentences should suffice. The content of the ontology should stay within the confines of the stated scope. Ideally the scope should be fairly narrow. Required terms that are out of scope should be imported from the appropriate ontology.

## Textual Definitions (principle 6):

The ontology has textual definitions for the majority of its classes and for top level terms in particular. A textual definition provides a human-readable understanding about what is a member of the associated class. Textual definitions MUST be unique within an ontology (i.e. no two terms should share a definition). Textual definitions SHOULD follow Aristotelian form (e.g. “a B that Cs” where B is the parent and C is the differentia), where this is practical. For terms lacking textual definitions, there should be evidence of implementation of a strategy to provide definitions for all remaining undefined terms. In lieu of textual definitions, there can be elucidations when the term can not be rigorously defined.
Terms often benefit from examples of usage, as well as editor notes about edge cases and the history of the term, but these should be included as separate annotations and not in the definition. Instances, such as organizations or geographical locations, can benefit from definitions although it is understood that definitions for instances are not required. It is recognized that OBO format (e.g., versions 1.2 and 1.4) does not allow this as an option. Logical definitions should agree with textual definitions. In fact, logical definitions can be programmatically used to generate textual definitions (see http://oro.open.ac.uk/21501/1/)
Textual definitions should be identified using the annotation property: ‘definition’ http://purl.obolibrary.org/obo/IAO_0000115. The source of the definition should be provided using the annotation property ‘definition source’ http://purl.obolibrary.org/obo/IAO_0000119, or as an axiom annotation on the definition assertion.
An example of providing source in an axiom annotation:

<http://purl.obolibrary.org/obo/GO_0000109> rdf:type owl:Class ;
                                            <http://purl.obolibrary.org/obo/IAO_0000115> "Any complex formed of proteins that act in nucleotide-excision repair."@en ;
                                            rdfs:label "nucleotide-excision repair complex"^^xsd:string .

[ rdf:type owl:Axiom ;
   owl:annotatedSource <http://purl.obolibrary.org/obo/GO_0000109> ;
   owl:annotatedProperty <http://purl.obolibrary.org/obo/IAO_0000115> ;
   owl:annotatedTarget "Any complex formed of proteins that act in nucleotide-excision repair."@en ;
   <http://www.geneontology.org/formats/oboInOwl#hasDbXref> "PMID:10915862"^^xsd:string
 ] .

this corresponds to the obo format:

id: GO:0000109
name: nucleotide-excision repair complex
def: "Any complex formed of proteins that act in nucleotide-excision repair." [PMID:10915862]
Examples
Class: reproductive shoot system 
Term IRI: http://purl.obolibrary.org/obo/PO_0025082 
Definition: A shoot system (PO:0009006) in the sporophytic phase that has as part at least one sporangium (PO:0025094). 
Logical definition: ```intersectionOf: shoot system intersectionOf: participates_in some reproductive shoot system development stage

<i><b>Class</b></i>: chromatography device
<br>  <i><b>Term IRI</b></i>: http://purl.obolibrary.org/obo/OBI_0000048
<br>  <i><b>Definition</b></i>: A device that facilitates the separation of mixtures. The function of a chromatography device involves passing a mixture dissolved in a "mobile phase" through a stationary phase, which separates the analyte to be measured from other molecules in the mixture and allows it to be isolated.
<br>  <i><b>Definition source</b></i>: http://en.wikipedia.org/wiki/Chromatography
<br>  <i><b>Logical definition</b></i>:
intersectionOf: device intersectionOf: has_function some material separation function
AVOID:
No definition, Circular/Self-referential definition: “A chromatography device is a device that uses chromatography” when chromatography is not defined elsewhere

## Relations (principle 7):

Relations should be reused from the Relations Ontology (RO). The purpose of requiring the use of RO is to facilitate interoperability between multiple ontologies, especially with respect to logical inference. That is, a reasoner can only detect logical inconsistencies between ontologies and infer new axioms if the ontologies use the same object properties.
Each OBO ontology MUST reuse existing relations (aka object properties) that have already been declared in the Relations Ontology (RO), rather than declaring duplicative relations. In some cases it may make sense for an ontology to declare a new relation in its own ID space. In these cases, there SHOULD still be coordination with RO, for example in the form of an issue submitted to the RO tracker.
Reuse means that the actual relations PURLs are used. Ontology developers should be aware that RO relations (in rare instances) can evolve over time and previous relations might become obsolete. This means developers should monitor the state of the RO relations they use.

## Documentation (principle 8):

The owners of the ontology should strive to provide as much documentation as possible. The documentation should detail the different processes specific to an ontology life cycle and target various audiences (users or developers).
Central to the issue of ontology documentation is ensuring transparency and traceability of artefact development. For each of the development steps, clear procedures should be made available. Documentation availability will be used to assess the quality of the resource. The following itemized list provides a core checklist, distinguishing general ontology documentation (general information about the resource) and local ontology documentation (documentation at artefact level itself and representational unit level (class and relations)). Documentation assessment with the purpose of assessing Ontology soundness, will cover updates and revision to the documentation. As ontology evolve, so should the documentation, for example by including a release documentation file.
Documented Plurality of Users (principle 9):
The ontology developers should document that the ontology is used by multiple independent people or organizations. This principle aims to ensure that the ontology tackles a relevant scientific area and does so in a usable and sustainable fashion. The ontology developers should provide links/citations to evidence of use (publication, external ontology; see examples below) as input to the review process. It is important to be able to illustrate usage outside of the immediate circle of ontology developers and stakeholders. An ontology that has not been used by other than the developer(s) is not yet ready for review. Note that the ontology can still be listed in other ontology portals such as the OBO Library while publicizing your resource in appropriate channels and searching for users with needs you can meet.
Examples
Use of the target ontology’s term IRIs in other ontologies. This can be evidenced by linking to the other ontology that uses an ontology term IRI from this ontology
Imports in other ontologies, again, evidenced through a link to the importing ontology
A documentation page with links to databases using the ontology for annotation
Use in semantic web projects (e.g., Open PHACTS usage)
Use in diverse software applications, including text mining or analysis pipelines
Publications showing the ontology being used in research (evidenced by citation details for the publications; if behind paywall it may be necessary to provide a PDF for the paper)
Citations to the ontology publication(s); such citations are only relevant if the authors indicate actual use of the cited ontology within some community (mere mention of the existence is not enough to warrant inclusion)
Documentation of requests from multiple users, e.g., via an issue tracker (provide a link to the issue tracker online)
Use of the terms from the ontology to structure or annotate experimental or derived data (e.g. GOA; provide details of how to review the annotations)

To pass review, the ontology developers must demonstrate at least three external users. External users are defined either as researchers not significantly overlapping in personnel with the developers or three independent groups with three independent artefacts (db, etc) that use the ontology.

## Commitment to Collaboration (principle 10):

OBO Foundry ontology development, in common with many other standards-oriented scientific activities, should be carried out in a collaborative fashion. The benefits of collaboration are threefold: (1) Avoid duplication of work; (2) Increase interoperability; and (3) Ensure that ontology content is both scientifically sound and meets community needs.
It is expected that Foundry ontologies will collaborate with other Foundry ontologies, particularly in ensuring orthogonality of distinct ontologies, in re-using content from other ontologies in cross-product definitions where appropriate, and in establishing and evolving Foundry principles to advance the Foundry suite of ontologies to better serve the joint users. Where there are multiple ontology providers in a particular domain, they are particularly encouraged to get together and determine how the domain should be divided between the ontologies, or whether the ontologies should be merged into a single artifact. Should it be determined that there is a competing ontology in the same domain, the Foundry ontology should invite the developers of the external ontology to collaborate and should strive to negotiate an arrangement that is beneficial to both projects. If necessary, conflicts can be mediated in dedicated workshops or using the obo-discuss@lists.sourceforge.net discussion list where Foundry advisors and members of the editorial board can help the parties negotiate to a mutually agreeable solution.
Examples
Collaborative workshop: http://ncorwiki.buffalo.edu/index.php/Protein_Ontology_Workshop
Conflict resolution: The Statistical Methods Ontology (STATO) and Ontology of Biological and Clinical Statistics (OBCS) both cover statistics. The developers of each have posted to the OBO Foundry discussion list to work out how to collaborate.
Contribution to external ontology: Plant Ontology (PO) curators contribute definitions to Gene Ontology (GO) for biological processes and cell components in plants. PO then uses the GO terms in their definition of corresponding structures and stages. *Documentation of collaboration: Cell Line Ontology (CLO), Cell Ontology (CL), and Ontology of Biomedical Investigations (OBI) published a paper sorting out their overlap and documented working together. Sarntivjiai et al., “CLO: The cell line ontology”, J. Biomed. Sem., 2014, 5, 37. http://www.ncbi.nlm.nih.gov/pubmed/25852852
Providing terms upon request: The Disease Ontology (DO) responded to a request from the PRotein Ontology for curation of certain disease terms.
To pass review, the ontology developers must document their attempts at an open dialog with OBO Foundry members, for example by attempting to ascertain if there are other possible ontologies in (or overlapping) the domain of interest. Such documentation can be a simple pointer to an e-mail thread on the OBO discuss list. If there are other ontologies that might need to be aligned or have boundaries determined, evidence of coordination or cooperation should be provided. Further evidence of collaboration may include examples of terms that have been provided to other ontologies in the OBO Foundry community. Finally, hosting or participating in collaborative workshops or meetings attended by OBO Foundry community members is considered evidence of collaboration.

## Locus of Authority (principle 11):

There should be a person who is responsible for communications between the community and the ontology developers, for communicating with the Foundry on all Foundry-related matters, for mediating discussions involving maintenance in the light of scientific advance, and for ensuring that all user feedback is addressed. It is important that there is a person responsible for communication rather than a group of people or a list. Secondary or tertiary contacts are however appropriate. Often in communications to a list, the responsibility for responding can be diffused and it is likely that in some scenarios no response will be given. It may also, from time to time, be necessary to engage in strategic communications (e.g. relating to funding or collaboration possibilities) that are not able to be made public, and these should not be conducted on public mailing lists. The designation of a contact person is not to be interpreted as a designation for credit.
The name, email address and github username of this person should be provided when requesting to register with OBO. This person must be subscribed to obo-discuss in order to be kept abreast of community developments of relevance to participating ontology projects. The email address of the person who is the locus of the authority must be kept up-to-date, and before that person ceases to have responsibility for the project, they should identify a replacement and update the metadata accordingly (via the OBO Foundry issue tracker) before they move on. The contact person can, of course, delegate these responsibilities as necessary.

## Naming Conventions (principle 12):

Details: For full details, see this paper: http://www.biomedcentral.com/1471-2105/10/125
Briefly, some important things to remember:
use rdfs:label for the primary label
include exactly one rdfs:label for every declared entity (e.g. class, property)
write labels, synonyms, etc as if writing in plain English text. ie use spaces to separate words, only capitalize proper names (e.g. Parkinson disease). Do not use CamelCase, do_not_use_underscores
spell out abbreviations. Abbreviations can be included as a separate property.
make the primary labels to be as unambiguous as possible. Remember, your ontology may be used in a different context than that for which it was originally intended. Remember also of course that the label should be unambiguous without looking at parent terms
labels should be unique within an ontology
use the IAO property ‘obo foundry unique label’ http://purl.obolibrary.org/obo/IAO_0000589 to declare a pan-OBO unique label if required

## Maintenance (principle 16):

The ontology needs to reflect changes in scientific consensus to remain accurate over time. Ideally, the maintainer of an ontology should actively monitor for any changes in scientific consensus, but at a minimum, the maintainer needs to be responsive in a timely manner (less than 3 months) to requests from the community pointing out such changes in scientific consensus. Tentatively, we consider scientific consensus to be reached if multiple publications by independent labs over a year come to the same conclusion, and there is no or limited (<10 percent) dissenting opinions published in the same time frame. In cases an area remains controversial, and no consensus is reached, then it is up to the ontology maintainer to either leave out the controversial term, or pick a viewpoint for practical considerations, and note the presence of controversy in an editor note.
The developers of the ontology need to include a statement specifying how they are planning to maintain the ontology. We expect that an ontology will be maintained for at least 3 years from the time of review.
