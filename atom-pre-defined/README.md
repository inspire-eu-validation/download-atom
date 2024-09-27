# Conformance class: Pre-defined Atom

This conformance class is part of the [Abstract Test Suite for the INSPIRE Download Services Technical Guidance](http://inspire.ec.europa.eu/id/ats/download-atom/master).

## Standardization target type

Atom download service feed with sub-feeds for data sets

## Dependencies <a name="dep"/>

### Direct dependencies

A direct dependency is another conformance class whose requirements must be met by the download service, too.

| Specification | Conformance class | Parameters | 
| ------------- | ----------------- | ---------- |
| [ATOM](#ref_atom) | n/a | n/a |
| [OpenSearch](#ref_opensearch) | n/a | n/a |
| [GeoRSS Simple](#ref_georss_simple) | n/a | n/a |

Note that it was decided that conformance to third-party specifications will be expressed as a dependency to the relevant conformance class(es) in the abstract test suites. Deciding which executable test suites (ETS) to use for this will be decided during the implementation of the INSPIRE ETSs. INSPIRE will not develop its own ETSs for third-party specifications, but instead rely on passing external ETSs (e.g. OGC CITE tests) where available or rely on self-declaration. 

However, where no robust third-party ETS is known, an INSPIRE ATS may include basic tests (e.g. validation against an XML or RELAX-NG schema). In this case the [basic schema validation test](./schema-validation.md) has been added.

### Indirect dependencies

An indirect dependency is another conformance class whose requirements must be met by a related resource.

| Specification | Conformance class | Related resource | Parameters |
| ------------- | ----------------- | ---------------- | ---------- |
| [OpenSearch](#ref_opensearch) | n/a | OpenSearch description | n/a |
 
## External document references

The following abbreviations are used in the test text for referring to external documents:

Abbreviation                     | Document name
-------------------------------- | --------------------------------------------------
INSPIRE <a name="ref_INSPIRE"></a> | [Directive 2007/2/EC of the European Parliament and of the Council of 14 March 2007 establishing an Infrastructure for Spatial Information in the European Community (INSPIRE)](http://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32007L0002&from=EN)
TG DL <a name="ref_TG_DL"></a>   | [INSPIRE Download Services Technical Guidance](https://inspire-mif.github.io/technical-guidelines/services/download-atom-wfs/DownloadServices.pdf)
IR NS <a name="ref_IR_NS"></a>   | [COMMISSION REGULATION (EC) No 976/2009 of 19 October 2009 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards the Network Services](http://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:02009R0976-20101228&from=EN)
IR MD <a name="ref_IR_MD"></a>   | [COMMISSION REGULATION (EC) No 1205/2008 of 3 December 2008 implementing Directive 2007/2/EC of the European Parliament and of the Council as regards metadata](http://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=OJ:L:2008:326:0012:0030:EN:PDF)
ATOM <a name="ref_atom"></a>      | [The Atom Syndication Format](http://tools.ietf.org/html/rfc4287) (RFC 4287)
GeoRSS Simple <a name="ref_georss_simple"></a> | [GeoRSS Simple](http://www.georss.org/simple.html)
OpenSearch <a name="ref_opensearch"></a> | [OpenSearch 1.1 specification, version Draft 5](http://www.opensearch.org/Specifications/OpenSearch/1.1)

## TG Requirement coverage

Based on requirement numbering in [TG DL](#ref_TG_DL).

| Req#  | Description                          | Covered by test(s)                 | IR reference(s)                  |
| ----- | ------------------------------------ | ---------------------------------- | -------------------------------- |
| 1     | Datasets as individual entries       | [Separate dataset individual Atom service feed](./download-service-feed-entry-per-dataset.md) | n/a |
| 2     | Atom specification conformance       | [Schema validation](./schema-validation.md) | n/a |
| 3     | GeoRSS Simple conformance            | [Schema validation](./schema-validation.md) | n/a |
| 4     | OpenSearch conformance               | [Schema validation](./schema-validation.md) | n/a |
| 5     | Download Service Feed title          | [Provide a title element](./download-service-feed-title.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1 |
| 6(1)  | Scenario 1 - Metadata record link for service     | [Provide link to metadata record for Download Service](./download-service-feed-link-to-metadata-record.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1; [IR MD](#ref_IR_MD), section 2.2.4 |
| 6(2)  | Scenario 2 - Metadata elements in the Feed document    | [Provide Download Service metadata elements in the Feed document](./download-service-feed-embedded-metadata-elements.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1; [IR MD](#ref_IR_MD), section 2.2.4 |
| 7     | Download Service Feed self reference | [Download Service feed self-reference link](./download-service-feed-self-reference-link.md) | n/a |
| 8     | OpenSearch Description link          | [Download Service feed link OpenSearch Description document](./download-service-feed-link-opensearch-description-document.md) |[IR NS](#ref_IR_NS), M1, section 2.2.2|
| 9     | Download Service Feed ID             | [Download Service feed HTTP URI](./download-service-feed-id.md) | n/a |
| 10    | Download Service Rights              | [Download Service feed rights element](./download-service-feed-rights-element.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1 |
| 11    | Download Service Updated             | [Download Service feed updated element](./download-service-feed-updated-element.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1 |
| 12    | Download Service Author              | [Download Service feed contact information](./download-service-feed-contact-information.md) |[IR NS](#ref_IR_NS), M1, section 2.2.1 |
| 13    | Spatial Data Set identifiers in Service Feed | [Download Service feed dataset identifiers](./download-service-feed-dataset-identifiers.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1|
| 14    | Dataset metadata record links in Service Feed | [Download Service feed links dataset metadata records](./download-service-feed-links-dataset-metadata-records.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1|
| 15    | Dataset Feed links in Service Feed   | [Download Service feed links dataset feed](./download-service-feed-links-dataset-feed.md) | n/a |
| 16    | WFS Capabilities document link       | [Download Service feed link to WFS Capabilities document](./download-service-feed-wfs-link.md) ||
| 17    | Dataset Feed ID in Service Feed      | [Download Service feed identifiers](./download-service-feed-identifiers.md) |n/a|
| 18    | Dataset Feed title in Service Feed   | [Download Service feed title](./download-service-feed-entry-titles.md) |n/a|
| 19    | Dataset Feed Updated element in Service Feed | [Download Service feed updated element date](./download-service-feed-updated-element-date.md) |n/a|
| 20    | Dataset CRS category elements in Service Feed | [Download Service feed CRS information](./download-service-feed-crs-information.md) | [IR NS](#ref_IR_NS), M1, section 2.2.4|
| 21    | Dataset Feed title in Dataset Feed   | [Dataset Feed title](./dataset-feed-title.md) | [IR NS](#ref_IR_NS), M1, section 2.2.4|
| 22    | Dataset Feed ID in Dataset Feed      | [Dataset feed HTTP URI](./dataset-feed-id.md) |n/a|
| 23    | Dataset Feed Rights in Dataset Feed  | [Dataset feed rights element](./dataset-feed-rights-element.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1 |
| 24    | Dataset Updated in Dataset Feed      | [Dataset feed updated element](./dataset-feed-updated-element.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1|
| 25    | Dataset Author in Dataset Feed       | [Dataset feed contact information](./dataset-feed-contact-information.md) | [IR NS](#ref_IR_NS), M1, section 2.2.1|
| 26    | Dataset content entry                | [Dataset feed link download dataset](./dataset-feed-link-download-dataset.md) | [IR NS](#ref_IR_NS), M1, section 3.1|
| 27    | Dataset format/CRS specific content entries | [Separate entries for each format/CRS combination](./dataset-feed-entries.md) | [IR NS](#ref_IR_NS), M1, section 3.1.3 |
| 28    | Dataset Spatial Object Type link     | [Links for Spatial Object Types](./dataset-feed-links-spatial-object-types.md) | [IR NS](#ref_IR_NS), M1, section 4|
| 29    | Dataset entry content links          | [Dataset feed link download dataset](./dataset-feed-link-download-dataset.md) | [IR NS](#ref_IR_NS), M1, section 3.1 |
| 30    | Dataset entry content media type     | [Use INSPIRE media-types only](./dataset-feed-link-media-type.md) | n/a |
| 31    | Dataset entry content language       | [Language for download link](./dataset-feed-dataset-language.md) | [IR NS](#ref_IR_NS), M1, section 3.1.1 |
| 32    | Sectioned dataset entry links        | [Multiple links for multiple physical files](./dataset-feed-multiple-files.md) |n/a|
| 33    | Sectioned dataset structure          | [Provide guidance for downloading multiple physical files](./dataset-feed-multiple-files-description.md) |n/a|
| 34    | Only INSPIRE media types allowed     | [Use INSPIRE media-types only](./dataset-feed-link-media-type.md) |n/a|
| 35    | Dataset CRS category elements in Dataset Feed | [Each entry has CRS information](./dataset-feed-crs.md) |[IR NS](#ref_IR_NS), M1, section 3.1.3|
| 36    | Alternate languages in Service Feed  | Requirement always met | n/a |
| 37    | Language request parameter           | Requirement always met | n/a |
| 38    | Alternate language feed interlinking | [Language for download link](./dataset-feed-dataset-language.md) | n/a |
| 39    | OpenSearch Description document      | [Download Service feed link OpenSearch Description document](./download-service-feed-link-opensearch-description-document.md) |[IR NS](#ref_IR_NS), M1, section 2.2.2|
| 40    | OpenSearch Description self reference | [OpenSearch Description URI to itself](./opensearch-description-uri-to-itself.md) |n/a|
| 41    | OpenSearch Generic search results URL template | [OpenSearch Description URL generic search queries](./opensearch-description-url-generic-search-queries.md) |n/a|
| 42    | OpenSearch Describe Spatial Data Set Operation template | [OpenSearch Description URL Describe Spatial Dataset operation](./opensearch-description-url-describe-spatial-dataset-operation.md) | [IR NS](#ref_IR_NS), M1, section 4|
| 43    | OpenSearch Get Spatial Data Set Operation template | [OpenSearch Description one URL Get Spatial Dataset operation](./opensearch-description-one-url-get-spatial-dataset-operation.md) |n/a|
| 44    | OpenSearch Spatial Data Set IDs as example queries | [OpenSearch Description Query examples for each dataset](./opensearch-description-query-examples-for-each-dataset.md) | [IR NS](#ref_IR_NS), M1, section 4|
| 45    | OpenSearch supported languages       | [OpenSearch Description provides languages](./opensearch-description-provides-languages.md) |[IR NS](#ref_IR_NS), M1, section 4.1.1|

## Tests

This Conformance Class contains the following tests:

| Identifier                                                        | Status   |
| ----------------------------------------------------------------- | -------- |
| [Dataset feed contact information](./dataset-feed-contact-information.md) | ready for review |
| [Dataset feed HTTP URI](./dataset-feed-id.md) | ready for review |
| [Dataset feed link download dataset](./dataset-feed-link-download-dataset.md) | ready for review |
| [Dataset feed rights element](./dataset-feed-rights-element.md) | ready for review |
| [Dataset Feed title](./dataset-feed-title.md) | ready for review |
| [Dataset feed updated element](./dataset-feed-updated-element.md) | ready for review |
| [Download Service feed contact information](./download-service-feed-contact-information.md) | ready for review |
| [Download Service feed CRS information](./download-service-feed-crs-information.md) | ready for review |
| [Download Service feed dataset identifiers](./download-service-feed-dataset-identifiers.md) | ready for review |
| [Download Service feed HTTP URI](./download-service-feed-id.md) | ready for review |
| [Download Service feed identifiers](./download-service-feed-identifiers.md) | ready for review |
| [Download Service feed link OpenSearch Description document](./download-service-feed-link-opensearch-description-document.md) | ready for review |
| [Download Service feed link to WFS Capabilities document](./download-service-feed-wfs-link.md) | ready for review |
| [Download Service feed links dataset feed](./download-service-feed-links-dataset-feed.md) | ready for review |
| [Download Service feed links dataset metadata records](./download-service-feed-links-dataset-metadata-records.md) | ready for review |
| [Download Service feed rights element](./download-service-feed-rights-element.md) | ready for review |
| [Download Service feed self-reference link](./download-service-feed-self-reference-link.md) | ready for review |
| [Download Service feed title](./download-service-feed-entry-titles.md) | ready for review |
| [Download Service feed updated element date](./download-service-feed-updated-element-date.md) | ready for review |
| [Download Service feed updated element](./download-service-feed-updated-element.md) | ready for review |
| [Each entry has CRS information](./dataset-feed-crs.md) | ready for review |
| [Language for download link](./dataset-feed-dataset-language.md) | ready for review |
| [Links for Spatial Object Types](./dataset-feed-links-spatial-object-types.md) | ready for review |
| [Multiple links for multiple physical files](./dataset-feed-multiple-files.md) | ready for review |
| [OpenSearch Description one URL Get Spatial Dataset operation](./opensearch-description-one-url-get-spatial-dataset-operation.md) | ready for review |
| [OpenSearch Description provides languages](./opensearch-description-provides-languages.md) | ready for review |
| [OpenSearch Description Query examples for each dataset](./opensearch-description-query-examples-for-each-dataset.md) | ready for review |
| [OpenSearch Description URI to itself](./opensearch-description-uri-to-itself.md) | ready for review |
| [OpenSearch Description URL Describe Spatial Dataset operation](./opensearch-description-url-describe-spatial-dataset-operation.md) | ready for review |
| [OpenSearch Description URL generic search queries](./opensearch-description-url-generic-search-queries.md) | ready for review |
| [Provide a title element](./download-service-feed-title.md) | ready for review |
| [Provide guidance for downloading multiple physical files](./dataset-feed-multiple-files-description.md) | ready for review |
| [Provide link to metadata record for Download Service - Scenario 1](./download-service-feed-link-to-metadata-record.md) | ready for review |
| [Provide Download Service metadata elements in the Feed document - Scenario 2](./download-service-feed-embedded-metadata-elements.md) | ready for review |
| [Schema validation](./schema-validation.md) | ready for review |
| [Separate dataset individual Atom service feed](./download-service-feed-entry-per-dataset.md) | ready for review |
| [Separate entries for each format/CRS combination](./dataset-feed-entries.md) | ready for review |
| [Use INSPIRE media-types only](./dataset-feed-link-media-type.md) | ready for review |

## <a name="scenarios"></a> Two scenarios for providing the service metadata

The [TG DL](#ref_TG_DL) gives two options (scenarios) for providing the service metadata in the Download Service Feed of the ATOM services:

* Scenario 1: Use of an Atom 'link' element that links to the metadata record of the Download Service (e.g. in a discovery service). The value of the 'rel' attribute of the Atom 'link' element shall be 'describedby' and the value of the 'type' attribute shall be either 'application/xml' or 'application/vnd.ogc.csw.GetRecordByIdResponse_xml';

* Scenario 2: Publish all the metadata elements directly in Download Service Feed document in accordance with Table 17b.

Since there is no dedicated method in [TG DL](#ref_TG_DL) for the data provider to indicate which scenario has been chosen, the validator software must use the following logic to decide the appropriate set of tests to apply:

- If the Atom 'link' element is present we assume it to be in Scenario 1.
- If the Atom 'link' element is not present, we assume it to be in Scenario 2.


## Open issues

* Is it allowed for more than one Download Service Feed to point to the same Dataset Feed? If yes, and if these Download Service Feeds contain different entries pointing to this Dataset Feed, which parent feed should be used for validation? One example for the possible conflict would be different CRS categories in the Download Service Feed entries.

* Should it be allowed for the Dataset Feed to additionally contain download links to files containing the data in other CRSes than the ones mentioned in it's parent Download Service Feed, or should the CRS (category) list in the Download Service Feed entry and the corresponding Dataset Feed match exactly?

* Is the hreflang attribute mandatory in the Dataset Feed link entries even if the data is provided only in a single language? If so, the test [Language for download link](./dataset-feed-dataset-language) is not automatically testable and the should be removed.

## XML namespace prefixes <a name="namespaces"></a>

The following prefixes are used to refer to the corresponding XML namespaces in all test descriptions:

Prefix         | Namespace
-------------- | -------------------------------------------------
atom           | http://www.w3.org/2005/Atom
georss         | http://www.georss.org/georss
gmd            | http://www.isotc211.org/2005/gmd
inspire\_common| http://inspire.ec.europa.eu/schemas/common/1.0
inspire\_dls   | http://inspire.ec.europa.eu/schemas/inspire_dls/1.0
os             | http://a9.com/-/spec/opensearch/1.1/
xlink          | http://www.w3.org/1999/xlink
xml            | http://www.w3.org/XML/1998/namespace
