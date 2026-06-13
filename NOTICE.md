# NOTICE — Provenance and Privilege Statement

This document is part of the public release of the `indian-ip-drafting` plugin (v0.1.0-alpha and onwards). It declares the provenance of the plugin's content, in order to address any question about advocate-client privilege, client confidentiality, professional ethics, personal-data protection, and commercial confidentiality that may be raised by any reader, complainant, regulator, or Bar Council disciplinary authority.

The plugin is **case-config-aware**: the universal structural skeleton of any Indian intellectual-property litigation pleading is uniform, and the parties' chosen forum (Commercial Division of the High Court / High Court Intellectual Property Rights Division — Delhi or Madras or Calcutta or Bombay or such other High Court as may, by Practice Direction, constitute one — under the Tribunals Reforms Act 2021 post-IPAB-abolition / District Court of competent pecuniary jurisdiction / Commercial Court of competent pecuniary jurisdiction under the Commercial Courts Act 2015), nature of IP right (copyright / trade mark / patent / design / passing-off), infringement allegation, prior-use position, and registration particulars are supplied by the user via a `case-config.md` file in the case folder.

This NOTICE is published in plain language so that any reader — practising advocate, judge, Bar Council officer, regulator, member of the public, fellow developer — can understand the position without ambiguity.

---

## 1. What this plugin contains

This plugin contains the following categories of content, and **only** the following categories of content:

(a) **Universal IP-pleading skeleton** — the structural shape of any Indian intellectual-property litigation pleading (Cause Title with correct forum nomenclature, Parties block, Statutory Opening invoking the operative section, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications including the interim-injunction application and John Doe / Anton Piller / Ashok Kumar order applications).

(b) **Formatting conventions** — text-formatting conventions for pleadings before the Commercial Division of the High Court, the High Court Intellectual Property Rights Division (post-IPAB-abolition, holding IPAB jurisdiction by virtue of the Tribunals Reforms Act 2021), the District Court of competent pecuniary jurisdiction, and the Commercial Court of competent pecuniary jurisdiction under the Commercial Courts Act 2015.

(c) **Statutory references** — citations to public statutes (Copyright Act 1957, Trade Marks Act 1999, Patents Act 1970 as amended by the Patents (Amendment) Act 2005, Designs Act 2000, Tribunals Reforms Act 2021, Commercial Courts Act 2015, Code of Civil Procedure 1908 — especially Order 39 Rules 1 and 2 and Order 26 read with the Anton Piller line, Bharatiya Nagarik Suraksha Sanhita 2023, Bharatiya Sakshya Adhiniyam 2023, Limitation Act 1963, Indian Contract Act 1872, Specific Relief Act 1963, Information Technology Act 2000, applicable State Court-Fees Acts).

(d) **Procedural rule references** — citations to public rules (Delhi High Court Intellectual Property Rights Division Rules 2022, Madras High Court Intellectual Property Rights Division Rules, Copyright Rules 2013, Trade Marks Rules 2017, Patents Rules 2003 as amended, Designs Rules 2001 as amended, Commercial Courts (Pre-Institution Mediation and Settlement) Rules 2018, and the various Practice Directions of the High Courts on intellectual-property original-side procedure).

(e) **Generic placeholders** — every variable in every template is a placeholder (`[Plaintiff]`, `[Defendant]`, `[Copyright Work Title]`, `[Trade Mark]`, `[Patent No.]`, `[Design Registration No.]`, `[Date of First Publication]`, `[Date of First Use]`, `[Date of Registration]`, `[Date of Priority]`, `[Schedule of Infringing Product]`, `[Damages Quantum]`). No placeholder is filled with any specific plaintiff, defendant, copyright work title, trade mark, patent number, design registration number, infringing-product description, damages figure, or any other identifying information.

(f) **Anti-hallucination and privacy-firewall workflow** — six agents (Reader, Format, Drafter, Verifier, Refiner, Overseer) that operate on a case folder supplied by the user. The plugin itself contains no case folder. The Reader substitutes every plaintiff name, defendant name, copyright-work title, trade-mark name, patent number, design registration number, infringing-product name, and damages-quantum figure with placeholders before downstream AI processing.

---

## 2. What this plugin does NOT contain

This plugin does **not** contain any of the following, and has never contained any of the following at any point in any committed version:

(a) **No specific client matter or intellectual-property dispute.** No client of the author, and no specific copyright dispute, trade mark dispute, patent dispute, design dispute, or passing-off dispute handled by the author or any client, appears in the plugin — by name, by registration number, by work title, by trade mark, by patent number, by design number, by infringing-product description, by damages figure, by party name, by registration number (CIN / LLPIN / GSTIN / PAN), or by any other identifying signature.

(b) **No client communications.** No oral or written communication made to the author by or on behalf of any client (whether a copyright owner, a trade mark proprietor, a patent holder, a design registrant, an alleged infringer, or any other party) appears in the plugin in any form.

(c) **No client documents.** No document or instrument with which the author has become acquainted in the course of professional employment as an advocate appears in the plugin, in original, in redacted, in summary, in extract, or in pattern. This includes — but is not limited to — copyright registration certificates, trade mark registration certificates, patent grant certificates, design registration certificates, deeds of assignment, licence agreements, prior-use affidavits, infringement-product samples, market-survey reports, damages computations, and cease-and-desist correspondence of any specific matter.

(d) **No personal data of any data principal.** The plugin processes no personal data, collects no personal data, stores no personal data.

(e) **No specific board resolution, no specific power-of-attorney, no specific authorisation letter** of any specific intellectual-property owner or any other party handled by the author or any other advocate.

(f) **No client list, no panel-counsel list of any rights holder, no chamber list, no associate list, no opposing-counsel list, no Judge-specific intelligence, no Roster-specific intelligence.**

(g) **No tracking, no telemetry, no analytics, no opt-in error reporting, no login, no account, no cloud sync.** The plugin runs entirely on the user's machine. The author receives no information about who installs the plugin, who uses it, on what cases, with what consideration, with what outcomes.

(h) **No verbatim prose from any proprietary corpus.** Specifically, the plugin contains no verbatim prose from any private precedent collection. The clauses pertaining to *Moral Rights* and *Reversionary Interests* under the Copyright Act 1957 are encoded by reference to Section 19 of the Copyright Act 1957 only, in statutory-only paraphrase, without importing proprietary commentary or proprietary clause-text.

---

## 3. The legal distinction

Indian law has long recognised a clear distinction between two categories:

(i) **Specific client communications and documents** — protected under Section 132 of the Bharatiya Sakshya Adhiniyam 2023 (formerly Section 126 of the Indian Evidence Act 1872) and under Rule 17 of the Bar Council of India Standards of Professional Conduct and Etiquette. This category is privileged and confidential.

(ii) **General professional knowledge of intellectual-property law, IP-litigation procedure, and pleading craft** — an advocate's accumulated knowledge of how a Section 51 read with Section 55 copyright infringement suit is structured, how a Section 29 trade mark infringement suit reads, how a Section 64 Patents Act revocation petition is mounted post-IPAB-abolition, what *Yahoo! Inc. v. Akash Arora* (1999) PTC 19 (Del) holds on internet trade-mark infringement, what *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 lays down on the passing-off triple test, what *Bayer Corporation v. Union of India* (2014) Bom HC holds on compulsory licensing scope, what *Bajaj Auto Ltd. v. TVS Motor Company* (2009) 9 SCC 797 holds on suit-injunction-and-cross-undertaking discipline in patent matters, what the Tribunals Reforms Act 2021 has done to the appellate IP architecture (abolition of the Intellectual Property Appellate Board and transfer of jurisdiction to the High Court Intellectual Property Rights Division). This category is the advocate's own professional knowledge. It is not the property of any specific client. It is not privileged.

This plugin operates **entirely within category (ii)**.

Every Indian advocate accumulates this knowledge through years of practice, through study of *Narayanan on Trade Marks and Passing Off*, *Narayanan on Patent Law*, *Iyengar's Copyright Act*, *Ananth Padmanabhan on Intellectual Property Rights*, *Cornish on Intellectual Property*, *Bently and Sherman*, the bare statutes, the various commentaries on the Copyright Act 1957, Trade Marks Act 1999, Patents Act 1970, and Designs Act 2000, and the case-law of the Supreme Court and the High Courts on copyright, trade-mark, passing-off, patent, and design disputes. The plugin codifies that accumulated procedural knowledge into machine-readable form. It does not codify any client's confidential information.

The plugin is, in this respect, identical in legal character to a published intellectual-property-law textbook, a continuing legal education handout, or a senior advocate's drafting-style lecture. The medium is software. The content is procedural knowledge.

---

## 4. The author's professional position

The author is **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa, practising before the High Courts of India. The plugin is published under the open-source brand **wolfgang_rush**, which is the author's publishing handle for legal-technology infrastructure; the real-identity accountability declared in this section attaches to the author personally and is not displaced by the use of a publishing handle.

The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961, the Bar Council of India Rules, and the Standards of Professional Conduct and Etiquette.

The plugin is published as a personal contribution to the open-source legal-technology ecosystem. It is published without any commercial channel, without any solicitation of professional work, without any advertisement of professional services, and without any acceptance of work through this repository.

This NOTICE is filed of record in this open-source repository so that any person who reads, reviews, audits, or assesses this plugin has full transparency about its provenance and its scope from the moment of release.

---

## 5. Verification of clean provenance

The repository owner shall maintain, on a private offline record, a build log demonstrating that every line of every file in the plugin was either:

(a) authored from scratch as procedural skeleton, OR
(b) derived from public statute, public rule, public judgment, or public intellectual-property-law textbook, OR
(c) derived from the author's own original procedural knowledge as a practitioner.

No line of any file was, at any stage, copied from, paraphrased from, summarised from, or pattern-matched against any specific client matter, intellectual-property dispute, client communication, or client document.

This NOTICE is the author's signed declaration of that position.

---

## 6. Reporting concerns

If any reader, regulator, fellow advocate, or member of the public believes any specific content in this plugin is derived from a specific client matter or specific confidential communication, the reader is requested to:

(a) identify the file and line at issue in the plugin,
(b) identify the specific client matter or communication believed to be the source,
(c) explain the basis of the belief,

and raise the concern via a GitHub Issue on this repository.

Concerns raised with these particulars will be investigated and the file or line will be removed or rewritten if the concern is well-founded. Concerns raised without these particulars cannot be acted upon.

---

## 7. Standing instruction to forks and derivatives

Any fork, derivative, downstream redistribution, or commercial integration of this plugin or its content shall preserve this NOTICE in unmodified form, and shall extend the same provenance discipline to any content added in the fork or derivative.

This NOTICE travels with the code under the same MIT licence that governs the source.

---

*Signed and dated by way of public commit history on the repository. The author stands by every line of this notice.*
