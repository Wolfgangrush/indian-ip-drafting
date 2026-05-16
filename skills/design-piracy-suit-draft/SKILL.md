---
name: design-piracy-suit-draft
description: Draft a civil suit for piracy of a registered design under Section 22 of the Designs Act 2000 read with the Section 19 cancellation framework. Jurisdictional anchor under Section 22(4) (Court of District Judge or above; on counter-claim for cancellation under Section 19, the suit transfers to the High Court). Encodes the Section 22 piracy framework, the Section 11 term of registration (10 years initial + 5 years extension), the Section 19 cancellation grounds (no prior publication / no contrary-to-public-order / no scandalous matter / novel / not significantly distinguishable from known designs), the Section 22(2) damages cap (Rs. 25,000 per design contravention not exceeding Rs. 50,000 per design), the Bharat Glass Tube v. Gopal Glass Works novelty / originality framework, the Carlsberg Breweries v. Som Distilleries composite-suit framework (design piracy + passing-off), and the functionality exclusion (design dictated solely by function). Auto-fires on "draft design piracy suit", "draft Section 22 Designs Act suit", "draft design infringement suit" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Design Piracy Suit Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: SUIT FOR PERMANENT INJUNCTION RESTRAINING PIRACY OF REGISTERED DESIGN, DAMAGES (SUBJECT TO STATUTORY CAP) OR CONTRACT-DEBT RECOVERY, DELIVERY-UP OF INFRINGING ARTICLES / DIES / BLOCKS / MOULDS, AND COSTS UNDER SECTION 22 OF THE DESIGNS ACT 2000
case_short_code: DESIGN_PIRACY_SUIT
case_number_prefix: CS (COMM) / CS (COMM.IPD) / CS (OS) — Court of District Judge or High Court Commercial Division depending on pecuniary jurisdiction; on counter-claim for cancellation under Section 19, transfer to High Court under Section 22(4)
pleading_type: Plaint
typical_forum: Court of District Judge or above under Section 22(4) of the Designs Act 2000; on counter-claim for cancellation under Section 19, transfer to the High Court
typical_parties: Plaintiff (registered design proprietor / assignee) + Defendant(s) (alleged infringer — manufacturer / seller / importer of articles to which the registered design has been pirated)
statutory_opening: "This suit is filed under Section 22 of the Designs Act 2000 read with the Code of Civil Procedure 1908, the Specific Relief Act 1963, and the Commercial Courts Act 2015, for permanent injunction restraining the Defendants from piracy of the Plaintiff's registered Design No. ___ (in Class ___ under the Locarno Classification), damages subject to the statutory cap under Section 22(2) OR recovery as contract-debt at the Plaintiff's election, delivery-up of all infringing articles / dies / blocks / moulds / tools used in the manufacture, and costs."
ground_clauses:
  - "Plaintiff's title — the Plaintiff is the registered proprietor of Design No. ___ in Class ___ (under the Locarno Classification) registered on ____ ('the Suit Design'), the registration being valid and subsisting on the date of institution of the suit (Exhibit ___ — registration certificate with representations of the Suit Design)."
  - "Term of registration — under Section 11 of the Designs Act 2000, the Suit Design's registration is in force for an initial period of 10 years from the date of registration, extendable by 5 years on payment of the prescribed fee. The current term [originally registered / extended] expires on ____ (Exhibit ___ — extension certificate where applicable)."
  - "Section 22 piracy — the Defendants have, for the purposes of sale, applied or caused to be applied the Suit Design or any fraudulent or obvious imitation thereof to an article of the same class as that in which the Suit Design is registered, without the Plaintiff's licence or written consent — particulars at paragraph ___ and Exhibit ___ (infringing-article photographs and comparison chart)."
  - "Comparison and substantial similarity — the impugned article and the Suit Design are substantially similar in their visual appeal (shape / configuration / pattern / ornament / composition of lines or colours) such that the Defendants' article amounts to a fraudulent or obvious imitation of the Suit Design within the meaning of Section 22(1). The comparison chart at Exhibit ___ demonstrates the substantial similarity feature-by-feature."
  - "Validity affirmed — the Suit Design is novel and original within the meaning of Section 2(g) and Section 4 of the Designs Act 2000. The Suit Design is not (a) previously published in India or elsewhere prior to the date of filing, (b) significantly distinguishable from known designs, (c) contrary to public order or morality. The novelty / originality framework laid down in *Bharat Glass Tube v. Gopal Glass Works* (2008) 10 SCC 657 is satisfied."
  - "Jurisdiction — under Section 22(4) of the Designs Act 2000, this suit is filed before the Court of District Judge / High Court of competent pecuniary jurisdiction. The Plaintiff is aware that under the proviso to Section 22(4), on a counter-claim for cancellation of the Suit Design under Section 19, the suit shall be transferred to the High Court."
  - "Limitation — the suit is filed within 3 years of each continuing act of piracy (Article 113 of the Schedule to the Limitation Act 1963); each continuing act of piracy constitutes a fresh cause of action."
  - "Section 12A Commercial Courts Act 2015 exemption — urgent interim relief is contemplated and prayed for (Application No. ___), pleading the exemption from pre-institution mediation under the *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework."
prayer_clauses:
  - "(a) Pass a decree of permanent injunction restraining the Defendants, by themselves, their servants, agents, distributors, retailers, and all persons claiming through them, from applying, causing to be applied, publishing, or exposing for sale any article to which the Plaintiff's registered Design No. ___ has been applied or to which any fraudulent or obvious imitation thereof has been applied;"
  - "(b) Pass a decree for damages, subject to the cap under Section 22(2) of the Designs Act 2000 (Rs. 25,000 per design contravention, not exceeding Rs. 50,000 in respect of any one design), OR direct the Defendants to pay the contract-debt amount at the Plaintiff's election;"
  - "(c) Pass a decree directing the Defendants to deliver up to the Plaintiff for destruction all infringing articles, together with all dies, blocks, moulds, and tools used in the manufacture of the infringing articles;"
  - "(d) Pass a decree for costs of the suit;"
mandatory_exhibits:
  - certified_copy_of_the_design_registration_certificate_with_representations_of_the_design
  - extension_certificate_where_the_initial_10_year_term_has_been_extended
  - register_of_designs_extract_showing_current_proprietorship
  - evidence_of_the_plaintiffs_commercial_application_of_the_design_to_articles_in_the_market
  - infringing_article_samples_or_photographs
  - comparison_chart_feature_by_feature_visual_appeal_shape_configuration_pattern_ornament_lines_colours
  - prior_art_search_report_to_pre_empt_section_19_cancellation_grounds
  - evidence_of_the_defendants_scale_of_piracy_for_damages_quantum
  - cease_and_desist_correspondence_with_proof_of_service
  - board_resolution_authorising_the_litigation_where_corporate_plaintiff
accompanying_applications:
  - "I.A. under Order 39 Rules 1 and 2 CPC for interim injunction (with American Cyanamid / Gujarat Bottling three-limb pleading + Bharat Glass Tube novelty pleading)"
  - "I.A. under Order 39 Rule 3 CPC for ex-parte ad-interim relief (with Order 39 Rule 3 first-proviso affidavit on why notice would defeat the purpose)"
  - "I.A. under Order 26 Rules 9 and 10 CPC for appointment of Local Commissioner (for seizure of infringing articles / dies / blocks / moulds)"
  - "I.A. for composite-suit framework where passing-off is also pleaded — the *Carlsberg Breweries v. Som Distilleries* (2018) 76 PTC 1 (DB Del) framework"
  - "I.A. for exemption from pre-institution mediation under Section 12A Commercial Courts Act 2015"
court_fee: "Ad valorem under the applicable State Court-Fees Act on the damages quantum or as per the High Court Original Side Rules"
```

## Section 22(2) damages cap

Section 22(2) of the Designs Act 2000 imposes a statutory cap on damages — Rs. 25,000 per design contravention, not exceeding Rs. 50,000 in respect of any one design. The Drafter pleads the damages within the statutory cap and notes the Plaintiff's election to either (a) take damages within the cap, or (b) recover the same as contract-debt under Section 22(2)(b) — the contract-debt route offers the Plaintiff potentially a higher recovery in appropriate cases.

## Composite suit (design piracy + passing-off)

Where the Plaintiff's registered design is also a trade-mark-like get-up that has built up secondary meaning in the market, a composite suit for design piracy under Section 22 PLUS passing-off at common law is permissible per *Carlsberg Breweries v. Som Distilleries* (2018) 76 PTC 1 (DB Del). The composite suit retains the design-jurisdiction anchor for the design claim and the passing-off claim follows. See the `passing-off-suit-draft` skill for the passing-off framework.

## Section 19 cancellation counter-claim anticipation

The most common Defendant move in a design piracy suit is a counter-claim for cancellation under Section 19 on the grounds that the design (a) was previously published in India or in any other country, (b) is not new or original, (c) is not significantly distinguishable from known designs or combinations of known designs, or (d) comprises or contains scandalous or obscene matter. This counter-claim transfers the suit from the District Court to the High Court under the proviso to Section 22(4). The Drafter pre-empts by pleading the novelty / originality of the Suit Design with prior-art search reports.

## Functionality exclusion anticipation

A design dictated solely by function is not registrable / is liable to cancellation. The Drafter, where the Suit Design has both aesthetic and functional features, affirmatively pleads that the visual appeal is independent of the function and that the registration protects the visual features, not the underlying function.

## Cross-references

For the interim-injunction application, see `interim-injunction-application-ip-draft`. For the composite passing-off claim, see `passing-off-suit-draft`. For Local Commissioner seizure / Anton Piller in the design context, see `john-doe-anton-piller-order-application-draft`.
