# David Dashti

Product security for regulated medical software. Biomedical engineer turned security
specialist - I turn STRIDE threat models into concrete, traceable security requirements
and back them with SBOM-driven SCA, static analysis, and black-box dynamic testing.

Currently QA/RA & Security Specialist at Hermes Medical Solutions in Stockholm, working on
secure SDLC for medical devices, FDA premarket cybersecurity and IEC 81001-5-1, AppSec, and
the AI governance that increasingly wraps around them. Building toward product and
application security engineering.

[dashti.se](https://dashti.se) - [LinkedIn](https://www.linkedin.com/in/david-dashti/)

## Open source

**13 merged pull requests into 7 security and medical-imaging projects:**

| Project | Merged | What |
|---|---|---|
| [fo-dicom](https://github.com/fo-dicom/fo-dicom) | 3 | DICOM parsing hardening (bounded decompression) |
| [syft](https://github.com/anchore/syft) | 2 | SBOM generation |
| [grype](https://github.com/anchore/grype) | 2 | Vulnerability matching correctness |
| [fo-dicom.Codecs](https://github.com/Efferent-Health/fo-dicom.Codecs) | 2 | JPEG/JPEG-2000 decoder crash fixes |
| [DefectDojo](https://github.com/DefectDojo/django-DefectDojo) | 2 | Vulnerability-management platform |
| [presidio](https://github.com/data-privacy-stack/presidio) | 1 | PII detection |
| [stereoscope](https://github.com/anchore/stereoscope) | 1 | Container image analysis |

Open PRs under review at [checkov](https://github.com/bridgecrewio/checkov) (Terraform
OIDC trust-policy checks), [pydicom](https://github.com/pydicom/pydicom),
[cartography](https://github.com/cartography-cncf/cartography) and
[purl2cpe](https://github.com/scanoss/purl2cpe).

[All of my pull requests](https://github.com/pulls?q=is%3Apr+author%3ADashtid+archived%3Afalse)

## Projects

- [subvectors](https://github.com/Dashtid/subvectors) - cited, versioned conformance
  vectors for CI/CD OIDC trust decisions: does subject S satisfy trust condition C,
  and is C safe? Covers GitHub/GitLab issuers against AWS/Azure/GCP consumers.
  On PyPI (`pip install subvectors`) with the full corpus in the wheel.
- [subcheck](https://github.com/Dashtid/subcheck) - decodes and validates GitHub Actions
  OIDC token claims against an expected-claims policy. A CI gate against trust-policy
  drift, differentially tested against the pinned subvectors corpus.
  On PyPI (`pip install subcheck`) and usable as a GitHub Action.
- [portfolio-site](https://github.com/Dashtid/portfolio-site) - full-stack personal site
  (Vue 3 + TypeScript, FastAPI) with GitHub OAuth, analytics and an admin CMS.
- [sysadmin-toolkit](https://github.com/Dashtid/sysadmin-toolkit) - Windows/Linux
  administration automation: maintenance, infrastructure setup, monitoring, DevOps.

## Certifications

- CompTIA Security+ (2026)
