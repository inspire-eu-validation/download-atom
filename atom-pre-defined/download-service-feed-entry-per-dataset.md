# Download service feed: separate entries per dataset

**Purpose**: Each dataset must have a separate entry in the service feed

**Prerequisites**

**Test method**

In the Atom service feed (the top-level feed), each combination of the [spatial_dataset_identifier_code](#spatial_dataset_identifier_code) and [spatial_dataset_identifier_namespace](#spatial_dataset_identifier_namespace) must be unique.

**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 1

**Test type**: Automated

**Notes**

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
spatial_dataset_identifier_code <a name="spatial_dataset_identifier_code"></a>   | //atom:entry/inspire_dls:spatial_dataset_identifier_code
spatial_dataset_identifier_namespace <a name="spatial_dataset_identifier_namespace"></a>   | //atom:entry/inspire_dls:spatial_dataset_identifier_namespace
