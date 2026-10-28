# NIH 2026 DMS Plan Format Reference

Authority: NOT-OD-26-046. Applies to applications due on or after May 25, 2026.
Source of truth: the NIH DMS Plan format page (blank .docx on the NIH site).
There is no form page; the plan must follow the format page.

The whole plan should fit on about one page. Checkbox elements take a
checkbox only.

---

## Element 1: Maximum appropriate sharing

Checkbox: Yes / No

Mark Yes in nearly all cases. The commitment is to share as openly as possible
and as restricted as necessary, so mixed open and controlled access is still
Yes. Mark No only for a categorical barrier (e.g., tribal sovereignty
agreement), and explain in element 4.

## Element 2: Timeline

Checkbox: Yes / No

The policy timeline is: data underlying publications shared by the time of
publication; other findings shared by the end of the period of performance,
including no-cost extensions. Do not substitute other timelines (such as a
fixed number of months after collection). Mark No only for a documented
reason for delay, explained in element 4.

## Element 3: Availability duration

Checkbox: Yes / No

Established repositories (GEO, SRA, dbGaP, ImmPort, Zenodo, etc.) satisfy
this. A lab website or institutional server without a preservation policy
does not; redirect to a repository rather than answering No.

## Element 4: Limitations

Free text, 300 words maximum.

Complete when any of elements 1 through 3 is No, or when sharing will be
limited in some other way (most often controlled access for human data).
Otherwise leave the element 4 answer area blank on the format page
(in the markdown fallback, leave it blank as well).

State the specific reason for each limitation: consent restrictions,
HIPAA/other legal limits, tribal or cultural considerations, contractual or
proprietary restrictions, or technical barriers with mitigation. "We prefer
not to share" is not a reason. If raw data are controlled and processed data
are open, say which is which.

Aim for well under the limit; 50 to 150 words covers most projects.

Example (human participants):
> This study enrolls human participants. Individual-level genomic and
> clinical data will be shared under controlled access consistent with
> participant consent and the IRB-approved protocol. De-identified aggregate
> data will be shared openly.

## Element 5: Human participant protections

Checkbox only: Yes / No / Not Applicable

- Not Applicable: no data from human research participants will be shared.
- Yes: human participant data will be shared with protections per
  NOT-OD-22-213.
- No: essentially never appropriate.

Do not write a paragraph under element 5. Any description of access controls
belongs in element 4.

## Element 6: Data table

Two columns only: Expected Data Type | Established Repository or Example.
100 words maximum across the table.

Expected Data Type must name the species and modality where known
("mouse lung spatial transcriptomics," "Plasmodium falciparum whole-genome
sequencing reads," "human longitudinal clinical cohort data"). NIH notes the
list does not need to be exhaustive; list the key types.

Repository: name an established repository or a representative example.
No URLs needed.

Example:

| Expected Data Type | Established Repository or Example |
|---|---|
| Mouse lung spatial transcriptomics, raw reads (Visium HD) | NCBI SRA |
| Mouse lung spatial transcriptomics, processed matrices | NCBI GEO |
| Analysis code and workflows | GitHub, archived to Zenodo |

## Element 7: Genomic Data Sharing Policy

Two checkboxes, each Yes / No / Not Applicable. A "No" is explained in
element 4.

- 7a asks about sharing large-scale human genomic and associated data in an
  NIH-designated repository on the GDS accelerated timelines.
- 7b asks whether the institution can meet the GDS Institutional
  Certification expectations.

If the project generates no large-scale human genomic data, mark both Not
Applicable. The GDS Policy also has expectations for large-scale non-human
genomic data; if the project generates such data and the user is unsure how
to mark element 7, choose the best reading and list it as an assumption for
Program Officer confirmation.

## Common mistakes

1. Adding narrative under checkbox elements.
2. Adding columns to the element 6 table.
3. Exceeding 300 words (element 4) or 100 words (element 6).
4. Omitting element 7.
5. Putting budget text, assumptions, or checklists on the plan.
6. Leaving italic template instructions in the submitted plan.
7. Vague data types without species or modality.
