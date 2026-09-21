---
name: nih-dmsp
description: >
  Generate an NIH Data Management and Sharing Plan (DMSP) that mirrors the 2026
  NIH DMS Plan format page (NOT-OD-26-046, due dates on or after May 25, 2026):
  seven elements, mostly checkboxes, one limitations text box (300 words max),
  a two-column data table (100 words max), and Genomic Data Sharing (GDS)
  checkboxes. Use whenever a user wants to write, draft, fill out, or check an
  NIH data management plan, data sharing plan, DMSP, or DMS plan, or asks what
  goes in one. Produces a one-page markdown plan plus a separate companion file
  (budget justification language, assumptions, review checklist).
---

# NIH Data Management and Sharing Plan (DMSP) Skill

## Overview

NIH publishes the 2026 DMS Plan as a format page (there is no form page). The
plan must follow that format exactly. It has seven elements:

| # | Element | Response type |
|---|---|---|
| 1 | Maximum appropriate sharing | Yes / No checkbox |
| 2 | Sharing timeline (publication, or end of performance period incl. NCEs) | Yes / No checkbox |
| 3 | Availability for as long as repository/journal policies require | Yes / No checkbox |
| 4 | Limitations on sharing | Free text, 300 words max |
| 5 | Human participant privacy per NOT-OD-22-213 | Yes / No / Not Applicable checkbox |
| 6 | Data table: Expected Data Type, Established Repository or Example | Table, 100 words max |
| 7a | GDS: share large-scale human genomic data per accelerated timelines | Yes / No / Not Applicable checkbox |
| 7b | GDS: able to meet Institutional Certification expectations | Yes / No / Not Applicable checkbox |

The plan itself is short. Checkbox elements get a checkbox and nothing else.
All explanatory material the skill generates (budget language, assumptions,
review checklist) goes in a separate companion file and never on the plan.

If the user's deadline is before May 25, 2026, note this and use the older
narrative format in `references/pre-2026-format.md` instead.

If the user uploads the NIH format page (.docx), read it and follow its
wording and limits. If it differs from this skill, the uploaded template wins;
tell the user what differed.

---

## Step 1: Intake

### Data sensitivity notice

Show this before collecting input:

> **Privacy note:** This plan only needs logistical information about your
> grant, not your science. Please do not paste Specific Aims, preliminary
> data, hypotheses, or unpublished findings. Grant content shared with an AI
> tool may be subject to your institution's data governance policies.

### Intake questions

Ask as one grouped set. Pull answers from context first and only ask for
what is missing. Each has a fallback so the user is never blocked.

| # | Question | Drives | If unknown |
|---|---|---|---|
| 1 | NIH mechanism (R01, R21, U01, K, etc.) | Companion file, IC checks | Assume R01; flag |
| 2 | NIH Institute or Center | IC-specific repository rules | Flag for user to verify |
| 3 | Data types generated, with species and modality (e.g., "mouse lung spatial transcriptomics") | Element 6 | Must answer; a short description is enough |
| 4 | Human participants involved? (Yes / No / Some components) | Elements 4 and 5 | Must answer |
| 5 | Will the project generate large-scale human genomic data? (Yes / No / Unsure) | Element 7 | Unsure: mark per best reading and flag |
| 6 | Preferred repositories, or recommend? | Element 6 | Recommend from `references/repositories.md` |
| 7 | Any known restrictions on sharing? (Yes / No, no details needed) | Element 4 | Assume No; flag |
| 8 | Submission deadline | Format choice | Assume 2026 format |
| 9 | Approximate data volume (optional) | Companion budget language only | Assume ~1 TB; flag |

Never ask for Specific Aims, preliminary data, unpublished findings, or
collaborator details. If the user volunteers them, use only the logistical
facts and do not echo the sensitive content.

---

## Step 2: Repository selection

Match each data type to an established repository. See
`references/repositories.md` for the full list.

| Data type | Repository |
|---|---|
| Raw sequencing reads | NCBI SRA (open) or dbGaP (human, controlled) |
| Processed expression, scRNA-seq, spatial | NCBI GEO; CZ CELLxGENE optional |
| Human clinical / phenotype | dbGaP, ImmPort (NIAID), NIMH Data Archive |
| Radiology imaging | TCIA |
| Microscopy imaging | IDR, BioImage Archive |
| Proteomics | PRIDE, MassIVE |
| Pathogen genomics / variants | SRA plus VEuPathDB or BV-BRC as fits |
| Code and workflows | GitHub archived to Zenodo with a DOI |
| General / mixed | Zenodo, Figshare, OSF |
| NCI-funded | NCI CRDC |

If nothing fits cleanly, use Zenodo and flag it for Program Officer review.

---

## Step 3: Write the plan

Read `references/dmsp-2026-format.md` for element-by-element rules before
writing.

### Output files

- Plan: `DMSP_[Mechanism]_[DataTypeShorthand]_[YYYY-MM-DD].md`
- Companion: `DMSP_[Mechanism]_[DataTypeShorthand]_[YYYY-MM-DD]_companion.md`

No project titles or PI names in filenames.

### Plan structure (reproduce exactly; this is the whole plan)

```
# Data Management and Sharing Plan

1. Will there be maximum appropriate sharing of scientific data underlying
   peer-reviewed publications and other findings resulting from the work
   supported by this award (including preprints, refereed papers reported at
   conferences, and other findings)?

   Yes [x]  No [ ]

2. Will the scientific data underlying peer-reviewed publications be shared by
   the time of publication, or for other findings, by the end of the period of
   performance, which includes no-cost extensions?

   Yes [x]  No [ ]

3. Will shared scientific data be made available for at least as long as
   required by applicable data repository policies and/or journal policies?

   Yes [x]  No [ ]

4. If you answered "no" to elements 1, 2, or 3, or if you anticipate that
   sharing will be limited in some other way, please describe these
   limitations and the ethical, legal, or technical factors for them.

   [Text, 300 words max, or "Not applicable."]

5. If scientific data derived from human research participants will be shared,
   will privacy, rights, and confidentiality of participants be protected as
   outlined in NOT-OD-22-213?

   Yes [ ]  No [ ]  Not Applicable [ ]

6.
   | Expected Data Type | Established Repository or Example |
   |---|---|
   | ... | ... |

7. For studies subject to the NIH Genomic Data Sharing Policy (GDS):

   a. Will you share all large-scale human genomic and associated data in a
      NIH-designated repository according to the accelerated timelines
      expected in the GDS Policy?

      Yes [ ]  No [ ]  Not Applicable [ ]

   b. Do you anticipate that when sharing you will be able to meet the
      expectations of the Institutional Certification in the GDS Policy?

      Yes [ ]  No [ ]  Not Applicable [ ]
```

### Rules

- Omit all italic instructional text from the NIH template. Keep the
  numbered question text.
- No narrative under elements 1, 2, 3, 5, 7a, or 7b. A "No" is explained in
  element 4, never next to the checkbox.
- Element 6 has exactly two columns. Do not add format, volume, access level,
  or timing columns. Timing is covered by element 2; access restrictions go in
  element 4.
- Do not put a headline, IC/mechanism banner, assumptions, budget text, or
  checklist on the plan.

### Length check (required before delivering)

Count words with a script and report the counts to the user:
- Element 4 text: must be 300 words or fewer.
- Element 6 table cell text: must be 100 words or fewer in total.

If either is over, cut it and recount.

---

## Step 4: Companion file

Everything that helps the researcher but is not part of the plan goes here.

1. **Budget justification language.** Use `references/budget-language.md`.
   Two to four sentences for standard projects; more only for large data
   volumes or heavy curation. This text belongs in the budget justification,
   not the DMSP.
2. **Assumptions.** Each default or guess made during intake (mechanism, IC,
   restrictions, GDS applicability, volume).
3. **Researcher review checklist.**
   - Confirm each repository fits the data type and IC expectations
     (https://sharing.nih.gov/other-sharing-policies)
   - If human participants: confirm consent language covers the planned sharing
   - Confirm element 7 applicability with the Program Officer if unsure
   - Confirm budget line items with the grants administrator
   - Paste into the NIH format page and delete remaining italic text

Keep the companion file brief. Do not add an explainer on the format change
unless the user asks.

---

## Reference files

| File | When to read |
|---|---|
| `references/dmsp-2026-format.md` | Always, before writing elements 1 through 7 |
| `references/repositories.md` | When choosing or recommending repositories |
| `references/budget-language.md` | When writing the companion budget section |
| `references/pre-2026-format.md` | Only if the deadline is before May 25, 2026 |
