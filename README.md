# Global University AI Policy Audit 2026

An open dataset of **186 audit records** covering whether universities publish official
guidance on student/staff use of generative AI. Compiled 2026-10-14 by Study Intelligence
(aclas.si) as research for *The Second Printing Press: Higher Education for the Intelligence Age*.

## Headline numbers

| Sample | Rows | Published AI policy (YES) | No policy (NO) | Unclear |
|---|---|---|---|---|
| QS 2026 ranks 1–50 | 50 | 46 (92%) | 1 | 3 |
| QS 2026 ranks 51–100 | 49 | 43 | 0 | 6 |
| QS 2026 ranks 101–150 | 50 | 38 | 6 | 6 |
| Global South flagships | 37 | 17 (46%) | 17 | 3 |
| **Total** | **186** | **144 (77%)** | **24** | **18** |

Key finding: **not one of the top-100 universities imposes a campus-wide AI ban.**
The global norm is delegated permission — instructors set per-course AI rules, students
disclose AI use. The policy gap maps onto the wealth gap: 92% of the top 50 publish
guidance vs 46% of Global South flagships.

## Files

| File | Format | Description |
|---|---|---|
| `ai-policy-audit-2026.csv` | CSV (UTF-8) | 186 rows, 14 columns |
| `ai-policy-audit-2026.json` | JSON | Same data + dataset metadata |
| `METHODOLOGY.md` | Markdown | How the audit was conducted, definitions, caveats |
| `parse.py` | Python 3 | The exact script that generated CSV/JSON from the raw audit tables |
| `CITATION.cff` | CFF | Machine-readable citation |

## Columns

| Column | Description |
|---|---|
| `id` | Stable row id, e.g. `qs-14`, `gs-10` (`-2` suffix where QS ranks tie) |
| `sample` | `qs_top_50` / `qs_51_100` / `qs_101_150` / `global_south` |
| `rank` | QS 2026 rank as printed in source (`=17` = tied rank); null for Global South |
| `university` | Institution name |
| `country` | Country (Global South sample only) |
| `official_domain` | University's official domain (QS samples only) |
| `has_policy` | `YES` / `NO` / `UNCLEAR` |
| `policy_url` | First URL found in the source cell (null when none) |
| `policy_url_raw` | Original cell text when it contained more than just the URL |
| `page_title` | Title of the policy page |
| `date_info` | Date / last-updated as shown on the page (often "Not shown") |
| `scope` | Who the policy covers, e.g. `student-facing / exams-integrity` |
| `note` | Auditor's one-line note |
| `name_overlap` | `true` for the 30 rows (15 universities) audited in more than one sample |

## Honest notes on the numbers

- The published summary said "187 universities". The source tables contain **186 data rows**
  covering **171 unique university names** — 15 names appear in two samples (the rank-band
  files overlap: e.g. TU Delft at QS 47 and QS 61). Rows are kept as audited; `name_overlap`
  flags them. Deduplicate on `university` if you need institution-level counts.
- `UNCLEAR` (18) means "could not verify", not "confirmed absent" — dead links,
  portal-gated intranets and non-English sites are the main causes. True adoption is
  likely higher than 77%.
- ~5 of the Global South YES cases are faculty/school-level rather than university-wide.
- Snapshot date: **2026-10-14**. Policies are being published monthly; treat as a snapshot,
  not a live registry. Contributions and corrections welcome via issues/PRs.

## License

[CC-BY-4.0](LICENSE) — use it, build on it, just cite it.

## Citation

```bibtex
@dataset{studyintelligence2026aipolicyaudit,
  author = {{Study Intelligence}},
  title = {Global University AI Policy Audit 2026},
  year = {2026},
  publisher = {Study Intelligence (aclas.si)},
  doi = {pending},
  url = {https://aclas.si/data/ai-policy-audit-2026}
}
```

See `CITATION.cff` for the machine-readable version.
