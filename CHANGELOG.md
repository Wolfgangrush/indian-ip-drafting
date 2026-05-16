# Changelog

All notable changes to the `indian-ip-drafting` plugin are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/) and this project adheres to [Semantic Versioning](https://semver.org/).

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
