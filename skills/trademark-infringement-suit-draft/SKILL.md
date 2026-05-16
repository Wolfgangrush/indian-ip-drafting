---
name: trademark-infringement-suit-draft
description: Draft a civil suit for infringement of a registered trade mark under Section 29 read with Section 134 and Section 135 of the Trade Marks Act 1999. Jurisdictional anchor under Section 134 (plaintiff resides / carries on business / works for gain — displaces Section 20 CPC; IPRS v. Sanjay Dalia principal-place-of-business qualification). Encodes the Section 29 infringement framework (identical / deceptively similar mark in respect of identical / similar / dissimilar goods), Section 28 rights-conferred-by-registration, Section 31 prima-facie evidence of validity, Section 33 acquiescence anticipation, Section 34 prior-use anticipation, Section 35 own-name / descriptive-use anticipation, Section 47 non-use rectification anticipation, Section 124 stay-pending-rectification framework, Section 135 reliefs (injunction, damages or account of profits, delivery-up), and the Cadila Healthcare triple-test framework for likelihood of confusion. Auto-fires on "draft trade mark infringement suit", "draft trademark suit", "draft Section 29 TMA suit" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Trade Mark Infringement Suit Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: SUIT FOR PERMANENT INJUNCTION RESTRAINING INFRINGEMENT OF REGISTERED TRADE MARK, DAMAGES OR ACCOUNT OF PROFITS, DELIVERY-UP, AND COSTS UNDER SECTION 29 READ WITH SECTION 134 AND SECTION 135 OF THE TRADE MARKS ACT 1999
case_short_code: TM_INFRINGEMENT_SUIT
case_number_prefix: CS (COMM) / CS (COMM.IPD) / CS (OS)
pleading_type: Plaint
typical_forum: District Court of competent pecuniary jurisdiction / High Court Commercial Division / High Court Intellectual Property Rights Division — Section 134 Trade Marks Act 1999 anchors jurisdiction at the place where the Plaintiff resides / carries on business / personally works for gain (displaces Section 20 CPC)
typical_parties: Plaintiff (registered trade mark proprietor / exclusive licensee) + Defendant(s) (alleged infringer / distributor / online intermediary) + Directors (Section 141-equivalent joinder under Companies Act 2013 where corporate defendant)
statutory_opening: "This suit is filed under Section 29 read with Section 134 and Section 135 of the Trade Marks Act 1999 read with the Code of Civil Procedure 1908, the Specific Relief Act 1963, and the Commercial Courts Act 2015, for permanent injunction restraining the Defendants from infringing the Plaintiff's registered trade mark [Trade Mark] (TM Registration No. ___ in Class ___ ), damages of Rs. ___ OR account of profits at the Plaintiff's election, delivery-up of all infringing labels, packaging, and promotional material, and costs."
ground_clauses:
  - "Subsistence of registration — the Plaintiff is the proprietor of the registered trade mark [Trade Mark] under TM Registration No. ___ in Class ___ , the registration being valid and subsisting on the date of institution of the suit (Exhibit ___ — registration certificate; Exhibit ___ — renewal certificate dated ____ )."
  - "Section 31 prima facie validity — under Section 31 of the Trade Marks Act 1999, the registration of the Plaintiff's mark is prima facie evidence of its validity in all legal proceedings; the burden lies on the Defendant to displace the presumption."
  - "Section 28 rights conferred by registration — the registration confers on the Plaintiff the exclusive right to use the mark in respect of the goods / services covered by the registration."
  - "Section 29 infringement — the Defendants have, in the course of trade, used a mark identical with / deceptively similar to the Plaintiff's registered trade mark, in respect of identical / similar goods / services, such that the use is likely to cause confusion on the part of the public or to cause the public to associate the Defendants' mark with the Plaintiff's (Section 29(1), (2), (3) as applicable). The relevant comparison is set out in the comparison chart at Exhibit ___."
  - "Cadila Healthcare triple-test — the *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 framework on likelihood of confusion is satisfied: (i) the nature of the goods is [specify], (ii) the class of purchasers is [specify], (iii) the mode of purchase is [specify], (iv) the overall similarity in essential features (phonetic / visual / structural / conceptual) of the marks compared as a whole and not in their parts."
  - "Jurisdiction — under Section 134(2) of the Trade Marks Act 1999, the Plaintiff is entitled to file this suit in this Hon'ble Court within whose local limits the Plaintiff actually and voluntarily resides / carries on business / personally works for gain. The *IPRS v. Sanjay Dalia* (2015) 10 SCC 161 principal-place-of-business qualification is satisfied as set out in paragraph ___ above."
  - "Limitation — the suit is filed within 3 years of each continuing act of infringement (Article 75 of the Schedule to the Limitation Act 1963); each continuing act of infringement constitutes a fresh cause of action."
  - "Section 12A Commercial Courts Act 2015 exemption — urgent interim relief is contemplated and prayed for in this suit (Application No. ___ for ex-parte ad-interim injunction), pleading the exemption from pre-institution mediation under the *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework."
prayer_clauses:
  - "(a) Pass a decree of permanent injunction restraining the Defendants, by themselves, their servants, agents, distributors, retailers, online intermediaries, and all persons claiming through them, from using in the course of trade the mark [Impugned Mark] or any other mark identical with or deceptively similar to the Plaintiff's registered trade mark [Trade Mark] in respect of the goods / services covered by the Plaintiff's TM Registration No. ___ in Class ___ ;"
  - "(b) Pass a decree for damages of Rs. ___ OR direct the Defendants to render account of the profits earned from the infringing use and decree the amount so ascertained in favour of the Plaintiff, at the Plaintiff's election;"
  - "(c) Pass a decree directing the Defendants to deliver up to the Plaintiff for destruction all labels, packaging, signages, printed material, promotional material, and digital assets bearing the impugned mark;"
  - "(d) Pass a decree for costs of the suit;"
mandatory_exhibits:
  - trade_mark_registration_certificate
  - renewal_certificate_currently_subsisting
  - evidence_of_adoption_and_first_use_of_the_mark_by_the_plaintiff
  - evidence_of_continuous_use_in_commerce
  - evidence_of_goodwill_and_reputation_sales_data_advertising_spend_press_coverage_awards
  - infringing_product_photographs_packaging_signage_promotional_material
  - comparison_chart_phonetic_visual_structural_conceptual
  - cease_and_desist_correspondence_with_proof_of_service
  - damages_quantum_computation_or_evidence_of_defendants_profits
  - board_resolution_authorising_the_litigation_where_corporate_plaintiff
  - power_of_attorney_in_favour_of_the_authorised_signatory_where_applicable
accompanying_applications:
  - "I.A. under Order 39 Rules 1 and 2 CPC for interim injunction restraining the Defendants from the infringing use pending the suit (with American Cyanamid / Gujarat Bottling three-limb pleading + Cadila Healthcare triple-test factual particulars)"
  - "I.A. under Order 39 Rule 3 CPC for ex-parte ad-interim relief (with Order 39 Rule 3 first-proviso affidavit on why notice would defeat the purpose)"
  - "I.A. under Order 26 Rules 9 and 10 CPC for appointment of Local Commissioner (where seizure of infringing labels / packaging / stock is sought)"
  - "I.A. under Order 39 Rules 1 and 2 read with Order 26 CPC for John Doe / Ashok Kumar order against unknown infringers (in counterfeit-ring contexts)"
  - "I.A. for exemption from pre-institution mediation under Section 12A Commercial Courts Act 2015 (urgent interim relief contemplated)"
  - "I.A. for rendition-of-accounts inquiry post-decree"
court_fee: "Ad valorem under the applicable State Court-Fees Act on the damages quantum or as per the High Court Original Side Rules / IPD Rules Schedule"
```

## Section 134 jurisdiction-at-plaintiff note

Section 134(2) of the Trade Marks Act 1999 is a *suis generis* jurisdictional provision. It displaces Section 20 CPC and confers jurisdiction on the District Court within whose local limits the **Plaintiff** actually and voluntarily resides / carries on business / personally works for gain. The *IPRS v. Sanjay Dalia* (2015) 10 SCC 161 qualification limits this to the **principal place of business** (not a subordinate office where the Plaintiff has its head office elsewhere). The Drafter must establish the Plaintiff's principal-place-of-business connection to the forum.

## Section 124 stay-pending-rectification anticipation

If the Defendant pleads invalidity of the Plaintiff's registration and applies for rectification under Section 57, the suit may be stayed pending the rectification application's adjudication (the *Patel Field Marshal Agencies v. P.M. Diesels* (2018) 2 SCC 112 framework — election once made is final; the Defendant must elect between rectification before the HC IPD and counter-claim in the infringement suit). The Drafter pre-empts by pleading the Plaintiff's confidence in the validity of the registration with particulars.

## Composite suit (infringement + passing-off)

Where the Plaintiff also has prior-use rights independent of registration, a composite suit for infringement under Section 29 PLUS passing-off at common law is typically pleaded. The composite suit retains Section 134 jurisdiction for the infringement claim; the passing-off claim follows the same forum by virtue of being joined. See the `passing-off-suit-draft` skill for the passing-off-specific framework.

## Cross-references

For the interim-injunction application, see `interim-injunction-application-ip-draft`. For John Doe / Anton Piller against counterfeit rings, see `john-doe-anton-piller-order-application-draft`. For the rectification cross-challenge by the Defendant, see `trademark-rectification-application-draft`.
