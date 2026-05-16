---
name: trademark-rectification-application-draft
description: Draft an application for rectification of the Register of Trade Marks under Section 57 of the Trade Marks Act 1999, before the High Court Intellectual Property Rights Division (post-IPAB-abolition per Sections 12 to 14 of the Tribunals Reforms Act 2021). For any aggrieved person seeking removal / variation of a registered trade mark on grounds under Section 9 (absolute grounds — devoid of distinctive character / descriptive / generic / deceptive / contrary to public order), Section 11 (relative grounds — earlier marks / well-known marks), Section 12 (honest concurrent use / condition-of-registration breach), Section 47 (non-use for continuous period of 5 years and 3 months from date of registration), Section 57(1) wrongful entry, or Section 57(2) failure to observe condition of registration. Encodes the post-IPAB transition (every IPAB reference re-routed to HC IP Division), the standing requirement (person aggrieved), and the supporting evidence framework. Auto-fires on "draft trade mark rectification", "draft Section 57 TMA application", "draft cancellation of trade mark", "draft TM rectification petition" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Trade Mark Rectification Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: ORIGINAL APPLICATION FOR RECTIFICATION OF THE REGISTER OF TRADE MARKS BY REMOVAL / VARIATION OF THE IMPUGNED REGISTRATION UNDER SECTION 57 OF THE TRADE MARKS ACT 1999 READ WITH SECTIONS 12 TO 14 OF THE TRIBUNALS REFORMS ACT 2021
case_short_code: TM_RECTIFICATION
case_number_prefix: C.O. (Comm.IPD-TM) — Delhi HC IPD nomenclature; corresponding nomenclature for Madras HC IPD / Calcutta HC IPD / Bombay HC IPD as constituted; the High Court of competent jurisdiction otherwise (the Intellectual Property Appellate Board stands abolished by the Tribunals Reforms Act 2021 — jurisdiction now lies in the HC IP Division)
pleading_type: Original Application for Rectification
typical_forum: High Court Intellectual Property Rights Division — Delhi HC IPD (Delhi HC IPR Division Rules 2022) / Madras HC IPD / Calcutta HC IPD / Bombay HC IPD where established; otherwise the High Court of competent jurisdiction
typical_parties: Petitioner (aggrieved person — rival mark proprietor / competitor / person whose interests are prejudicially affected) + Respondent No. 1 (registered proprietor of the impugned trade mark) + Respondent No. 2 (the Registrar of Trade Marks — formal party)
statutory_opening: "This Original Application is filed under Section 57 of the Trade Marks Act 1999 read with Sections 12 to 14 of the Tribunals Reforms Act 2021, the Intellectual Property Appellate Board having stood abolished thereby and the jurisdiction earlier vested in the Board now lying in this Hon'ble High Court Intellectual Property Rights Division, for rectification of the Register of Trade Marks by removal of / variation in the registration in respect of the impugned trade mark [Impugned Trade Mark] (TM Registration No. ___ in Class ___ ) registered in the name of Respondent No. 1, on the grounds set out hereinafter."
ground_clauses:
  - "Standing as person aggrieved — the Petitioner is a person aggrieved within the meaning of Section 57 of the Trade Marks Act 1999, by reason of [specify: rival mark / earlier mark / market presence in the same class / well-known mark / consumer-protection interest]. The Petitioner's competing commercial interest is set out in paragraph ___ above and Exhibit ___."
  - "Section 9 absolute ground (where pleaded) — the impugned mark is liable to be removed from the Register on the ground that it is [devoid of distinctive character under Section 9(1)(a) / consists exclusively of marks or indications which may serve in trade to designate the kind, quality, quantity, intended purpose, values, geographical origin, or time of production under Section 9(1)(b) / has become customary in the current language under Section 9(1)(c) / is of such a nature as to deceive the public or cause confusion under Section 9(2)(a) / contains scandalous or obscene matter under Section 9(2)(c) / is in respect of a sign which exclusively consists of the shape of goods resulting from the nature of the goods themselves under Section 9(3)]."
  - "Section 11 relative ground (where pleaded) — the impugned mark is liable to be removed from the Register because of (i) identity with or similarity to an earlier trade mark and identity or similarity of goods or services, leading to a likelihood of confusion under Section 11(1); OR (ii) the existence of a well-known trade mark protectable across all classes under Section 11(2). The Petitioner's earlier / well-known mark is [Earlier Mark] under TM Registration No. ___ / by virtue of well-known mark status as recognised in [judicial or registry recognition]."
  - "Section 12 honest concurrent use breach (where pleaded) — the impugned mark was registered subject to conditions under Section 12, which have not been observed by Respondent No. 1."
  - "Section 47 non-use (where pleaded) — the impugned mark has not been used by Respondent No. 1, or any predecessor in title, in respect of the goods / services in respect of which it is registered, for a continuous period of 5 years and 3 months from the date on which the mark was actually entered on the Register up to a date three months before the date of the present application, with no special circumstances within the meaning of Section 47(3) justifying the non-use."
  - "Section 57(1) wrongful entry — the registration of the impugned mark was made in contravention of the provisions of the Trade Marks Act 1999 (specify which provisions); the entry is wrongly remaining on the Register and is liable to be removed."
  - "Section 57(2) failure to observe condition — Respondent No. 1 has failed to observe a condition entered on the Register in relation to the impugned mark; the entry is liable to be varied accordingly."
  - "Jurisdiction — the IPAB having stood abolished by the Tribunals Reforms Act 2021 (Act 33 of 2021), the jurisdiction earlier vested in the Board under Section 57 of the Trade Marks Act 1999 now lies in this Hon'ble High Court Intellectual Property Rights Division per Sections 12 to 14 of the Tribunals Reforms Act 2021. This Hon'ble Court has territorial jurisdiction by reason of [specify: the impugned mark having been registered through the Trade Marks Registry within the High Court's territorial jurisdiction / the Petitioner / Respondent No. 1 having its principal place of business within the High Court's territorial jurisdiction]."
prayer_clauses:
  - "(a) Rectify the Register of Trade Marks by removing the registration in respect of the impugned trade mark [Impugned Trade Mark] under TM Registration No. ___ in Class ___ ;"
  - "(b) Alternatively, vary the entry in respect of the impugned registration by [specify the variation sought];"
  - "(c) Direct Respondent No. 2 (the Registrar of Trade Marks) to give effect to the rectification by an order issued under Section 57(4) read with the procedure prescribed under the Trade Marks Rules 2017;"
  - "(d) Pass a decree for costs of these proceedings;"
mandatory_exhibits:
  - certified_copy_of_the_impugned_registration_certificate
  - certified_copy_of_the_petitioners_earlier_or_well_known_mark_registration_where_applicable
  - evidence_of_the_petitioners_standing_as_person_aggrieved_competing_commercial_interest_market_presence
  - evidence_of_non_use_where_section_47_invoked_market_survey_trade_inquiry_search_reports
  - evidence_of_the_section_9_ground_dictionary_extract_genericness_evidence_descriptive_evidence_where_applicable
  - evidence_of_the_section_11_ground_earlier_mark_well_known_status_consumer_perception_where_applicable
  - registry_record_of_oppositions_or_applications_for_rectification_filed_previously_where_relevant
  - board_resolution_authorising_the_application_where_corporate_petitioner
accompanying_applications:
  - "I.A. for early hearing / urgent listing (where the impugned mark causes ongoing market harm)"
  - "I.A. for production of further documents from the Trade Marks Registry"
  - "I.A. for joinder of additional respondents (where multiple proprietors are recorded)"
court_fee: "Per the Schedule attached to the Delhi HC IPR Division Rules 2022 / Madras HC IPR Division Rules / corresponding High Court IPD Rules as applicable; otherwise the standard original-petition fee per the High Court Original Side Rules"
```

## IPAB-abolition lock (mandatory)

This pleading is **always** filed before the **High Court Intellectual Property Rights Division** (Delhi / Madras / Calcutta / Bombay where established; the High Court of competent jurisdiction otherwise). The Intellectual Property Appellate Board (IPAB) stands abolished by the Tribunals Reforms Act 2021 (Sections 12 to 14). Any reference to the IPAB as a live rectification forum is **fatal** and is flagged by the Verifier with mandatory re-routing.

Pre-2021 IPAB decisions on rectification remain valid **precedent** and may be cited. The shift is the **forum**, not the precedential weight of past IPAB decisions.

## Standing as "person aggrieved" — mandatory pleading

Bare invocation of Section 57 is insufficient. The Petitioner must affirmatively plead its **competing commercial interest** with particulars:

- Identity of the Petitioner's competing mark / business
- Class(es) of goods / services in which the Petitioner operates
- Geographic territory of the Petitioner's operations
- Market presence and reputation evidence
- Specific commercial harm caused by the impugned registration

The respondent's first challenge is typically against standing — the Drafter pre-empts.

## Ground specification with particulars

Bare invocation of Section 9 / 11 / 12 / 47 / 57 is insufficient. Each ground must be pleaded with full particulars and supporting evidence:

- Section 9(1)(a) devoid of distinctive character — specify why (descriptive / generic / non-distinctive in the relevant trade)
- Section 11 earlier mark — produce certified copy of the earlier mark + evidence of confusion likelihood
- Section 47 non-use — produce market-survey / trade-inquiry / Trade Mark Registry search reports demonstrating non-use during the 5-years-and-3-months window

## Cross-references

For the parallel infringement suit (where the Petitioner is also the Plaintiff in an infringement action), see `trademark-infringement-suit-draft`. For Section 124 stay of the rectification application pending the infringement suit (or vice versa — the *Patel Field Marshal* election framework), the Drafter notes the election and pre-empts.
