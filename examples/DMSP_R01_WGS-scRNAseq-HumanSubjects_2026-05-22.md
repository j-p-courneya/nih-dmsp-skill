# NIH Data Management and Sharing Plan
## R01 | NHGRI | Bulk RNA-seq / Single-cell RNA-seq / Whole Genome Sequencing
Prepared: 2026-05-22 | Format: 2026 Pilot (NOT-OD-26-046)

---

> **Privacy note:** This document was generated using only logistical inputs
> (mechanism, institute, data types, human subjects status, and data volume).
> No grant narrative, specific aims, or preliminary data were used or required.

---

## Data Management and Sharing Plan (2026 Pilot Format — NOT-OD-26-046)

**Q1. Maximum appropriate sharing:** Yes

**Q2. Sharing by required timelines:** Yes

**Q3. Data availability duration:** Yes

**Q4. Limitations on data sharing:** This project generates genomic and associated
phenotypic data from human participants. Raw genomic data and identifiable clinical
variables will be deposited under controlled access consistent with participant
informed consent and IRB protocol. De-identified summary statistics and processed
expression matrices will be made openly available. Access to controlled-access data
requires a Data Access Request reviewed by the NIH Data Access Committee, consistent
with NOT-OD-22-213.

**Q5. Human participant data protections:** Yes

Raw genomic sequences and linked phenotypic data will be deposited in dbGaP under
controlled access. Applicants for data access must submit a Data Access Request
through the dbGaP system, subject to NIH DAC review. All data will be de-identified
per HIPAA Safe Harbor standards prior to submission, consistent with participant
consent and the approved IRB protocol.

---

## Data Table

| Data Type | Format | Est. Volume | Repository | Access Level | Sharing Timeline |
|---|---|---|---|---|---|
| Whole genome sequencing reads (human) | FASTQ, CRAM | ~5 TB | dbGaP | Controlled | Upon associated publication or by end of performance period, whichever is first |
| Bulk RNA-seq reads (human) | FASTQ | ~2 TB | dbGaP | Controlled | Upon associated publication or by end of performance period, whichever is first |
| Single-cell RNA-seq reads (human) | FASTQ | ~1 TB | dbGaP | Controlled | Upon associated publication or by end of performance period, whichever is first |
| Processed gene expression count matrices (de-identified) | CSV, HDF5 | ~20 GB | NCBI GEO | Open | Upon associated publication |
| Processed single-cell objects (de-identified) | .h5ad (AnnData) | ~10 GB | NCBI GEO + CZ CELLxGENE | Open | Upon associated publication |
| Variant calls / VCF files (de-identified, population-level) | VCF | ~50 GB | dbGaP | Controlled | Upon associated publication |
| Analysis code and bioinformatics pipelines | R, Python, Nextflow | <1 GB | GitHub + Zenodo (DOI-archived) | Open | Upon associated publication |

---

## Budget Justification Language for Data Management

Data management and sharing costs are estimated at **$[FILL IN] per year**
($[FILL IN] total over the [FILL IN]-year project period). This project will
generate approximately 8 TB of raw sequencing data and ~80 GB of processed
outputs from human participants. Estimated costs include: (1) approximately
[FILL IN]% effort of a bioinformatics analyst for data de-identification, QC,
format conversion to community standards, metadata documentation, and dbGaP
submission preparation (~$[FILL IN]/year); (2) one-time dbGaP submission
coordination costs (~$[FILL IN]); and (3) secure local storage for protected
data during the active project period (~$[FILL IN]/year). De-identified processed
data will be deposited to NCBI GEO and CZ CELLxGENE at no cost. Analysis
pipelines will be archived on Zenodo upon publication at no cost.

---

## Researcher Review Checklist

Before submitting this plan:

1. **Repository** — Confirm with your Program Officer that dbGaP is the
   appropriate controlled-access repository for your data type. NHGRI may
   also require AnVIL for large-scale genomic datasets — verify this applies
   to your project: https://sharing.nih.gov/other-sharing-policies
2. **IC-specific requirements** — Check your specific FOA for repository
   mandates beyond the trans-NIH policy.
3. **Consent language** — Confirm your IRB-approved consent form covers future
   data sharing through NIH repositories. If consent was obtained before 2023,
   review whether re-consent is needed.
4. **Data Table volumes** — Update estimated volumes once sequencing scope is
   finalized with your core facility.
5. **Budget placeholders** — Fill all `[FILL IN]` values in consultation with
   your grants administrator before submission.
6. **GitHub visibility** — Ensure your analysis code repository will be made
   public at the time of publication and that a Zenodo DOI is minted.

---

> **Assumptions made in this draft:**
> - Mechanism assumed R01; adjust header and budget scale for other mechanisms.
> - IC assumed NHGRI based on genomics data types; update if submitting to NHLBI,
>   NCI, NIAID, or another IC — repository requirements differ.
> - Human subjects = Yes; controlled access via dbGaP applied throughout.
> - Data volumes are illustrative estimates — update to reflect your actual scope.
> - All human data assumed to require controlled access; if some data are
>   fully de-identified and consent allows open sharing, adjust access levels
>   in the Data Table accordingly.

---

*This plan was generated using the NIH DMSP Skill (2026 Pilot Format, NOT-OD-26-046),
a community tool available at [github.com/yourhandle/nih-dmsp-skill]. The 2026 format
is required for all NIH applications with due dates on or after May 25, 2026, replacing
the previous six-element narrative. The underlying 2023 DMS Policy has not changed.*
