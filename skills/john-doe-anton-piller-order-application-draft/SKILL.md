---
name: john-doe-anton-piller-order-application-draft
description: Draft an application for a John Doe / Ashok Kumar order (relief against unknown infringers) and / or an Anton Piller order (ex-parte search-and-seizure against identified defendants where evidence is likely to be destroyed on notice), under Order 39 Rules 1 and 2 read with Order 26 Rules 9 and 10 of the Code of Civil Procedure 1908 and the inherent powers of the Court. Encodes the Anton Piller four-limb framework as adopted into Indian practice (Bucyrus Europe v. Vulcan Industries (2005) 30 PTC 280 (Cal)), the Taj Television v. Rajan Mandal (2003) 26 PTC 627 (Del) framework for John Doe orders against unknown infringers in cinematograph / broadcast contexts, the Local-Commissioner powers specification framework, the sealed-cover deposit protocol, and the over-breadth-risk Overseer flags. Auto-fires on "draft John Doe order", "draft Ashok Kumar order", "draft Anton Piller", "draft ex-parte search and seizure" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# John Doe / Anton Piller / Ashok Kumar Order Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION FOR EX-PARTE AD-INTERIM INJUNCTION AND APPOINTMENT OF LOCAL COMMISSIONER WITH POWERS OF ENTRY, INSPECTION, AND SEIZURE (JOHN DOE / ASHOK KUMAR / ANTON PILLER ORDER) UNDER ORDER 39 RULES 1 AND 2 READ WITH ORDER 26 RULES 9 AND 10 OF THE CODE OF CIVIL PROCEDURE 1908 AND THE INHERENT POWERS OF THIS HON'BLE COURT
case_short_code: JOHN_DOE_ANTON_PILLER
case_number_prefix: (interlocutory application — case number adopted from the parent suit)
pleading_type: Interlocutory Application
typical_forum: same court as the parent IP suit (High Court Commercial Division / High Court IP Division / District Court Commercial Division)
typical_parties: Plaintiff in the parent suit (Applicant in this IA) + Named Defendant(s) (where Anton Piller against identified defendants) + Unknown Defendants (where John Doe / Ashok Kumar against unidentified infringers — typically in cinematograph piracy / broadcast theft / counterfeit-ring contexts)
statutory_opening: "This application is filed under Order 39 Rules 1 and 2 read with Order 26 Rules 9 and 10 of the Code of Civil Procedure 1908 and the inherent powers of this Hon'ble Court, for ex-parte ad-interim injunction restraining the named and / or unknown Defendants from the infringing acts pending the suit, and for appointment of a Local Commissioner with powers of entry, inspection, and seizure at the premises identified herein, in aid of the Plaintiff's prayer for permanent injunction in the parent suit."
ground_clauses:
  - "Parent suit pending — the present application is filed in the parent suit being CS (COMM) / CS (OS) No. ___ of ___ pending before this Hon'ble Court for permanent injunction, damages, and delivery-up in respect of [copyright / trade mark / patent / design / passing-off — specify]."
  - "John Doe / Ashok Kumar framework (where unknown defendants are involved) — per *Taj Television Ltd. v. Rajan Mandal* (2003) 26 PTC 627 (Del), this Hon'ble Court has jurisdiction to grant ex-parte ad-interim injunctive relief and to appoint a Local Commissioner with seizure powers, against a defined class of unknown infringers in cases of [cinematograph piracy / broadcast signal theft / counterfeit-goods rings] where the class is identifiable by type even if the individual infringers are not yet identified. Liberty is sought to add unidentified defendants upon their identification."
  - "Anton Piller framework (where identified defendants are involved with risk of evidence destruction) — per *Bucyrus Europe Ltd. v. Vulcan Industries* (2005) 30 PTC 280 (Cal) the Anton Piller four-limb test is satisfied:"
  - "    (i) Extremely strong prima facie case — particulars at paragraphs ___ to ___ and Exhibits ___ to ___ ;"
  - "    (ii) Potential or actual damage of a very serious nature — particulars of irreversible market harm / customer confusion / loss of patent monopoly period / mass-market dissemination ;"
  - "    (iii) Clear evidence that the named defendants possess incriminating material — particulars of (a) sample-purchases / market-surveys, (b) defendants' premises identified at [A], [B], [C], (c) inventory / packaging / digital masters likely held at those premises ;"
  - "    (iv) Real possibility that the defendants will destroy or remove the incriminating material if forewarned by notice — particulars of (a) defendants' historic conduct, (b) ease of digital evidence destruction, (c) urgency of the market situation."
  - "Order 39 Rule 3 first proviso (mandatory affidavit) — notice would defeat the very object of the order sought. The grounds are: [specify — risk of removal / destruction of evidence / dissemination of pirated content beyond recall / counterfeit stock dispersal]. Affidavit at Exhibit ___ records these grounds."
  - "Local-Commissioner powers (Order 26 Rules 9 and 10) — the Local Commissioner appointed is sought to be conferred specific powers: (a) entry at premises [A], [B], [C] identified at Exhibit ___ ; (b) inspection of all material in the premises pertaining to the infringing acts; (c) seizure under sealed cover of all infringing articles, packaging, dies, blocks, moulds, books of account, invoices, digital storage devices, and any other material relevant to the infringing acts; (d) inventory of all material seized, with copy to the defendants on the spot; (e) deposit of all seized material in sealed cover with the Registry of this Hon'ble Court pending inter-partes hearing; (f) protection of defendants' privileged material / personal data through sealed-cover procedure."
  - "Cross-undertaking on damages — the Plaintiff offers an unconditional cross-undertaking to pay such damages as this Hon'ble Court may award to the Defendants if the application is ultimately found to have been wrongly granted (the *Bajaj Auto Ltd. v. TVS Motor Company* (2009) 9 SCC 797 discipline applied by analogy)."
  - "Section 12A Commercial Courts Act 2015 exemption — urgent interim relief is contemplated in the parent suit and is the subject of this very application."
prayer_clauses:
  - "(a) Pass an ex-parte ad-interim order of injunction restraining the named Defendants [where applicable] and / or unknown defendants from doing the infringing acts identified in the parent suit, pending disposal of this application and the suit;"
  - "(b) Appoint a Local Commissioner under Order 26 Rules 9 and 10 of the Code of Civil Procedure 1908 to enter the premises identified at [A], [B], [C] (Exhibit ___) with powers of inspection and seizure as more particularly set out in paragraph ___ above;"
  - "(c) Direct that all material seized by the Local Commissioner shall be deposited in sealed cover with the Registry of this Hon'ble Court pending inter-partes hearing of this application;"
  - "(d) Direct the Local Commissioner to file a report of the inspection and seizure within ____ days of completion of the same;"
  - "(e) Direct the police authorities of the relevant area to provide police protection to the Local Commissioner during the execution of the inspection and seizure;"
  - "(f) Grant liberty to the Plaintiff to add unidentified defendants upon their identification (where John Doe / Ashok Kumar relief is sought);"
  - "(g) Pass such further and other orders as this Hon'ble Court may deem fit and proper, including costs."
mandatory_exhibits:
  - parent_suit_papers_or_reference_to_pending_CS_COMM_number
  - affidavit_in_support_with_Order_39_Rule_3_first_proviso_pleading_on_why_notice_would_defeat_purpose
  - particulars_of_the_premises_to_be_inspected_with_address_and_specifications
  - sample_purchase_records_or_market_survey_evidence_demonstrating_the_defendants_possession_of_infringing_stock
  - evidence_of_the_defendants_historic_conduct_relevant_to_evidence_destruction_risk_where_anton_piller
  - for_john_doe_cases_evidence_of_the_class_of_unknown_infringers_and_their_modus_operandi
  - cross_undertaking_on_damages_affidavit
  - draft_local_commissioner_warrant_with_powers_and_protocols_specified
accompanying_applications:
  - "I.A. for police protection during execution of the Local Commissioner's warrant"
  - "I.A. for extension of the timeline for filing the Local Commissioner's report (where the scope of seizure warrants)"
  - "I.A. for production of the seized material at the hearing of the parent application"
court_fee: "Standard interlocutory-application fee as per the High Court Original Side Rules / District Court Court-Fees Rules"
```

## Anton Piller four-limb test — mandatory pleading

Per *Bucyrus Europe v. Vulcan Industries* (2005) 30 PTC 280 (Cal), the Anton Piller framework requires the Applicant to satisfy each of the four limbs with **factual particulars**:

(i) **Extremely strong prima facie case** — stronger than the *American Cyanamid* prima facie case standard required for an ordinary interim injunction
(ii) **Potential or actual damage of a very serious nature** — not ordinary commercial damage; damage that is irreversible / mass-market / dissemination-of-infringing-content-beyond-recall
(iii) **Clear evidence that the defendants possess incriminating material** — based on sample-purchases, market-surveys, intelligence; bare suspicion is insufficient
(iv) **Real possibility of destruction of material if forewarned by notice** — based on defendants' historic conduct, ease of evidence destruction, market dynamics

The Overseer flags applications that lack particulars on any limb. An over-broad Anton Piller order is liable to be vacated and exposes the Applicant to the cross-undertaking on damages.

## John Doe / Ashok Kumar framework — class identification mandatory

Per *Taj Television v. Rajan Mandal* (2003) 26 PTC 627 (Del), John Doe orders are permissible only where the class of unknown infringers is identifiable by **type** (cinematograph piracy / broadcast signal theft / counterfeit ring / software piracy). Unbounded relief against the world is impermissible.

The Drafter defines the class with precision:

- The **type** of infringing activity (e.g. unauthorised exhibition of a specific cinematograph film)
- The **geographic territory** of the relief sought
- The **time-window** of the operation (e.g. for first 28 days post-theatrical release)
- The **mechanism** for identification of unknown defendants (e.g. identification by the Local Commissioner during execution)

## Local-Commissioner powers — particularity mandatory

Order 26 Rules 9 and 10 CPC require the powers conferred on the Local Commissioner to be specified with **particularity**:

- **Premises** — specific address(es), with floor / room identification where applicable
- **Scope of search** — what material may be inspected / seized
- **Sealed-cover protocol** — how the seized material is handled and deposited with the Registry
- **Inventory protocol** — on-the-spot inventory with copy to defendants
- **Privileged material protocol** — how the Local Commissioner handles documents protected by advocate-client privilege (Section 132 BSA 2023) / personal data (DPDPA 2023)

## Cross-undertaking on damages

The *Bajaj Auto v. TVS Motor* (2009) 9 SCC 797 discipline on cross-undertaking applies to Anton Piller by analogy. The Plaintiff's unconditional cross-undertaking is a *quid pro quo* for the ex-parte seizure relief. Missing cross-undertaking is a fatal weakness.

## Cross-references

For the parent infringement suit (copyright / trade mark / patent / design / passing-off), see the corresponding case-type skill. For the general interim-injunction application (without the Anton Piller seizure dimension), see `interim-injunction-application-ip-draft`.
