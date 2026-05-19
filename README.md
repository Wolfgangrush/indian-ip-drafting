# indian-ip-drafting

> **Open-source Claude-compatible plugin for drafting Indian intellectual-property litigation pleadings — copyright, trade marks, passing-off, patents, and designs.**
>
> Six-agent drafting pipeline · ten case-type skills · case-config-aware · Copyright Act 1957 + Trade Marks Act 1999 + Patents Act 1970 (as amended) + Designs Act 2000 + Tribunals Reforms Act 2021 (IPAB abolition) + Delhi HC IP Division Rules 2022 + Madras HC IP Division Rules + Commercial Courts Act 2015 + CPC Order 39 + Anton Piller / John Doe / Ashok Kumar doctrine + American Cyanamid / Gujarat Bottling interim-injunction framework + Bharatiya Nagarik Suraksha Sanhita 2023 + Bharatiya Sakshya Adhiniyam 2023 discipline encoded.
>
> Released under MIT. Open infrastructure for the legal community. No commercial engagement offered through this repository — see Disclaimer below.

> ⚠️ **AI can make mistakes. Always verify the output.**
>
> This software generates assistive drafts and suggestions only. Every legal claim, citation, statute reference, procedural step, deadline calculation, and ground of relief must be independently verified by a qualified human practitioner before filing, advising a client, or relying on the output. The publisher accepts no liability for outputs used without verification.

---

## Table of contents

1. [What this plugin does](#what-this-plugin-does)
2. [Case-type skills (full inventory with statutory authority)](#case-type-skills-full-inventory-with-statutory-authority)
3. [The 6-agent drafting pipeline (what each agent does)](#the-6-agent-drafting-pipeline)
4. [Installation](#installation) — Claude Desktop application
5. [Your first pleading — step-by-step walkthrough](#your-first-pleading--step-by-step-walkthrough)
6. [The `case-config.md` file](#the-case-configmd-file)
7. [Built-in compliance disciplines](#built-in-compliance-disciplines)
8. [Privacy firewall — extra discipline for IP content](#privacy-firewall--extra-discipline-for-ip-content)
9. [IPAB abolition — appellate-forum currency](#ipab-abolition--appellate-forum-currency)
10. [Why MIT License](#why-mit-license)
11. [Sibling plugins](#sibling-plugins)
12. [Why this exists](#why-this-exists)
13. [Roadmap](#roadmap)
14. [Contributing](#contributing)
15. [Contact](#contact)
16. [Author and brand](#author-and-brand)
17. [Provenance and privilege statement](#provenance-and-privilege-statement)
18. [Disclaimer and Bar Council of India Rule 36 compliance](#disclaimer-and-bar-council-of-india-rule-36-compliance)
19. [License](#license)

---

## What this plugin does

This plugin lets an Indian advocate, sitting inside the Claude Desktop application, point at a case folder on disk and obtain a complete intellectual-property litigation pleading in `.docx` form — Cause Title, Parties, Statutory Opening, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, and the accompanying applications (interim injunction under Order 39 Rules 1 and 2 CPC, John Doe / Ashok Kumar / Anton Piller search-and-seizure order, application for appointment of Local Commissioner under Order 26 Rules 9 and 10 CPC, application for ex-parte ad-interim relief, application for damages-rendition of accounts, application for delivery-up and destruction of infringing copies / dies / blocks / moulds) — formatted in the forum's idiom and the case-type-specific structure, sourced from a `case-config.md` file the user places in the case folder.

The pipeline is six agents running in sequence:

1. **Reader** — extracts IP case-facts (parties, nature of right, registration particulars, date of creation / first publication / first use / registration / priority, infringement-mode allegations, prior-use evidence inventory, damages computation) from the case folder with a per-document audit log, and applies the **IP-specific privacy firewall** (every plaintiff name, every defendant name, every copyright-work title, every trade-mark, every patent number, every design registration number, every infringing-product description, and every damages-quantum figure substituted with structural placeholders before downstream AI processing; the placeholder → real-value mapping is stored locally on the user's machine only).
2. **Format** — loads the case-type skill template, reads the user's `case-config.md`, and pre-substitutes forum name (High Court Commercial Division / HC IP Division / District Court / Commercial Court) / case-number prefix (CS (COMM) / CS (OS) / CS (IPD) / C.O. (Comm.IPD-TM / Comm.IPD-PAT) / Tr. P. / DOP) / court-fee / statutory opening / limitation anchor into a `format-shell.md` ready for the Drafter.
3. **Drafter** — writes the actual pleading. Cause Title in the correct forum nomenclature, Parties block, Statutory Opening invoking the operative section, Prelude, Facts as numbered narrative paragraphs with inline exhibit markers, Grounds with statutory anchors and document anchors, Prayer with case-type-specific reliefs (permanent injunction, damages or rendition of accounts, delivery-up of infringing copies / dies / blocks / moulds, declaration of validity / invalidity, rectification / revocation, costs), Verification, Affidavit-in-support, Index, List of Documents, and accompanying applications.
4. **Verifier** — anti-hallucination firewall **plus** **IPAB-abolition currency check** (every reference to the erstwhile Intellectual Property Appellate Board flagged and re-routed to the High Court Intellectual Property Rights Division per Sections 12 to 14 of the Tribunals Reforms Act 2021) **plus** statutory-currency check (CrPC 1973 → BNSS 2023 for ancillary criminal-copyright references; IEA 1872 → BSA 2023 for evidence) **plus** Section 62 Copyright Act jurisdictional check **plus** Section 134 Trade Marks Act jurisdictional check **plus** Section 104 Patents Act jurisdictional check **plus** Section 22 Designs Act jurisdictional check **plus** Section 19 Copyright Act assignment-validity check (where assignment is in issue) **plus** Section 31 / 31D / 31A Copyright Act statutory-licence framework check (where relevant) **plus** Section 31B compulsory-licence framework for the disabled (where relevant) **plus** *American Cyanamid* / *Gujarat Bottling* three-limb test for interim injunction.
5. **Refiner** — applies Verifier flags, polishes language to the formal Indian High Court / District Court register, enforces internal numbering and exhibit-cross-reference consistency, strips AI-style markers, and re-substitutes real party names, real work titles, real trade marks, real patent numbers, real design registration numbers, real infringing-product descriptions, and real damages figures into the final `.docx` (strictly on the user's local machine — the underlying AI never holds real values).
6. **Overseer** — reads the polished draft with an opposing-counsel lens (defendant's counsel for a plaintiff pleading; plaintiff's counsel for a defendant pleading; respondent's counsel for a rectification / revocation applicant; petitioner's counsel for a respondent in rectification / revocation). Flags attackable prior-use defences in trade-mark suits, fair-dealing defences in copyright suits, *Bilski / Aerotel* and Section 3 Patents Act exclusions in patent suits, originality-vs-prior-art defences in design suits, the *Cadila Healthcare* triple-test challenges in passing-off, *Bajaj Auto v. TVS* discipline on patent interim injunctions, Anton Piller / Ashok Kumar over-breadth risk, Order 39 Rule 3 ex-parte affidavit defects, Order 39 Rule 3A six-month adjudication discipline, balance-of-convenience weaknesses, and the *Wander v. Antox* deference framework.

The output is what an advocate would put before the Hon'ble High Court IP Division / Commercial Division / District Court / Commercial Court for filing — **not a template. Not a checklist. A pleading** — ready for the advocate's review, professional verification, signature, court fee, and filing.

---

## Case-type skills (full inventory with statutory authority)

The plugin ships with ten case-type skills, each covering a distinct intellectual-property litigation case-type:

### 1. `copyright-infringement-suit-draft`

**Statutory authority:** Copyright Act 1957 — Section 51 (acts constituting infringement); Section 55 (civil remedies — injunction, damages, rendition of accounts, delivery-up); Section 62 (jurisdiction lies in the District Court within whose local limits the plaintiff resides or carries on business or personally works for gain, displacing Section 20 CPC); Section 14 (rights conferred by copyright); Section 17 (first owner of copyright); Section 18 (assignment of copyright); Section 19 (mode of assignment — writing + duration + territorial extent); Section 22 (term of copyright); Section 52 (acts not constituting infringement — fair dealing). **Use case:** copyright owner / exclusive licensee suing for infringement of a literary / dramatic / musical / artistic / cinematograph / sound-recording / software work. **Output:** complete plaint with Cause Title in District Court / High Court Commercial Division nomenclature (Section 62 Copyright Act anchors jurisdiction at plaintiff), Section 51 read with Section 55 statutory opening, full Facts paragraphs anchored to creation / first publication / registration (if any — copyright subsists without registration per Section 13 read with Section 44) / assignment / licensing / infringement-mode evidence, Grounds, Prayer with permanent injunction + damages or rendition of accounts + delivery-up of infringing copies + costs, accompanying interim-injunction and John Doe / Ashok Kumar applications.

### 2. `copyright-fair-dealing-defence-draft`

**Statutory authority:** Copyright Act 1957 — Section 52 (acts not constituting infringement); the *Civic Chandran v. Ammini Amma* (1996) 16 PTC 670 (Ker) framework; the *Eastern Book Company v. D.B. Modak* (2008) 1 SCC 1 framework on transformation / originality. **Use case:** alleged infringer pleading the Section 52 defence (research / private use / criticism / review / news reporting / educational use / library reproduction / Government publications etc.). **Output:** complete written statement-style defence pleading with each Section 52 sub-clause pleaded affirmatively with particularity (which sub-clause, what factual basis, what attribution-given evidence, what de minimis / transformative-use argument), Grounds for dismissal of the plaint, Prayer for dismissal with costs.

### 3. `trademark-infringement-suit-draft`

**Statutory authority:** Trade Marks Act 1999 — Section 29 (infringement of registered trade marks); Section 134 (jurisdiction — District Court / High Court Commercial Division at the place where the plaintiff actually and voluntarily resides or carries on business or personally works for gain, displacing Section 20 CPC); Section 135 (reliefs — injunction, damages or account of profits, delivery-up); Section 28 (rights conferred by registration); Section 31 (registration prima-facie evidence of validity); Section 33 (acquiescence); Section 34 (saving for vested rights — prior use); Section 35 (use of own name / description); Section 47 (removal for non-use); the *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 triple-test framework for confusion; the *Milmet Oftho v. Allergan* (2004) 12 SCC 624 transborder-reputation framework. **Use case:** registered trade-mark proprietor suing for infringement by use of identical / deceptively similar mark in respect of identical / similar / dissimilar goods or services. **Output:** complete plaint with Cause Title in District Court / High Court Commercial Division nomenclature (Section 134 Trade Marks Act anchors jurisdiction at plaintiff), Section 29 read with Section 135 statutory opening, full Facts paragraphs anchored to adoption / first use / registration / reputation / infringement-mode evidence, Grounds, Prayer with permanent injunction + damages or account of profits + delivery-up of infringing labels / packaging + costs, accompanying interim-injunction and John Doe / Ashok Kumar applications.

### 4. `passing-off-suit-draft`

**Statutory authority:** Common-law tort of passing-off, read with Section 27(2) of the Trade Marks Act 1999 (which saves the action for passing-off whether or not the mark is registered); the *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 triple-test framework (goodwill / misrepresentation / damage); the *N.R. Dongre v. Whirlpool* (1996) 5 SCC 714 framework on transborder reputation; the *Toyota Jidosha Kabushiki Kaisha v. Prius Auto Industries* (2018) 2 SCC 1 framework on territorial extent of goodwill. **Use case:** unregistered-mark holder (or registered-mark holder pleading passing-off in addition to infringement) suing the defendant for representing the defendant's goods or services as those of the plaintiff. **Output:** complete plaint with Cause Title in District Court / High Court Commercial Division nomenclature (Section 134 Trade Marks Act does not extend to a pure passing-off action — Section 20 CPC applies; for a composite infringement-and-passing-off suit, Section 134 anchors), statutory opening (Section 27 TMA + common-law tort), full Facts paragraphs anchored to goodwill build-up + misrepresentation acts + damage / likelihood of damage, Grounds, Prayer with permanent injunction + damages or rendition of accounts + delivery-up + costs.

### 5. `trademark-rectification-application-draft`

**Statutory authority:** Trade Marks Act 1999 — Section 57 (rectification of the Register and cancellation of registration on grounds of contravention or failure to observe a condition of registration, or absence of bona fide intention to use, or non-use, or that the registration is contrary to Sections 9, 11, 12); Sections 47 (removal for non-use); the **post-IPAB-abolition transition** under Sections 12 to 14 of the Tribunals Reforms Act 2021 — every reference to the erstwhile Intellectual Property Appellate Board as the appellate / rectification forum is **expressly displaced** by the transfer of jurisdiction to the High Court Intellectual Property Rights Division (Delhi / Madras / Calcutta / Bombay HC IPD where established; otherwise the High Court of competent jurisdiction). **Use case:** any aggrieved person (including a rival mark proprietor / a person whose interests are prejudicially affected by the registered mark) applying for rectification or cancellation of the Register. **Output:** complete rectification application with Cause Title in the High Court Intellectual Property Rights Division nomenclature (NOT IPAB nomenclature — see IPAB Abolition section below), Section 57 statutory opening, full Facts paragraphs anchored to the registered mark + ground for rectification (Section 9 / Section 11 / Section 12 / Section 47 non-use / Section 57(1) wrongful entry / etc.) + the rectification-applicant's standing, Grounds, Prayer with rectification of the Register / removal of the mark from the Register / variation of conditions, supporting affidavits.

### 6. `patent-infringement-suit-draft`

**Statutory authority:** Patents Act 1970 (as amended by the Patents (Amendment) Act 2005) — Section 104 (jurisdiction — District Court / High Court of competent pecuniary jurisdiction; counterclaim for revocation transfers the suit to the High Court); Section 108 (reliefs — injunction, damages or account of profits, seizure / forfeiture / destruction of infringing goods); Section 48 (rights conferred by a patent); Section 64 (revocation grounds — typically pleaded by way of counter-claim and triggering Section 104 transfer); Section 107 (defences); Section 107A (Bolar exemption / parallel-import defence); the *Bajaj Auto Ltd. v. TVS Motor Company* (2009) 9 SCC 797 framework on day-to-day hearing in patent matters; the *F. Hoffmann-La Roche v. Cipla* (2015) 65 PTC 187 (DB Del) framework on credible-challenge-to-validity at the interim-injunction stage; the *Merck Sharp & Dohme v. Glenmark* (2015) 64 PTC 417 (DB Del) framework. **Use case:** patentee or exclusive licensee suing for infringement of a granted patent. **Output:** complete plaint with Cause Title in District Court / High Court nomenclature (Section 104 first proviso transfers to High Court on counter-claim for revocation), Section 104 read with Section 108 statutory opening, full Facts paragraphs anchored to grant of patent + claim-construction + infringement-mode evidence + comparison of accused product / process to the patent claims (Markman-type chart in the form of an Annexure), Grounds, Prayer with permanent injunction + damages or account of profits + seizure / forfeiture / destruction of infringing goods + costs, accompanying interim-injunction application with the *Bajaj Auto* and *F. Hoffmann-La Roche* discipline.

### 7. `patent-revocation-application-draft`

**Statutory authority:** Patents Act 1970 — Section 64 (revocation of a patent on grounds of want of novelty / want of inventive step / non-patentable subject matter under Section 3 / insufficient disclosure under Section 10(4) / wrongful obtainment / false suggestion / non-disclosure of foreign filings under Section 8 / non-working under Section 64(1)(m)); the **post-IPAB-abolition transition** under Sections 12 to 14 of the Tribunals Reforms Act 2021 — every reference to the IPAB as the revocation forum is **expressly displaced** by the transfer of jurisdiction to the High Court Intellectual Property Rights Division; Section 117G (transfer of pending IPAB proceedings to the High Court); the *Aloys Wobben v. Yogesh Mehra* (2014) 15 SCC 360 framework on choice of revocation forum (Section 64 application before HC IPD or counter-claim in a Section 104 patent infringement suit — not both). **Use case:** any person interested (including a competitor / a person whose business is affected by the patent / a Government party) applying for revocation of a granted patent. **Output:** complete revocation application with Cause Title in the High Court Intellectual Property Rights Division nomenclature (NOT IPAB nomenclature), Section 64 statutory opening with the specific sub-clauses invoked, full Facts paragraphs anchored to the granted patent + prior-art chart (Annexure with claim-construction + invalidity charts) + the applicant's standing as a person-interested, Grounds, Prayer for revocation of the patent / striking down of specified claims / costs, supporting affidavits and expert declarations.

### 8. `design-piracy-suit-draft`

**Statutory authority:** Designs Act 2000 — Section 22 (piracy of registered design — civil remedies including injunction, damages up to ₹25,000 per design contravention not exceeding ₹50,000 in respect of any one design, recovery as damages or contract debt at the proprietor's option); Section 19 (cancellation of a registered design — typically pleaded by way of counter-claim and transferring the suit to the High Court under Section 22(4)); Section 2(d) (definition of design); Section 4 (prohibition of registration of certain designs); the *Bharat Glass Tube v. Gopal Glass Works* (2008) 10 SCC 657 framework on novelty and originality; the *Carlsberg Breweries v. Som Distilleries & Breweries Ltd.* (2018) 76 PTC 1 (DB Del) framework on composite suit for design piracy + passing off. **Use case:** registered-design proprietor suing for piracy of the registered design (applied to the same or similar article, fraudulently or obviously imitated). **Output:** complete plaint with Cause Title in District Court / High Court nomenclature (Section 22(4) transfers to High Court on counter-claim for cancellation), Section 22 read with Section 19 statutory opening, full Facts paragraphs anchored to date of design registration + registered features (visual appeal — shape / configuration / pattern / ornament / composition of lines or colours) + the infringing-article features + comparison chart (Annexure), Grounds, Prayer with permanent injunction + damages (subject to the Section 22(2) cap) or contract-debt recovery + delivery-up of infringing articles / dies / blocks / moulds + costs, accompanying interim-injunction application.

### 9. `john-doe-anton-piller-order-application-draft`

**Statutory authority:** Code of Civil Procedure 1908 — Order 39 Rules 1 and 2 (temporary injunction); Order 26 Rules 9 and 10 (Local Commissioner for inspection / seizure); the *Anton Piller KG v. Manufacturing Processes Ltd.* [1976] Ch 55 framework as adopted into Indian practice via *Bucyrus Europe Ltd. v. Vulcan Industries* (2005) 30 PTC 280 (Cal); the *Taj Television Ltd. v. Rajan Mandal* (2003) 26 PTC 627 (Del) framework for John Doe / Ashok Kumar orders against unknown infringers in cinematograph / broadcast contexts. **Use case:** any IP plaintiff seeking (i) ex-parte search-and-seizure orders against identified defendants where evidence is likely to be destroyed on notice (Anton Piller), or (ii) ex-parte injunctive relief and Local Commissioner appointment against unknown infringers (John Doe / Ashok Kumar) — typically in cinematograph piracy, software piracy, counterfeit-good ring, or broadcast-signal-theft contexts. **Output:** complete application with Cause Title and case-tag matched to the parent suit, statutory opening (Order 39 read with Order 26 CPC + the Anton Piller / Taj Television framework), full Facts paragraphs anchored to the threat of evidence destruction / the open-ended class of unknown infringers / the irreparable injury to the plaintiff, Grounds, Prayer for (a) ex-parte ad-interim injunction restraining identified / unknown defendants; (b) appointment of a Local Commissioner under Order 26 with powers of entry / inspection / seizure / sealed-cover deposit; (c) directions on inventory; (d) protection of the defendant's confidentiality by sealed-cover filing pending inter-partes hearing; (e) costs.

### 10. `interim-injunction-application-ip-draft`

**Statutory authority:** Code of Civil Procedure 1908 — Order 39 Rules 1 and 2 (temporary injunction); Order 39 Rule 3 (ex-parte ad-interim order — reasons recorded in writing); Order 39 Rule 3A (decision within 30 days where ex-parte order made — the *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225 discipline); the *American Cyanamid Co. v. Ethicon Ltd.* [1975] AC 396 / *Gujarat Bottling Co. Ltd. v. Coca-Cola Co.* (1995) 5 SCC 545 three-limb framework (prima facie case + balance of convenience + irreparable injury); the *Wander Ltd. v. Antox India Pvt. Ltd.* 1990 Supp SCC 727 framework on appellate deference; the *Bajaj Auto Ltd. v. TVS Motor Company* (2009) 9 SCC 797 framework on day-to-day hearing of IP injunctions; the *F. Hoffmann-La Roche v. Cipla* (2015) 65 PTC 187 (DB Del) framework on credible-challenge-to-validity in patent injunctions. **Use case:** any IP plaintiff applying for an interim / ex-parte ad-interim injunction in any case-type (copyright / trade mark / passing-off / patent / design / John Doe). **Output:** complete application with Cause Title and case-tag matched to the parent suit, Order 39 Rules 1 and 2 statutory opening, full Facts paragraphs anchored to the three limbs of the *American Cyanamid* / *Gujarat Bottling* test — prima facie case (with evidence of right and infringement) + balance of convenience (with concrete particulars of the plaintiff's investment / market reputation versus the defendant's recent or limited use) + irreparable injury (with particulars of why damages are an inadequate remedy), Grounds, Prayer for (a) interim injunction restraining the defendant from the infringing acts pending the suit; (b) ex-parte ad-interim relief under Order 39 Rule 3 where notice would defeat the purpose; (c) cross-undertaking on damages (*Bajaj Auto* discipline); (d) appointment of Local Commissioner where seizure of infringing stock is sought; (e) costs.

### Shared infrastructure skills

- **`_drafting_common`** — anti-pollution rules, IP-specific privacy firewall (plaintiff / defendant / work title / trade mark / patent / design / damages substitution), AI-style-marker blacklist, citation discipline, **statutory currency rules** (CrPC 1973 → BNSS 2023 for criminal-copyright references; IEA 1872 → BSA 2023 for evidence; Companies Act 1956 → 2013 transitions), **IPAB-abolition currency rule** (every IPAB reference flagged and re-routed to HC IP Division per Tribunals Reforms Act 2021), **Copyright firewall** (Moral Rights and Reversionary Interests encoded by Section 19 Copyright Act 1957 alone — no proprietary clause-prose), **Limitation Act 1963 Article map** for IP actions, **Section 62 Copyright Act / Section 134 Trade Marks Act / Section 104 Patents Act / Section 22 Designs Act jurisdictional rules**, **Commercial Courts Act 2015** mandatory-mediation pre-institution rule (post-*Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 — pre-institution mediation under Section 12A is **mandatory** for commercial suits not contemplating urgent interim relief; IP suits typically contemplate urgent interim relief and are accordingly exempt — the Verifier flags any IP plaint that fails to plead urgent interim relief expressly).
- **`_ip_drafting_base`** — universal Indian intellectual-property pleading skeleton (Cause Title, Parties block, Statutory Opening, Prelude, Facts, Grounds, Prayer, Verification, Affidavit-in-support, Index, List of Documents, accompanying applications including Order 39 interim injunction and John Doe / Anton Piller order applications).

---

## The 6-agent drafting pipeline

| Agent | What it reads | What it writes | Key IP-domain specialisation |
|---|---|---|---|
| **`reader`** | Every file in the case folder + the case-type skill's expected exhibits list | `case-facts.md` with per-document audit log + privacy-firewalled placeholder mapping in the header | Privacy firewall — substitutes plaintiff names + defendant names + copyright-work titles + trade marks + patent numbers + design registration numbers + infringing-product descriptions + damages figures before downstream AI processing; mapping stored locally only |
| **`format`** | `case-facts.md` + `case-config.md` + case-type SKILL.md + `_ip_drafting_base` | `format-shell.md` with forum / case-number-prefix / court-fee / statutory-opening / limitation-anchor pre-substituted | Resolves High Court Commercial Division vs HC IP Division vs District Court vs Commercial Court nomenclature for the Cause Title; resolves Section 62 / Section 134 / Section 104 / Section 22 jurisdictional anchor |
| **`drafter`** | `case-facts.md` + `format-shell.md` + case-type SKILL.md + `_ip_drafting_base` + law PDFs | `draft-v1.md` + `draft-v1.docx` | Writes Cause Title + Parties + Statutory Opening + Prelude + Facts (with inline exhibit markers) + Grounds + Prayer + Verification + Affidavit + Index + List of Documents + accompanying applications (interim injunction + John Doe / Anton Piller where applicable) |
| **`verifier`** | `draft-v1.md` + `case-facts.md` + `case-config.md` + law PDFs | `verification-report.md` | Anti-hallucination + **IPAB-abolition currency** (every IPAB reference flagged) + statutory currency (CrPC → BNSS / IEA → BSA / Companies Act 1956 → 2013) + Section 62 / 134 / 104 / 22 jurisdictional anchor + Section 19 Copyright Act assignment-validity (where in issue) + *American Cyanamid* / *Gujarat Bottling* three-limb interim-injunction discipline + *Bajaj Auto* / *F. Hoffmann-La Roche* patent-injunction discipline + Section 3 Patents Act non-patentable-subject-matter check (in revocation pleadings) + Section 9 / 11 / 12 Trade Marks Act absolute / relative grounds for refusal (in rectification pleadings) + Section 4 Designs Act non-registrability (in design suits) + **Copyright firewall** (no proprietary Moral Rights / Reversionary Interests clause-prose — statutory rewrite under Section 19 only) |
| **`refiner`** | `draft-v1.md` + `verification-report.md` + `case-config.md` + `case-facts.md` | `draft-v2.md` + `draft-v2.docx` | Polish to Indian High Court / District Court / Commercial Court formal register + internal numbering / cross-reference / exhibit-marker consistency + privacy-firewall reversal (real values re-substituted from local mapping into final `.docx`) |
| **`overseer`** | `draft-v2.docx` + `case-facts.md` + `case-config.md` | `opposing-notes.md` + `final-draft.docx` | Opposing-counsel critique — prior-use defences (Section 34 Trade Marks Act), Section 52 fair-dealing defences (Copyright), Section 3 Patents Act exclusions and Section 107A Bolar / parallel-import defences, *Cadila Healthcare* triple-test attacks on passing-off, prior-art attacks on designs, Anton Piller / Ashok Kumar over-breadth, Order 39 Rule 3 ex-parte affidavit defects, Order 39 Rule 3A six-month discipline, *Wander v. Antox* appellate-deference framework |

---

## Installation

This is a Claude-compatible plugin in the Anthropic plugin format, designed to run inside the **Claude Desktop application** (available at <https://claude.ai/download>). The plugin folder location depends on your operating system:

| Operating system | Plugin folder path |
|---|---|
| **macOS** | `~/Library/Application Support/Claude/plugins/` |
| **Linux** | `~/.config/Claude/plugins/` |

Clone the plugin into that folder:

```bash
# macOS / Linux
mkdir -p ~/Library/Application\ Support/Claude/plugins   # adjust per OS table
cd ~/Library/Application\ Support/Claude/plugins
git clone https://github.com/Wolfgangrush/indian-ip-drafting.git indian-ip-drafting
```

Restart the Claude Desktop application. The plugin is auto-discovered on the next session start.

### Anthropic Plugin Marketplace (when available)

When the plugin lands on the Anthropic Plugin Marketplace, you will be able to install it from inside the application's plugin browser without `git`. Until then, the manual clone steps above are canonical.

### Verifying the install

In a Claude session, type:

- *"draft copyright infringement suit"* — triggers `copyright-infringement-suit-draft`
- *"draft fair-dealing defence"* — triggers `copyright-fair-dealing-defence-draft`
- *"draft trade mark infringement suit"* — triggers `trademark-infringement-suit-draft`
- *"draft passing-off suit"* — triggers `passing-off-suit-draft`
- *"draft trade mark rectification"* — triggers `trademark-rectification-application-draft`
- *"draft patent infringement suit"* — triggers `patent-infringement-suit-draft`
- *"draft patent revocation"* — triggers `patent-revocation-application-draft`
- *"draft design piracy suit"* — triggers `design-piracy-suit-draft`
- *"draft John Doe order"* / *"draft Anton Piller"* / *"draft Ashok Kumar"* — triggers `john-doe-anton-piller-order-application-draft`
- *"draft interim injunction"* / *"draft Order 39 Rule 1 application"* — triggers `interim-injunction-application-ip-draft`

---

## Your first pleading — step-by-step walkthrough

Suppose you wish to draft a **trade mark infringement suit** under Section 29 read with Section 134 and Section 135 of the Trade Marks Act 1999, before the Commercial Division of the Delhi High Court, on behalf of a registered-mark proprietor against a defendant using a deceptively similar mark.

### Step 1 — create a case folder

```
~/Desktop/cases/
└── cs-comm-tm-2026-MARK-MATTER/
    ├── case-config.md         ← declares forum + claim quantum + nature of IP + registration particulars
    ├── inputs/
    │   ├── trade-mark-registration-certificate.pdf
    │   ├── renewal-certificate.pdf
    │   ├── evidence-of-prior-use.pdf
    │   ├── market-survey-report.pdf
    │   ├── infringement-product-photos.pdf
    │   ├── cease-and-desist-correspondence.pdf
    │   ├── damages-quantum-computation.pdf
    │   └── board-resolution-authorising-filing.pdf
    └── laws/
        ├── trade-marks-act-1999.pdf
        ├── trade-marks-rules-2017.pdf
        ├── cpc-1908-order-39.pdf
        ├── commercial-courts-act-2015.pdf
        ├── delhi-hc-ipd-rules-2022.pdf
        └── limitation-act-1963.pdf
```

### Step 2 — write `case-config.md`

```yaml
forum: "High Court of Delhi at New Delhi (Commercial Division / Intellectual Property Rights Division as applicable)"
case_type: "trademark-infringement-suit"
case_number_year: 2026
case_number_prefix: "CS (COMM)"
claim_quantum_rupees: 20000000          # ₹2 crore
nature_of_ip: "registered_trade_mark"
trade_mark_registration_no: "[TM-Reg-No-Placeholder]"
trade_mark_class: "[Class-Placeholder]"
date_of_first_use: "[Date-of-First-Use-Placeholder]"
date_of_registration: "[Date-of-Registration-Placeholder]"
last_renewal_date: "[Renewal-Date-Placeholder]"
infringement_mode: "use_of_deceptively_similar_mark_in_respect_of_identical_goods"
jurisdiction_anchor: "Section 134(2) Trade Marks Act 1999 — plaintiff carries on business at New Delhi"
limitation_article: "Article 75"
limitation_anchor_date: "[Date-of-Knowledge-of-Infringement-Placeholder]"
limitation_filing_date: "[Date-of-Filing-Placeholder]"
urgent_interim_relief_pleaded: true     # Section 12A Commercial Courts Act exemption
authorised_signatory_role: "Director (per Board Resolution dated [BR-Date-Placeholder])"
parties:
  - role: "Plaintiff"
    party_type: "Registered trade mark proprietor (Private Limited Company)"
    party_name: "[Plaintiff-Name-Placeholder]"
  - role: "Defendant No. 1"
    party_type: "Alleged infringer (Private Limited Company)"
    party_name: "[Defendant-Name-Placeholder]"
  - role: "Defendant No. 2"
    party_type: "Director of Defendant No. 1 (joinder under Companies Act 2013)"
    party_name: "[Director-Name-Placeholder]"
```

### Step 3 — invoke the plugin

Open Claude Desktop, navigate to the case folder, and type:

> *draft trade mark infringement suit*

The pipeline runs:

1. **Reader** reads every PDF in `inputs/`, builds `case-facts.md` with privacy-firewalled placeholder mapping, validates that all required statutes are in `laws/`.
2. **Format** loads the `trademark-infringement-suit-draft` skill, reads `case-config.md`, builds `format-shell.md`.
3. **Drafter** writes `draft-v1.md` and `draft-v1.docx`.
4. **Verifier** reads `draft-v1.md` against `case-facts.md`, writes `verification-report.md`.
5. **Refiner** applies the verification flags, polishes the prose, re-substitutes real values, writes `draft-v2.docx`.
6. **Overseer** reads `draft-v2.docx` with a defendant's-counsel lens, writes `opposing-notes.md` and `final-draft.docx`.

The advocate now reviews `final-draft.docx` against `opposing-notes.md`, makes professional adjustments, applies court fee, signs the verification, swears the affidavit, and files.

---

## The `case-config.md` file

This file declares all forum-level / case-type-level / matter-level constants that the plugin substitutes into the format shell. Keep it on the user's local machine — `.gitignore` excludes it from any git repo.

Minimum fields:

- `forum` — exact name of the court / division (e.g. *"High Court of Delhi at New Delhi (Commercial Division / Intellectual Property Rights Division)"* / *"High Court of Judicature at Madras (Intellectual Property Rights Division)"* / *"District Court at Tis Hazari, Delhi (Commercial Court of competent pecuniary jurisdiction under the Commercial Courts Act 2015)"*)
- `case_type` — one of the ten supported case types
- `case_number_year` — current year for case-number placeholder
- `case_number_prefix` — CS (COMM) / CS (OS) / CS (IPD) / C.O. (Comm.IPD-TM) / C.O. (Comm.IPD-PAT) / Tr. P. / DOP — per the forum's nomenclature
- `claim_quantum_rupees` — the principal claim figure (or the damages figure)
- `nature_of_ip` — one of *"copyright_work"* / *"registered_trade_mark"* / *"unregistered_mark_passing_off"* / *"granted_patent"* / *"registered_design"*
- IP-specific registration particulars (copyright registration number if registered / trade-mark registration number + class / patent number / design registration number)
- `date_of_first_use` / `date_of_first_publication` / `date_of_registration` / `date_of_priority` (as applicable)
- `infringement_mode` — particulars of the alleged infringing act
- `jurisdiction_anchor` — Section 62 Copyright Act / Section 134 Trade Marks Act / Section 104 Patents Act / Section 22 Designs Act / Section 20 CPC (for pure passing-off)
- `limitation_article` + `limitation_anchor_date` + `limitation_filing_date`
- `urgent_interim_relief_pleaded` — *true* or *false* (for Section 12A Commercial Courts Act mandatory-mediation exemption)
- `authorised_signatory_role` + `board_resolution_date`
- `parties` — list of party-role + party-type + party-name-placeholder

Case-type-specific fields (for the relevant skill) layer on top of the minimum schema — see each case-type SKILL.md.

---

## Built-in compliance disciplines

The Verifier enforces several disciplines mandatory in Indian intellectual-property practice — see `skills/_drafting_common/SKILL.md` for the full discipline framework. Headline disciplines:

- **IPAB-abolition currency** — every reference to the erstwhile Intellectual Property Appellate Board as an appellate / rectification / revocation forum is flagged and re-routed to the High Court Intellectual Property Rights Division per Sections 12 to 14 of the Tribunals Reforms Act 2021.
- **Section 62 Copyright Act jurisdictional rule** — copyright infringement suits lie in the District Court within whose local limits the plaintiff actually and voluntarily resides or carries on business or personally works for gain (Section 62 displaces Section 20 CPC).
- **Section 134 Trade Marks Act jurisdictional rule** — trade-mark infringement suits lie at the place where the plaintiff actually and voluntarily resides or carries on business or personally works for gain (Section 134 displaces Section 20 CPC; the *IPRS v. Sanjay Dalia* (2015) 10 SCC 161 framework qualifies — plaintiff must establish the principal-place-of-business connection).
- **Section 104 Patents Act jurisdictional rule** — patent infringement suits lie in the District Court of competent pecuniary jurisdiction; on counter-claim for revocation under Section 64, the suit transfers to the High Court (Section 104 first proviso).
- **Section 22 Designs Act jurisdictional rule** — design piracy suits lie in the Court of District Judge or higher; on counter-claim for cancellation under Section 19, the suit transfers to the High Court (Section 22(4)).
- **Commercial Courts Act 2015 — Section 12A mandatory pre-institution mediation** — every commercial suit not contemplating urgent interim relief must undergo pre-institution mediation under Section 12A read with the *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework. IP suits typically contemplate urgent interim relief and are accordingly exempt — the Verifier flags any IP plaint that fails to plead urgent interim relief expressly in the body and the prayer.
- **Order 39 Rule 3 / Rule 3A discipline** — every ex-parte interim order requires reasons recorded in writing and is to be disposed of within 30 days of the application (the *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225 framework on ex-parte injunctions). The Verifier flags any application that fails to plead the why-notice-would-defeat-the-purpose case.
- **American Cyanamid / Gujarat Bottling three-limb test** — every interim-injunction application must plead, with particulars, (i) prima facie case, (ii) balance of convenience, (iii) irreparable injury. The *Wander v. Antox* discipline on appellate deference is noted in the *Overseer*'s checklist.
- **Limitation Act 1963 discipline** — applicable Article per case-type: Article 75 for trade-mark infringement / passing-off (3 years from date of knowledge / each continuing act); Article 113 for copyright infringement (3 years residual); Article 113 for patent infringement (3 years residual / each continuing infringement); Article 113 for design piracy (3 years residual).
- **Section 19 Copyright Act assignment-validity** — wherever an assignment of copyright is in issue, the Verifier checks that the assignment is (a) in writing, (b) signed by the assignor, (c) identifies the work, (d) specifies the rights assigned, (e) specifies the duration, (f) specifies the territorial extent, and (g) (per the 2012 amendment) does not contravene the second proviso to Section 19(3) on the share of royalties due to the author.
- **Section 3 Patents Act non-patentable subject matter** — in any revocation pleading or fairness-of-grant ground, the Verifier checks the Section 3 clauses pleaded with particularity (Section 3(d) on incremental innovation post-*Novartis v. Union of India* (2013) 6 SCC 1 / Section 3(k) on computer programs per se / Section 3(b) on morality / etc.).
- **Statutory-currency discipline** — Section 200 CrPC references converted to Section 223 BNSS for any ancillary copyright criminal complaint references; Section 65B IEA references converted to Section 63 BSA for digital-evidence pleadings; Companies Act 1956 references converted to Companies Act 2013 for corporate-party pleadings.
- **Copyright firewall** — clauses on *Moral Rights* and *Reversionary Interests* are encoded by Section 19 of the Copyright Act 1957 alone, in statutory-only paraphrase. No proprietary commentary or proprietary clause-prose is imported.

---

## Privacy firewall — extra discipline for IP content

Intellectual-property pleadings contain some of the most commercially sensitive material an advocate handles — registered trade marks (often the proprietor's brand identity), copyright work titles (often unpublished or commercially sensitive), patent numbers and the proprietary technology that the claims describe, design registration numbers (often the look-and-feel of products in pipeline), infringing-product descriptions (often involving photographs of the defendant's wares), damages computations (often involving the plaintiff's revenue / profit data), market-survey reports, cease-and-desist correspondence. The plugin's privacy discipline is therefore stricter than the generic discipline of sibling plugins:

1. **Reader** substitutes every plaintiff name, every defendant name, every copyright-work title, every trade mark, every patent number, every design registration number, every infringing-product description, and every damages-quantum figure with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw trade marks, raw patent numbers, raw design numbers, or raw damages figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

The user can verify the firewall by inspecting `case-facts.md` after the Reader runs — every party name appears as `[Plaintiff]` / `[Defendant No. 1]`, every trade mark as `[Trade-Mark-Placeholder]`, every patent number as `[Patent-No.-Placeholder]`, every design number as `[Design-Reg-No.-Placeholder]`. The mapping is in the header of the same file.

---

## IPAB abolition — appellate-forum currency

Until 2021, the Intellectual Property Appellate Board (IPAB) constituted under Section 83 of the Trade Marks Act 1999 (and the parallel provisions in the Patents Act 1970, Copyright Act 1957, and Geographical Indications of Goods (Registration and Protection) Act 1999) was the appellate forum for orders of the Registrar of Trade Marks, the Controller of Patents, the Registrar of Copyright, and the Registrar of Geographical Indications, and the original forum for rectification of the Trade Mark Register under Section 57 Trade Marks Act 1999 and for revocation of a patent under Section 64 Patents Act 1970.

**The IPAB stands abolished by the Tribunals Reforms Act 2021** (Act 33 of 2021), which received Presidential assent on 13 August 2021. Sections 12 to 14 of the Tribunals Reforms Act 2021 effect the abolition of the IPAB and the transfer of pending IPAB proceedings to the High Courts. The jurisdiction earlier vested in the IPAB now lies in the **High Court of competent jurisdiction**, exercised through the **Intellectual Property Rights Division** of that High Court where one has been constituted by Practice Direction or Rules of the High Court.

Constituted IP Divisions as at the date of this release:

- **Delhi High Court Intellectual Property Rights Division** — constituted by the Delhi High Court Intellectual Property Rights Division Rules 2022 (notified 24 February 2022).
- **Madras High Court Intellectual Property Rights Division** — constituted by the Madras High Court Intellectual Property Rights Division Rules.
- **Calcutta High Court** — IP roster in operation; IPD Rules notified.
- **Bombay High Court** — IP roster in operation; IPD Rules under consideration.

The Verifier flags any reference to the IPAB as a live forum and re-routes the Cause Title to the High Court Intellectual Property Rights Division (or the High Court of competent jurisdiction where no IPD has been constituted). Past references to IPAB decisions remain valid as precedent and may be cited; what is flagged is the use of IPAB as a *present-day forum* in the Cause Title or prayer.

---

## Why MIT License

The MIT licence is the most permissive widely-recognised open-source licence. Anyone may use, modify, distribute, sublicense, or sell the plugin or any derivative. The licence is short, well-understood, and compatible with every other open-source licence the legal community is likely to encounter. No proprietary gating, no field-of-use restriction, no contributor licence agreement (CLA) gymnastics. The accompanying `NOTICE.md` does not modify the licence — it documents the provenance and the privilege position so that any future audit can verify the plugin's clean origin.

---

## Sibling plugins

This plugin is one in the **Wolfgang Rush** family of Indian legal-drafting plugins. All thirteen siblings ship under the same six-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) and the family-of-plugins doctrine — each plugin narrowly scoped to one practice area / forum:

| Plugin | GitHub repo | Scope |
|---|---|---|
| `supreme-court-drafting` | [supreme-court-drafting-litigation](https://github.com/Wolfgangrush/supreme-court-drafting-litigation) | SLPs · Writ Art 32 · Transfer · Review · Curative — Supreme Court of India |
| `indian-hc-drafting` | [indian-hc-drafting-litigation](https://github.com/Wolfgangrush/indian-hc-drafting-litigation) | Pleadings across all 25 Indian High Courts (bench-config-aware) |
| `district-court-drafting` | [district-court-drafting-litigation](https://github.com/Wolfgangrush/district-court-drafting-litigation) | Plaints · WS · CPC applications · BNSS complaints across 25+ States (state-config) |
| `indian-family-drafting` | [indian-family-drafting-litigation](https://github.com/Wolfgangrush/indian-family-drafting-litigation) | HMA · SMA · IDA · matrimonial · custody · DV Act · maintenance · adoption |
| `indian-contracts-drafting` | [indian-contracts-drafting-litigation](https://github.com/Wolfgangrush/indian-contracts-drafting-litigation) | MSA · NDA · employment · lease · sale · GPA · SHA · will · loan · arbitration |
| `indian-banking-drafting` | [indian-banking-drafting-litigation](https://github.com/Wolfgangrush/indian-banking-drafting-litigation) | DRT · SARFAESI · NI Act 138 · IBC §7 / §95 · DRAT |
| `indian-labour-drafting` | [indian-labour-drafting-litigation](https://github.com/Wolfgangrush/indian-labour-drafting-litigation) | ID Act · POSH · PG · EPF · ESI · MW · IESO + State exemplars |
| `indian-property-drafting` | [indian-property-drafting-litigation](https://github.com/Wolfgangrush/indian-property-drafting-litigation) | Gift · Exchange · Release · Trust · Wakf · Easement · Partition · Settlement · Mortgage · TIR |
| `indian-company-drafting` | [indian-company-drafting](https://github.com/Wolfgangrush/indian-company-drafting) | NCLT (241/242 · 245 · 230-232 · 66 · 252 · 213) · NCLAT (421 + 61) · IBC §9 / §10 |
| `indian-tax-drafting` | [indian-tax-drafting](https://github.com/Wolfgangrush/indian-tax-drafting) | Form 35 CIT(A) · Form 36 ITAT · Form 10A · Sec 148A · 263/264 · 271/270A · 144C · 201 · 260A |
| `indian-consumer-drafting` | [indian-consumer-drafting](https://github.com/Wolfgangrush/indian-consumer-drafting) | District / State / NCDRC + medical-negligence + product liability |
| `indian-mact-drafting` | [indian-mact-drafting](https://github.com/Wolfgangrush/indian-mact-drafting) | MV Act 1988 (2019 amended) · Sarla Verma + Pranay Sethi · state-config |
| `indian-ip-drafting` (this) | [indian-ip-drafting](https://github.com/Wolfgangrush/indian-ip-drafting) | Copyright · Trade Marks · Patents · Designs + HC IP Divisions (post-IPAB-abolition) + Anton Piller / John Doe |

Each plugin can be installed independently, each plugin's Rule 36 firewall is narrow and reviewable, each plugin's bench / forum discipline is depth-validated within its scope, and the user installs only what they need.

---

## Why this exists

Indian intellectual-property practice has, in the post-IPAB-abolition era (post-2021), undergone a substantial procedural restructuring. The appellate forum for rectification of the Trade Mark Register, for revocation of patents, for appeals from orders of the Registrar of Copyright and the Controller of Patents, has shifted from a specialised tribunal to the High Court Intellectual Property Rights Division. The Delhi High Court IPD Rules 2022 are in force; the Madras High Court IPD Rules are in force; the Calcutta High Court has notified an IP roster; the Bombay High Court has an IP roster in operation. The pleading conventions have shifted accordingly, and the practising IP advocate now negotiates between (a) the High Court Commercial Division, (b) the High Court Intellectual Property Rights Division, (c) the District Court of competent pecuniary jurisdiction, and (d) the Commercial Court under the Commercial Courts Act 2015 (and the Section 12A pre-institution mediation regime as clarified by *Patil Automation*).

There is, as at the date of this release, no open-source pleading-drafting infrastructure for the Indian IP practitioner. Practising advocates piece together pleadings from their own past drafts, from senior advocates' templates, from the various textbook precedent collections (Narayanan, Iyengar, Ananth Padmanabhan, the *Sarkar / Tewari / Cornish / Bently & Sherman* commentary lineages), and from such precedent volumes as the publishers issue from time to time. The result is uneven quality, uneven compliance with the post-IPAB-abolition transition, uneven discipline on the procedural traps (Section 12A mediation exemption pleading / Order 39 Rule 3 ex-parte affidavit / Order 39 Rule 3A six-month timeline / *Bajaj Auto* day-to-day discipline in patent matters), and routine omissions that opposing counsel exploit.

A plugin that codifies the post-IPAB procedural skeletons + the IPD-Rules nomenclature + the Anton Piller / John Doe doctrine + the *American Cyanamid* / *Gujarat Bottling* three-limb test + the *Cadila Healthcare* triple-test + the Verifier-side discipline + the privacy firewall is the first piece of infrastructure that the Indian IP practice has had — the second piece is community contribution from advocates who practise regularly before the Delhi / Madras / Calcutta / Bombay HC IP Divisions and who deepen the bench-specific Practice Directions discipline.

Foreign legal-AI tools cannot fill this gap. The procedural conventions are jurisdiction-specific; the statutory framework is Indian Copyright Act 1957 / Trade Marks Act 1999 / Patents Act 1970 / Designs Act 2000 / Tribunals Reforms Act 2021 which no foreign training data has indexed at depth; the formatting requirements at the Registry counter of the Delhi HC IPD / Madras HC IPD / a District Court Commercial Division are matters of bench practice that no foreign tool has encountered.

This plugin opens that door. It is most-deeply-validated for the practice idiom of the author at the Bombay High Court Nagpur Bench, and shall be deepened with respect to other benches as community contributors raise GitHub issues and Pull Requests with their bench's specific Practice Directions.

---

## Roadmap

- [x] **v0.1.0-alpha (current)** — universal IP-pleading skeleton + 10 case-type skills + 6-agent pipeline + privacy firewall + Verifier disciplines + IPAB-abolition currency + Copyright firewall + 0 bench-specific exemplars
- [ ] **v0.1.x** — bug fixes, quality-gate iteration, language-register polish, formatting refinements driven by user feedback
- [ ] **v0.x onward** — bench-specific Practice Direction calibration deepening per Delhi HC IPD / Madras HC IPD / Calcutta HC / Bombay HC roster, additional case-type skills (geographical-indications litigation under the GI Act 1999 / Section 31 statutory licensing under the Copyright Act / compulsory-licensing under Section 84 Patents Act / Section 91 Patents Act parallel-litigation / suit for restoration of a lapsed patent under Section 60 Patents Act), and procedural-rule updates as they arrive
- [ ] **v1.0.0** — stable release after community-validated formatting and field-testing

Per-bench deep validation will arrive in the order advocates contribute. The plugin's case-config architecture means any advocate filing regularly before a given HC IPD / District Court Commercial Division can deepen the calibration for that bench by opening an issue or pull request with their bench's idiom — no central roadmap is needed to enable that. The roadmap above is therefore intentionally open-ended.

---

## Contributing

Advocates with regular IP-litigation practice are invited to contribute bench-config calibration for the specific division / court they practise before. Open a GitHub issue with:

- Your practice bench (e.g., *"Delhi HC IPD"* / *"Madras HC IPD"* / *"Bombay HC IP Roster"* / *"Tis Hazari District Court Commercial Division"*)
- Your bench's Cause Title format
- Your bench's case-number convention (CS (COMM) / CS (OS) / CS (IPD) / C.O. (Comm.IPD-TM) / C.O. (Comm.IPD-PAT) / Tr. P. / DOP)
- Your bench's filing-counter conventions (annexure markers / index format / verification format)
- Recent Practice Directions issued by the bench affecting pleading format

Pull requests are welcome with a one-paragraph explanation of the change and a reference to the bench rule or Practice Direction that justifies it.

This plugin is open source under MIT.

---

## Contact

Author and maintainer: **Rushikesh R. Mahajan**, Advocate, enrolled with the Bar Council of Maharashtra and Goa.

GitHub: <https://github.com/Wolfgangrush>

Issues raised with reproducible context are handled on a best-effort basis; this is an open-source contribution maintained outside the author's professional engagements and does not constitute a vehicle for legal services.

---

## Author and brand

The author is **Rushikesh R. Mahajan**, Advocate, practising before the Bombay High Court, Nagpur Bench. The plugin is published under the open-source brand **Wolfgang Rush**, which is the author's publishing handle for legal-technology infrastructure. Personal accountability under the Advocates Act 1961 attaches to the author regardless of the use of a publishing handle.

---

## Provenance and privilege statement

See `NOTICE.md` for the full provenance + privilege + privacy + Rule 36 compliance statement. The short version:

- The plugin contains only universal procedural skeletons, formatting conventions, statutory references, and generic placeholders
- The plugin contains no specific client matter, no client communications, no client documents, no personal data of any data principal, and no tracking / telemetry / analytics
- The plugin is, in legal character, identical to a published intellectual-property-law textbook — procedural knowledge in machine-readable form
- The author retains full enrolment, full responsibility, and full liability under the Advocates Act 1961 and the Bar Council of India Rules

---

## Compliance posture — Supreme Court e-Committee AI framework

This plugin is **assistive drafting infrastructure**, not autonomous decision-making software. Its operational posture is aligned with the Supreme Court of India e-Committee's stated position on AI in legal work.

> *"AI and digital tools must be used as supportive instruments and should not be allowed to override judicial reasoning."*
>
> — **Justice Rajesh Bindal**, Judge, Supreme Court of India
> [*Judicial Process Re-engineering and Digital Transformation*](https://www.sci.gov.in/press-release-dated-april-12-2026/) conference, 11–12 April 2026
> Organised by the Supreme Court e-Committee in collaboration with the Department of Justice, Government of India.
> ([Coverage — Law Trend](https://lawtrend.in/ai-must-not-replace-judicial-reasoning-warns-supreme-court-justice-rajesh-bindal/))

The same posture underpins the Supreme Court's own AI infrastructure for the judiciary:

- **[SUPACE](https://www.drishtiias.com/daily-news-analysis/ai-portal-supace)** — *Supreme Court Portal for Assistance in Court Efficiency.* AI-enabled assistive tool launched on 6 April 2021 by then-CJI S.A. Bobde. Provides legal research, fact extraction, document review, and drafting assistance to judges and legal researchers. **By design, SUPACE is not a decision-making system** — it processes facts and surfaces them to the human user. The Supreme Court has recommended adoption across all Indian High Courts.

- **[SUVAS](https://www.drishtijudiciary.com/current-affairs/supreme-court-vidhik-anuvaad-software-suvas)** — *Supreme Court Vidhik Anuvaad Software.* AI-powered translation tool launched in November 2019 by then-CJI S.A. Bobde. Translates judicial documents, orders, and judgments between English and ten Indian regional languages.

### What this plugin does — and does not — do under that framework

**Does:**

- Generate structural skeletons of pleadings, drawing on public statutes, schedule forms, and court rules.
- Run a six-agent assistive pipeline (Reader → Formatter → Drafter → Verifier → Refiner → Overseer) over the user's case facts.
- Surface citations, procedural anchors, and bench-specific conventions for advocate review.

**Does NOT:**

- Generate final filings autonomously.
- Substitute for advocate professional judgment.
- Replace human verification.
- Operate without an enrolled advocate retaining full professional responsibility.

**Every draft produced through this plugin must be advocate-owned and human-verified before filing.** The enrolled advocate using this plugin retains full professional responsibility under the Advocates Act 1961 and the Bar Council of India Rules, including verification of facts, accuracy of citations, correctness of legal grounds, propriety of the prayer, and signature on every pleading filed.

This is the same standard the Supreme Court itself applies to its own AI infrastructure (SUPACE / SUVAS): **AI as supportive instrument, never as decision-maker.**

---

## Disclaimer and Bar Council of India Rule 36 compliance

This repository is published as a personal open-source contribution to the legal-technology ecosystem. It is **not** an advertisement of professional services, **not** a solicitation of work, **not** an undertaking to act as counsel in any matter, and **not** a vehicle through which the author accepts professional engagement.

Bar Council of India Rule 36 of the Standards of Professional Conduct and Etiquette prohibits an advocate from soliciting work or advertising professional services through any medium. This repository complies with Rule 36 in both letter and spirit:

- No commercial offering is made through this repository
- No representation of professional results is made
- No invitation to engage the author professionally is made
- The README contains no contact details inviting professional retainer

The plugin is published in the same legal character as any practitioner's open-source library, public continuing-legal-education contribution, or published textbook chapter — the medium is software, the content is procedural knowledge, the practitioner retains full Bar discipline and accountability.

---

## License

MIT — see `LICENSE`.
