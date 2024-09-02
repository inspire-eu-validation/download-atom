# Dataset Feed title

**Purpose**: The "title" element of an Atom Dataset feed must be populated with a human readable title for the feed

**Prerequisites**

**Test method**

* the [feed title](#feedtitle) must be non-empty text; the text content must include at least one alpha-numeric character.

**Reference(s)**:

* [TG DL](./README#ref_TG_DL), Requirement 21

**Test type**: Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
feed title <a name="feedtitle"></a> | /atom:feed/atom:title
