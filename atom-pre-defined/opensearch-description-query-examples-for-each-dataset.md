# OpenSearch Description Query examples for each dataset

**Purpose**:

For each dataset available the OpenSearch description must contain a ["Query" element](#queryelement)" element that has a "role" attribute with the value "example" and "spatial_dataset_identifier_code" attribute. The 'Query' element may also contain an attribute 'spatial_dataset_identifier_namespace' if the dataset identifier has a namespace component. The value of the "crs" and "language" attributes must be set to the values considered as the default ones by the service provider.

**Prerequisites**

**Test method**

* test if there is one ["Query" element](#queryelement) with the "example" role for each dataset declared in the relevant atom "Dataset Feed"

For each ["Query" element](#queryelement):
* create a [Get Spatial Dataset url](#getspatialdataseturl) with the values of the provided inspire_dls:spatial_dataset_identifier_code, the inspire_dls:spatial_dataset_identifier_namespace (if present) and the values of the "crs" and "language" attributes from the ["Query" element](#queryelement)
* check the HTTP response code to be a valid code from: 200,206,301,302,303


**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 44
* [OpenSearch](./README.md#ref_opensearch)

**Test type**:

Automated 

**Notes**

The Get Spatial Data Set response shall be the file corresponding to the specified spatial_dataset_identifier_code, spatial_dataset_identifier_namespace (if present), crs and language, as declared in the relevant atom "Dataset Feed".


## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Query element <a name="queryelement"></a> | /os:OpenSearchDescription/os:Query[@role='example' and string-length(@inspire_dls:spatial_dataset_identifier_code) > 0 and string-length(@inspire_dls:spatial_dataset_identifier_namespace) >= 0 ]
Get Spatial Dataset url <a name="getspatialdataseturl"></a> | /os:OpenSearchDescription/os:Url[@rel='results' and starts-with(@template,'http') and contains(@template,'crs') and contains(@template,'spatial_dataset_identifier_code') and contains(@template,'language')]
Get Spatial Dataset url with namespace <a name="getspatialdataseturlnamesp"></a> | /os:OpenSearchDescription/os:Url[@rel='results' and starts-with(@template,'http') and contains(@template,'crs') and contains(@template,'spatial_dataset_identifier_code') and contains(@template,'spatial_dataset_identifier_namespace') and contains(@template,'language')]
