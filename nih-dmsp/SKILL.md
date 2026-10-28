---
name: nih-dmsp
description: >
  Generate an NIH Data Management and Sharing Plan (DMSP) that mirrors the 2026
  NIH DMS Plan format page (NOT-OD-26-046, due dates on or after May 25, 2026):
  seven elements, mostly checkboxes, one limitations text box (300 words max),
  a two-column data table (100 words max), and Genomic Data Sharing (GDS)
  checkboxes. Use whenever a user wants to write, draft, fill out, convert, or
  check an NIH data management plan, data sharing plan, DMSP, or DMS plan, or
  asks what goes in one. Produces the plan as a filled-in NIH format page
  (.docx) plus a separate companion markdown file (budget justification
  language, assumptions, review checklist).
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

The deliverable is the NIH format page itself (.docx) with the checkboxes
ticked, element 4 filled, and the element 6 table populated. This is what the
researcher pastes into or uploads with the application, so it should be ready
to send. All explanatory material (budget language, assumptions, review
checklist) goes in a separate companion markdown file and never on the plan.

If the user's deadline is before May 25, 2026, note this and use the older
narrative format in `references/pre-2026-format.md` instead.

---

## Step 0: Get the template

The plan is built by filling a copy of the NIH DMS Plan format page .docx. In
order of preference:

1. A blank NIH format page the user uploads or points to.
2. A previously completed 2026-format DMSP .docx from the user's own files
   (for example, an earlier plan they wrote). Reuse its structure and replace
   every answer; never carry over the old checkbox states, element 4 text, or
   table rows.
3. If neither is available, ask the user for the blank format page from the
   NIH "Writing a Data Management and Sharing Plan" page. If they cannot
   provide one, fall back to the markdown layout in Appendix A and say so.

If the template's wording or limits differ from this skill, the template wins;
tell the user what differed.

If the user is converting an existing funded plan (pre-2026 narrative) to the
new format, read that plan first and take every answer from it. Record in the
companion file which old section each new element came from, and list any
old sections that were dropped because the new format has no place for them
(typically tools/software, standards, findability, and oversight).

---

## Step 1: Intake

### Data sensitivity notice

Show this before collecting input (skip it when converting a plan the user
has already supplied):

> **Privacy note:** This plan only needs logistical information about your
> grant, not your science. Please do not paste Specific Aims, preliminary
> data, hypotheses, or unpublished findings. Grant content shared with an AI
> tool may be subject to your institution's data governance policies.

### Intake questions

Ask as one grouped set. Pull answers from context (including any existing
plan) first and only ask for what is missing. Each has a fallback so the user
is never blocked.

| # | Question | Drives | If unknown |
|---|---|---|---|
| 1 | NIH mechanism (R01, R21, U01, K, etc.) | Companion file, IC checks | Assume R01; flag |
| 2 | NIH Institute or Center | IC-specific repository rules | Flag for user to verify |
| 3 | Data types generated, with species and modality | Element 6 | Must answer; a short description is enough |
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
| Immunology assays (titers, flow cytometry) | ImmPort |
| Radiology imaging | TCIA |
| Microscopy imaging | IDR, BioImage Archive |
| Proteomics | PRIDE, MassIVE |
| Pathogen genomics / variants | SRA plus VEuPathDB (e.g., PlasmoDB) or BV-BRC as fits |
| Code and workflows | GitHub archived to Zenodo with a DOI |
| General / mixed | Zenodo, Figshare, OSF |
| NCI-funded | NCI CRDC |

If nothing fits cleanly, use Zenodo and flag it for Program Officer review.

---

## Step 3: Decide the answers

Read `references/dmsp-2026-format.md` for element-by-element rules before
deciding.

- Elements 1 to 3: Yes in nearly all cases. A No is explained in element 4.
- Element 4: write plain text (300 words max; 50 to 150 is typical) when any
  of elements 1 to 3 is No or sharing is limited in some other way (controlled
  access, de-identification of participant-derived data, consent limits).
  If nothing is limited, leave the answer area blank in the .docx.
- Element 5: Yes if any data derived from human participants is shared
  (including de-identified sample metadata); Not Applicable otherwise.
- Element 6: two columns only. Keep each Expected Data Type a short label
  that still names species and modality where known (for example,
  "P. falciparum whole-genome sequencing reads", "10X Genomics scRNA/CITE-seq").
  Repository column names the repository only. List the key types; the list
  need not be exhaustive.
- Element 7a and 7b: Not Applicable if no large-scale human genomic data.
  If large-scale non-human genomic data is generated, choose the best reading
  and flag it in the companion file for Program Officer confirmation.

Do not add a headline, IC/mechanism banner, assumptions, budget text, or
checklist to the plan.

---

## Step 4: Build the .docx

Fill a copy of the template with python-docx. The NIH format page uses Word
checkbox content controls (`w14:checkbox` inside `w:sdt`), so toggle the
control's `w14:checked` value and its displayed glyph together; typing a
glyph into a run is not enough.

Locate things by content, not by fixed paragraph index:

- Checkbox groups appear in document order: element 1, 2, 3, 5, 7a, 7b.
  Groups 1 to 3 have two boxes (Yes, No); 5, 7a, 7b have three
  (Yes, No, Not Applicable). Assert the counts before writing.
- Element 4 answer goes in the first empty paragraph after the paragraph
  that starts "If you answered" (or the template's equivalent).
- Element 6 is the first table; keep the header row, deep-copy the first data
  row as a style template, remove existing data rows, and append one row per
  data type.

Reference implementation (adapt paths and answers):

```python
import copy, docx
from docx.oxml.ns import qn

W14 = "http://schemas.microsoft.com/office/word/2010/wordml"

def checkbox_groups(doc):
    groups = []
    for p in doc.paragraphs:
        boxes = [s for s in p._p.iter(qn("w:sdt"))
                 if s.find(".//{%s}checkbox" % W14) is not None]
        if boxes:
            groups.append(boxes)
    return groups

def set_box(sdt, on):
    sdt.find(".//{%s}checked" % W14).set("{%s}val" % W14, "1" if on else "0")
    for t in sdt.iter(qn("w:t")):
        t.text = "☒" if on else "☐"

def fill(template, out, answers, element4, rows):
    # answers: six lists, e.g. [[1,0],[1,0],[1,0],[1,0,0],[0,0,1],[0,0,1]]
    d = docx.Document(template)
    groups = checkbox_groups(d)
    assert len(groups) == 6, len(groups)
    for boxes, want in zip(groups, answers):
        assert len(boxes) == len(want)
        for s, v in zip(boxes, want):
            set_box(s, v)
    if element4:
        paras = d.paragraphs
        i = next(k for k, p in enumerate(paras) if p.text.strip().startswith("If you answered"))
        target = next(p for p in paras[i + 1:] if not p.text.strip())
        for r in list(target.runs):
            r._r.getparent().remove(r._r)
        target.add_run(element4)
    t = d.tables[0]
    tmpl = copy.deepcopy(t.rows[1]._tr)
    for r in list(t.rows)[1:]:
        t._tbl.remove(r._tr)
    for a, b in rows:
        t._tbl.append(copy.deepcopy(tmpl))
        for cell, txt in zip(t.rows[-1].cells, (a, b)):
            for extra in cell.paragraphs[1:]:
                extra._p.getparent().remove(extra._p)
            p = cell.paragraphs[0]
            if not p.runs:
                p.add_run("")
            for r in p.runs[1:]:
                r._r.getparent().remove(r._r)
            p.runs[0].text = txt
    d.save(out)
```

After saving, reopen the file and print each checkbox group's glyphs, the
element 4 text, and the table rows to confirm they match the decided answers.

### Italic instructions

The NIH format page tells applicants to delete the italic instructional text
before submitting. Leave the italics in the draft by default so the
researcher can see the guidance while reviewing, and list "delete italic
template text" in the companion checklist. If the user asks for a
submission-ready copy, remove runs where `run.italic is True` (and paragraphs
that become empty) while keeping the numbered question text.

### Output files

- Plan: `DMSP_[Mechanism]_[ShortName]_JPC.docx` (or the user's own naming
  convention if they have one), saved in the project folder the user is
  working in.
- Companion: `DMSP_[Mechanism]_[ShortName]_[YYYY-MM-DD]_companion.md`.

No PI names or project titles in filenames unless the user's convention
includes them.

### Length check (required before delivering)

Count words with a script and report the counts to the user:
- Element 4 text: must be 300 words or fewer.
- Element 6 table cell text (excluding the header row): must be 100 words or
  fewer in total.

If either is over, cut it and recount.

---

## Step 5: Companion file (markdown)

Everything that helps the researcher but is not part of the plan goes here.
Keep it brief.

1. **Source mapping** (conversions only). Which section of the old plan each
   new element came from, and which old sections were dropped.
2. **Assumptions.** Each default or guess made during intake (mechanism, IC,
   restrictions, GDS applicability, volume), and any data-type rows added
   beyond what the source plan named.
3. **Budget justification language.** Use `references/budget-language.md`.
   Two to four sentences for standard projects. For a post-award conversion,
   note that a new budget justification is probably not needed.
4. **Researcher review checklist.**
   - Confirm each repository fits the data type and IC expectations
     (https://sharing.nih.gov/other-sharing-policies)
   - If human participants: confirm consent language covers the planned sharing
   - Confirm element 7 applicability with the Program Officer if unsure
   - Confirm budget line items with the grants administrator
   - Delete remaining italic template text before submission

Do not add an explainer on the format change unless the user asks.

---

## Appendix A: Markdown fallback layout

Use only when no .docx template is available. Reproduce exactly.

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

   [Text, 300 words max, or blank]

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

---

## Reference files

| File | When to read |
|---|---|
| `references/dmsp-2026-format.md` | Always, before deciding elements 1 through 7 |
| `references/repositories.md` | When choosing or recommending repositories |
| `references/budget-language.md` | When writing the companion budget section |
| `references/pre-2026-format.md` | Only if the deadline is before May 25, 2026 |
