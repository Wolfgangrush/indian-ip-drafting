---
name: interim-injunction-application-ip-draft
description: Draft an application for an interim injunction in an Indian IP suit under Order 39 Rules 1 and 2 of the Code of Civil Procedure 1908. Encodes the American Cyanamid v. Ethicon (1975) AC 396 / Gujarat Bottling v. Coca-Cola (1995) 5 SCC 545 three-limb framework (prima facie case + balance of convenience + irreparable injury), the Wander v. Antox (1990) Supp SCC 727 appellate-deference framework, the Bajaj Auto v. TVS Motor (2009) 9 SCC 797 day-to-day hearing discipline, the F. Hoffmann-La Roche v. Cipla (2015) 65 PTC 187 (DB Del) and Merck Sharp & Dohme v. Glenmark (2015) 64 PTC 417 (DB Del) credible-challenge-to-validity framework (patent matters), the Order 39 Rule 3 first proviso framework on ex-parte ad-interim relief (the Morgan Stanley Mutual Fund v. Kartick Das (1994) 4 SCC 225 discipline), and the Order 39 Rule 3A six-month adjudication discipline. Auto-fires on "draft interim injunction", "draft Order 39 Rule 1 application", "draft ex-parte ad-interim relief", "draft IA for injunction in IP suit" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Interim Injunction Application Draft Skill (IP)

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: APPLICATION FOR INTERIM INJUNCTION RESTRAINING THE DEFENDANTS FROM THE INFRINGING ACTS PENDING DISPOSAL OF THE SUIT, UNDER ORDER 39 RULES 1 AND 2 READ WITH SECTION 151 OF THE CODE OF CIVIL PROCEDURE 1908
case_short_code: INTERIM_INJUNCTION_IP
case_number_prefix: (interlocutory application — case number adopted from the parent suit)
pleading_type: Interlocutory Application
typical_forum: same court as the parent IP suit (High Court Commercial Division / High Court IP Division / District Court Commercial Division)
typical_parties: Plaintiff in the parent suit (Applicant in this IA) + Defendant(s)
statutory_opening: "This application is filed under Order 39 Rules 1 and 2 read with Section 151 of the Code of Civil Procedure 1908, for grant of an interim injunction restraining the Defendants from the infringing acts identified in the parent suit, pending disposal of the suit. The application invokes the three-limb framework of *American Cyanamid Co. v. Ethicon Ltd.* [1975] AC 396 as adopted in India by *Gujarat Bottling Co. Ltd. v. Coca-Cola Co.* (1995) 5 SCC 545."
ground_clauses:
  - "Parent suit pending — the present application is filed in the parent suit being CS (COMM) / CS (OS) No. ___ of ___ pending before this Hon'ble Court for permanent injunction, damages, and delivery-up in respect of [copyright / trade mark / patent / design / passing-off — specify]."
  - "First limb — prima facie case — the Plaintiff's right is established prima facie:"
  - "    (i) The Plaintiff holds [registered trade mark / granted patent / registered design / copyright in the [Copyright Work] (Exhibit ___ in the parent suit);"
  - "    (ii) The registration is valid and subsisting (renewal / annuity records at Exhibit ___);"
  - "    (iii) The Defendants' acts amount to infringement / piracy / passing-off as more particularly set out in paragraph ___ of the plaint and the comparison chart at Exhibit ___."
  - "Second limb — balance of convenience — the balance lies in favour of the Plaintiff:"
  - "    (i) The Plaintiff has invested Rs. ___ over [years] in building goodwill / market presence / R&D for the right in suit (Exhibit ___);"
  - "    (ii) The Defendants' use is recent / limited / contested in scope, as evidenced by [particulars];"
  - "    (iii) Refusal of interim relief would cause irreversible market dilution / loss of customer association / erosion of the patent monopoly period;"
  - "    (iv) Grant of interim relief would not impose disproportionate hardship on the Defendants who could conduct lawful business under their own non-infringing mark / product / design."
  - "Third limb — irreparable injury — damages would be an inadequate remedy:"
  - "    (i) Market dilution and loss of distinctive reputation are not capable of accurate monetary quantification;"
  - "    (ii) Customer confusion erodes the Plaintiff's goodwill in ways that no post-decree damages can restore;"
  - "    (iii) For patent matters — the patent monopoly period (20 years from priority date — Section 53 Patents Act 1970) is finite and erosion during the suit's pendency is irrecoverable;"
  - "    (iv) For perishable / fast-moving consumer goods / pharmaceutical products — the harm to consumer safety is irreparable."
  - "Wander v. Antox (1990) Supp SCC 727 deference — this Hon'ble Court's discretion in granting interim relief is to be exercised on the three-limb framework; appellate courts will defer to the trial-court's exercise unless arbitrary, capricious, or perverse."
  - "(For patent matters) Credible-challenge-to-validity readiness — per *F. Hoffmann-La Roche v. Cipla* (2015) 65 PTC 187 (DB Del) and *Merck Sharp & Dohme v. Glenmark* (2015) 64 PTC 417 (DB Del), the Defendants may raise a credible challenge to the validity of the Suit Patent at the interim stage. The Plaintiff pre-empts: no anticipating prior art has been disclosed; no Section 3 ground is sustainable; the prosecution history (Exhibit ___) demonstrates the patent's defensible validity."
  - "(Where ex-parte ad-interim relief is sought) Order 39 Rule 3 first proviso CPC — the Plaintiff submits that the object of granting the injunction would be defeated by delay, and that this Hon'ble Court may be pleased to grant ex-parte ad-interim relief. The grounds for dispensing with notice are: [specify — risk of evidence destruction / risk of mass-market dissemination / risk of counterfeit stock dispersal / urgency of the market situation]. Affidavit at Exhibit ___ records these grounds per the *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225 discipline."
  - "Order 39 Rule 3A CPC — the Plaintiff invites this Hon'ble Court to dispose of this application within 30 days of its grant ex-parte, in compliance with the statutory time-frame."
  - "(For patent matters) Bajaj Auto v. TVS Motor day-to-day hearing — the Plaintiff invokes the discipline laid down in *Bajaj Auto Ltd. v. TVS Motor Company Ltd.* (2009) 9 SCC 797 that intellectual-property suits, particularly patent suits, ought to be heard from day-to-day to ensure speedy disposal. The Plaintiff offers an unconditional cross-undertaking to pay such damages as this Hon'ble Court may award to the Defendants if the interim relief is ultimately found to have been wrongly granted."
prayer_clauses:
  - "(a) Pass an order of interim injunction restraining the Defendants, by themselves, their servants, agents, distributors, retailers, online intermediaries, and all persons claiming through them, from the infringing acts identified in the parent suit, pending disposal of the suit;"
  - "(b) Pending hearing of this application, grant an ex-parte ad-interim order of injunction on the same terms, in the interests of justice and per Order 39 Rule 3 first proviso of the Code of Civil Procedure 1908;"
  - "(c) (For patent matters) Direct day-to-day hearing of the suit per *Bajaj Auto Ltd. v. TVS Motor Company* (2009) 9 SCC 797;"
  - "(d) Accept the Plaintiff's unconditional cross-undertaking on damages, as evidenced by the affidavit at Exhibit ___ ;"
  - "(e) Pass such further and other orders as this Hon'ble Court may deem fit and proper, including costs."
mandatory_exhibits:
  - parent_suit_papers_or_reference_to_pending_CS_COMM_number
  - affidavit_in_support_with_Order_39_Rule_3_first_proviso_pleading_where_ex_parte_relief_is_sought
  - cross_undertaking_on_damages_affidavit
  - sales_figures_advertising_spend_market_share_data_for_balance_of_convenience
  - infringement_evidence_for_prima_facie_case
  - comparison_chart_for_prima_facie_case_of_substantial_similarity_or_deceptive_similarity_or_claim_by_claim_infringement
  - for_patent_matters_prior_art_search_report_and_prosecution_history_pre_empting_credible_challenge
  - for_pharmaceutical_or_fast_moving_consumer_goods_evidence_of_consumer_safety_harm_for_irreparable_injury
accompanying_applications:
  - "I.A. for early hearing of this application"
  - "I.A. for day-to-day hearing of the suit (in patent and high-value IP matters per *Bajaj Auto v. TVS Motor*)"
  - "I.A. for short notice on the Defendants pending ex-parte ad-interim disposal"
  - "I.A. for production of the Defendants' books of account at the interim stage (rendition-of-accounts inquiry)"
court_fee: "Standard interlocutory-application fee as per the High Court Original Side Rules / District Court Court-Fees Rules"
```

## American Cyanamid / Gujarat Bottling three-limb test — particulars mandatory

Bare invocation of the three-limb test is fatal. Each limb must be pleaded with **factual particulars**:

**Prima facie case** — particulars of (a) the right (registration / first-use / subsistence) and (b) the infringement (act / date / channel / scale).

**Balance of convenience** — particulars of (a) Plaintiff's investment / market reputation / continuous use / market harm versus (b) Defendant's recent / limited / contested use.

**Irreparable injury** — particulars of why damages would be inadequate:
- Trade mark — market dilution / customer confusion / brand reputation erosion
- Copyright — mass-market dissemination beyond recall / lost royalties / artistic reputation
- Patent — erosion of finite monopoly period (20 years from priority) / lost R&D recoupment
- Design — erosion of finite registration period (10 + 5 years) / market-launch window distortion
- Pharmaceuticals / FMCG — consumer-safety harm

## Order 39 Rule 3 first proviso — mandatory where ex-parte relief sought

Every application for ex-parte ad-interim relief must, in the supporting affidavit, **expressly state** the circumstances why notice would defeat the purpose. Per *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225, this is mandatory. Missing → ex-parte order liable to be vacated on first hearing.

## Bajaj Auto cross-undertaking discipline

In patent matters and high-value IP matters generally, the *Bajaj Auto v. TVS Motor* (2009) 9 SCC 797 discipline requires the Plaintiff to offer an unconditional cross-undertaking to pay damages if the interim relief is ultimately found to have been wrongly granted. The Drafter incorporates the cross-undertaking expressly in the application.

## Credible-challenge-to-validity (patent matters)

Per *F. Hoffmann-La Roche v. Cipla* (2015) 65 PTC 187 (DB Del) and *Merck Sharp & Dohme v. Glenmark* (2015) 64 PTC 417 (DB Del), the interim-injunction threshold in patent matters is **elevated** where the Defendant raises a credible challenge to validity. The Plaintiff's interim-injunction application in a patent matter must pre-emptively address the credible-challenge framework with:

- Prior-art search report demonstrating no anticipating disclosure
- Prosecution history demonstrating the patent's defensible scope
- Expert declaration on the inventive step
- Pre-emptive Section 3 (non-patentable subject matter) analysis

## Cross-references

For the parent IP suit (the relief here being interim and the parent suit holding the permanent reliefs), see the corresponding case-type skill. For ex-parte seizure relief alongside the interim injunction (Anton Piller), see `john-doe-anton-piller-order-application-draft`.
