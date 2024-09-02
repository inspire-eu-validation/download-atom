# OpenSearch Description URL Describe Spatial Dataset operation

**Purpose**:

The OpenSearch description must contain a ["Url" element](#urlelement) that describes a template URL for the Describe Spatial Data Set operation. This template must accept the INSPIRE parameters "spatial_dataset_identifier_code", "spatial_dataset_identifier_namespace" and the OpenSearch "language" parameter. The ["Url" element](#urlelement) must have an attribute "type" with a value of "application/atom+xml" or 'application/xml' or 'text/xml' and an attribute "rel" with the value "describedby".

**Prerequisites**

**Test method**

* test if the OpenSearch Description provides a [Describe Spatial Dataset url](#describespatialdataseturl)
* for this [Describe Spatial Dataset url](#describespatialdataseturl), checks that the parameters "spatial_dataset_identifier_code", "spatial_dataset_identifier_namespace" and "language" are contained in the template URL.

**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 42
* [OpenSearch](./README.md#ref_opensearch)

**Test type**:

Automated

**Notes**

The requirement has been updated according to the following TG change proposal: https://github.com/INSPIRE-MIF/technical-guidelines/issues/26

[1] The values for the parameters "spatial_dataset_identifier_code", "spatial_dataset_identifier_namespace" and "language" can be obtained from the OpenSearch description

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
url element <a name="urlelement"></a> | /os:OpenSearchDescription/os:Url
Describe Spatial Dataset url <a name="describespatialdataseturl"></a> | /os:OpenSearchDescription/os:Url[@rel='describedby' and @type='application/atom+xml' OR @type='application/xml' OR @type='text/xml' and starts-with(@template,'http') and contains(@template,'spatial_dataset_identifier_code') and contains(@template,'spatial_dataset_identifier_namespace') and contains(@template,'language')]
