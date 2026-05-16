---
name: passing-off-suit-draft
description: Draft a common-law passing-off suit, read with Section 27 of the Trade Marks Act 1999 (which saves the action for passing-off whether or not the mark is registered). For an unregistered-mark holder OR a registered-mark holder pleading passing-off in addition to infringement (composite suit). Jurisdictional anchor — Section 20 CPC for a pure passing-off action (Section 134 TMA does NOT extend to pure passing-off); Section 134 for a composite infringement-and-passing-off suit. Encodes the Cadila Healthcare triple-test (goodwill / misrepresentation / damage), the N.R. Dongre v. Whirlpool transborder-reputation framework, the Toyota v. Prius Auto territorial-extent-of-goodwill framework, and the get-up / trade-dress / look-and-feel infringement framework. Auto-fires on "draft passing-off suit", "draft passing off suit", "draft common-law trade mark suit" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Passing-Off Suit Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: SUIT FOR PERMANENT INJUNCTION RESTRAINING PASSING-OFF, DAMAGES OR RENDITION OF ACCOUNTS, DELIVERY-UP, AND COSTS, UNDER SECTION 27 OF THE TRADE MARKS ACT 1999 READ WITH THE COMMON LAW
case_short_code: PASSING_OFF_SUIT
case_number_prefix: CS (COMM) / CS (COMM.IPD) / CS (OS)
pleading_type: Plaint
typical_forum: District Court of competent pecuniary jurisdiction / High Court Commercial Division — for a PURE passing-off action, Section 20 CPC anchors jurisdiction (defendant residence / business / cause of action). For a COMPOSITE infringement + passing-off action, Section 134 TMA anchors jurisdiction at the Plaintiff's residence / principal place of business
typical_parties: Plaintiff (unregistered mark holder / registered mark holder pleading also passing-off) + Defendant(s) (alleged passing-off offender)
statutory_opening: "This suit is filed under Section 27 of the Trade Marks Act 1999 read with the common-law tort of passing-off, the Code of Civil Procedure 1908, the Specific Relief Act 1963, and the Commercial Courts Act 2015, for permanent injunction restraining the Defendants from passing-off their goods / services as those of the Plaintiff by use of the impugned mark / get-up / trade-dress, damages of Rs. ___ OR rendition of accounts of the Defendants' wrongful profits at the Plaintiff's election, delivery-up, and costs."
ground_clauses:
  - "Section 27 saving — Section 27(2) of the Trade Marks Act 1999 expressly preserves the right of action for passing-off whether or not the Plaintiff's mark is registered."
  - "Cadila Healthcare triple-test — the *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 three-limb framework is satisfied:"
  - "    (i) Goodwill and reputation — the Plaintiff has, by continuous use from ____ , built substantial goodwill and reputation in the impugned mark / get-up / trade-dress in the relevant market, as evidenced by sales of Rs. ___ , advertising spend of Rs. ___ , press coverage at Exhibit ___ , awards at Exhibit ___ , and length-of-use of [years];"
  - "    (ii) Misrepresentation — the Defendants have made misrepresentations to the public in the course of trade by adopting an identical / deceptively similar mark / get-up / trade-dress, such that the public is likely to be deceived into believing that the Defendants' goods / services originate from or are associated with the Plaintiff;"
  - "    (iii) Damage — the said misrepresentations have caused / are likely to cause damage to the Plaintiff's goodwill (loss of distinctive reputation / customer confusion / diversion of sales / dilution of the Plaintiff's mark)."
  - "Transborder reputation (where applicable) — per *N.R. Dongre v. Whirlpool* (1996) 5 SCC 714 and *Milmet Oftho v. Allergan Inc.* (2004) 12 SCC 624, the Plaintiff's goodwill extends to India by reason of transborder reputation evidenced by [advertising in India / spillover circulation / consumer awareness through global media]."
  - "Territorial extent — per *Toyota Jidosha Kabushiki Kaisha v. Prius Auto Industries* (2018) 2 SCC 1, the Plaintiff's goodwill is established in the relevant Indian territory as evidenced by [specify territorial reach evidence]."
  - "Jurisdiction — Section 20 CPC 1908 anchors jurisdiction at [defendant residence / business / cause of action — specify the operative clause]. [Where composite with infringement: Section 134 of the Trade Marks Act 1999 anchors jurisdiction at the Plaintiff's principal place of business.]"
  - "Limitation — the suit is filed within 3 years of each continuing act of passing-off (Article 75 of the Schedule to the Limitation Act 1963)."
  - "Section 12A Commercial Courts Act 2015 exemption — urgent interim relief is contemplated and prayed for, pleading the exemption from pre-institution mediation under the *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework."
prayer_clauses:
  - "(a) Pass a decree of permanent injunction restraining the Defendants, by themselves, their servants, agents, distributors, retailers, online intermediaries, and all persons claiming through them, from passing-off their goods / services as those of the Plaintiff by use of the impugned mark / get-up / trade-dress / colour scheme / layout, or any other mark or get-up that is likely to cause confusion with the Plaintiff's;"
  - "(b) Pass a decree for damages of Rs. ___ OR direct the Defendants to render accounts of the wrongful profits earned from the passing-off acts and decree the amount so ascertained in favour of the Plaintiff, at the Plaintiff's election;"
  - "(c) Pass a decree directing the Defendants to deliver up to the Plaintiff for destruction all labels, packaging, signages, printed material, promotional material, and digital assets bearing the impugned mark / get-up;"
  - "(d) Pass a decree for costs of the suit;"
mandatory_exhibits:
  - evidence_of_first_use_and_continuous_use_of_the_mark_or_get_up_by_the_plaintiff
  - sales_data_demonstrating_goodwill_and_reputation
  - advertising_spend_records
  - press_coverage_awards_market_recognition
  - market_survey_or_consumer_perception_evidence_where_available
  - infringing_product_photographs_packaging_signage_promotional_material
  - comparison_chart_get_up_trade_dress_visual_concept
  - cease_and_desist_correspondence_with_proof_of_service
  - damages_quantum_computation_or_evidence_of_defendants_profits
  - for_transborder_reputation_global_advertising_and_circulation_evidence_in_India
  - board_resolution_authorising_the_litigation_where_corporate_plaintiff
accompanying_applications:
  - "I.A. under Order 39 Rules 1 and 2 CPC for interim injunction (with American Cyanamid / Gujarat Bottling three-limb pleading + Cadila Healthcare triple-test factual particulars)"
  - "I.A. under Order 39 Rule 3 CPC for ex-parte ad-interim relief"
  - "I.A. under Order 26 Rules 9 and 10 CPC for appointment of Local Commissioner (where seizure of infringing stock is sought)"
  - "I.A. under Order 39 Rules 1 and 2 read with Order 26 CPC for John Doe / Ashok Kumar order against unknown infringers (in counterfeit-ring contexts)"
  - "I.A. for exemption from pre-institution mediation under Section 12A Commercial Courts Act 2015 (urgent interim relief contemplated)"
court_fee: "Ad valorem under the applicable State Court-Fees Act on the damages quantum or as per the High Court Original Side Rules"
```

## Jurisdictional point (pure passing-off vs composite)

Section 134(2) TMA 1999 confers Plaintiff-residence jurisdiction only for a suit for **infringement of a registered trade mark**. A pure passing-off action — where the Plaintiff's mark is unregistered — does NOT enjoy the Section 134 anchor. Jurisdiction in a pure passing-off action lies under Section 20 CPC (defendant residence / business / cause of action). The Drafter must establish the jurisdictional foundation accordingly.

For a composite suit (infringement of a registered mark PLUS passing-off in respect of the same mark / get-up), Section 134 anchors the entire composite suit at the Plaintiff's principal place of business — the passing-off claim is joined as ancillary to the infringement claim.

## Cadila Healthcare triple-test mandatory

Every passing-off pleading must affirmatively plead the *Cadila Health Care Ltd. v. Cadila Pharmaceuticals Ltd.* (2001) 5 SCC 73 triple-test with **factual particulars** for each limb:

(i) **Goodwill** — sales data + advertising spend + length of use + market reputation evidence
(ii) **Misrepresentation** — deceptive similarity of mark / get-up / trade-dress with comparison chart
(iii) **Damage** — actual damage OR likelihood of damage with concrete particulars (loss of distinctive reputation / customer confusion / diversion of sales / dilution)

Bare invocation of the triple-test without particulars is fatal at the interim-injunction stage.

## Transborder reputation pleading

Where the Plaintiff is a foreign rights holder or has only nascent direct Indian operations, the Drafter pleads transborder reputation per *N.R. Dongre v. Whirlpool* / *Milmet Oftho v. Allergan*, with particulars of (a) global advertising spend / publication / promotional activity, (b) spillover circulation in India through global media / internet, (c) consumer awareness in India as evidenced by surveys / press / trade recognition. The *Toyota v. Prius Auto* qualification on territorial extent of goodwill is anticipated and addressed.

## Cross-references

For the interim-injunction application, see `interim-injunction-application-ip-draft`. For John Doe / Anton Piller against counterfeit rings, see `john-doe-anton-piller-order-application-draft`. For the composite suit framework alongside a registered-mark claim, see `trademark-infringement-suit-draft`.
