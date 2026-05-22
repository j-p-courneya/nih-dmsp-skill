# nih-dmsp-skill

A Claude skill that generates submission-ready NIH Data Management and Sharing Plans (DMSPs) in the **2026 Pilot Format** (NOT-OD-26-046), required for all applications with due dates on or after May 25, 2026.

Built for the research community. Designed with data sensitivity in mind.

---

## Background

In February 2026, NIH released [NOT-OD-26-046](https://grants.nih.gov/grants/guide/notice-files/NOT-OD-26-046.html), replacing the previous six-element narrative DMSP with a new structured format: a set of Yes/No commitment questions plus a data table. The new format is required starting **May 25, 2026**.

Most existing DMSP examples, templates, and guides still reflect the old format. This skill was built to fill that gap.

---

## What it does

Given a small set of logistical inputs — mechanism, institute, data type, human subjects status, data volume — the skill produces:

- A complete DMSP in the 2026 Pilot Format (Q1–Q5 + Data Table)
- Repository recommendations matched to your data type
- Draft budget justification language for the Research Plan
- A researcher review checklist flagging IC-specific requirements and open questions

**No grant narrative required.** See the [Privacy Design](#privacy-design) section below.

---

## Example output

→ [DMSP_R01_WGS-scRNAseq-HumanSubjects_2026-05-22.md](examples/DMSP_R01_WGS-scRNAseq-HumanSubjects_2026-05-22.md)

This example covers an R01 with whole genome sequencing, bulk RNA-seq, and single-cell RNA-seq from human participants — one of the more complex DMSP scenarios involving mixed open and controlled access.

---

## Privacy design

Grant content is sensitive pre-submission IP. Specific aims, preliminary data, and unpublished hypotheses should not be shared with external AI tools without understanding your institution's data governance policies.

This skill was explicitly designed around that constraint. The intake questions ask only for:

| Input | Example |
|---|---|
| NIH mechanism | R01, R21, U01 |
| NIH Institute / Center | NHGRI, NHLBI, NIAID |
| Data type(s) | "bulk RNA-seq," "clinical imaging," "proteomics" |
| Human participants? | Yes / No / Some components |
| Approximate data volume | "<100 GB," "~1 TB," ">10 TB" |
| Known sharing restrictions? | Yes / No |
| Preferred repository? | Or let the skill recommend |
| Submission deadline | To confirm format version |

None of these reveal your scientific approach, your hypotheses, or your unpublished findings. A complete, useful DMSP can be generated from logistics alone.

> **Institutional AI policy:** Before using any AI tool with grant-related content,
> check your institution's sponsored programs or research compliance office for guidance.
> Policies vary significantly across institutions and are evolving rapidly.

---

## Installation

This skill requires [Claude](https://claude.ai) with skills support enabled.

1. Download [`nih-dmsp.skill`](nih-dmsp.skill)
2. In Claude, open **Settings → Skills**
3. Click **Install skill** and select the downloaded file
4. The skill will be available in all future conversations

---

## Usage

Once installed, trigger the skill by asking Claude something like:

- *"Help me write an NIH data management plan for my R01"*
- *"Generate a DMSP for a genomics grant submitted to NHGRI"*
- *"I need the new 2026 NIH data sharing plan format"*
- *"Write the data management section for my grant — no human subjects, bulk RNA-seq"*

Claude will display the privacy notice, ask the 8 intake questions as a group, and generate your DMSP as a markdown file ready for review and editing.

---

## Skill structure

```
nih-dmsp/
├── SKILL.md                          # Main skill instructions
└── references/
    ├── dmsp-2026-format.md           # Q1–Q5 field specs, word limits, examples
    ├── repositories.md               # NIH-recommended repos by data type
    ├── budget-language.md            # Budget justification templates
    └── pre-2026-format.md            # Legacy six-element format (pre-May 25, 2026)
```

---

## Scope and limitations

- **Format coverage:** Generates the 2026 Pilot Format by default. Falls back to the pre-2026 six-element format for submissions due before May 25, 2026.
- **IC-specific requirements:** The skill flags known IC-specific repository mandates (NHGRI → AnVIL, NCI → CRDC, NIMH → NDA, etc.) but cannot guarantee completeness. Always verify with your Program Officer.
- **Not legal or compliance advice:** The output is a drafting aid. Researchers are responsible for ensuring their DMSP meets all applicable requirements.
- **Budget figures:** All dollar amounts in the budget section are placeholders marked `[FILL IN]`. Final figures require input from your grants administrator.
- **Human review required:** Treat the output as a strong first draft, not a final document.

---

## Contributing

Issues and pull requests welcome. Particularly useful contributions:

- Additional IC-specific repository requirements
- Updated repository recommendations as NIH guidance evolves
- Example outputs for additional data types and mechanisms
- Corrections to field specifications as NOT-OD-26-046 is finalized post-OMB review

---

## License

MIT License. See [LICENSE](LICENSE).

---

## Citation

If this tool saves you time on a funded grant, a star on the repo is appreciated.
If you write about it, feel free to link back here.

---

*Built by [Jean-Paul Courneya](https://github.com/yourhandle) · University of Maryland, Baltimore*
*Last updated: May 2026 · Reflects NOT-OD-26-046*
