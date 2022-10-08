# Controlled vocabularies used in DCAT-EP

|Prefix|Namespace URI|
|--|--|
|`adms:`|http://www.w3.org/ns/adms#|
|`dcat:`|http://www.w3.org/ns/dcat#|
|`dcterms:`|http://purl.org/dc/terms/|
|`iana:`|https://www.iana.org/assignments/|
|`op-aut:`|http://publications.europa.eu/resource/authority/|

|Vocabulary name|Vocabulary URI|Used in class|With property|
|--|--|--|--|
|EU Vocabularies Access Rights NAL|[`op-aut:access-right`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/access-right)|`dcat:Catalog`, `dcat:Dataset`, `dcat:DatasetSeries`, `dcat:DataService`|`dcterms:accessRights`|
|EU Vocabularies Countries NAL|[`op-aut:country`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/country)|`dcat:Catalog`, `dcat:Dataset`, `dcat:DatasetSeries`, `dcat:DataService`|`dcterms:spatial`|
|EU Vocabularies Dataset Status NAL|[`op-aut:dataset-status`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/dataset-status)|`dcat:Dataset`, `dcat:Distribution`|`adms:status`|
|EU Vocabularies Dataset Themes NAL|[`op-aut:dataset-theme`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/dataset-theme)|`dcat:Dataset`, `dcat:DatasetSeries`, `dcat:DataService`|`dcat:theme`|
|EU Vocabularies File Types NAL|[`op-aut:file-type`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/file-type)|`dcat:DataService`, `dcat:Distribution`|`dcterms:format`|
|EU Vocabularies Frequencies NAL|[`op-aut:frequency`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/frequency)|`dcat:Catalog`, `dcat:Dataset`, `dcat:DatasetSeries`|`dcterms:accrualPeriodicity`|
|EU Vocabularies Languages NAL|[`op-aut:language`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/language)|`dcat:Catalog`, `dcat:CatalogRecord`, `dcat:Dataset`, `dcat:DatasetSeries`, `dcat:Distribution`|`dcterms:language`|
|EU Vocabularies Licences NAL|[`op-aut:licence`](https://publications.europa.eu/en/web/eu-vocabularies/at-dataset/-/resource/dataset/licence)|`dcat:Catalog`, `dcat:DataService`, `dcat:Distribution`|`dcterms:license`|
|IANA Media Types|[`iana:media-types`](https://www.iana.org/assignments/media-types)|`dcat:Distribution`|`dcat:mediaType`|

