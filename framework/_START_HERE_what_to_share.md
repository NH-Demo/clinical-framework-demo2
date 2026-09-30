# SANGRA75 — what to share, with whom

**Index for the Extended_Panel folder. Updated 1 September 2026.**

> **The three pilot documents were audited against the live 28 August dev export on 1 September and
> nine issues were fixed.** Filenames are unchanged, internal versions are now **Start Here (revised
> 1 Sep)**, **Clinic Card v4.2** and **Sweden Pilot Framework v6.2**. Pre-edit copies are in the
> `Superceded` folders, prefixed `PRE-EDIT_`.
>
> The two that mattered: progesterone no longer flags high in any group, so the 50.6 threshold and its
> pregnancy-and-tumour pathway were removed from five places across v6 and the clinic card. And the free
> androgen index in v6 §8.8 read 0.5 and 7.4 while the build and v6's own changelog read 0.7 and 8.7.
> Also fixed: the unscoped troponin T5 rule in Start Here, both documents describing phase-specific
> ranges as live when they are not, the clinic card's missing units and its two internal contradictions,
> the prolactin ceiling, and the FSH flowchart screenshot, which is pulled.

Read this before sending anyone anything. Every file below is current as of today. Anything in a
`SUPERCEDED` or `Superceded` folder is archived on purpose — do not send it, and do not resurrect it
without checking why it was archived (the filename prefix says).

---

## Share now

| File | Who | What it is |
|---|---|---|
| `Education/SANGRA75_Start_Here_2026-08-19.html` | **Pilot doctors** | The debrief walkthrough. ~30 min read. **MANDATORY** pre-reading |
| `Education/SANGRA75_Clinic_Card_v4_2026-08-18.docx` | **Pilot doctors** | In-room action card. **MANDATORY**, bring it to the debrief |
| `Education/SANGRA75_Training_Scenarios_2026-08-27.md` | **Product, Toby, MedEd** | Nine cases to build as test members. Needs questionnaire answers, not just results |
| `Education/SANGRA75_Training_Plan_2026-08-27.md` | **MedEd, ops, Mood clinic** | Staff day, pre-work, f2f design, employee testing as training |
| `Cross-Panel/Sweden Ratification/SANGRA75_Sweden_Pilot_Framework_v6_2026-08-25.docx` | **Reference for all** | The clinical framework. Look things up in it; do not read cover to cover |
| `Cross-Panel/Sweden Ratification/SANGRA75_Platform_Status_2026-08-25.md` | **Send WITH v6, always** | What is actually live and where. v6 describes the design; this is the gap |

**One rule when you send v6:** it goes with the platform status sheet or not at all. v6 describes the
panel as designed, and right now the female hormone build is **dev only** — prod holds zero grouped
rows. Sent alone, v6 reads as a description of what members are getting today, which it is not.

---

## Trainer-only

| File | Why not wider |
|---|---|
| `Pilot/SANGRA75_Mood_Verification_Viewer_2026-08-24.html` | 14 real employee members plus two worked cases. Real people's results — trainers and observers only |
| `Pilot/SANGRA75_Mood_Verification_Extract_14pat_2026-08-24.csv` | The source data behind the viewer |
| `Education/SANGRA75_ConnectedBody_Extended.html` | Opener of Start Here, also a standalone printable poster if MedEd want one for the room |

---

## Internal working files — do not circulate

| File | What it is for |
|---|---|
| `Pilot/SANGRA75_Open_Questions_Register_2026-08-25.xlsx` | The register. Open questions and their reasoning live HERE, not on the task board |
| `Cross-Panel/SANGRA75_Marker_By_Marker_Review_2026-08-25.docx` | The live per-marker work list, 25 comments with threaded status replies |
| `Cross-Panel/SANGRA75_Board_Evidence_2026-08-26.md` | Reasoning lifted off the task board so the board holds actions only |
| `Pilot/SANGRA75_Scan_Tracker_2026-08-11.xlsx` | Scan-by-scan tracking |
| `Pilot/SANGRA_Measuring_Intervals_CORRECTED_2026-08-19.xlsx` | The assay floor and ceiling audit. The only live version — two earlier ones are archived |
| `Cross-Panel/SANGRA75_AdminUI_Pending_Changes_2026-08-24.md` | Mostly executed as of 27 Aug. Re-read before trusting it |
| `Education/SANGRA75_Hormone_Debrief_Narrative_LIVING.md` | Source narrative for education writing. Carries no numbers by design |
| `Education/SANGRA75_Extended_Panel_Education_Provenance_Map.docx` | **STALE** — three revisions behind. Fix or archive |

---

## Owned by other people, do not edit

| File | Owner |
|---|---|
| `Female_Hormones/SANGRA75_For_Sarah_Open_Items_2026-08-24.docx` | Sarah Nolan. Her answers plus our replies, one thread. **Never create a second file for this conversation** |
| `Female_Hormones/SANGRA75_Female_Risk_Range_Template.xlsx` | Sarah Nolan. **Canonical copy unconfirmed** — she asked whether we are in the same spreadsheet and sent a SharePoint link. Settle it before either of you edits again |
| `Female_Hormones/SANGRA_Extended_Female_Hormones_Framework_V1.6_2026-08-12.docx` | Sarah Nolan |
| `Female_Hormones/SANGRA75_Cycle_Phase_Logic_Sarah_2026-08-12.docx` | Sarah Nolan. **Option 1 versus Option 2 lives here** — she believes we built Option 2, we built Option 1 |
| `Cross-Panel/Sweden Ratification/[MARCUS]SWEFramework.docx` | Marcus Olausson. His words, deliberately untouched |
| `Cross-Panel/Sweden Ratification/[MARCUS]_..._Ratification_Pack_v3-Marcus.klar.xlsx` | Marcus Olausson. His returned copy is the record |
| `Male_Hormones_PSA/SANGRA_Framework_Male_Hormones_PSA_V1.8_2026-08-12.docx` | Dariush Baboli |
| `Thyroid_Cardiac_Nutritional/SANGRA_Extended_Thyroid_Cardiac_Framework_V1.5_2026-08-11.docx` | Kishan / Julia |

---

## For engineering

| File | For |
|---|---|
| `Education/SANGRA75_Group_and_Cycle_Phase_By_Hand_2026-08-18.docx` | The phase algorithm. Give them this rather than letting them re-derive it |
| `Female_Hormones/SANGRA75_Female_Eng_Spec_2026-07-27_v4.docx` | Group assignment, section A3 |
| `Cross-Panel/Engineering/SANGRA75_HormoneGroup_Dev_Test_Plan_2026-08-24.md` | The dummy-member test |
| `Cross-Panel/Sweden Ratification/SANGRA75_FE_GroupSpecific_Risk_Ranges_2026-08-18.csv` | The front-end hardcode. **Retire this the moment the questionnaire pipeline lands** — never two sources of phase-specific ranges |

---

## Three things left unresolved by this clean-up

**TWO LIVE SCAN TRACKERS, identical filename, different content.**
`Cross-Panel/Programme Management/SANGRA75_Scan_Tracker_2026-08-11.xlsx` (12 Aug, 34 KB) and
`Pilot/SANGRA75_Scan_Tracker_2026-08-11.xlsx` (25 Aug, 38 KB). The Pilot copy is newer and larger.
This is exactly the failure the archiving rule exists to prevent, and it needs one of them retired —
but not by guessing, because whoever has a link to the other one keeps using it. **Decide which is
canonical, then archive the twin rather than moving the live one.**

**Two thyroid risk-range documents, same date, different content, and they are NOT duplicates:**
`Cross-Panel/SANGRA75_Risk_Ranges_Thyroid_UK_SE_2026-08-18.docx` and
`Risk_Range_Docs/UK_Risk_Ranges_Thyroid_2026-08-18.docx`. The second probably belongs to the UK Health
Chart risk range review rather than SANGRA75, in which case it should move out of Extended_Panel
entirely. Left in place deliberately until confirmed.

**`Education/Sana LMS - Debrief Masterclass.pdf`** (22 MB) is core-panel material, not SANGRA75. Fine
as reference, but it is the biggest file in the folder by a factor of fifteen and belongs with the core
panel.

---

## What was archived on 27 August, and why

| Archived | Reason |
|---|---|
| Debrief Training Pack v3, Training Deck v2, Visual Set v2 | Superseded by Start Here, which was built to replace them after the doctors said the material was overwhelming |
| Start Here SME feedback | All 30 of Sarah's changes applied |
| `body_subscreens.png`, `screen_hierarchy.png` | Early design references, overtaken |
| Measuring Interval Audit, Measuring Intervals WHAT_TO_FIX | Superseded by the CORRECTED version. Three live copies of one audit was the problem |
| Findings And Pre Pilot Actions | Superseded by the task board and the board evidence file |
| Sarah Open Items `.md` | The `.docx` is the live thread |
| SE Framework v5-vs-live comparison, v6 reframe proposal, v4 build sheet | Their job is done; v6 is the output |
