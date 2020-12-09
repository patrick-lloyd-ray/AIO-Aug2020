# Allen Institute Ontology: Fall 2020 Release

Focus: The focus of the AIO is to represent research and the results of research in a manner that is useful for scientists. It is a link between scientific knowledge gained through experimentation and the distribution/dissemination of that knowledge. The ontology development team's goal is to report areas that are in need of development in the ontology and to implement those changes in a predictable and consistent manner. The development team adheres, as much is as possible, to the standards of best practices in ontology development as outlined by the OBO Foundry (obofoundry.org). The team members are also responsible for reviewing changes in the ontology to be sure that they accurately reflect the best current understandings of brain science. The team works in conjunction with a team of software developers to ensure that the ontology and its applications are consistent and up-to-date.

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

Ontology developers edit a source version of the ontology -- this is often called something like [foo-edit.owl].  

This source version is compiled down to make the release versions [foo.owl]. Note that the name is always the same as the ontology ID space, all in lowercase. 

The release version includes links inferred by a reasoner and asserted in the ontology.

The release version should always have an [owl:versionIRI] tag based on the date (YYYY-MM-DD format). 

After the release version is prepared there are different methods for publishing this. A common method is to publish directly on github by committing the release file. Some groups also use the github release mechanism. 
