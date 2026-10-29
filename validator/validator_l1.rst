Validate your L1 metadata implementation
------------

After following these instructions, your resource should appear on the Virtual Platform. Check whether it is listed here [`link <https://vp.ejprarediseases.org/discovery/sources>`_]. If your resource does not appear, or is not displayed correctly, you can validate your metadata with the ERDERA test hosted in the FAIR Champion tool.

The Level 1 test checks that your metadata:

* uses the current w3id properties instead of the deprecated EJP purl properties;
* includes the VPDiscoverable property;
* provides dcat:theme, dcat:contactPoint, dct:description, dcat:keyword, dct:language, dct:license, dct:publisher, dct:title and dcat:landingPage;
* has a dct:publisher that is a foaf:Agent with a foaf:name.

Steps to use the Level 1 validation test:

1. Find the `ERDERA test for Level 1 in FAIR Champion <https://tools.ostrails.eu/champion/tests/?keyword=ERDERA%3A+Minimal+VP+Metadata+for+Level+1+Compliance>`_ and click on the blue button with that title.
2. In the test's interface, enter your resource identifier/GUID (record URL) and run the test. More detailed information can be found in the description of the test, and if clicking the "Additional details" entry.
3. Read the result at the top of the response (pass/fail). In case of fail, the log explains which requirements are not met, as shown in the figure below.

..  figure:: _images/L1_fail.jpeg
    :alt:  Resulting screen of the validator, in case of failure.
    :width: 100%

4. Based on the test feedback, you can either fix the information yourself or contact the onboarding team for support. Once all fixes are made, run the test again to confirm it passes.

..  figure:: _images/L1_pass.jpeg
    :alt:  Resulting screen of the validator, in case of failure.
    :width: 100%


Alternatively, you can also run the test from the command line:

.. code-block:: bash

   curl -X POST -H "Content-Type: application/json" -H "Accept: application/json" \
     -d '{"resource_identifier": "YOUR_URL_HERE"}' \
     https://tests.ostrails.eu/community-tests/assess/test/erdera_core_vp_metadata

