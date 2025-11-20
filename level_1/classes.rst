ERDERA Metadata Schema Classes
------------

The tables that follow describe all classes depicted in Figure 5. The tables also provide usage notes for the classes’ properties. 

To facilitate navigation within this document, each class is hyperlinked to its corresponding sections within this chapter. By identifying which sections are applicable to your resource, you can jump directly to the relevant fields to describe your resource's metadata.

Mandatory Classes
~~~~~~~~~~~~

.. list-table:: Level 1 - Mandatory Classes
	:widths: 20 60 20
	:header-rows: 1

	* - Class
	  - Definition and usage note
	  - URI
	* - `Organisation <properties/organization.html>`_
	  - To add resources to the ERDERA RD Virtual Platform the organisations that provide the resources need to be registered first. For each organisation, the biobanks, patient registries, guidelines, datasets (which may have associated data services) or data services (with no specific dataset), provided by the organisation, need to be added.
	  - foaf:Organisation
	* - "*Resource*"
	  - "*Resource is a generic concept from the DCAT2 vocabulary. In our metadata model, we extended it with Rare Disease specific concepts like Biobank and Patient registry, which means that you rarely use this class directly, but indirectly through its extensions. We recommend that you avoid using dcat:Resource directly for your document unless the type that you are looking for is not available in this table (not a Biobank, Patient Registry, Dataset, Data Service, or Guideline). At least one of the resource types described in this table is Mandatory.*"
	  - dcat:Resource (use dcat:Dataset, dcat:DataService, ejprd:PatientRegistry, ejprd:Guideline, or ejprd:Biobank according to your resource type)


Class definitions (per Resource Type)
~~~~~~~~~~~~

.. warning::

	Choose the class that best represents the type of resource you are describing.


.. list-table:: Level 1 - Mandatory Classes for Resource Type
	:widths: 20 60 20
	:header-rows: 1

	* - Class
	  - Definition and usage note
	  - URI
	* - `Patient Registries <properties/patient_registry.html>`_ **(Resource Type)**
	  - Defines all the patient registries for this ERDERA resource in the case where datasets are about content of a rare disease resource such as a patient registry. This class can be used under Catalogue.
	  - ejprd:PatientRegistry
	* - `Biobanks <properties/biobanks.html>`_ **(Resource Type)**
	  - Defines all the biobanks for this ERDERA resource in the case where datasets are about the content of a rare disease resource such as a biobank. This class can be used under Catalogue.
	  - ejprd:Biobank
        * - `Distribution <properties/distribution.html>`_
	  - A single dataset can be made available via a Data Service. It is important to note that this requirement is being imposed for all health data providers. Its implementation here is not an arbitrary decision, but rather a regulatory obligation that is expected to be met. Implementing it here offers a clear way to ease compliance with the requirement and ensures consistency across the board. Note that distributions are entirely optional.
	  - dcat:Distribution
	* - `Data Service <properties/data_service.html>`_ **(Resource Type)**
	  - There are two types of data services in ERDERA: 1) those that depend on a catalog or a dataset, and 2) those that exist independently of a catalog or dataset. 
	  - dcat:DataService
	* - `Guideline <properties/guideline.html>`_ **(Resource type)**
	  - This concept describes guidelines that a resource may have about a particular context. An example would be “Biomarker Development Manual”.
	  - ejprd:Guideline



Recommended Classes
~~~~~~~~~~~~

.. warning::

	Note that this class is **mandatory** for FDP Reference Implementation and FiaB, since you cannot create any kind of dataset without first having a Catalog, even if the Catalog has almost no useful metadata


.. list-table:: Level 1 - Recommended Classes
	:widths: 20 60 20
	:header-rows: 1

	* - Class
	  - Definition and usage note
	  - URI
	* - `Catalogue <properties/catalog.html>`_
	  - If the organisation wants to bundle numerous datasets, data services, biobanks, patient registries, or guidelines together under a single title, this sheet needs to be filled-in. We recommend this class because it makes the organization more discoverable in the virtual platform.
	  - dcat:Catalog
