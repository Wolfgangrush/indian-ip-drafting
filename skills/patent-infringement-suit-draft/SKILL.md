---
name: patent-infringement-suit-draft
description: Draft a civil suit for infringement of a granted patent under Section 104 read with Section 108 of the Patents Act 1970 (as amended by the Patents (Amendment) Act 2005). Jurisdictional anchor under Section 104 (District Court of competent pecuniary jurisdiction; first proviso to Section 104 transfers to the High Court on counter-claim for revocation under Section 64). Encodes the Section 48 monopoly rights, the Section 107 defences anticipation, the Section 107A Bolar exemption / parallel-import anticipation, the Section 64 revocation counter-claim anticipation (with Aloys Wobben election framework), the Bajaj Auto v. TVS Motor day-to-day-hearing discipline, the F. Hoffmann-La Roche v. Cipla / Merck Sharp & Dohme v. Glenmark credible-challenge-to-validity framework at the interim-injunction stage, and the Section 84 compulsory licence anticipation. Auto-fires on "draft patent infringement suit", "draft Section 104 suit", "draft patent violation suit" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Patent Infringement Suit Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: SUIT FOR PERMANENT INJUNCTION RESTRAINING INFRINGEMENT OF PATENT, DAMAGES OR ACCOUNT OF PROFITS, SEIZURE / FORFEITURE / DESTRUCTION OF INFRINGING GOODS, AND COSTS UNDER SECTION 104 READ WITH SECTION 108 OF THE PATENTS ACT 1970 (AS AMENDED)
case_short_code: PATENT_INFRINGEMENT_SUIT
case_number_prefix: CS (COMM) / CS (COMM.IPD)
pleading_type: Plaint
typical_forum: District Court of competent pecuniary jurisdiction under Section 104 of the Patents Act 1970 — first proviso to Section 104 transfers the suit to the High Court on counter-claim for revocation under Section 64. In practice, patent suits are often instituted directly in the High Court Commercial Division / Intellectual Property Rights Division where pecuniary jurisdiction so admits, to avoid the transfer mechanism
typical_parties: Plaintiff (patentee / exclusive licensee) + Defendant(s) (alleged infringer — manufacturer / importer / distributor / retailer of the impugned product or process)
statutory_opening: "This suit is filed under Section 104 read with Section 108 and Section 48 of the Patents Act 1970 (as amended by the Patents (Amendment) Act 2005), the Code of Civil Procedure 1908, the Specific Relief Act 1963, and the Commercial Courts Act 2015, for permanent injunction restraining the Defendants from infringing the Plaintiff's Patent No. ___ titled '___' granted on ____ , damages of Rs. ___ OR account of profits at the Plaintiff's election, seizure / forfeiture / destruction of infringing articles under Section 108 of the Patents Act 1970, and costs."
ground_clauses:
  - "Plaintiff's title — the Plaintiff is the patentee of Patent No. ___ ('the Suit Patent') granted by the Controller of Patents on ____ , with priority date of ____ , the grant being valid and subsisting as on the date of institution of this suit (Exhibit ___ — grant certificate; Exhibit ___ — most recent annuity-payment receipt under Section 53)."
  - "Subsistence and validity — the Suit Patent is in force as on the date of institution. The Plaintiff has complied with all conditions of validity, including timely payment of annuities under Section 53 and Section 142 of the Patents Act 1970."
  - "Section 48 rights conferred — the grant of the Suit Patent confers on the Plaintiff the exclusive right to prevent third parties, not having the Plaintiff's consent, from the act of making, using, offering for sale, selling, or importing for those purposes the patented product / from the act of using the patented process and from the act of using, offering for sale, selling, or importing for those purposes the product obtained directly by that process — in the territory of India."
  - "Infringement — the Defendants have made / used / offered for sale / sold / imported the impugned product / process which falls within the scope of the claims of the Suit Patent. The claim-by-claim infringement analysis is set out in the comparison chart at Exhibit ___ — each independent claim of the Suit Patent (Claim 1, Claim ___) is mapped element-by-element to the corresponding features of the impugned product / process, demonstrating literal infringement / infringement under the doctrine of equivalents."
  - "Jurisdiction — under Section 104 of the Patents Act 1970, this suit is filed in the District Court of competent pecuniary jurisdiction within whose local limits [specify cause of action / defendant residence]. The Plaintiff is aware that under the first proviso to Section 104, on a counter-claim for revocation under Section 64, this suit shall be transferred to the High Court."
  - "Limitation — the suit is filed within 3 years of each continuing act of infringement (Article 113 of the Schedule to the Limitation Act 1963); each continuing act of infringement constitutes a fresh cause of action."
  - "Section 107A defences pre-empted — the Defendants' acts do not fall within the Bolar exemption (Section 107A(a) — acts done for research / development / submission of regulatory information) or the parallel-import exemption (Section 107A(b)). Particulars: [specify why the Defendants' use is commercial sale / production at scale beyond research]."
  - "Section 12A Commercial Courts Act 2015 exemption — urgent interim relief is contemplated and prayed for (Application No. ___), pleading the exemption from pre-institution mediation under the *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework."
  - "Bajaj Auto v. TVS Motor day-to-day hearing — the Plaintiff invokes the discipline laid down by the Hon'ble Supreme Court in *Bajaj Auto Ltd. v. TVS Motor Company Ltd.* (2009) 9 SCC 797 that intellectual-property suits, particularly patent suits, ought to be heard from day-to-day to ensure speedy disposal."
prayer_clauses:
  - "(a) Pass a decree of permanent injunction restraining the Defendants, by themselves, their servants, agents, distributors, retailers, importers, online intermediaries, and all persons claiming through them, from making, using, offering for sale, selling, or importing into India the impugned product / process that infringes the claims of Patent No. ___ as set out in the comparison chart at Exhibit ___ ;"
  - "(b) Pass a decree for damages of Rs. ___ OR direct the Defendants to render account of the profits earned from the infringing acts and decree the amount so ascertained in favour of the Plaintiff, at the Plaintiff's election;"
  - "(c) Pass a decree under Section 108(2) of the Patents Act 1970 directing the seizure / forfeiture / destruction of all infringing articles in the possession, custody, or control of the Defendants, together with all materials and implements predominantly used in their creation;"
  - "(d) Pass a decree for costs of the suit on an indemnity basis having regard to the wilful and deliberate nature of the infringement;"
mandatory_exhibits:
  - certified_copy_of_the_patent_grant_certificate
  - certified_copy_of_the_complete_specification_and_claims_as_granted
  - most_recent_annuity_payment_receipt_under_section_53
  - register_of_patents_extract_showing_current_proprietorship
  - claim_construction_chart_with_meanings_of_disputed_terms
  - element_by_element_infringement_chart_mapping_claims_to_the_impugned_product_or_process
  - infringing_product_samples_photographs_promotional_material_technical_data_sheets
  - prosecution_history_excerpts_of_the_suit_patent
  - section_8_disclosures_of_foreign_filings_with_proof_of_filing
  - prior_art_search_reports_pre_emptively_addressing_revocation_grounds
  - cease_and_desist_correspondence_with_proof_of_service
  - damages_quantum_computation_or_evidence_of_defendants_profits
  - board_resolution_authorising_the_litigation_where_corporate_plaintiff
accompanying_applications:
  - "I.A. under Order 39 Rules 1 and 2 CPC for interim injunction (with American Cyanamid / Gujarat Bottling three-limb pleading + pre-emptive credible-challenge-to-validity analysis per *F. Hoffmann-La Roche v. Cipla* (2015) 65 PTC 187 (DB Del) and *Merck Sharp & Dohme v. Glenmark* (2015) 64 PTC 417 (DB Del))"
  - "I.A. under Order 39 Rule 3 CPC for ex-parte ad-interim relief (with Order 39 Rule 3 first-proviso affidavit on why notice would defeat the purpose + cross-undertaking on damages per *Bajaj Auto v. TVS Motor*)"
  - "I.A. under Order 26 Rules 9 and 10 CPC for appointment of Local Commissioner (for seizure of infringing samples / inspection of the Defendants' manufacturing premises)"
  - "I.A. under Section 108(2) Patents Act for interim seizure / forfeiture"
  - "I.A. for day-to-day hearing of the suit per *Bajaj Auto v. TVS Motor* (2009) 9 SCC 797"
  - "I.A. for exemption from pre-institution mediation under Section 12A Commercial Courts Act 2015"
court_fee: "Ad valorem under the applicable State Court-Fees Act on the damages quantum or as per the High Court Original Side Rules / IPD Rules Schedule"
```

## Counter-claim for revocation anticipation

The most common Defendant move in a patent infringement suit is a counter-claim for revocation under Section 64 of the Patents Act 1970. This counter-claim:

1. Transfers the suit from the District Court to the High Court under the first proviso to Section 104
2. Forces the *Aloys Wobben v. Yogesh Mehra* (2014) 15 SCC 360 election — the Defendant cannot pursue both a Section 64 application before the HC IPD AND a counter-claim for revocation in the suit
3. Triggers the credible-challenge-to-validity framework at the interim-injunction stage (*F. Hoffmann-La Roche v. Cipla* / *Merck Sharp & Dohme v. Glenmark*)

The Drafter anticipates by pleading the validity of the Suit Patent affirmatively, with prior-art search reports demonstrating that no anticipating or obvious prior art has been disclosed.

## Bajaj Auto v. TVS Motor day-to-day discipline

The *Bajaj Auto v. TVS Motor* (2009) 9 SCC 797 discipline requires patent suits to be heard from day-to-day to ensure speedy disposal. The Plaintiff invokes this discipline in the plaint and the interim-injunction application, and seeks a direction for day-to-day hearing.

## Cross-undertaking on damages

In patent matters, the *Bajaj Auto* discipline on cross-undertaking is the *quid pro quo* for interim injunction. The Plaintiff's interim-injunction application offers the cross-undertaking expressly.

## Cross-references

For the interim-injunction application (with credible-challenge-to-validity pleading), see `interim-injunction-application-ip-draft`. For revocation counter-claim handling, see `patent-revocation-application-draft`. For Anton Piller in the patent context (seizure of infringing samples / inspection of manufacturing premises), see `john-doe-anton-piller-order-application-draft`.
