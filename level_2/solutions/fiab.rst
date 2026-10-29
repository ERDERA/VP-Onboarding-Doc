Sextans Suite for Level 2 onboarding
------------

*The Level 2 interface installed with Sextans Suite serves a single dataset per deployment: each Sextans Fix installation holds one dataset, and the Beacon facade reports results for that dataset only. If your resource contains multiple distinct datasets that need to be queried independently, each one requires its own Sextans Fix, Severance and Beacon facade deployment*. [confirm this, please!]

`Sextans Suite <https://github.com/wilkinsonlab/Sextans-Suite/>`_ replaces FAIR-in-a-Box (FiaB), which is deprecated and no longer receives security patches. Level 2 relies on three components: **Sextans Fix** (record data, inside your firewall), **Severance** (a secure relay that runs only pre-approved, named SPARQL queries), and the **Beacon facade** (a Beacon v2-shaped API on top of Severance).

To install Sextans Suite, follow the instructions you will find `here <https://github.com/wilkinsonlab/Sextans-Suite/blob/main/README.md>`_. 

Level 2 is not enabled by default. To enable it:

1. Deploy `Severance <https://github.com/FAIR-Data-Systems/Severance>`_ (External and Internal), with Internal connected to your Fix triplestore.
2. Install the ``individuals_exists`` and ``individuals_count`` queries into Severance Internal. The facade cannot answer any query until these are installed.
3. Deploy the `Beacon facade <https://github.com/FAIR-Data-Systems/Severance-Facades>`_ and set ``BEACON_SEVERANCE_URL``, ``BEACON_SEVERANCE_AUTH_TOKEN`` and ``BEACON_FACADE_AUTH_KEY`` (the pre-shared key ERDERA configures when registering your resource) in its ``.env`` file.


**Record-level content-based discovery:**

To facilitate content discoverability within your record-level data, first, populate Sextans Fix with data following the CARE-SM-2 model.
Sextans Fix implements a workflow based on CSV templates that can transform your data, from a CSV format file into an RDF-based format that is then stored in a protected Virtuoso triplestore instance, where all access requires authenticated credentials. 

Supported Beacon filters for querying are disease, sex, age this year, age at symptom onset and age at diagnosis; while symptom and gene variant filters are implemented but untested. Where several values are given for sex or disease, only the first is used. 
These queries exclusively retrieve non-sensitive information, providing anonymous and secure answers for each query performed. 
Only aggregate results are returned: callers without the auth-key receive a yes/no answer, and the Virtual Platform, presenting the auth-key, receives counts.

*Note that CSVs written for the original CARE-SM are not compatible with CARE-SM-2 (see the `CARE-SM-2 documentation <https://care-sm-semantic-model-v2.readthedocs.io/>`_).*
