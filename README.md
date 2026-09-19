# David Dashti

Product security for regulated medical software. Biomedical engineer turned security
specialist - I turn STRIDE threat models into concrete, traceable security requirements
and back them with SBOM-driven SCA, static analysis, and black-box dynamic testing.

Currently QA/RA & Security Specialist at Hermes Medical Solutions in Stockholm, working on
secure SDLC for medical devices, FDA premarket cybersecurity and IEC 81001-5-1, AppSec, and
the AI security work and regulatory evidence AI-enabled devices need. Building toward
product and application security engineering.

[dashti.se](https://dashti.se) - [LinkedIn](https://www.linkedin.com/in/david-dashti/)

## Open source

**15 merged pull requests into 8 security and medical-imaging projects:**

| Project | Merged | What |
|---|---|---|
| [fo-dicom](https://github.com/fo-dicom/fo-dicom) | 3 | Depth guard in the DICOM reader against unbounded SQ recursion ([#2114](https://github.com/fo-dicom/fo-dicom/pull/2114)); network-layer fixes - a .NET 8 enum-format crash in `RawPDU.ToString` ([#2147](https://github.com/fo-dicom/fo-dicom/pull/2147)) and an unobserved per-connection service task exception in `DicomServer` ([#2149](https://github.com/fo-dicom/fo-dicom/pull/2149)) |
| [fo-dicom.Codecs](https://github.com/Efferent-Health/fo-dicom.Codecs) | 3 | Decoder input validation: reject a JPEG 2000 ([#190](https://github.com/Efferent-Health/fo-dicom.Codecs/pull/190)) or HTJ2K ([#192](https://github.com/Efferent-Health/fo-dicom.Codecs/pull/192)) codestream that does not fit the declared pixel buffer; fix a process crash on a JPEG referencing an undefined Huffman table ([#181](https://github.com/Efferent-Health/fo-dicom.Codecs/pull/181)) |
| [DefectDojo](https://github.com/DefectDojo/django-DefectDojo) | 2 | Parsers for two LLM security scanners: Garak, an LLM vulnerability scanner ([#15013](https://github.com/DefectDojo/django-DefectDojo/pull/15013)), and Promptfoo, LLM eval and red-teaming ([#15081](https://github.com/DefectDojo/django-DefectDojo/pull/15081)) |
| [syft](https://github.com/anchore/syft) | 2 | SBOM field correctness: exclude the distro group from the CycloneDX package name ([#4791](https://github.com/anchore/syft/pull/4791)); extract the License field for opkg/ipkg entries ([#4963](https://github.com/anchore/syft/pull/4963)) |
| [grype](https://github.com/anchore/grype) | 2 | Honour the `match.rust.using-cpes` configuration instead of ignoring it ([#3611](https://github.com/anchore/grype/pull/3611)); small change - warn when an insecure registry transport is configured ([#3396](https://github.com/anchore/grype/pull/3396)) |
| [presidio](https://github.com/data-privacy-stack/presidio) | 1 | Small docs fix - an undefined variable in the Document Intelligence image-redaction example ([#2089](https://github.com/data-privacy-stack/presidio/pull/2089)) |
| [stereoscope](https://github.com/anchore/stereoscope) | 1 | Small change - one log line when the registry transport is configured insecurely ([#587](https://github.com/anchore/stereoscope/pull/587)) |
| [purl2cpe](https://github.com/scanoss/purl2cpe) | 1 | Small data addition - a PURL-to-CPE mapping for Crypto++, whose 29 NVD CPE entries previously resolved to nothing ([#32](https://github.com/scanoss/purl2cpe/pull/32)) |

Open PRs under review: bounding the inflated size of a deflated dataset in the DICOM
reader at [fo-dicom](https://github.com/fo-dicom/fo-dicom/pull/2166), Terraform OIDC
trust-policy checks at [checkov](https://github.com/bridgecrewio/checkov), plus
[pydicom](https://github.com/pydicom/pydicom) and
[cartography](https://github.com/cartography-cncf/cartography).

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
