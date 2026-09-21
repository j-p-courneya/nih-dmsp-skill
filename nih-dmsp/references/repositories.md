# NIH-Recommended Data Repositories

Use this reference to select an appropriate repository for each data type.
NIH strongly prefers domain-specific repositories over general-purpose ones
where a domain-specific option exists.

**Key principle:** When in doubt, recommend the most specific repository that
fits, and note that the researcher should confirm with their Program Officer —
especially for IC-specific requirements.

---

## Genomics & Sequencing

| Repository | URL | Best for | Access model |
|---|---|---|---|
| **NCBI GEO** | ncbi.nlm.nih.gov/geo | Processed expression data, microarray, RNA-seq, scRNA-seq, spatial transcriptomics | Open (raw data via SRA link) |
| **NCBI SRA** | ncbi.nlm.nih.gov/sra | Raw sequencing reads (FASTQ, BAM) | Open |
| **dbGaP** | ncbi.nlm.nih.gov/gap | Human genomic + phenotypic data; requires consent for sharing | Controlled (DAR via NIH DAC) |
| **ClinVar** | ncbi.nlm.nih.gov/clinvar | Clinical variant interpretations | Open |
| **EVA** (European Variant Archive) | ebi.ac.uk/eva | Variant data (alternative to dbSNP) | Open |

**Spatial transcriptomics note:** GEO accepts Visium, Visium HD, Xenium, MERFISH,
and other spatial platforms. Deposit processed count matrices + tissue images to GEO;
raw FASTQ to SRA (linked automatically via GEO submission).

---

## Single-Cell Data

| Repository | URL | Best for |
|---|---|---|
| **NCBI GEO** | ncbi.nlm.nih.gov/geo | Primary deposition for scRNA-seq, scATAC-seq |
| **CZ CELLxGENE** | cellxgene.cziscience.com | Interactive exploration + community standard AnnData format |
| **Human Cell Atlas DCP** | data.humancellatlas.org | HCA-affiliated projects |
| **Single Cell Portal** (Broad) | singlecell.broadinstitute.org | scRNA-seq with interactive visualization |

**Best practice for single-cell:** Deposit raw + processed data to GEO; also submit
an `.h5ad` (AnnData) object to CELLxGENE for discoverability.

---

## Clinical & Human Subjects Data

| Repository | URL | Best for | Access model |
|---|---|---|---|
| **dbGaP** | ncbi.nlm.nih.gov/gap | Genomic + phenotypic data with consent requirements | Controlled |
| **NIMH Data Archive (NDA)** | nda.nih.gov | Mental health, brain, behavioral data | Controlled |
| **NCATS N3C** | covid.cd2h.org/N3C | EHR/clinical data (COVID and beyond) | Controlled |
| **PCORnet** | pcornet.org | Patient-centered outcomes research | Controlled |
| **SEER** (NCI) | seer.cancer.gov | Cancer epidemiology (for NCI-funded work) | Open/Controlled |

---

## Imaging

### Radiology / Medical Imaging

| Repository | URL | Best for |
|---|---|---|
| **TCIA** (The Cancer Imaging Archive) | cancerimagingarchive.net | Cancer radiology: CT, MRI, PET, pathology |
| **NIMH Data Archive** | nda.nih.gov | Neuroimaging (MRI, fMRI, EEG) |
| **OpenNeuro** | openneuro.org | BIDS-format neuroimaging datasets |
| **FITBIR** | fitbir.nih.gov | Traumatic brain injury imaging |

### Microscopy / Bioimaging

| Repository | URL | Best for |
|---|---|---|
| **BioImage Archive** (EMBL-EBI) | bioimage.info | General bioimaging |
| **Image Data Resource (IDR)** | idr.openmicroscopy.org | Reference image datasets with metadata |
| **Cell Image Library** | cellimagelibrary.org | Cell biology microscopy |

---

## Proteomics & Metabolomics

| Repository | URL | Best for |
|---|---|---|
| **PRIDE** | ebi.ac.uk/pride | Mass spectrometry proteomics |
| **MassIVE** | massive.ucsd.edu | Mass spectrometry data (GNPS for metabolomics) |
| **MetaboLights** | ebi.ac.uk/metabolights | Metabolomics studies |
| **Metabolomics Workbench** | metabolomicsworkbench.org | NIH-funded metabolomics |

---

## Structural Biology

| Repository | URL | Best for |
|---|---|---|
| **PDB** (RCSB) | rcsb.org | Macromolecular structures |
| **EMDB** | ebi.ac.uk/emdb | Cryo-EM density maps |
| **BMRB** | bmrb.io | NMR spectroscopy data |

---

## General / Multidisciplinary

Use these when no domain-specific repository fits, or for supplementary files.

| Repository | URL | Notes |
|---|---|---|
| **Zenodo** | zenodo.org | CERN-hosted, free, DOI-minting, 50 GB/dataset default |
| **Figshare** | figshare.com | Good for figures, datasets, code |
| **OSF** (Open Science Framework) | osf.io | Preprints, protocols, datasets |
| **Harvard Dataverse** | dataverse.harvard.edu | General research data |
| **Dryad** | datadryad.org | Ecology, evolutionary biology (fee-based) |

---

## Code & Software

| Repository | URL | Notes |
|---|---|---|
| **GitHub + Zenodo** | github.com + zenodo.org | Archive a GitHub release to Zenodo for a citable DOI |
| **Code Ocean** | codeocean.com | Reproducible computational capsules |
| **Bioconductor** | bioconductor.org | R packages for bioinformatics |

NIH expects analysis code and pipelines to be shared alongside data where feasible.
Recommend GitHub + Zenodo archiving for any custom code.

---

## IC-Specific Requirements

Some NIH Institutes have repository mandates beyond the trans-NIH policy.
Always check the specific FOA and IC policies.

| IC | Specific requirement |
|---|---|
| **NHGRI** | Large-scale genomic data → dbGaP or AnVIL |
| **NCI** | Cancer data → NCI CRDC repositories (GDC, TCIA, etc.) |
| **NIMH** | Mental health / brain data → NDA |
| **NHLBI** | BioData Catalyst (BDC) for genomic + clinical data |
| **NIDDK** | NIDDK Central Repository for some programs |
| **NEI** | eyeGENE for genetic eye disease data |

When drafting for a specific IC, flag these requirements in the `> **Assumptions:**`
block and instruct the researcher to verify.
