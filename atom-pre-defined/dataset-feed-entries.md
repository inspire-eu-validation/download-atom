# Separate entries for each format/CRS combination

**Purpose**: The Dataset Feed shall contain separate [entries](#entry) for each format/CRS combination in which the pre-defined dataset is made available for download.

**Prerequisites**

**Test method**

* For each [category element](#category) in the Download Service feed entity, which included the link to the Dataset feed document, check that at least one entry exists in the Dataset feed containing a category element with an identical term attribute.
* Check that the Dataset Feed contains separate [entries](#entry) for each [format](#format)/[CRS](#CRS) combination in which the pre-defined dataset is made available for download.

**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 27

**Test type**: Automated

**Notes**

1. A Dataset Feed [entry](#entry) can contains multiple occurrencies of the 'link' element if the dataset is provided in multiple physical files; each file is linked to via a separate [link element with 'rel' value equal to "section"](#link_sec). If only one dataset file is present, the related link is provided with a [link element with 'rel' value equal to "alternate"](#link_alt).
2. The method of discovering the parent Download Service Document(s) is left to the ETS. If the Dataset Feed contains the [up-link](#uplink) element it may be used for the parent feed discovery. Alternatively, the validator should use the information about the parent-child relation previously collected when validating the Download Service Feeds pointing to the Dataset Feed. If the validator has not (yet) followed any Download Service Feed entry links to validate this Dataset Feed, it should postpone validation until the parent feed is discovered.

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
entry <a name="entry"></a> | //atom:entry
category element <a name="category"></a> | //atom:entry/atom:category[string-length(@term)>0 and string-length(@label)>0]
format <a name="format"></a> | //atom:entry/atom:link/@type
CRS <a name="CRS"></a> | //atom:entry/atom:category/@term
link element (multiple files) <a name="link_sec"></a> | //atom:entry[./atom:link[@rel='section']]
link element (single file) <a name="link_alt"></a> | //atom:entry[./atom:link[@rel='alternate']]
up-link <a name="uplink"></a> | //atom:link[@rel='up' and @type='application/atom+xml']
