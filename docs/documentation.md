# Documentation on the use of DCAT-EP

## Datasets, series, and versions

In DCAT-EP, datasets are grouped into dataset series and dataset versions, following the approach defined in [[VOCAB-DCAT-3](https://www.w3.org/TR/vocab-dcat-3/)] - see, in particular, [§12. Dataset series](https://www.w3.org/TR/vocab-dcat-3/#dataset-series) and [§11. Versioning](https://www.w3.org/TR/vocab-dcat-3/#dataset-versions), respectively.

A dataset series groups datasets sharing similar characteristics. A typical case is datasets containing the same data but for different time periods. E.g., data about Members of the European Parliament (MEPs) are split into different datasets, each corresponding to a given Parliamentary Term (PT 1, PT 2, etc.). All these datasets are grouped into a series.

Dataset versions correspond to snapshots of the same dataset. E.g., the MEPs dataset of Parliamentary Term 1 (MEPs PT 1) may need to be updated to correct errors, when MEPs change their data, and/or whenever MEPs join or leave the EP during that Parliamentary Term. No assumption is made on how much frequently a new version is released, which depends on the data management workflow - e.g., the same day can see the release of more than one version.

The following diagram shows the general relationships between series, datasets, and versions, using the MEPs datasets as an example.

```mermaid
flowchart TD
subgraph Series
A(MEPs<br>dcat:DatasetSeries)
subgraph Datasets
direction BT
B0(MEPs PT 1<br>dcat:Dataset)
B1(MEPs PT 2<br>dcat:Dataset)
B2(MEPs PT 3<br>dcat:Dataset)
B3(MEPs PT ...<br>dcat:Dataset)
subgraph Versions
direction LR
C0(MEPs PT 1 - V1<br>dcat:Dataset)
C1(MEPs PT 1 - V2<br>dcat:Dataset)
C2(MEPs PT 1 - V3<br>dcat:Dataset)
end
end
end
A---B0 & B1 & B2 & B3
B0---C0 & C1 & C2
```

### Relationships between series and datasets

Datasets are linked to a series by using property `dcat:inSeries`, as shown in the following diagram:

```mermaid
flowchart BT
B0(MEPs PT 1<br>dcat:Dataset)
B1(MEPs PT 2<br>dcat:Dataset)
B2(MEPs PT 3<br>dcat:Dataset)
B3(MEPs PT ...<br>dcat:Dataset)
A(MEPs<br>dcat:DatasetSeries)
B0 & B1 & B2 & B3--dcat:inSeries-->A
```

Datasets in a series are linked by using property `dcat:prev` and, optionally, its inverse  `dcat:next`.

```mermaid
flowchart RL
B0(MEPs PT 1<br>dcat:Dataset)
B1(MEPs PT 2<br>dcat:Dataset)
B2(MEPs PT 3<br>dcat:Dataset)
B3(MEPs PT ...<br>dcat:Dataset)
B3--dcat:prev-->B2
B2--dcat:prev-->B1
B1--dcat:prev-->B0
```

### Relationships between a dataset and its versions

A dataset is linked to its versions by using property `dcat:hasVersion` and, optionally, its inverse `dcat:isVersionOf`. The link between a dataset and its current version (typically, the latest) is specified by using property `dcat:hasCurrentVersion`.

```mermaid
flowchart TD
B0(MEPs PT 1<br>dcat:Dataset)
C0(MEPs PT 1 - V1<br>dcat:Dataset)
C1(MEPs PT 1 - V2<br>dcat:Dataset)
C2(MEPs PT 1 - V3<br>dcat:Dataset)
B0--dcat:hasVersion-->C0 & C1 & C2
B0--dcat:hasCurrentVersion-->C2
```

Dataset versions are linked by using property `dcat:previousVersion` and, optionally, its inverse `dcat:nextVersion`.

```mermaid
flowchart RL
C0(MEPs PT 1 - V1<br>dcat:Dataset)
C1(MEPs PT 1 - V2<br>dcat:Dataset)
C2(MEPs PT 1 - V3<br>dcat:Dataset)
C2--dcat:previousVersion-->C1
C1--dcat:previousVersion-->C0
```

# References

<dl>

<dt>[VOCAB-DCAT-3]</dt>
<dd><cite>Data Catalog Vocabulary (DCAT) - Version 3</cite>. Riccardo Albertoni; David Browning; Simon Cox; Alejandra Gonzalez Beltran; Andrea Perego; Peter Winstanley. W3C. 10 May 2022. W3C Working Draft. URL: <a href="https://www.w3.org/TR/vocab-dcat-3/">https://www.w3.org/TR/vocab-dcat-3/</a></dd>

</dl>
