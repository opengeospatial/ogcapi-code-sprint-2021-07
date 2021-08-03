|**Queryables**|**Obligation**|**Description**|**ISO 19115-1 (for dataset metadata)**|**ISO Obligation**|**ISO Definition**| **Notes** | 
|--------------| -------------|---------------|--------------------------------------|------------------|-----------------|--------|
 | recordId | M | A unique record identifier assigned by the server. | //mdb:MD\_Metadata<br> /mcc:MD\_Identifier | M | Unique identifier for the metadata record |  | 
 | recordCreated | O  | The date this record was created in the server.  | //mdb:MD\_Metadata<br> /mdb:dateInfo<br> /cit:CI\_Date<br>  /cit:date <br> \--With--<br> /cit:dateType<br> /cit:CI\_DateTypeCode @codeListValue=“creation” |  M  | date(s) associated with the metadata <br> NOTE Creation date must be provided,others can also be provided  |  |
 | recordUpdated  | O | The most recent date on which the record was changed.  | //mdb:MD\_Metadata<br> /mdb:dateInfo<br> /cit:CI\_Date<br>  /cit:date <br> \--With--<br> /cit:dateType<br> /cit:CI\_DateTypeCode @codeListValue=“lastUpdate”   | O | date(s) associated with the metadata <br> NOTE Creation date must be provided, others can also be provided  | |
 | links | O | A list of links for navigating the API. | For link to self <br>//mdb:MD\_Metadata/mdb:metadataLinkage<br>For link to alternate source - <br>//mdb:MD\_Metadata/mdb:alternativeMetadataReference<br>For link to parent - <br>//mdb:MD\_Metadata/mdb:parentMetadata | O | Not sure how to best map "collection where this record is a part of" or "links to related records". What goes into \`links\` and what goes into \`associations\`? | 
 | type | M | The nature or genre of the resource.   | //mdb:MD\_Metadata<br> /mdb:metadataScope<br> /mdb:MD\_MetadataScope<br>  /mdb:resourceScope | M | the scope/type of resource for which metadata is provided. <br>From codelist - MD\_ScopeCode  |  |
 | title | M|  A human-readable name given to the resource. | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> //mri:MD\_DataIdentification<br> /mri:citation<br>  /cit:CI\_Citation<br>   /cit:title | M | name by which the cited resource is known | |
 | description | O | A free-text description of the resource. | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:citation<br>   /cit:CI\_Citation<br>    /cit:abstract  | M | brief narrative summary of the resource  | |
 | keywords | O | A list of keywords or tag associated with the resource.  | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:descriptiveKeywords<br>   /mri:MD\_Keywords<br>    /mri:keyword | O | commonly used word(s) or formalised word(s) or phrase(s) used to describe the subject | |
 | keywordsCodespace | O | A reference to a controlled vocabulary used for the keywords property.  | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:descriptiveKeywords<br>   /mri:MD\_Keywords<br>    /mri:thesaurusName |  O | name of the formally registered thesaurus or a similar authoritative source of keywords  | |
 | language | O | This refers to the natural language used for textual values.  | For the record-<br>//mdb:MD\_Metadata<br> /mdb:defaultLocale<br>For the resource-<br>//mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mdb:defaultLocale | O | language and character set used for documenting metadata<br>Or<br>language and character set used within the resource | Is this for the record or the resource? |
 | externalId | O | An identifier for the resource assigned by an external entity. | //mdb:MD\_Metadata<br> /mdb:identificationInfo <br> /mri:MD\_DataIdentification<br>  /mri:citation<br>   /cit:CI\_Citation<br>    /cit:identifier |  O | value uniquely identifying an object within a namespace | Part of the CI\_Citation class. Used in multiple locations | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:citation<br>   /cit:CI\_Citation<br>    /cit:date<br>       \--With--<br>     /cit:dateType<br>      /cit:CI\_DateTypeCode <br>       @codeListValue=“creation” | reference date for the cited resource | |
 | updated | O | The more recent date on which the resource was changed.  | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:citation<br>   /cit:CI\_Citation<br>    /cit:date<br>       \--With--<br>     /cit:dateType<br>      /cit:CI\_DateTypeCode <br>       @codeListValue=“lastUpdate”  | O | reference date for the cited resource | |
 | publisher | O | The entity making the resource available.  | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:pointOfContact<br>     \--With--<br>  /cit:role<br>   /CI\_RoleCode<br>    @codeListValue=“publisher”<br>      —And/Or—<br> /mdb:distributionInfo<br> /mrd:MD\_Distribution<br>  /mrd:distributor<br>   /mrd:MD\_Distributor<br>    /mrd:distributorContact | O | | At least 3 posible locations. Could also be captured under dataset citation citedResponsibleParty                                                                 |
 | themes | O | A knowledge orgnaization system used to classify the resource.  | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>   /mri:topicCategory | O | main theme(s) of the resource<br><br>from enumeration “MD\_TopicCategoryCode” | |
 | formats | O | A list of available distributions for the resource. | //mdb:MD\_Metadata<br> /mdb:distributionInfo<br> /mrd:MD\_Distribution<br>  /mrd:MD\_Format<br> | O | description of the computer language construct that specifies the representation of data objects in a record, file, message, storage device or transmission channel |  |
 | contactPoint | O | An entity to contact about the resource.  | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:pointOfContact<br>     \--With--<br>  /cit:role<br>   /CI\_RoleCode<br>   @codeListValue=“pointOfContact” | O | identification of, and means of communication with, person(s) and organisation(s) associated with the resource  |
 | license  | O | A legal document under which the resource is made available.  |  //mdb:MD\_Metadata <br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:resourceConstraints<br>   /mco:MD\_LegalConstraints<br>With either<br>  /mco:accessConstraints<br>or <br> /mco:useConstraints <br>  /mco:MD\_RestrictionCode <br>    @codeListValue=“license” | O | restrictions and legal prerequisites for accessing and using the resource or metadata | both license and copyright are captured as legal constraints |
 | rights | O | A statement that concerns all rights not addressed by the license such as a copyright statement.  | //mdb:MD\_Metadata <br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:resourceConstraints<br>   /mco:MD\_LegalConstraints<br>With either<br>  /mco:accessConstraints<br>or <br> /mco:useConstraints <br>  /mco:MD\_RestrictionCode <br>    @codeListValue=“copyright” | O  |   | both license and copyright are captured as legal constraints |
 | extent | O | The spatio-temporal coverage of the resource.   | //mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:extent<br>   /gex:EX\_Extent |O | spatial and temporal extent of the resource |   |
 | associations  |  O  | A list of links for accessing the resource, links to other resources associated with this resource, etc. |  For the resource -<br>//mdb:MD\_Metadata<br> /mdb:distributionInfo<br> /mrd:MD\_Distribution<br>For associated data -<br>//mdb:MD\_Metadata<br> /mdb:identificationInfo<br> /mri:MD\_DataIdentification<br>  /mri:asssociatedResource | O |  | Multiple locations posible. Two most common listed. |