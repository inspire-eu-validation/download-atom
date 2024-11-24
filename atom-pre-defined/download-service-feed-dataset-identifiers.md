# Download Service feed dataset identifiers

**Purpose**: The Download Service feed must provide the INSPIRE identifier element [spatial_dataset_identifier_code](#datasetidentifiercode) for each feed [entry](#entry). In addition, the [spatial_dataset_identifier_namespace](#datasetidentifiernamespace) element may be present if the data set identifier has a namespace component.

**Prerequisites**

**Test method**

For each [entry](#entry):

* The [spatial_dataset_identifier_code](#datasetidentifiercode) must be a non-empty text element;
* If the optional [spatial_dataset_identifier_namespace](#datasetidentifiernamespace) element is present, it must be a non-empty text element.

**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 13

**Test type**: Automated

**Notes**

The text content of the elements must include at least one alpha-numeric character.

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
entry <a name="entry"></a> | //atom:entry
spatial_dataset_identifier_code <a name="datasetidentifiercode"></a> | //atom:entry/inspire_dls:spatial_dataset_identifier_code
spatial_dataset_identifier_namespace <a name="datasetidentifiernamespace"></a> | //atom:entry/inspire_dls:spatial_dataset_identifier_namespace
