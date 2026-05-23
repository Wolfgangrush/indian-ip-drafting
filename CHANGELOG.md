# Changelog

All notable changes to the `indian-ip-drafting` plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [0.2.2-alpha] — 2026-05-24

### Output-pairing discipline — every `.md` paired with `.docx`

Advocates do not natively read Markdown. Every pipeline output artifact (case-facts.md from Reader, format-shell.md from Format, draft-v1.md from Drafter, verification-report.md from Verifier, draft-v2.md from Refiner, opposing-notes.md + final-draft.md from Overseer) is now paired with a corresponding `.docx` rendered using the same locked Word styles in the shipped reference.docx.

### Added

- **`pair_md_to_docx.sh`** — helper script in `skills/<base>/` that every agent calls after writing a `.md` output. Wraps the two-step pandoc + fix_docx_tables.py pipeline so every agent produces a paired `.docx` without re-implementing the conversion logic.
- **OUTPUT-PAIRING DISCIPLINE** section in `_drafting_common/SKILL.md` documenting the per-agent output-pairing map (Reader → case-facts.{md,docx}; Format → format-shell.{md,docx}; Drafter → draft-v1.{md,docx}; Verifier → verification-report.{md,docx}; Refiner → draft-v2.{md,docx}; Overseer → opposing-notes.{md,docx} + final-draft.{md,docx}).

### Why the change

User feedback from the 2026-05-24 EPFO test demonstrated that the QC pipeline output (`verification-report.md`, `opposing-notes.md`) was not accessible to the advocate in their normal Word workflow. The advocate explicitly stated: "every note … needs to be docx too." v0.2.2 closes this gap.

### Clarification — per-court formatting

v0.2.1 propagated a single Bombay HC Nagpur pleading-style reference.docx across all 14 plugins. The structural styling (TNR 14pt 1.5 spacing 4cm-left margin Heading 1/2/3/4) is broadly defensible for pleading-style plugins (HC / SC / Tax / Rent / MACT / Banking / Company / Consumer / Labour / Family / IP / District Court) because the court-specific differences (cause-title text, annexure prefix, statutory opening, AOR Certificate language) live in the case-type SKILL.md (Drafter content) not the reference.docx (style template). For SC the universal style is correct as the SC Registry mandate matches the HC convention (A4 + TNR 14pt + 1.5 spacing + 4cm left margin). Court-specific content (P-1/P-2 annexure prefix instead of ANNEXURE-A; SYNOPSIS + LIST OF DATES instead of just INDEX; AOR Certificate verbatim) is rendered by the Drafter from the case-type skill. Per-bench fine-tuning (e.g., Delhi HC double-spacing under Original Side Rules 2018; Punjab & Haryana watermarked paper) is achieved by supplying a case-folder reference.docx override.

For the two TRANSACTIONAL plugins (indian-contracts-drafting-litigation + indian-property-drafting-litigation), v0.2.1 wrongly applied the pleading-style reference.docx. Those two plugins now ship a transactional-instrument variant (TNR 12pt single-spaced, no spaced section headers, no underline on headings) under their own v0.2.2 release.

---

## [0.2.1-alpha] — 2026-05-24

### Filing-grade render-defect repair + pipeline-optionality

The v0.1.0 render path produced filing-grade Markdown but the pandoc → `.docx` conversion failed Bombay HC / equivalent Registry expectations on multiple counts (title not bold, section headers left-aligned, Index table column-headers wrapping vertically, party block leaking onto cover pages, ~6,200-word bloat). This release repairs the render path, calibrated against an actual filed Bombay HC Nagpur Second Appeal pleading the author supplied as the filing-grade reference. Inherits the v0.2.1 fixes from `indian-hc-drafting-litigation`.

### Added

- **Pre-customised `reference.docx`** in the plugin's base-skill folder with locked Word styles (TNR 14pt body, 1.5 line spacing, 4cm left / 2.5cm right-top-bottom margins, Heading 1 bold centered, Heading 2 bold + UNDERLINED + centered + letter-spacing for the spaced `F A C T S` effect, Heading 3 bold + UNDERLINED + centered for unspaced section headers, Heading 4 bold + UNDERLINED + left for `MOST RESPECTFULLY SHEWETH:` style anchors, fixed table layout).
- **`build_reference_docx.py`** — reproducible python-docx build script for the shipped reference.docx.
- **`fix_docx_tables.py`** — post-pandoc Python script that forces column widths on every table (5-col 8/8/60/14/10; 4-col 10/10/65/15; 3-col 10/75/15; 2-col 18/82). Locks first-row bold + centered + vertically-centered cells. Drafter runs this as the final post-pandoc step.
- **MARKDOWN HEADING DISCIPLINE** in the Drafter prompt + base SKILL.md (Heading 1 / Heading 2 / Heading 3 / Heading 4 mapping for court header / spaced section headers / unspaced section headers / left-anchored headings).
- **VERBOSITY DISCIPLINE** with per-case-type word-count targets and hard ceilings.
- **PIPELINE-OPTIONALITY** — Verifier / Refiner / Overseer now OPTIONAL QC layers. Default exit point is after Stage 3 (Drafter).
- **COVER-PAGE DISCIPLINE** — INDEX / SYNOPSIS / LIST OF ANNEXURES each begin on `\newpage` with short cause-title only.
- **Bold-number paragraph convention** — Facts and Grounds paragraphs use `**1.** **2.** **3.**`.
- **Inline-bold highlighting convention** for property descriptors / annexure markers / key terms within Facts narrative.

### Changed

- **Drafter pandoc command** is now TWO steps (pandoc → .docx, then `fix_docx_tables.py`). Step 2 is non-negotiable; skipping it reproduces the v0.2.0 stacking-column defect.

### Cost / token-budget note

Running the full 6-agent pipeline burns approximately 600K tokens per draft, which can exhaust an advocate's Claude session limit. v0.2.1 makes Stages 4–6 OPTIONAL so a baseline Reader → Format → Drafter run (~280K tokens) is sufficient for routine pleadings. The optional QC stages remain available for high-stakes matters.

---

## [0.1.0-alpha] — 2026-05-16 (initial release)

### Added

- **Plugin scaffolding** — `.claude-plugin/plugin.json` manifest · MIT `LICENSE` · `NOTICE.md` provenance and privilege statement · `.gitignore` · this `CHANGELOG.md` · comprehensive `README.md`.
- **Six-agent drafting pipeline** — Reader → Format → Drafter → Verifier → Refiner → Overseer. Each agent is a markdown file under `agents/<name>/<name>.md` with YAML frontmatter declaring `name`, `description`, and `allowed-tools`. The Verifier is encoded with the **IPAB-abolition currency check** — every reference to the erstwhile Intellectual Property Appellate Board as an appellate forum is flagged and re-routed to the High Court Intellectual Property Rights Division per Sections 12 to 14 of the Tribunals Reforms Act 2021.
- **Shared infrastructure skills:**
  - `_drafting_common` — anti-pollution rules, encoding standards, language conventions, AI-style-marker blacklist, IP-specific privacy firewall, citation discipline, statutory-currency rules (CrPC 1973 → BNSS 2023 transitions for ancillary criminal-copyright references; IEA 1872 → BSA 2023 transitions for evidence; Companies Act 1956 → 2013 transitions where corporate party arises), and the *Copyright Firewall* — clauses on Moral Rights and Reversionary Interests are encoded by Section 19 of the Copyright Act 1957 alone, with no importation of proprietary clause prose.
  - `_ip_drafting_base` — universal Indian intellectual-property pleading skeleton (Cause Title with correct forum nomenclature · Parties block · Statutory Opening invoking the operative section · Prelude · Facts · Grounds · Prayer · Verification · Affidavit-in-support · Index · List of Documents · accompanying applications including the Order 39 Rule 1 and Rule 2 CPC interim-injunction application and the John Doe / Ashok Kumar / Anton Piller order applications) — with appellate-forum nomenclature locked to the High Court Intellectual Property Rights Division per the Tribunals Reforms Act 2021.
- **Ten case-type skill scaffolds:**
  - `copyright-infringement-suit-draft` — civil suit under Section 51 read with Section 55 of the Copyright Act 1957, with Section 62 jurisdiction-at-plaintiff anchor
  - `copyright-fair-dealing-defence-draft` — defence under Section 52 of the Copyright Act 1957 (fair dealing for research / criticism / review / news reporting)
  - `trademark-infringement-suit-draft` — civil suit under Section 29 read with Section 134 (jurisdiction) and Section 135 (reliefs) of the Trade Marks Act 1999
  - `passing-off-suit-draft` — common-law passing-off suit, read with Section 27 of the Trade Marks Act 1999
  - `trademark-rectification-application-draft` — application for rectification of the Register under Section 57 of the Trade Marks Act 1999 (post-IPAB-abolition, before the High Court Intellectual Property Rights Division)
  - `patent-infringement-suit-draft` — civil suit under Section 104 (jurisdiction) read with Section 108 (reliefs) of the Patents Act 1970, as amended
  - `patent-revocation-application-draft` — application for revocation of a patent under Section 64 of the Patents Act 1970 (post-IPAB-abolition, before the High Court Intellectual Property Rights Division)
  - `design-piracy-suit-draft` — civil suit under Section 22 of the Designs Act 2000 read with the Section 19 cancellation framework
  - `john-doe-anton-piller-order-application-draft` — application for a John Doe / Ashok Kumar order under Order 39 read with Order 26 CPC, applying the Anton Piller line of authority
  - `interim-injunction-application-ip-draft` — application for an interim injunction under Order 39 Rules 1 and 2 CPC in an intellectual-property suit, applying the *American Cyanamid v. Ethicon* / *Gujarat Bottling v. Coca-Cola* framework
- **Forum-aware design** — the user supplies `case-config.md` declaring the chosen forum (High Court Commercial Division / High Court Intellectual Property Rights Division — Delhi or Madras or Calcutta or Bombay or other / District Court of competent pecuniary jurisdiction / Commercial Court under the Commercial Courts Act 2015), nature of IP right, registration particulars, prior-use position, infringement-mode allegation, and the relief sought.
- **IPAB-abolition currency** — every reference to the erstwhile Intellectual Property Appellate Board as an appellate forum is flagged by the Verifier and re-routed to the High Court Intellectual Property Rights Division per Sections 12 to 14 of the Tribunals Reforms Act 2021, which came into force in 2021 and is in force as at the date of this release.

### Notes on this release

This is a **v0.1.0-alpha scaffold release**. The structural skeletons, agent pipeline, base skills, and 10 case-type skill frames are in place. Deep per-skill encoding (full pleading exemplars for each case type, the full *Anton Piller* / *Yahoo!* / *Cadila Healthcare* / *Bayer* / *Bajaj Auto* / *Mardia Chemicals* line of binding authority, and bench-specific Practice Directions for Delhi High Court IP Division, Madras High Court IP Division, Calcutta High Court IP Division, and Bombay High Court IP Division roster as constituted) will land in v0.1.0 and onward.

### Released under

MIT License. Authored by Rushikesh R. Mahajan, Advocate, publishing under the Wolfgang Rush open-source brand for legal-tech infrastructure.
