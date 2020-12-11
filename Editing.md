# Editing the Ontology

For editing AIO, it is recommended that you use Protege. As of December 2020, the development team uses Protege 5.5.0. To download Protege, visit [protege.stanford.edu]. Then unzip and move the app to your [applications] folder. Follow the instructions when prompted. 

The ELK OWL reasoner is used to infer relationships and annotations derived from logical principles. If you do not have ELK installed, then use the [Check for plugins] menu to do so. 

There are also other plugins that are handy for AIO and can be installed from the Protege menu. Also recommended is the [OntoGraph View], which displays a connected graph of classification (is_a) and other relationships. Both children and parents can be viewed in OntoGraph and many (in some cases all) relations are displayed. 

To edit the ontology locally and push changes to github (see below), you will need git installed. Make sure that you have git installed before you check out AIO from github. 

An essential feature of ontologies (and OBO principle) is that they must be maintained and updated regularly. This document outlines the method and steps for ensuring consistent updates and maintenance for the Allen Institute Ontology (AIO).

The ontology will be housed on github in the form of an OWL file. In order to work on the ontology, create a new working branch using 'git checkout'. When working on the AIO it is imperative that you create a new branch of the repository to edit the ontology. You should not work on the master branch of the ontology. Once you are on the master branch, you can create a new branch. To create a new branch, type [git checkout -b branch_name] in the terminal. To name your new branch, follow this convention: use string 'issue-' then type the issue number. For example, if you have an issue in the tracker with the following URL (https://github.com/alleninstituteontology/aio-ontology/issues/3453) you would create a branch [git checkout -b issue-3453]. If you type this command, you will automatically be in a new branch.

Ontology editing should be done in Protege or some other ontology-editing application. Before you launch Protege, make sure that you are in the correct branch. If you need to check the active branch, type [git status]. To open the aio-edit.owl file, click on the 'file' pulldown in Protege. You will then navigate to the URL of the AIO owl file or load the file directly (from download). If you have recently worked on the file, it should appear in 'Open/Recent'. 

Next, click on the 'classes' tab. This will allow you to view the classes in AIO. You can search AIO by using the search box in the upper-right portion of Protege. To view a term, double-click on the term. This will provide the term in the 'class hierarchy' window. To launch the reasoner and see the term in the 'class hierarchy (inferred)' window, first go to menu: ['Reasoner' > select ELK 0.4.3], then click 'Start reasoner'. You can close the pop-up warnings about ELK and then see the terms in the inferred hierarchy.  After you modify the ontology, you should synchronize the reasoner. To do this, go to menu: ['Reasoner' > 'Synchronize reasoner']. The reasoner will only detect those changes that impact the ontology structure: changes in subclasses, merges, obsoletions, new term, equivalence axioms. To save your changes, use ['File' > 'Save']. 

When you change the ontology, you can view the changes by typing [git diff] in the terminal window. If there are changes that have already been committed, the full changes in the active branch relative to master can be viewed by typing [git diff master]. 

You can also track changes in the ontology using tools. If you are using Protege, you can use the [ontology differences] tab. You can also use Bubastis and their online and downloadable tools for locating differences between ontologies and versions of ontologies. 

## Publishing Ontologies

First, there needs to be a release version of the ontology. (we can use OWLTools and OORT, or ROBOT). The general principles are that: 

1. Ontology developers edit a source version of the ontology -- this is often called something like [foo-edit.owl].  
2. This source version is compiled down to make the release versions [foo.owl]. Note that the name is always the same as the ontology ID space, all in lowercase. 
3. The release version includes links inferred by a reasoner and asserted in the ontology.
4. The release version should always have an [owl:versionIRI] tag based on the date (YYYY-MM-DD format). 

After the release version is prepared there are different methods for publishing this. A common method is to publish directly on github by committing the release file. Some groups also use the github release mechanism. 
