---
name: patent-revocation-application-draft
description: Draft an application for revocation of a patent under Section 64 of the Patents Act 1970, before the High Court Intellectual Property Rights Division (post-IPAB-abolition per Sections 12 to 14 of the Tribunals Reforms Act 2021). For any person interested (typically a competitor / a person whose business is affected by the patent / a Government party) seeking revocation of a granted patent on the grounds listed in Section 64(1) (want of novelty / want of inventive step / non-patentable subject matter under Section 3 / insufficient disclosure under Section 10(4) / wrongful obtainment / false suggestion / non-disclosure of foreign filings under Section 8 / non-working under Section 64(1)(m) / etc.). Encodes the post-IPAB transition (every IPAB reference re-routed to HC IP Division), the Aloys Wobben v. Yogesh Mehra election framework (Section 64 application vs counter-claim — election is final), the Section 3 non-patentable subject matter framework (Novartis on Section 3(d) / software-per-se on Section 3(k) / morality on Section 3(b) / methods of treatment on Section 3(i)), and the prior-art chart framework. Auto-fires on "draft patent revocation", "draft Section 64 application", "draft revocation petition" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Patent Revocation Application Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: ORIGINAL APPLICATION FOR REVOCATION OF PATENT UNDER SECTION 64 OF THE PATENTS ACT 1970 READ WITH SECTIONS 12 TO 14 OF THE TRIBUNALS REFORMS ACT 2021
case_short_code: PATENT_REVOCATION
case_number_prefix: C.O. (Comm.IPD-PAT) — Delhi HC IPD nomenclature; corresponding nomenclature for Madras HC IPD / Calcutta HC IPD / Bombay HC IPD as constituted; the High Court of competent jurisdiction otherwise (the Intellectual Property Appellate Board stands abolished by the Tribunals Reforms Act 2021 — jurisdiction now lies in the HC IP Division per Section 117G transitional provision)
pleading_type: Original Application for Revocation
typical_forum: High Court Intellectual Property Rights Division — Delhi HC IPD (Delhi HC IPR Division Rules 2022) / Madras HC IPD / Calcutta HC IPD / Bombay HC IPD where established; otherwise the High Court of competent jurisdiction
typical_parties: Petitioner (person interested — competitor / affected business / Government / consumer-protection party) + Respondent No. 1 (patentee) + Respondent No. 2 (Controller of Patents — formal party)
statutory_opening: "This Original Application is filed under Section 64 of the Patents Act 1970 (as amended by the Patents (Amendment) Act 2005) read with Sections 12 to 14 of the Tribunals Reforms Act 2021, the Intellectual Property Appellate Board having stood abolished thereby and the jurisdiction earlier vested in the Board now lying in this Hon'ble High Court Intellectual Property Rights Division, for revocation of Patent No. ___ titled '___' granted in the name of Respondent No. 1 on ____ , on the grounds set out hereinafter."
ground_clauses:
  - "Standing as person interested — the Petitioner is a person interested within the meaning of Section 64 read with Section 2(1)(t) of the Patents Act 1970, by reason of [specify: engagement in business / manufacture / trade / research in the field to which the impugned patent pertains]. The Petitioner's competing commercial interest is set out in paragraph ___ above and Exhibit ___."
  - "Section 64(1)(a) — invention claimed in any claim of the impugned patent has been claimed in a complete specification of an earlier patent published before the priority date of the claim (prior claiming)."
  - "Section 64(1)(b) — invention claimed was, before the priority date of the claim, published in India or elsewhere (anticipation by publication). Prior art chart at Exhibit ___ identifies the anticipating publications."
  - "Section 64(1)(d) — invention claimed is not an invention within the meaning of the Act / is not patentable under the Act, in particular falls within Section 3 (non-patentable subject matter): [specify sub-clause — Section 3(d) on incremental innovation per *Novartis AG v. Union of India* (2013) 6 SCC 1 / Section 3(k) on computer programs per se / mathematical methods / business methods / algorithms / Section 3(b) on morality and public order / Section 3(i) on methods of treatment / Section 3(j) on plants and animals other than micro-organisms]."
  - "Section 64(1)(e) — invention claimed is not new having regard to what was publicly known or publicly used in India or to what was published in India or elsewhere before the priority date of the claim."
  - "Section 64(1)(f) — invention claimed is obvious or does not involve any inventive step having regard to the prior art (combination of prior art at Exhibit ___ renders the claimed invention obvious)."
  - "Section 64(1)(g) — invention as defined in any claim of the complete specification is not useful."
  - "Section 64(1)(h) — complete specification does not sufficiently and fairly describe the invention and the method by which it is to be performed, or does not disclose the best method of performing the invention which was known to the applicant for the patent (insufficient disclosure under Section 10(4))."
  - "Section 64(1)(i) — scope of any claim of the complete specification is not sufficiently and clearly defined / claim is not fairly based on the matter disclosed in the specification."
  - "Section 64(1)(j) — patent was obtained on a false suggestion or representation."
  - "Section 64(1)(k) — subject of any claim of the complete specification is not patentable under the Act (broader catch-all)."
  - "Section 64(1)(l) — invention so far as claimed in any claim was secretly used in India, otherwise than as mentioned in sub-section (3), before the priority date of the claim."
  - "Section 64(1)(m) — applicant has failed to disclose to the Controller the information required by Section 8 (foreign filings) or has furnished information which in any material particular was false to the knowledge of the applicant — the *Chemtura Corporation v. Union of India* (2009) 41 PTC 260 (Del) framework."
  - "Section 64(1)(n) — applicant has contravened any direction for secrecy passed under Section 35 or made or caused to be made an application for the grant of a patent outside India in contravention of Section 39."
  - "Section 64(1)(o) — leave to amend the complete specification under Section 57 or Section 58 was obtained by fraud."
  - "Section 64(1)(p) — complete specification does not disclose, or wrongly mentions, the source or geographical origin of biological material used for the invention."
  - "Section 64(1)(q) — invention so far as claimed in any claim was anticipated having regard to the knowledge, oral or otherwise, available within any local or indigenous community in India or elsewhere (traditional-knowledge ground)."
  - "Jurisdiction — the IPAB having stood abolished by the Tribunals Reforms Act 2021 (Act 33 of 2021), the jurisdiction earlier vested in the Board under Section 64 of the Patents Act 1970 now lies in this Hon'ble High Court Intellectual Property Rights Division per Sections 12 to 14 of the Tribunals Reforms Act 2021 and Section 117G of the Patents Act 1970 (transitional provision). This Hon'ble Court has territorial jurisdiction by reason of [specify: the impugned patent having been granted through the Patent Office within the High Court's territorial jurisdiction / the Petitioner / Respondent No. 1 having its principal place of business within the High Court's territorial jurisdiction]."
  - "Aloys Wobben election — the Petitioner has not filed a counter-claim for revocation of the impugned patent in any pending suit for infringement, and accordingly is entitled to maintain this Section 64 application per the *Aloys Wobben v. Yogesh Mehra* (2014) 15 SCC 360 framework."
prayer_clauses:
  - "(a) Revoke Patent No. ___ in whole on the grounds set out herein;"
  - "(b) In the alternative, revoke the impugned claims (Claim ___, Claim ___, Claim ___) of Patent No. ___ ;"
  - "(c) Direct Respondent No. 2 (the Controller of Patents) to give effect to the revocation by entering the order on the Register of Patents and publishing the same in the Patent Office Journal;"
  - "(d) Pass a decree for costs of these proceedings;"
mandatory_exhibits:
  - certified_copy_of_the_impugned_patent_grant_certificate
  - certified_copy_of_the_complete_specification_and_claims_as_granted
  - prosecution_history_of_the_impugned_patent
  - prior_art_chart_with_anticipating_or_rendering_obvious_publications_each_mapped_element_by_element_to_the_impugned_claims
  - expert_declaration_or_affidavit_supporting_the_invalidity_grounds
  - evidence_of_the_petitioners_standing_as_person_interested
  - evidence_supporting_section_3_non_patentable_subject_matter_ground_where_invoked
  - section_8_disclosures_of_foreign_filings_obtained_from_the_patent_office_record
  - traditional_knowledge_digital_library_extracts_where_section_64_1_q_is_invoked
  - board_resolution_authorising_the_application_where_corporate_petitioner
accompanying_applications:
  - "I.A. for early hearing / urgent listing (where the impugned patent is actively asserted against the Petitioner)"
  - "I.A. for production of further documents from the Patent Office"
  - "I.A. for joinder of additional respondents (where multiple proprietors are recorded)"
court_fee: "Per the Schedule attached to the Delhi HC IPR Division Rules 2022 / Madras HC IPR Division Rules / corresponding High Court IPD Rules as applicable; otherwise the standard original-petition fee per the High Court Original Side Rules"
```

## IPAB-abolition lock (mandatory)

This pleading is **always** filed before the **High Court Intellectual Property Rights Division** (Delhi / Madras / Calcutta / Bombay where established; the High Court of competent jurisdiction otherwise). The Intellectual Property Appellate Board (IPAB) stands abolished by the Tribunals Reforms Act 2021 (Sections 12 to 14). Pending IPAB revocation proceedings transferred to the High Court IPD by virtue of Section 117G of the Patents Act 1970 read with the Tribunals Reforms Act transitional provisions.

Any reference to the IPAB as a live revocation forum is **fatal** and is flagged by the Verifier with mandatory re-routing.

Pre-2021 IPAB decisions on patent revocation remain valid **precedent** and may be cited.

## Aloys Wobben election framework — mandatory pleading

The *Aloys Wobben v. Yogesh Mehra* (2014) 15 SCC 360 framework requires the Petitioner to elect between:

(i) a Section 64 application for revocation before the HC IPD, OR
(ii) a counter-claim for revocation in a pending suit for infringement under Section 64 read with Section 104 first proviso

The election is final. The Drafter pleads affirmatively that the Petitioner has not invoked the alternative forum.

## Standing as "person interested" — mandatory pleading

Bare invocation of Section 64 is insufficient. The Petitioner must affirmatively plead its **engagement in business / manufacture / trade / research** in the field to which the impugned patent pertains, with particulars and supporting evidence.

## Ground specification with prior-art mapping

Section 64(1)(a) to (q) grounds are not pleaded in the abstract. Each invoked ground must be supported by:

- For Section 64(1)(a) / (b) / (e) / (f) anticipation / obviousness grounds — a prior-art chart that maps each cited prior-art reference to the impugned claims element-by-element
- For Section 64(1)(d) / Section 3 non-patentable subject matter — specific sub-clause analysis with binding authority (*Novartis v. Union of India* (2013) 6 SCC 1 on Section 3(d) for incremental innovation; the *Yahoo! Inc. v. Controller of Patents* line on Section 3(k) for business methods / software)
- For Section 64(1)(h) — pinpoint reference to the parts of the specification that fail the sufficiency test
- For Section 64(1)(m) — the *Chemtura Corporation v. Union of India* (2009) 41 PTC 260 (Del) framework on Section 8 disclosures
- For Section 64(1)(q) — traditional-knowledge ground supported by Traditional Knowledge Digital Library (TKDL) extracts where applicable

## Cross-references

For revocation by way of counter-claim in an infringement suit (the alternative forum), see `patent-infringement-suit-draft`. For interim relief sought in the revocation proceedings (rare but possible — directions on Section 8 disclosures / on Defendant patentee's enforcement activity), see `interim-injunction-application-ip-draft`.
