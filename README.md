# nih-dmsp-skill

A Claude skill that drafts NIH Data Management and Sharing Plans (DMSPs) in the **2026 format** (NOT-OD-26-046), required for applications with due dates on or after May 25, 2026.

Built for the research community. Designed with data sensitivity in mind.

---

## Background

In February 2026, NIH released [NOT-OD-26-046](https://grants.nih.gov/grants/guide/notice-files/NOT-OD-26-046.html), replacing the six-element narrative DMSP with a structured format page. The new plan is mostly checkboxes: three Yes/No commitments, a limitations text box, a human participant protections checkbox, a two-column data table, and two Genomic Data Sharing (GDS) Policy checkboxes. The whole plan fits on about one page.

Most existing DMSP examples, templates, and guides still reflect the old format. This skill was built to fill that gap.

---

## What it does

Given a small set of logistical inputs (mechanism, institute, data types, human subjects status, GDS applicability), the skill produces two files.

The **plan** is the NIH DMS Plan format page itself (.docx), filled in: checkboxes ticked, element 4 written, and the element 6 table populated. The skill builds it from a blank format page you provide, or from one of your earlier 2026-format plans, so the output is ready to review and submit. If no template is available, it falls back to a markdown version of the same layout. The plan covers each element of the format page:

| # | Element | Response |
|---|---|---|
| 1 | Maximum appropriate sharing | Yes / No |
| 2 | Shared by publication or end of performance period | Yes / No |
| 3 | Available as long as repository/journal policies require | Yes / No |
| 4 | Limitations on sharing | Text, 300 words max |
| 5 | Human participant protections (NOT-OD-22-213) | Yes / No / Not Applicable |
| 6 | Data table: Expected Data Type, Repository | Table, 100 words max |
| 7a, 7b | GDS Policy: accelerated sharing, Institutional Certification | Yes / No / Not Applicable |

Checkbox elements get a checkbox and nothing else. The skill counts words for elements 4 and 6 and reports them. The draft keeps NIH's italic instructions so you can see the guidance while reviewing; ask for a submission-ready copy and the skill removes them.

The skill can also convert a funded pre-2026 narrative plan to the new format, taking every answer from the old plan and recording in the companion file which old section each new element came from.

The **companion file** holds everything that does not belong on the plan: draft budget justification language, the assumptions made during drafting, and a researcher review checklist.

**No grant narrative required.** See [Privacy design](#privacy-design) below.

---

## Example output

- Plan: [DMSP_R01_WGS-scRNAseq-HumanSubjects_2026-05-22.md](examples/DMSP_R01_WGS-scRNAseq-HumanSubjects_2026-05-22.md)
- Companion: [DMSP_R01_WGS-scRNAseq-HumanSubjects_2026-05-22_companion.md](examples/DMSP_R01_WGS-scRNAseq-HumanSubjects_2026-05-22_companion.md)

This example covers an NHGRI R01 with whole-genome sequencing, bulk RNA-seq, and single-cell RNA-seq from human participants. It is one of the more complex scenarios, with mixed open and controlled access and the GDS Policy in scope.

---

## Privacy design

Grant content is sensitive pre-submission IP. Specific aims, preliminary data, and unpublished hypotheses should not be shared with external AI tools without understanding your institution's data governance policies.

This skill was designed around that constraint. The intake questions ask only for:

| Input | Example |
|---|---|
| NIH mechanism | R01, R21, U01 |
| NIH Institute / Center | NHGRI, NHLBI, NIAID |
| Data types, with species and modality | "human bulk RNA-seq," "mouse lung spatial transcriptomics" |
| Human participants? | Yes / No / Some components |
| Large-scale human genomic data? | Yes / No / Unsure |
| Preferred repository? | Or let the skill recommend |
| Known sharing restrictions? | Yes / No |
| Submission deadline | To confirm format version |
| Approximate data volume (optional) | "<100 GB," "~1 TB," ">10 TB" (budget language only) |

None of these reveal your scientific approach, hypotheses, or unpublished findings. A complete DMSP can be drafted from logistics alone.

> **Institutional AI policy:** Before using any AI tool with grant-related content,
> check your institution's sponsored programs or research compliance office for guidance.
> Policies vary across institutions and are changing quickly.

---

## Installation

This skill requires [Claude](https://claude.ai) with skills support enabled.

1. Download [`nih-dmsp.skill`](nih-dmsp.skill).
2. In Claude, open Settings and go to the Skills section (under Capabilities or Customize, depending on app version).
3. If an older version of this skill is installed, remove or disable it first.
4. Upload the downloaded file and make sure the skill is toggled on. If the `.skill` extension is not accepted, rename it to `nih-dmsp.zip` and upload that.
5. Start a new conversation to use it.

---

## Usage

Once installed, trigger the skill by asking Claude something like:

- *"Help me write an NIH data management plan for my R01"*
- *"Generate a DMSP for a genomics grant submitted to NHGRI"*
- *"I need the new 2026 NIH data sharing plan format"*
- *"Write the data management section for my grant: no human subjects, bulk RNA-seq"*

Claude will show the privacy notice, ask the intake questions as a group, and produce the plan as a filled-in NIH format page (.docx) plus a markdown companion file. Upload the blank NIH format page (.docx) or point Claude to a previous 2026-format plan to use as the template; the skill follows the template's wording and limits and tells you if anything differs from what it expected. Without a template, the plan is produced as markdown.

To convert an existing funded plan, attach it and ask, for example: *"Convert this DMSP to the 2026 format."*

---

## Repository structure

```
nih-dmsp-skill/
├── LICENSE
├── README.md
├── examples/                          # Example plan + companion file
├── nih-dmsp/                          # Skill source (edit here)
│   ├── SKILL.md                       # Main skill instructions
│   └── references/
│       ├── dmsp-2026-format.md        # Element-by-element rules, word limits, examples
│       ├── repositories.md            # NIH-recommended repos by data type
│       ├── budget-language.md         # Budget justification templates
│       └── pre-2026-format.md         # Legacy six-element format (pre-May 25, 2026)
└── nih-dmsp.skill                     # Packaged skill, built from nih-dmsp/
```

To rebuild the package after editing the source, run from the repo root:

```bash
rm nih-dmsp.skill
zip -r nih-dmsp.skill nih-dmsp -x "*.DS_Store"
```

---

## Scope and limitations

- **Format coverage:** Drafts the 2026 format by default. Falls back to the pre-2026 six-element format for submissions due before May 25, 2026.
- **IC-specific requirements:** The skill flags known IC-specific repository expectations (NHGRI and AnVIL, NCI and CRDC, NIMH and NDA, etc.) but cannot guarantee completeness. Always verify with your Program Officer.
- **GDS applicability:** Whether a project generates "large-scale" genomic data is a judgment call. The skill records its reading as an assumption for you to confirm.
- **Not legal or compliance advice:** The output is a drafting aid. Researchers are responsible for making sure their DMSP meets all applicable requirements.
- **Budget figures:** Dollar amounts in the companion file are `[FILL IN]` placeholders. Final figures require input from your grants administrator.
- **Human review required:** Treat the output as a first draft.

---

## Contributing

Issues and pull requests welcome. Particularly useful contributions:

- Additional IC-specific repository requirements
- Updated repository recommendations as NIH guidance evolves
- Example outputs for additional data types and mechanisms
- Corrections to element wording or limits if NIH revises the format page

---

## License

MIT License. See [LICENSE](LICENSE).

---

## Citation

If this tool saves you time on a funded grant, a star on the repo is appreciated.
If you write about it, feel free to link back here.

---

*Built by [Jean-Paul Courneya](https://github.com/j-p-courneya) · University of Maryland, Baltimore*
*Last updated: October 2026 · Reflects NOT-OD-26-046 and the 2026 NIH DMS Plan format page*
