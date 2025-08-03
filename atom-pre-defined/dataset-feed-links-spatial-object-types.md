# Links for Spatial Object Types

**Purpose**: The dataset feed must contain an Atom link element for each INSPIRE Spatial Object Type in the dataset. The link must refer to the INSPIRE Registry unless the data does not conform to any Data Specification in which case a link to a local definition of the Spatial Object Type must be used instead. The value of the "rel" attribute of this element must be "describedby". For definitions in the INSPIRE Registry the value of the "type" attribute must be "text/html".

**Prerequisites**

**Test method**

* test if the dataset feed contains at least one [link to the definition of the Spatial Object Type](#definitionlink)
  * if the link points to the INSPIRE Registry, then check that the value of the "type" attribute is "text/html" ([Link to the INSPIRE Registry](#registrylink))

**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 28

**Test type**: Automated

**Notes**

This test could also be considered a test for the IR section 2.2.4, metadata elements.

No check is done to see if it is a valid description/reference to the INSPIRE Registry. This can't be strictly tested, because the ATOM service can publish datasets that are not harmonised, and then a different HTML description is also allowed.

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Link to the definition of the Spatial Object Type <a name="definitionlink"></a> | /atom:feed/atom:link[@rel='describedby']
Link to the INSPIRE Registry <a name="registrylink"></a> | /atom:feed/atom:link[@rel='describedby' and @type='text/html']
