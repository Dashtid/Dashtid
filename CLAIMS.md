# CLAIMS.md - verification ledger for README.md

Not rendered on the GitHub profile (only `README.md` is). This file exists so every
checkable claim on the profile page has a command next to it and can be re-run.

All rows verified **2026-09-14** against the README as it stands after that day's edit, and
**re-run 2026-09-19 before the first commit** - which caught one change already: purl2cpe #32
merged on 2026-09-15, so the headline moved from 14/7 to 15/8 and its row moved from the open-PR
sentence into the table. Five days was enough for the page to drift. Re-run before every edit.
Commands are `gh` / `curl` as shown; `gh` runs as the authenticated user `Dashtid`
(`gh api user --jq .login` -> `Dashtid`).

Re-verify after any edit to the page, and after any upstream PR merges or closes.

## Why per-repo searches, not one global search

The global form (`gh search prs --author Dashtid --merged`) caps its result set and
undercounts. Every count below comes from a search **scoped to one repository**, and the
headline on line 16 is the sum of those seven numbers - not a separately measured figure.

## Ledger

| README line | Claim | Verified by | Result (2026-09-14) |
|---|---|---|---|
| 7 | Current-employment statement. Content deliberately not reproduced here. | Not verified in this pass - out of scope by owner decision (public CV fact). | UNVERIFIED BY DESIGN |
| 9-10 | Focus statement: AI security and the regulatory evidence AI-enabled devices need; building toward product and application security engineering. | No external verifier - a statement of current work and intent, not a checkable fact. | NOT CHECKABLE |
| 12 | `https://dashti.se` resolves | `curl -s -o /dev/null -w "%{http_code}" -L https://dashti.se` | `200` |
| 12 | LinkedIn profile `in/david-dashti/` resolves | `curl -s -o /dev/null -w "%{http_code}" -L https://www.linkedin.com/in/david-dashti/` | `999` - LinkedIn blocks non-browser clients; this is not evidence the profile is missing. NOT VERIFIABLE by CLI; open in a browser to confirm. |
| 16 | "15 merged pull requests into 8 security and medical-imaging projects" | Sum of the eight per-repo rows below: 3 + 3 + 2 + 2 + 2 + 1 + 1 + 1 | `15` across `8` repositories - CONFIRMED 2026-09-19. Was 14/7 on 2026-09-14; purl2cpe #32 merged 2026-09-15 |
| 20 | fo-dicom, 3 merged | `gh search prs --author Dashtid --merged --repo fo-dicom/fo-dicom --json number,title,url --limit 50` | 3: #2149 "Observe per-connection service task exception in DicomServer", #2147 "Fix RawPDU.ToString throwing FormatException on .NET 8 enum format", #2114 "Add depth guard to DicomReader to prevent unbounded SQ recursion" - CONFIRMED |
| 21 | fo-dicom.Codecs, 3 merged | `gh search prs --author Dashtid --merged --repo Efferent-Health/fo-dicom.Codecs --json number,title,url --limit 50` | 3: #192 "Reject an HTJ2K codestream that does not fit the declared pixel buffer", #190 same for JPEG 2000, #181 "Fix process crash when decoding a JPEG that references an undefined Huffman table" - CONFIRMED (the page previously said 2) |
| 22 | DefectDojo, 2 merged, both LLM-scanner parsers | `gh search prs --author Dashtid --merged --repo DefectDojo/django-DefectDojo --json number,title,url --limit 50` | 2: #15013 "Add Garak (NVIDIA LLM vulnerability scanner) parser", #15081 "Add Promptfoo (LLM eval & red-teaming) parser" - CONFIRMED; both titles name the scanner, so the AI-security description is the PRs' own wording |
| 23 | syft, 2 merged | `gh search prs --author Dashtid --merged --repo anchore/syft --json number,title,url --limit 50` | 2: #4791 "fix(cyclonedx): exclude distro group from package name", #4963 "fix(dpkg): extract License field for opkg/ipkg entries" - CONFIRMED |
| 24 | grype, 2 merged | `gh search prs --author Dashtid --merged --repo anchore/grype --json number,title,url --limit 50` | 2: #3611 "fix: honor match.rust.using-cpes configuration", #3396 "fix(registry): warn when insecure transport is configured" - CONFIRMED; #3396 is a warning message, described as a small change on the page |
| 25 | presidio, 1 merged, and the link points at `data-privacy-stack/presidio` | `gh search prs --author Dashtid --merged --repo data-privacy-stack/presidio --json number,title,url --limit 50` | 1: #2089 "docs(image-redactor): fix undefined di_ocr variable in Document Intelligence example" - CONFIRMED; it is a documentation fix and the page now says so |
| 26 | stereoscope, 1 merged | `gh search prs --author Dashtid --merged --repo anchore/stereoscope --json number,title,url --limit 50` | 1: #587 "feat: log when registry transport is configured insecurely" - CONFIRMED; one log line, described as a small change on the page |
| 27 | purl2cpe, 1 merged | `gh pr view 32 -R scanoss/purl2cpe --json state,mergedAt,additions,deletions` | `MERGED` 2026-09-15, +6/-0, one data file: #32 "Add purl mapping for cryptopp/crypto++" - CONFIRMED. Was an OPEN PR when this ledger was first written on 2026-09-14; the page now lists it as merged and no longer as open |
| 29-30 | Bounded decompression at fo-dicom is an OPEN PR (#2166), not merged work | `gh pr view 2166 -R fo-dicom/fo-dicom --json state,reviews,createdAt,title,url` | `state: OPEN`, `reviews: []` (zero reviews), `createdAt: 2026-07-30T13:43:36Z`, title "Bound the inflated size of a deflated dataset in DicomReader" - CONFIRMED OPEN. [!] "under review" is generous: no review has been posted. |
| 31 | Open PRs at checkov, Terraform OIDC trust-policy checks | `gh search prs --author Dashtid --repo bridgecrewio/checkov --json number,title,state,url --limit 50` | 3 open: #7665 (multi-value OIDC sub condition), #7627 (CKV_AZURE_249 pull_request OIDC subjects), #7610 (GitHub immutable OIDC subject IDs) - CONFIRMED open and Terraform/OIDC in subject |
| 32 | Open PRs at pydicom | `gh search prs --author Dashtid --repo pydicom/pydicom --json number,title,state,url --limit 50` | 4 open: #2346, #2337, #2333, #2331 (charset and malformed-dataset error handling) - CONFIRMED |
| 33 | Open PRs at cartography | `gh search prs --author Dashtid --repo cartography-cncf/cartography --json number,title,state,url --limit 50` | 1 open: #3088 "feat(aws): model trust-policy conditions on the role trust edge" - CONFIRMED |
| 20-34 | All eleven linked upstream repositories exist and are not archived | `gh api repos/<owner>/<repo> --jq '.full_name + " archived=" + (.archived\|tostring)'` for each of the 11 | all 11 resolved, `archived=false` for every one - CONFIRMED |
| 36 | "All of my pull requests" search link | `https://github.com/pulls?q=is%3Apr+author%3ADashtid+archived%3Afalse` - the author handle checked with `gh api user --jq .login` | handle `Dashtid` matches the query - CONFIRMED as a well-formed link. It is a live GitHub search, so it returns whatever GitHub returns at click time and asserts no number. |
| 39, 43, 47, 49 | The four linked own-repos exist and are public | `gh repo view Dashtid/<repo> --json nameWithOwner,visibility,isArchived` for subvectors, subcheck, portfolio-site, sysadmin-toolkit | all four `PUBLIC`, `isArchived: false` - CONFIRMED |
| 42 | subvectors covers GitHub/GitLab issuers against AWS/Azure/GCP consumers | Wheel contents, listed below | `github-aws`, `github-azure`, `github-azure-flexible`, `github-gcp`, `gitlab-aws`, `gitlab-azure`, `gitlab-azure-flexible`, `gitlab-gcp` all present - CONFIRMED. [i] The corpus also carries bitbucket, circleci and terraform suites, so the page understates it. |
| 43 | subvectors is on PyPI and the wheel carries the full corpus | `curl -s -o /dev/null -w "%{http_code}" https://pypi.org/pypi/subvectors/json`; then download the `.whl` from the same JSON and `python -c "import zipfile; print(zipfile.ZipFile('sv.whl').namelist())"` | PyPI `200`, version `0.6.0`; wheel holds 14 vector JSON suites plus `vectors/schema/vector-suite.schema.json` and `vectors/LICENSE` under `subvectors/vectors/` - CONFIRMED |
| 46 | subcheck is differentially tested against the pinned subvectors corpus | `gh api repos/Dashtid/subcheck/contents/tests --jq '.[].name'` | `test_decoder_vectors.py`, `test_fixture_provenance.py`, `test_docs_pins.py` present among 15 test modules - PARTIAL: the tests that would implement this exist by name; the suite was not executed in this pass, so the wording is supported, not proven |
| 47 | subcheck is on PyPI and usable as a GitHub Action | `curl -s -o /dev/null -w "%{http_code}" https://pypi.org/pypi/subcheck/json`; `gh api repos/Dashtid/subcheck/contents/action.yml --jq '.name,.size'` | PyPI `200`, version `0.5.0`; `action.yml` present at the repo root (2086 bytes) - CONFIRMED |
| 48-49 | portfolio-site: Vue 3 + TypeScript frontend, FastAPI backend | `gh api repos/Dashtid/portfolio-site/languages`; `gh api repos/Dashtid/portfolio-site/contents --jq '.[].name'`; `gh api repos/Dashtid/portfolio-site/contents/backend/requirements.txt` | languages include `Vue`, `TypeScript`, `Python`; `frontend/` and `backend/` directories present; `fastapi` in the compiled backend requirements - CONFIRMED |
| 48-49 | portfolio-site: GitHub OAuth, analytics, admin CMS | `gh api repos/Dashtid/portfolio-site/contents/backend/app --jq '.[].name'`; backend requirements | indicative only - `githubkit` (a GitHub API client) is a backend dependency and `api/`, `services/`, `models/` exist. PARTIAL: the three features were not individually confirmed in this pass |
| 50-51 | sysadmin-toolkit: Windows/Linux administration automation | `gh api repos/Dashtid/sysadmin-toolkit/contents --jq '.[].name'` | top-level `Windows/` and `Linux/` directories present - CONFIRMED |
| 55 | CompTIA Security+ (2026) | No verification URL or credential code appears on the page, and CompTIA verification requires a candidate-issued link or code. | NOT VERIFIABLE FROM THE PAGE. A reader cannot check it by clicking. To make it checkable, add the CompTIA/Credly credential URL to the line. |

## Known gaps

- The certification line (55) is the one claim on the page a reader cannot check at all.
- The LinkedIn link (12) cannot be checked from a terminal; it needs a browser.
- Two rows are PARTIAL rather than confirmed: subcheck's differential testing (46) and
  portfolio-site's feature list (48-49).
- Line 7 is excluded from this ledger by owner decision, not by oversight.
