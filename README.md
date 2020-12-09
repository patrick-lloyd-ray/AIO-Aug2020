# Allen Institute Ontology: Fall 2020 Release

Focus: The focus of the AIO is to represent research and the results of research in a manner that is useful for scientists. It is a link between scientific knowledge gained through experimentation and the distribution/dissemination of that knowledge. The ontology development team's goal is to report areas that are in need of development in the ontology and to implement those changes in a predictable and consistent manner. The development team adheres, as much is as possible, to the standards of best practices in ontology development as outlined by the OBO Foundry (obofoundry.org). The team members are also responsible for reviewing changes in the ontology to be sure that they accurately reflect the best current understandings of brain science. The team works in conjunction with a team of software developers to ensure that the ontology and its applications are consistent and up-to-date.

# Trackers

## For trackers, each ticket must have the following information:

1. status (open, accepted, closed, fixed, wontfix)
2. creator (the person who opened the ticket)
3. owner (the developer that the ticket is assigned to)
4. category, milestone, priority (used mainly for sorting)
5. discussion thread (text with information pertinent to the issue)

## To request an ontology term:

First, check whether the term you would like occurs in an ontology already (use OntoBee or BioPortal). You should also check for synonyms of the term you would like. To request a new term, click [trackers] on the right hand side of the GitHub page for AIO, and then send a new term request to the issue tracker of AIO. When submitting your request for a new term, please follow the guidelines at the end of this section.

Things to know about terms: OBO has its own policy for naming terms. Every OBO ontology has its own "ID space" (a string of letters signifying the ontology [AIO]) and a "Local ID" (a string of digits). The combination of those two are the term's identifier -- this is the ID of an OBO term. When you add [http://purl.obolibrary.org/obo/] and an underscore between the ID space and the Local ID, you get the term's IRI.

Obviously using numeric IDs for terms makes the term ID opaque for the human reader. That is, there is nothing about the ID that tells you that it's the ID for some specific term. However, this has advantages when we must replace a term with another (better!) term. If (for example) the term 'assay' is to be replaced, then it is easy to replace 'assay'. In this case 'assay' would then get a new ID and the old term can retain its ID (to support legacy data). If, on the other hand, we used a meaningful word instead of numerals, then it would be difficult to make such changes. Because ontologies are susceptible to changes, we should adopt this convention.

An advantage to numerical (opaque) IDs is that they make versioning easier. If we have some sort of opacity we wish to dispel, it is somewhat easy to do this with tools (software to go from unique numerical ID to human-readable text). However, moving from a (possibly) ambiguous term to a unique ID is often much more difficult. 

PURLs are "persistent URLs" insofar as they are simply URLs with the expectation that it will always point to one resource. PURLs do not change even if a resource is moved to a new server. 

No More than One Name: IRIs allow us to assign as many names as we would like, but we need to ask how many names we would want. Names are most useful the entities we want to talk about have one name. If we are using different names for one entity, confusion proliferates. Coordinating names is a challenge and this challenge only becomes more difficult when the community of users is large or when the knowledge of the domain is changing rapidly. Ontology is part of the solution to the problem of coordinating names. 

Speaking of names, it is good practice to reuse ontology terms when possible. IRIs provide us with all of the globally unique names that we need. Ontologies then give us systems of standardized names (and a bunch of other things). "Using" an OBO reference ontology term simply means using its IRI in your data. Every term needs to have one (and only one) IRI. 

## Term Requests for existing terms:

If you find a term in OntoBee or BioPortal that you would like in AIO, simply ask for an import of that term in the next version release of the ontology. If you find a term that is close but may need some additions or changes, submit a new ticket to the issue tracker and include:

1. the name of the term in the title of the ticket
2. the IRI that identifies the term [http://purl.obolibrary.org/obo/OBI_0000008]
3. a description of the changes you would like and the reasons for the change.

## Term requests for new terms:

If you cannot find the term you would like using the above search parameters, you should request a new term. AIO developers would like the following information when possible:

1. editor preferred term -- a unique, unambiguous label for the term in American English. This is an unambiguous label that uniquely identifies the term within the OBO Foundry. Sometimes you might see [rdfs:label] for this instead. There must be one and only one editor preferred term, and it must be in American English. It should not contain any acronyms or jargon words, and it should make sense when read outside the context of a scientific investigation. This might make the terms become rather cumbersome and unsightly, but it is more important to make sure that they are clear. 
2. alternative terms -- common synonyms or translations. There can be many alternative term annotations for a given term. They can include acronyms and jargon -- if the editor preferred term spells out an acronym then it is a good idea to put the abbreviated form in an alternative term annotation. They can be in any language, but make sure to specify which language if it is not American English. Alternative term annotations do not have to be unique across OBO.
3. textual definition -- proposed. The textual definition is the most important annotation because it expresses the meaning of the term. Definitions should have Aristotelian form: "An A is a B that C" where A is the new term, B is the parent term, and C specifies how A is a special kind of B. Every term needs one and only one textual definition, in American English, and definitions must be unique across the OBO Foundry. 
4. definition source for the textual definition. Every textual definition should have a definition source. If you created the definition, then you are the source. If the definition was adapted from Wikipedia or some other website, then this annotation should contain the permanent URL. If it was adapted from a paper, use its DOI or PubMed URL.
5. logical definition (or simply the parent term). The logical definition of a term is almost as important as the textual definition. The logical definition expresses the meaning of the term in a machine-readable way using the Web Ontology Language (OWL) 2.0. Most OBO terms are OWL Classes (i.e., general nouns) and they require a single parent class. Many of them have more complex logical definitions. If you are not comfortable specifying a logical definition, that is fine -- the AIO developers will help create one based on the textual definition you provide. 
6. example of usage. One or more example of usage annotations can clarify the meaning of a term. While the textual definition must be general enough to cover all cases, the examples provide specific cases that show the term in use. Examples of usage can be common cases that demonstrate the prototypical usage, or uncommon edge cases that delimit the scope of the term. While not strictly required, every new term should have one or more examples of usage.
7. term editor -- your name and that of any collaborators (as it will appear in the ontology). We want to give you credit for your work. We will add one or more term editor annotations with your name, and the names of others who have collaborated on creating the term. 

## Term relationships

### Parents:
Every term in the ontology must have at least one (is_a) parent and can have as many relationships to other terms as necessary.

### Equivalence axioms:
Equivalence axioms represent a special set of relationships that define a term with both necessary and sufficient conditions. For example the equivalence axiom for GO:0055085 transmembrane transport is transport and ('results in transport across' some membrane). This means that if a process is transmembrane transport, it result in transport across a membrane (necessary condition). It also means that any process that transports across a membrane is_a transmembrane transport (sufficient). Whenever possible, equivalence axioms should be created for every term.

### Disjoint axioms:
Terms are made disjoint when they have no children in common. Disjoint relationships can be very useful in that they can be used to identify inconsistencies in the ontology. For example, GO:0003690 double-stranded DNA binding is disjoint with GO:0003697 single-stranded DNA binding.

### Importance of reasoning:
Reasoning is critical to the keeping the AIO maintainable. Any term in AIO may have many parents. In an ontology that is large and complex, maintaining classifications of this type by hand in is very error-prone as placing a class correctly in the hierarchy requires editors to know what parents are available. It is much more sustainable to record just one asserted classification along with a set of conditions for class membership and then to rely on automated classification for the rest.

## Editing the Ontology

For editing AIO, it is recommended that you use Protege. As of August 2020, the development team uses Protege 5.5.0. To download Protege, visit [protege.stanford.edu]. Then unzip and move the app to your [applications] folder. Follow the instructions when prompted. 

Protege requires a fair bit of memory for larger ontology files. To increase your memory, open [/Applications/Protege-5.5.0/Protege.app/Contents/info.plist] and below the line [<string>-Xss16M</string>] insert [<string>-Xmx12G</string>]. 

If you would like to adde a view as a window or a tab, then go to 'Windows' > 'View' > select the view you would like to insert. If you would like to add a view as a new window, then mouse over the window you would like to add a new window to (until you see a blue rectangle), then click to drop the window where you would like. If you would like to add a view as a new tab, then mouse over the middle area of the window you would like to add a new tab to, then click to drop the window there. 

To work on AIO, there are a few tabs that you will need: [Active Ontology], [Entities], [DL Query], and [Annotations]. Once you have Protege laid out to your preferences, then [Windows] > [Store Current Layout].

Sometimes Protege will ask you to install plugins or some plugins may not be available from the [Window] > [Views] tab. If the latter occurs, go to [File] > [Check for plugins]. The plugin menu will appear and display the various available plugins or newer versions of old plugins. NB: the box [Always check for updates on startup] is recommended to be 'off' because this will considerably slow Protege.

The ELK OWL reasoner is used to infer relationships and annotations derived from logical principles. If you do not have ELK installed, then use the [Check for plugins] menu to do so. 

There are also other plugins that are handy for AIO and can be installed from the Protege menu. Also recommended is the [OntoGraph View], which displays a connected graph of classification (is_a) and other relationships. Both children and parents can be viewed in OntoGraph and many (in some cases all) relations are displayed. 

To set the username and auto-adding creation data, take the following steps. 1. In the Protege Menu, go to [Preferences] > [New Entities Metadata] tab. 2. Check [Annotate new entities with creator (user)] 3. For [Creator property] enter 'http://alleninstituteontology.org/#created_by' 4. Toggle on the [Use user name] switch under [Creator value] 5. Check [Annotate new entities with creation date/time] 6. For [Date property] enter 'http://alleninstituteontology.org/#creation_date'. 7. Under [Date value format] select [ISO-8601].

To configure your user details, go to the Protege menu and select [Preferences] > [User details]. For [User name] select [Use supplied user name] and use your AIO id. 

To set the rendering, in the Protege menu, go to [Preferences] > [Renderer]. This allows you to set the annotation property you can use for rendering OWL entities (classes, object properties, annotation properties, individuals) in graphs, trees, and text. This should be set to [rdfs:label]. Note that all entities in OWL are identified by an IRI. Entities also include annotation properties such as human-readable labels. Choosing to render with [rdfs:label] displays term labels in Protege.

To edit the ontology locally and push changes to github (see below), you will need git installed. Make sure that you have git installed before you check out AIO from github. 

First, you will need to clone the AIO repository from github. 1. Create a directory called 'repos' on your local machine using the command: mkdir repos. 2. Paste this command into your terminal: git clone (example) https://github.com/alleninstituteontology/aio-ontology.git

Git also should keep a record of who is committing changes to the repository, so you will see some message with your name and email address configured automatically based on your username and hostname. You may set your name and email explicitly. 

An essential feature of ontologies (and OBO principle) is that they must be maintained and updated regularly. This document outlines the method and steps for ensuring consistent updates and maintenance for the Allen Institute Ontology (AIO).

The ontology will be housed on github in the form of an OWL file. In order to work on the ontology, create a new working branch using 'git checkout'. When working on the AIO it is imperative that you create a new branch of the repository to edit the ontology. You should not work on the master branch of the ontology. Once you are on the master branch, you can create a new branch. If your terminal is not configured to display the branch name, type [git status] to check which branch is active. If you need to move to the master, type [git checkout master]. To create a new branch, type [git checkout -b branch_name] in the terminal. To name your new branch, follow this convention: use string 'issue-' then type the issue number. For example, if you have an issue in the tracker with the following URL (https://github.com/alleninstituteontology/aio-ontology/issues/3453) you would create a branch [git checkout -b issue-3453]. If you type this command, you will automatically be in a new branch.

Ontology editing should be done in Protege or some other ontology-editing application. Before you launch Protege, make sure that you are in the correct branch. If you need to check the active branch, type [git status]. To open the aio-edit.owl file, click on the 'file' pulldown in Protege. You will then navigate to the URL of the AIO owl file or load the file directly (from download). If you have recently worked on the file, it should appear in 'Open/Recent'. 

Next, click on the 'classes' tab. This will allow you to view the classes in AIO. You can search AIO by using the search box in the upper-right portion of Protege. To view a term, double-click on the term. This will provide the term in the 'class hierarchy' window. To launch the reasoner and see the term in the 'class hierarchy (inferred)' window, first go to menu: ['Reasoner' > select ELK 0.4.3], then click 'Start reasoner'. You can close the pop-up warnings about ELK and then see the terms in the inferred hierarchy.  After you modify the ontology, you should synchronize the reasoner. To do this, go to menu: ['Reasoner' > 'Synchronize reasoner']. The reasoner will only detect those changes that impact the ontology structure: changes in subclasses, merges, obsoletions, new term, equivalence axioms. To save your changes, use ['File' > 'Save']. 

When you change the ontology, you can view the changes by typing [git diff] in the terminal window. If there are changes that have already been committed, the full changes in the active branch relative to master can be viewed by typing [git diff master]. 

You can also track changes in the ontology using tools. If you are using Protege, you can use the [ontology differences] tab. You can also use Bubastis and their online and downloadable tools for locating differences between ontologies and versions of ontologies. 

## Publishing ontologies:

First, there needs to be a release version of the ontology. (we can use OWLTools and OORT, or ROBOT). The general principles are that: 

1. Ontology developers edit a source version of the ontology -- this is often called something like [foo-edit.owl].  
2. This source version is compiled down to make the release versions [foo.owl]. Note that the name is always the same as the ontology ID space, all in lowercase. 
3. The release version includes links inferred by a reasoner and asserted in the ontology.
4. The release version should always have an [owl:versionIRI] tag based on the date (YYYY-MM-DD format). 

After the release version is prepared there are different methods for publishing this. A common method is to publish directly on github by committing the release file. Some groups also use the github release mechanism. 
