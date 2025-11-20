Data Service
~~~~~~~~~~~~

Data services are resources that provide access to data or analytical tools via some interface. The interface may be machine-readable (I.e., an Application Programming Interface – API) or via a Web page for humans to interact manually. There are different conventions for data services on the VP Portal, depending on the “nature” of the service. Resources that serve via a Web page, **must have** a landingPage property, while those that serve via an API **must have** both an endpointURL and endpointDescription. On the ERDERA VP, a service that serves a DCAT Dataset **must be** connected to a DCAT Distribution of that Dataset via the dcat:accessService property. A service not serving a dataset (e.g., a statistical analysis service, or an ontology lookup service) **must be** connected to the top-level DCAT Catalog via the dcat:service property.


**Mandatory Properties**

.. list-table:: 
	:widths: 20 60 20
	:header-rows: 1

	* - Property
	  - Definition and usage note
	  - URI
	* - **License**
	  - This should contain a URL that provides details regarding the license that is applicable to this resource. If no suitable license can be provided, then the default license should be used: `W3ID License v.10 <https://w3id.org/ejp-rd/resources/licenses/v1.0/>`_. Other licenses are: `Creative Commons <https://creativecommons.org/licenses/>`_, e.g. `CC BY-NC-ND 4.0 Deed <http://creativecommons.org/licenses/by-nc-nd/4.0>`_
	  - | dcterms:license
	* - **Type**
	  - In the context of ERDERA Data Services, if the service is a Beacon, the range is either http://purl.org/ejp-rd/vocabulary/VPBeacon2_individuals or http://purl.org/ejp-rd/vocabulary/VPBeacon2_catalog. If the service is anything besides a Beacon, use one of the children of `edam_operation <http://edamontology.org/operation_0004>`_.
	  - | dcterms:type
	* - **Title**
	  - The name of the data service. This is a required field and needs to be unique.
	  - | dcterms:title
	* - **Description**
	  - A description of the data service.
	  - | dcterms:description
	* - **Publisher**
	  - Pointer to the Organisation that published the resource. The range is foaf:Organisation
	  - | dcterms:publisher
	* - **Personal Data**
	  - Set to "true" if the resource onboarded to the Virtual Platform contains personal data, personal data meaning data related to identified or identifiable persons (as per GDPR definition), otherwise "false".
	  - | ejprd:personalData
	* - **Theme**
	  - Points to an URL that specifies relevant ontology concepts that classify the data service. Typically, these can be looked up using the `Ontology Lookup Service (OLS) <https://www.ebi.ac.uk/ols/index>`_ or Bioportal. Note that the purpose of 'Theme' is todescribe the service for the purpose of discovery, which is distinct from the purpose of classification of the service, which is served by 'Type'.
	  - | dcat:theme
	* - **Keyword**
	  - Keywords applicable to this patient registry
	  - | dcat:keyword
	* - **Contact Point**
	  - Pointer to a Contact Point, Range is vCard
	  - | dcat:contactPoint 
	* - **Language**
	  - An ISO 639-1 two-letter code for the languages this data service is provided in. Example: en indicates that this data service is available in English. The range is an xsd:string. The ISO language codes can be found at: `ISO639-1 <https://id.loc.gov/vocabulary/iso639-1.html>`_ and `an example <http://id.loc.gov/vocabulary/iso639-1/en>`_. 
	  - | dcterms:language 



**Recommended Properties**

.. list-table::
	:widths: 20 60 20
	:header-rows: 1

	* - Property
	  - Definition and usage note
	  - URI
	* - **Access Rights**
	  - Information about who can access the resource or an indication of its security status. This should point to a URL where this information can be found. We strongly recommend that access rights are described as `DUC CCE <https://duc.le.ac.uk/>`_ profile.
	  - | dcterms:accessRights
	* - **Conforms to**
	  - It describes the functionality of the service. If applicable, it should point to an API descriptor, which would be implemented by the 'Endpoint Description'. 
	  - | dcterms:conformsTo
	* - **Endpoint Description**
	  - A machine-readable document defining the API of the service (e.g., in openAPI).It is the specific implementation of the API descriptor pointed to by 'Conforms to'.  **This field is required for services that have an API.** This field is optional for services that are attached to Catalogue, or serve via a Web page.
	  - | dcat:endpointDescription
	* - **Endpoint URL**
	  - The URL to which API requests are sent. **This field is required for services that have an API.** This field is optional for services that are attached to Catalogue, or serve via a Web page
	  - | dcat:endpointURL
	* - **Landing Page**
	  - This a URL to a web page with more information regarding the Data Service. **This field is required for services that have an API.**
	  - | dcat:landingPage


**Optional Properties**

.. list-table::
	:widths: 20 60 20
	:header-rows: 1

	* - Property
	  - Definition and usage note
	  - URI
	* - **VP Connection**
	  - This property is attached to every portion of your Metadata record that you wish the VP to explore (e.g. Dataset X, Data Service Y, but NOT Dataset Z). **If you do not add this tag to at least the description of your resource, you will not be onboarded.** The range is `https://w3id.org/ejp-rd/vocabulary#VPDiscoverable <https://w3id.org/ejp-rd/vocabulary#VPDiscoverable>`_ 
	  - | ejprd:vpConnection
	* - **ODRL Policy**
	  - An ODRL conformant policy document (`https://www.w3.org/TR/odrl-model/ <https://www.w3.org/TR/odrl-model/>`_) expressing the rights and/or responsibilities associated with access to and/or use of the resource. This should point to a URL where this conformant document has been published.
	  - | odrl:hasPolicy
	* - **Logo**
	  - A link to the graphic representation of this resource.
	  - | foaf:logo
	* - **Serves Dataset**
	  - Used to indicate which dataset a DataService is serving data from. The URL of the dataset to which this service provides access. Range dcat:Dataset
	  - | dcat:servesDataset
	* - **identifier**
	  - Identifier of this resource. It can be a link.  Range is an xsd:string
	  - | dcterms:identifier
	* - **issued**
	  - This resource publication date. The range is xsd:date
	  - | dcterms:issued
	* - **modified**
	  - This resource last revision date. The range is xsd:date
	  - | dcterms:modified
	* - **version**
	  - The version indicator (name or identifier) of a resource. The range is a rdfs:literal
	  - | dcat:version



