# Download service feed: Provide Download Service metadata elements in the Feed document

**Purpose**: The Download Service Feed shall contain the INSPIRE Metadata for the Download Service in accordance with [Table 17b](#table17b).

**Prerequisites**

This test only applies to [Scenario 2](./README.md#scenarios). Otherwise, the test case is skipped.

**Test method**

In the Download Service Feed document performs the following checks:

* check that the [feed subtitle](#subtitletitle) is not empty.
* check that the keyword indicating the [spatial data service category](https://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory) is provided through the element [feed category](#category).

In addition, check manually that:

* if the service is conformant to one or more specifications, the degree of conformity equal to "conformant" shall be declared using a [feed category](#categoryConf) element for each specification against which the service is conformant (e.g., _\<category scheme="http://data.europa.eu/eli" term="[http://data.europa.eu/eli/reg/2009/976](http://data.europa.eu/eli/reg/2009/976)">_).


**Reference(s)**:

* [TG DL](./README.md#ref_TG_DL), Requirement 6 (2)


**Test type**: Automated + Manual

**Notes**

Table 17b  <a name="table17b"></a>: Mapping of INSPIRE metadata elements to Atom for scenario 2

| **INSPIRE Metadata element**<br>(***M***andatory - ***C***onditional) | **Atom** | **Fallback** | **Test covered by specific TG requirement** |
|---|---|---|---|
| Resource Title (M) | _/feed/title_ |  | [Requirement 5](./download-service-feed-title.md) |
| Resource Abstract (M) | _/feed/subtitle_ |  |  |
| Resource Type (M) | - | Is by default “service” |  |
| Resource Locator (C) | _/feed/link[@rel=""self""]_ in the top Atom feed | Resource Locator of the data set | [Requirement 7](./download-service-feed-self-reference-link.md) |
| Coupled Resource (C) | _/feed/entry/link[@rel=""describedby""]_ in the top Atom feed |  | [Requirement 14](./download-service-feed-links-dataset-metadata-records.md) |
| Spatial Data Service Type (M) | - | _gmd:MD_Metadata/gmd:distributionInfo/gmd:MD_Distribution/_<br>_gmd:transferOptions/gmd:MD_DigitalTransferOptions/_<br>_gmd:onLine/gmd:CI_OnlineResource/gmd:applicationProfile_ <br> in the ISO/TS 19139:2007 dataset metadata record |  |
| Keyword (M) | -/feed/category_; note that a keyword indicating the [spatial data service category](https://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory) is required, see example below this table. |  |  |
| Geographic Bounding Box (M) | - | Geographic Bounding Box of the data set |  |
| Temporal Reference (M) | _/feed/updated_ |  | [Requirement 11](./download-service-feed-updated-element.md)  |
| Spatial Resolution (C) | - | Spatial Resolution of the data set |  |
| Conformity (M) | /feed/category element | Using a _/feed/category_ element for each specification against which the service is conformant |  |
| Conditions for Access and Use (M) | - | _identificationInfo/*/resourceConstraints/*/accessConstraints_ in the ISO/TS 19139:2007 metadata record dataset |  |
| Limitations on Public Access (M) | _/feed/rights_ in the top Atom feed |  | [Requirement 10](./download-service-feed-rights-element.md)  |
| Responsible Organisation (M) | _/feed/author_ in the top Atom feed |  | [Requirement 12](./download-service-feed-contact-information.md)  |
| Metadata Point of Contact (M) | _/feed/author_ in the top Atom feed |  | [Requirement 12](./download-service-feed-contact-information.md)  |
| Metadata Date (M) | /feed/updated |  | [Requirement 11](./download-service-feed-updated-element.md) |
| Metadata Language (M) | Other supported language (if any) will be mapped to the _xml:lang_ | _gmd:MD_Metadata/gmd:language/gmd:LanguageCode_ in dataset metadata for main language |  |


* Example for the [spatial data service category](https://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory):

```xml
<category term="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory/infoFeatureAccessService" scheme="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory"/>
```

* The test for the Spatial Data Service Type metadata element is performed during the validation of the related Dataset metadata by the [Conformance Class 8: INSPIRE data sets and data set series linked service metadata](https://github.com/inspire-eu-validation/metadata/blob/2.0/ds-linked-service/README.md).

* The metadata elements "Responsible Organisation" and "Metadata Point Of Contact" are mapped to the _/feed/author_ element. This means that the Metadata Point Of Contact is assumed to be the same as the Responsible Organisation.

* The metadata elements "Temporal Reference" and "Metadata Date" are mapped to the _/feed/updated_ element. This means that the last update of the service metadata is assumed equal to the update date of the service.

## Contextual XPath references

The namespace prefixes used as described in [README.md](./README.md#namespaces).

Abbreviation                                               |  XPath expression
---------------------------------------------------------- | -------------------------------------------------------------------------
Resource Abstract (_feed/subtitle_) <a name="subtitletitle"></a>  | /atom:feed/atom:subtitle
Keyword (_feed/category_) <a name="category"></a>                 | /atom:feed/atom:category @term="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory/infoFeatureAccessService"<br> @scheme="http://inspire.ec.europa.eu/metadata-codelist/SpatialDataServiceCategory"
Conformity (_feed/category_) <a name="categoryConf"></a>          | /atom:feed/atom:category
