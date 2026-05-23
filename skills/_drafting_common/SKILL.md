---
name: _drafting_common
description: Shared reference for all 10 intellectual-property litigation drafting skills. Holds the anti-pollution rules, the IP privacy firewall protocol (plaintiff / defendant names, copyright-work titles, trade marks, patent numbers, design registration numbers, infringing-product descriptions, damages-quantum figures substituted with placeholders before downstream AI processing; real-value re-substitution local-only in the Refiner step), the AI-style-marker blacklist, citation discipline, statutory currency rules (Copyright Act 1957 / Trade Marks Act 1999 / Patents Act 1970 (as amended) / Designs Act 2000 / Tribunals Reforms Act 2021 / Commercial Courts Act 2015 / CPC Order 39 / BNSS 2023 / BSA 2023), the IPAB-abolition currency rule (every IPAB reference re-routed to HC IP Division), the Copyright firewall (Moral Rights / Reversionary Interests statutory-only rewrite under Section 19 Copyright Act 1957), the Section 12A Commercial Courts Act mandatory pre-institution mediation / urgent-interim-relief exemption rule, the Section 62 Copyright Act / Section 134 Trade Marks Act / Section 104 Patents Act / Section 22 Designs Act jurisdictional rules, the Limitation Act 1963 Article map for IP actions, and the American Cyanamid / Gujarat Bottling three-limb interim-injunction framework. NOT invoked directly — referenced from every case-type skill in this plugin.
allowed-tools: Read
---

# `_drafting_common` — shared IP drafting infrastructure

## Privacy firewall

Intellectual-property pleadings routinely contain highly sensitive material — registered trade marks (the proprietor's brand identity), copyright work titles (often unpublished commercial works), patent numbers and the proprietary technology described in the claims, design registration numbers, infringing-product descriptions, damages computations (with the plaintiff's revenue / profit data), market-survey reports, cease-and-desist correspondence. The plugin's privacy discipline:

1. **Reader** substitutes every plaintiff name, every defendant name, every copyright-work title, every trade mark, every patent number, every design registration number, every infringing-product description, and every damages-quantum figure with structural placeholders before downstream processing.
2. The placeholder → real-value mapping is stored in the header of `case-facts.md` on the user's local machine **only**.
3. **Format / Drafter / Verifier / Overseer** operate **only** on placeholder-substituted content. The underlying AI runtime never holds raw trade marks, raw patent numbers, raw design numbers, or raw damages figures.
4. **Refiner** re-substitutes real values into the final `.docx`, strictly on the user's machine.
5. `.gitignore` excludes `case-facts.md` and `case-config.md` so they cannot be committed accidentally.

## AI-style-marker blacklist

Stripped by the Refiner before output:

- Em-dash (`—`) used as sentence-internal pause (replaced with semicolon or comma-bounded clause)
- Sentence-final *thereby* / *hereby* / *whereby* without an attached verb
- *Moreover*, *furthermore*, *additionally*, *in addition* as sentence-openers — replaced with *"The Plaintiff submits that"* / *"The Plaintiff further submits that"*
- *Navigate*, *delve*, *foster*, *robust*, *seamless* (metaphorical uses)
- *It is important to note that*, *it should be noted that*, *worthy of note* — replaced with direct prose
- Bullet-list-style structure in operative paragraphs (operative paragraphs are numbered, not bulleted)

## Citation discipline

The Drafter does **not** generate case names + citations from training memory. Every case citation in any explanatory note or recital must trace to a user-supplied source. Untraceable citations become `[CITATION NEEDED]` placeholders.

Headline cases the Verifier scans for fabrication:

- *Mardia Chemicals Ltd. v. Union of India* (2004) 4 SCC 311 — cited in IP pleadings for the constitutional-validity framework applicable to special tribunals (analogically applied post-IPAB-abolition)
- *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 — passing-off triple-test
- *N.R. Dongre v. Whirlpool* (1996) 5 SCC 714 — transborder reputation
- *Toyota Jidosha Kabushiki Kaisha v. Prius Auto Industries* (2018) 2 SCC 1 — territorial extent of goodwill
- *Milmet Oftho v. Allergan Inc.* (2004) 12 SCC 624 — transborder reputation in pharmaceutical mark
- *IPRS v. Sanjay Dalia* (2015) 10 SCC 161 — Section 134 TMA / Section 62 CA principal-place-of-business qualification
- *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 — Section 12A Commercial Courts Act mandatory pre-institution mediation (unless urgent interim relief contemplated)
- *Eastern Book Company v. D.B. Modak* (2008) 1 SCC 1 — *modicum-of-creativity* test for copyright originality
- *R.G. Anand v. Delux Films* (1978) 4 SCC 118 — idea-expression dichotomy
- *Civic Chandran v. Ammini Amma* (1996) 16 PTC 670 (Ker) — Section 52 fair dealing
- *MySpace Inc. v. Super Cassettes Industries* (2016) 236 DLT 478 — intermediary liability under Section 52(1)(zb) / IT Act
- *Novartis AG v. Union of India* (2013) 6 SCC 1 — Section 3(d) Patents Act enhanced-efficacy test
- *Bayer Corporation v. Union of India* (2014) Bom HC — Section 84 compulsory licence
- *Aloys Wobben v. Yogesh Mehra* (2014) 15 SCC 360 — patent revocation forum choice (Section 64 application vs counter-claim)
- *F. Hoffmann-La Roche v. Cipla* (2015) 65 PTC 187 (DB Del) — credible-challenge-to-validity at interim-injunction stage
- *Merck Sharp & Dohme v. Glenmark* (2015) 64 PTC 417 (DB Del) — patent interim injunction discipline
- *Bajaj Auto Ltd. v. TVS Motor Company* (2009) 9 SCC 797 — day-to-day hearing of IP suits + cross-undertaking discipline
- *Bharat Glass Tube v. Gopal Glass Works* (2008) 10 SCC 657 — novelty / originality in design
- *Carlsberg Breweries v. Som Distilleries* (2018) 76 PTC 1 (DB Del) — composite suit for design piracy + passing-off
- *Bucyrus Europe Ltd. v. Vulcan Industries* (2005) 30 PTC 280 (Cal) — Anton Piller framework in India
- *Taj Television Ltd. v. Rajan Mandal* (2003) 26 PTC 627 (Del) — John Doe / Ashok Kumar order framework
- *American Cyanamid Co. v. Ethicon Ltd.* [1975] AC 396 (HL) — three-limb interim-injunction test
- *Gujarat Bottling Co. Ltd. v. Coca-Cola Co.* (1995) 5 SCC 545 — three-limb test as applied in India
- *Wander Ltd. v. Antox India Pvt. Ltd.* 1990 Supp SCC 727 — appellate deference to trial-court discretion
- *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225 — Order 39 Rule 3 ex-parte discipline
- *Patel Field Marshal Agencies v. P.M. Diesels* (2018) 2 SCC 112 — Section 124 TMA stay pending rectification
- *Yahoo! Inc. v. Akash Arora* (1999) PTC 19 (Del) — passing-off in domain-name disputes

## Statutory currency rules

Every pleading filed today should cite the operative statute. Common substitution checks:

- **Section 200 CrPC 1973 → Section 223 BNSS 2023** in any ancillary criminal-copyright complaint reference (Sections 63 to 70 Copyright Act criminal offences).
- **Section 482 CrPC 1973 → Section 528 BNSS 2023** for inherent-power petitions.
- **Section 65B Indian Evidence Act 1872 → Section 63 Bharatiya Sakshya Adhiniyam 2023** for admissibility of electronic records (relevant in trade-mark domain disputes, software-copyright suits, broadcast-piracy John Doe orders).
- **Section 126 IEA 1872 → Section 132 BSA 2023** for advocate-client privilege.
- **Companies Act 1956 → Companies Act 2013** for any corporate-defendant pleading.

Dual-citation is acceptable in any transitional pleading.

## IPAB-abolition currency rule

Until 2021, the Intellectual Property Appellate Board (IPAB) was the appellate / rectification / revocation forum for:

- Appeals from orders of the Registrar of Trade Marks (Section 91 TMA)
- Rectification of the Register of Trade Marks (Section 57 TMA)
- Appeals from orders of the Controller of Patents (Section 117A PA)
- Revocation of patents (Section 64 PA)
- Appeals from orders of the Registrar of Copyrights (Section 72 CA)
- Appeals from orders of the Registrar of Geographical Indications (Section 31 GI Act)

**The IPAB stands abolished by the Tribunals Reforms Act 2021** (Act 33 of 2021, received Presidential assent 13 August 2021). Sections 12 to 14 of the Tribunals Reforms Act 2021 transfer the IPAB's jurisdiction to the **High Court of competent jurisdiction**, exercised through the **Intellectual Property Rights Division** of that High Court where one has been constituted.

Constituted IP Divisions as at the date of this release:

- **Delhi High Court IP Division** — Delhi HC IPR Division Rules 2022
- **Madras High Court IP Division** — Madras HC IPR Division Rules
- **Calcutta High Court** — IP roster in operation
- **Bombay High Court** — IP roster in operation

Every reference to the IPAB as a *live forum* in any new pleading is flagged and re-routed to the HC IP Division. Past IPAB decisions remain valid as **precedent** and may be cited.

## Copyright firewall (Moral Rights / Reversionary Interests)

The clauses in the corpus on *Moral Rights* and *Reversionary Interests* deviated from the statutory text and require **statutory-only rewrite** before encoding. Specifically:

- **Moral Rights** — encoded by reference to **Section 57 of the Copyright Act 1957** only:
  - Right of paternity (right to claim authorship)
  - Right of integrity (right to restrain or claim damages for any distortion, mutilation, modification, or other act in relation to the work which would be prejudicial to the author's honour or reputation)
  - These rights are independent of the author's copyright and remain with the author even after assignment, whether wholly or partially, of the copyright
- **Reversionary Interests** — encoded by reference to the **proviso to Section 18(1) of the Copyright Act 1957** only:
  - Assignment of the copyright in a future work takes effect only when the work comes into existence
  - The right reverts to the author if the assignee does not exercise the rights assigned within a period of one year from the date of assignment, unless the assignment otherwise provides

No proprietary clause-prose from any commentary, precedent collection, or template volume is imported. Where the user's case-facts reference these concepts, the Drafter recites the statutory text only.

## Section 12A Commercial Courts Act 2015 — pre-institution mediation

Section 12A of the Commercial Courts Act 2015 requires every commercial suit not contemplating urgent interim relief to undergo pre-institution mediation under the Commercial Courts (Pre-Institution Mediation and Settlement) Rules 2018. The *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework confirms:

- Pre-institution mediation is **mandatory** (not directory)
- Non-compliance is fatal to the suit
- The "urgent interim relief" exemption applies only where such relief is **contemplated in the body of the plaint** and **prayed for explicitly**

IP suits typically contemplate urgent interim relief and are accordingly exempt — but the plaint must plead the urgent-interim-relief case **expressly**. The Verifier flags any IP plaint that fails to plead urgent interim relief expressly AND fails to plead Section 12A compliance.

## Jurisdictional anchor rules

| Case-type | Operative section | Anchor |
|---|---|---|
| Copyright infringement suit | Section 62 Copyright Act 1957 | Plaintiff resides / carries on business / works for gain (displaces Section 20 CPC) |
| Trade mark infringement suit | Section 134 Trade Marks Act 1999 | Plaintiff resides / carries on business / works for gain (displaces Section 20 CPC); *IPRS v. Sanjay Dalia* principal-place-of-business qualification |
| Patent infringement suit | Section 104 Patents Act 1970 | District Court of competent pecuniary jurisdiction; first proviso transfers to High Court on counter-claim for revocation |
| Design piracy suit | Section 22(4) Designs Act 2000 | Court of District Judge or above; transfer to High Court on counter-claim for cancellation under Section 19 |
| Passing-off (pure, no registration) | Section 20 CPC 1908 | Defendant residence / business / cause-of-action (Section 134 TMA does NOT extend to pure passing-off) |
| Rectification of Register of Trade Marks | Section 57 Trade Marks Act 1999 read with Tribunals Reforms Act 2021 | High Court Intellectual Property Rights Division |
| Revocation of patent | Section 64 Patents Act 1970 read with Tribunals Reforms Act 2021 | High Court Intellectual Property Rights Division |

## American Cyanamid / Gujarat Bottling three-limb interim-injunction test

Every interim-injunction application in an IP suit must plead, with particulars, the three limbs:

1. **Prima facie case** — particulars of (a) the right (registration certificate / first-use evidence / copyright subsistence) and (b) the infringement (act, date, channel, scale)
2. **Balance of convenience** — particulars of (a) the plaintiff's investment / market reputation / continuous use / market harm vs (b) the defendant's recent / limited / contested use
3. **Irreparable injury** — particulars of why damages would be an inadequate remedy (market dilution / loss of distinctive reputation / customer confusion / patent monopoly period erosion)

Cross-undertaking on damages (the *Bajaj Auto v. TVS Motor* (2009) 9 SCC 797 discipline) is the *quid pro quo* in patent matters and is increasingly applied across IP matters by analogy.

The *Wander v. Antox* 1990 Supp SCC 727 framework on appellate deference is noted in the Overseer's checklist — the Plaintiff's pleading anticipates the Defendant's appellate strategy.

## Limitation Act 1963 — Article map

| Case-type | Article | Period |
|---|---|---|
| Trade mark infringement / passing-off | Article 75 | 3 years from each continuing infringement / from date of knowledge |
| Copyright infringement | Article 113 (residual) | 3 years from date of infringement (each continuing act is a fresh cause) |
| Patent infringement | Article 113 (residual) | 3 years from date of infringement (each continuing act is a fresh cause) |
| Design piracy | Article 113 (residual) | 3 years from date of infringement (each continuing act is a fresh cause) |
| Rectification of trade mark under Section 57 TMA | no fixed limitation | continuing obligation of the Register; standing as aggrieved person |
| Revocation of patent under Section 64 PA | no fixed limitation | continuing obligation; standing as person interested |
| Suit for damages on a final injunction order | Article 113 | 3 years from date of decree |
| Appeal from interlocutory order | special — 30 days from date of order (Limitation Act read with CPC and HC Rules of the High Court concerned) | 30 days |

The Drafter pleads the limitation paragraph for every case-type using the applicable Article + date-of-accrual + date-of-filing + days-within-limitation.

## Order 39 Rule 3 / Rule 3A discipline

- **Order 39 Rule 3 first proviso CPC** — every ex-parte ad-interim order requires the court to record reasons in writing for not directing notice; the application's supporting affidavit must affirmatively plead the case for dispensing with notice (the *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225 discipline).
- **Order 39 Rule 3A CPC** — where ex-parte order is granted, the court shall make an endeavour to finally dispose of the application within 30 days. Each delay must be recorded in writing.

The Verifier flags any ex-parte application missing the why-notice-would-defeat-the-purpose affidavit averment.


---

## v0.2.1 RENDER DISCIPLINE (load-bearing — Drafter must follow)

**Pandoc + reference.docx + post-pandoc fix script.** The Drafter writes Markdown using the heading discipline below. Pandoc converts the Markdown to `.docx` using the SHIPPED reference.docx at `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/reference.docx` — pre-customised with locked Word styles matching the filing-grade Bombay HC Nagpur convention (extracted from an actual filed Second Appeal pleading):

- **Body (Normal)** — TNR 14pt, 1.5 line spacing, justified, 0.5cm first-line indent
- **Heading 1** — TNR 14pt **bold + centered** (NOT underlined) — for the Court / Forum / Tribunal header line and the case-number line
- **Heading 2** — TNR 14pt **bold + UNDERLINED + centered + letter-spacing** — for spaced section headers (`F A C T S`, `G R O U N D S`, `P R A Y E R`, `I N D E X`, `S Y N O P S I S`, `L I S T   O F   A N N E X U R E S`, `V E R I F I C A T I O N`)
- **Heading 3** — TNR 14pt **bold + UNDERLINED + centered** — for unspaced section headers (`SUBSTANTIAL QUESTIONS OF LAW`, `ACTS & RULES`, `CITATIONS`) and statutory opening (`WRIT PETITION UNDER ARTICLE 226 …`)
- **Heading 4** — TNR 14pt **bold + UNDERLINED + left-aligned** — for left-anchored bold-underlined headings (`MOST RESPECTFULLY SHEWETH:`)
- **Tables** — `tblLayout = fixed`; first row bold centered; cell margins locked

### Markdown heading mapping

| Markdown | Rendered as | Used for |
|---|---|---|
| `# Heading 1` | Bold centered (no underline) | Court header line; case-number line; cover-page anchors |
| `## Heading 2` | Bold centered UNDERLINED with letter-spacing | Spaced section headers (`## F A C T S`, `## G R O U N D S`, `## P R A Y E R`, `## I N D E X`, `## S Y N O P S I S`, `## L I S T   O F   A N N E X U R E S`, `## V E R I F I C A T I O N`) |
| `### Heading 3` | Bold centered UNDERLINED | Unspaced section headers + statutory opening |
| `#### Heading 4` | Bold left UNDERLINED | `#### MOST RESPECTFULLY SHEWETH:` |
| Body paragraph | TNR 14pt justified 1.5 spacing 0.5cm first-line indent | Everything else |
| `**Bold inline**` | Bold | Property descriptors / annexure markers / key terms inline within Facts narrative |

### Bold-number paragraph convention

Facts and Grounds paragraphs use **BOLD NUMBERS**: `**1.**`, `**2.**`, `**3.**` followed by a tab + body. Renders as the gold-standard pleading layout.

### Two-step pandoc command (Step 2 is NON-NEGOTIABLE)

```bash
# Step 1 — pandoc → .docx with locked Word styles
pandoc draft-v1.md -o draft-v1.docx \
  --reference-doc="${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/reference.docx" \
  --from=markdown+pipe_tables+raw_tex

# Step 2 — force table column widths
python3 "${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/fix_docx_tables.py" draft-v1.docx
```

Step 2 forces column widths on every table — 5-col (Sr.No / Annx / Particulars / Date / Pgs) = 8/8/60/14/10; 4-col = 10/10/65/15; 3-col = 10/75/15; 2-col Dates–Events = 18/82. Locks first-row bold + centered + vertically-centered cells. **Skipping the fix script reproduces the v0.2.0 Index-table defect (Sr.No / Annx columns stacking vertically).**

Do NOT auto-generate a fresh reference.docx in the case folder. Use the shipped one or a `<case-folder>/reference.docx` override.

### Cover-page discipline

INDEX, SYNOPSIS, LIST OF ANNEXURES each begin on a new page (`\newpage` in Markdown) and carry ONLY: forum header (`#`) + case-number line (`#`) + short cause-title (Petitioner short name `///VERSUS///` Respondent short name) + section header (`##`) + table + Counsel block. DO NOT repeat the full party address block on cover pages.

### Pipeline-optionality (advocate-cost discipline)

The full 6-agent pipeline (Reader → Format → Drafter → Verifier → Refiner → Overseer) is **NOT** mandatory. Only the first three stages are required to produce a filing-grade draft. Stages 4–6 are OPTIONAL QC layers the advocate explicitly invokes. Default exit point is here, after Drafter (~280K tokens). Full pipeline ~600K tokens — disproportionate for routine pleadings.

When `draft-v1.docx` is written, the Drafter's job is complete. The advocate decides whether to invoke the QC stages.
