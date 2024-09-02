# OpenSearch Description provides languages

**Purpose**:
For each language supported by the download service, the OpenSearch description must contain a ["Language" element](#languageelement) that contains the language code. The first ["Language" element](#languageelement) must contain the Default Language.

**Prerequisites**

**Test method**

* test if there is at least one ["Language" element](#languageelement)

**Reference(s)**:

* [TG DL](./README#ref_TG_DL), Requirement 45
* [OpenSearch](./README#ref_opensearch)

**Test type**:

Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Language element <a name="languageelement"></a> | /os:OpenSearchDescription/os:Language
