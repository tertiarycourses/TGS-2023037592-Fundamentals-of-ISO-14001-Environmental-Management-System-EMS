# Courseware QA Report — v8.0

Course: Fundamentals of ISO 14001 Environmental Management System (EMS)  
Course code: TGS-2023037592  
QA date: 20 August 2026

## A. Source and content alignment — PASS

- Extracted and reviewed all 104 slides in the legacy v7 trainer deck before redevelopment.
- Preserved useful legacy coverage and expanded it using official ISO 14001:2026/current-status sources, the published course page, Singapore NEA, and the user-supplied implementation guides.
- Verified four published learning outcomes, two-day/16-hour duration, TSC identity and the Written Assessment + Case Study design.
- Current-edition boundary is explicit: the material paraphrases the standard and directs formal conformity work to a licensed ISO 14001:2026 copy.
- K1–K6, A1–A8, activities and assessment mappings are documented in `SOURCE-COVERAGE-v8.md`.

## B. Presentation — PASS after fix-and-verify cycle

- Final deck: 157 widescreen slides; editable PowerPoint text, shapes, connectors, charts and hyperlinks.
- Cover uses a topic-specific image generated for the course; title, code, version and organisation remain editable.
- Detailed step-by-step procedures are excluded from the PPT and retained in the Learner Guide/activity packs.
- PowerPoint package validation passed; 157 slides have zero out-of-bounds geometry findings.
- Text extraction found no Lorem Ipsum, generic trainer placeholder, internal legacy path or “For Official Use Only” leakage.
- Independent montage QA identified and drove fixes for a generic trainer placeholder, orphaned title wrapping, the course-access URL, risk-matrix labels, chart semantics, internal source-path exposure and long source URLs.
- Final independent recheck found no remaining blocking visual defect; the corrected energy chart has a horizontal unit note, zero-baseline declaration, single series colour, in-bar values and an unobstructed target line.

## C. Learner Guide, Lesson Plan and activities — PASS

- Learner Guide: DOCX/PDF/Markdown, 30 rendered pages, static page-numbered TOC and detailed procedures for all eight activities.
- Lesson Plan: DOCX/PDF, 7 rendered pages, two-day schedule and slide-map/activity/assessment traceability.
- Activity structure: 8 activity folders; 9 Markdown files and 9 same-basename README PDFs; 8 scenario/checklist PDFs; 8 editable Excel evidence workbooks.
- All eight workbooks load successfully with intended worksheets and data-entry rows.
- Terminology is consistently `activities/`; no learner-facing `labs/` folder is used.

## D. Assessment — PASS with documented fallback

- The live TMS legacy-paper request returned `401 Not authenticated`; no retrieval success was claimed.
- Fallback follows the published and legacy-stated instrument design: 6-question Written Assessment (K1–K6), 1 hour; 4-question connected Case Study (A1–A8), 1 hour.
- Four DOCX files created: two candidate papers and two trainer-only answer keys.
- Rendered structural verifier passed all four: cover-only page 1; candidate information/instructions/grading on page 2; content from page 3; LMS link present; answer-key marking blocks present; no back-page “For Official Use Only”.

## E. Google Drive publication — PASS with disclosed archive exceptions

- Destination identity confirmed: folder ID `12yLNRcT3RMMzPP11z6i9oXWXd4KbPTHQ`.
- Dry-run completed before write; uploader archives/moves superseded files and does not delete Drive content.
- Current deck, guide, plan and candidate-paper MD5 values match local artifacts after upload.
- `Activities ` is the existing verified Drive folder name (trailing space preserved); 34 current files were read back.
- Candidate papers are the only assessment links eligible for LMS-TMS. Direct Drive permission inspection confirms that both candidate papers have explicit `anyoneWithLink` reader access and both trainer answer keys have no `anyone` permission. Anonymous byte-range tests returned DOCX bytes for the candidate papers and HTML access barriers for the answer keys.
- A same-name WA duplicate was moved by exact Drive file ID into `Assessment/archive`; the assessment root now contains one unambiguous current WA paper.
- Two legacy Google-native items could not be moved into archive because Drive returned insufficient permission; they remain disclosed stale items, while current v8 artifacts are present and unambiguous by name/version:
  - legacy personalised v7 trainer presentation;
  - legacy v7 learner-slide PDF.

## F. LMS-TMS and GitHub release — PASS

- Secret-safe LMS-TMS before-snapshot created outside the repository with mode 600.
- TMS dry-run resolved the correct course record and all intended v8 links, including candidate papers only and the current Activities folder.
- Production LMS-TMS write returned HTTP 200; all seven courseware URLs were read back and fetched successfully.
- Snapshot comparison verified that intended nested assessment links match and all non-target course-record fields are unchanged; the temporary snapshot was then removed.
- GitHub publication was restricted to public courseware, learner activities and release documentation. Private `.env`, `assessment/`, `reference/`, build tooling, source assets and QA renders are excluded.
- The stale public repository was replaced on its verified default branch, `master`, using a force-with-lease bound to the pre-release remote SHA; post-push local/remote SHA equality was verified.
