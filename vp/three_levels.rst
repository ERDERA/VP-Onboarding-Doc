Three Levels of Connectivity
------------

`Level 1: Resource Discovery <https://vp-onboarding-doc.readthedocs.io/en/latest/level_1/index.html>`_

.. list-table::
	:widths: 20 20 20 20 20
	:header-rows: 1

	* - Description
	  - Contributes to
	  - Technology Requirements
	  - Access Condition Options
	  - Usage Scenarios
	* - **At this level, the provider commits to openly publish online some standardised metadata about the offered resource, and hence make this available to the VP via the VP Index.**
	  - Resource discoverability via open metadata
	  - FAIR Data Point specification, ERDERA metadata schema
	  - Open Access
	  - Discoverying registries in one country, or registries that involve a particular disease. For instance: Which repositories for a certain rare disease are available from Germany? What’s the contact information for a registry? Which registries cover a certain disease (by ORPHAcode)?


| `Level 2 - Content-based discovery <https://vp-onboarding-doc.readthedocs.io/en/latest/level_2/index.html>`_
| **Prerequisite: Level 1 connectivity**

.. list-table::
	:widths: 20 20 20 20 20
	:header-rows: 1

	* - Description
	  - Contributes to
	  - Technology Requirements
	  - Access Condition Options
	  - Usage Scenarios
	* - **At this level, content can be queried based on specific characteristics such as disease IDs, ages, phenotypes and so on, responding with yes/no or approximate record count information. The goal of level 2 is still the discovery -and not the use- of the data. The questions are answered against summary metadata and safe content of each catalogue.**
	  - Resource discoverability via controlled querying of catalogue summary info and/or safe record data
	  - ERDERA Beacon2 v2/individual's API endpoint
	  - Open or authenticated user access, as per preference
	  - ‎ ‎ 
	* - **Level 2 – Querying at the catalogue level**
	  - Involves answering queries based on the the summary metadata about the catalog.
	  - ERDERA Beacon2 v2/individual's API endpoint
	  - Open user access
	  - Is the catalogue associated with the Marfan syndrome [ordo:Orphanet_558]?
	* - **Level 2 - Privacy-preserving queries at record level**
	  - Entails answering queries based on individual patient records within the catalog.
	  - ERDERA Beacon2 v2/individual's API endpoint
	  - Open or authenticated user access, as per preference
	  - Discovery of catalogs based on the existence of a cohort of patients of interest (patients that match query parameters such as disease codes, ages and so on) in sufficient numbers. For instance: Find catalogs based upon how many patients have Autosomal recessive polycystic kidney disease and had symptom onset before 8 years old.  Is there an appropriate registry in my country to which collected information about certain patients should be donated?  Within a certain registry, how many patients match less than 10 years old Duchene muscular dystrophy with gastrointestinal disorders? 


| `Level 3 - Data analysis <https://vp-onboarding-doc.readthedocs.io/en/latest/level_2/index.html>`_
| **Prerequisite: Level 1 connectivity. Optional level 2 connectivity.**

.. list-table::
	:widths: 20 20 20 20 20
	:header-rows: 1

	* - Description
	  - Contributes to
	  - Technology Requirements
	  - Access Condition Options
	  - Usage Scenarios
	* - **At this level, the provider commits to support interrogation and analysis over the catalog's content**
	  - Data reuse and analysis
	  - UNDEFINED. Examples include: SPARQL, FAIR Data Train, Data available according to the Clinical And Registry Entries Semantic Model (CARE-SM)
	  - Open or authenticated user access, as per preference
	  - Efficient health system monitoring. For instance: Are there countries which are diagnosing much faster than others, based on certain key performance indicators (KPIs)? What drugs are used to track certain symptoms in different countries?


