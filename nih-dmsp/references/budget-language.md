# NIH DMSP Budget Language Reference

The NIH DMS Policy allows (and expects) researchers to request funding for
data management and sharing activities. Budget items must be described in the
**budget justification narrative** — not in the DMSP itself.

Peer reviewers can comment on the proposed budget. Program Officers assess whether
costs are reasonable and consistent with the DMSP.

---

## What is budgetable

NIH considers the following allowable:

| Category | Examples |
|---|---|
| **Curating data** | Cleaning, reformatting, annotating, converting to community standards |
| **Local storage** | Computing infrastructure for active data management during the project |
| **Repository fees** | Submission or hosting fees charged by domain repositories |
| **De-identification** | Staff time or tools to remove PHI/PII prior to sharing |
| **Metadata & documentation** | Creating README files, data dictionaries, ontology mapping |
| **Personnel** | Percent effort for staff handling data management tasks |
| **Software/tools** | Licenses for data management or sharing tools |

**Not budgetable:** General computing infrastructure unrelated to data sharing;
publication costs (covered separately under open access policy).

---

## Budget language templates

Use these as starting points. Adapt the dollar amounts, staff roles, and data
volumes to match the project. Round numbers are fine at the budget justification
stage.

---

### Template 1: Small computational project, no human subjects

> Data management and sharing costs are estimated at **$X,XXX per year**
> ($X,XXX total over the X-year project period). Costs include approximately
> X% effort of [role, e.g., a research data analyst] for data curation,
> formatting processed datasets to community standards (e.g., AnnData/HDF5
> format), and preparing submission packages for NCBI GEO and SRA. No
> repository submission fees are anticipated, as GEO/SRA are free to submit.
> Storage costs for active data management during the project period are
> included in the institution's existing HPC allocation.

---

### Template 2: Moderate project with human subjects (controlled access)

> Data management and sharing activities are estimated at **$X,XXX per year**.
> Costs include: (1) approximately X% effort of a [role] for data de-identification,
> metadata documentation, and submission to dbGaP (~$X,XXX/year); (2) dbGaP
> submission preparation and coordination with the NIH Data Access Committee
> (~$X,XXX one-time); and (3) local secure storage for protected data during the
> active project period (~$X,XXX/year). Processed summary statistics will be
> deposited in a freely accessible repository at no cost.

---

### Template 3: Large-scale genomics / spatial transcriptomics

> Data management and sharing costs are estimated at **$XX,XXX per year**
> ($XX,XXX total). This project will generate approximately [X TB] of raw
> sequencing data and [X GB] of processed outputs. Estimated costs include:
> (1) X% effort of a bioinformatics analyst for data curation, QC, format
> conversion, and repository submission preparation ($XX,XXX/year); (2) cloud
> or HPC storage for active data management ($X,XXX/year); and (3) archival
> submission to NCBI GEO and SRA (no submission fee). Custom analysis pipelines
> and Seurat/AnnData objects will be archived on Zenodo upon publication at no
> cost. We anticipate no repository access or hosting fees for the primary
> deposition repositories.

---

### Template 4: Minimal data, mostly code/pipelines

> Data management and sharing activities are anticipated to require minimal
> dedicated resources, estimated at **$X,XXX total** over the project period.
> The primary sharable outputs are processed data files (<X GB) and analysis
> code. Processed data will be deposited to [repository] at no cost. Analysis
> code and computational pipelines will be publicly archived on GitHub with a
> Zenodo DOI at the time of associated publications. Approximately X hours of
> staff time annually are budgeted for documentation, metadata preparation, and
> repository submission.

---

## Tips for reviewers and POs

- **Be specific.** Vague language like "data management costs" without detail
  will raise questions. Name the repository, estimate the volume, name the role.
- **Tie costs to the DMSP.** The budget justification should map to what the
  DMSP promises — if the DMSP says data goes to dbGaP, the budget should reflect
  dbGaP-related costs.
- **Don't over-budget.** Reviewers know GEO and SRA are free. Inflating costs
  for free repositories will draw scrutiny.
- **Personnel is usually the biggest item.** A few percent of a postdoc or data
  analyst's time for curation and submission is typically the most defensible cost.
- **Check with your grants administrator** before finalizing numbers. Indirect cost
  rates, institution policies, and subaward structures all affect how budget lines
  are presented.

---

## Generating the budget section in the DMSP output

When producing the DMSP document, append a section titled:

```
## Budget Justification Language for Data Management
```

Use the most relevant template above as a base. Fill in:
- Estimated annual cost (leave as `$X,XXX` if unknown and note this must be filled in)
- Project duration
- Staff role and approximate percent effort
- Repository names (from the Data Table in the DMSP)
- Approximate data volumes

Flag all placeholder numbers with `[FILL IN]` so the researcher knows what
to complete before submission.
