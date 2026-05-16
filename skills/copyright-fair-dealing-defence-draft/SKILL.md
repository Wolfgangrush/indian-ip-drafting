---
name: copyright-fair-dealing-defence-draft
description: Draft the written statement / defence pleading for a Defendant in a copyright infringement suit, invoking the Section 52 Copyright Act 1957 fair-dealing defence. Encodes the Section 52 sub-clauses (Section 52(1)(a) fair dealing for research / private use / criticism / review / news reporting / Section 52(1)(h) judicial proceedings / Section 52(1)(i) educational use / Section 52(1)(za) / (zb) / (zc) intermediary safe harbours), the Civic Chandran framework on fair-dealing factors, the Eastern Book Company framework on transformation, the idea-expression dichotomy (R.G. Anand framework), and the substantial-similarity vs de minimis defences. Auto-fires on "draft fair-dealing defence", "draft Section 52 defence", "draft copyright defence", "draft written statement copyright" and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Copyright Fair-Dealing Defence Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: WRITTEN STATEMENT / DEFENCE TO THE PLAINT FOR ALLEGED INFRINGEMENT OF COPYRIGHT, INVOKING THE SECTION 52 FAIR-DEALING DEFENCE UNDER THE COPYRIGHT ACT 1957
case_short_code: COPYRIGHT_FAIR_DEALING_DEFENCE
case_number_prefix: (responsive — case number adopted from the Plaint)
pleading_type: Written Statement
typical_forum: same court as the Plaintiff's suit (District Court of competent pecuniary jurisdiction / High Court Commercial Division / High Court Intellectual Property Rights Division)
typical_parties: Defendant filing Written Statement vs Plaintiff
statutory_opening: "This Written Statement is filed under Order 8 Rule 1 of the Code of Civil Procedure 1908, on behalf of the Defendant in answer to the Plaint filed by the Plaintiff alleging infringement of copyright. The Defendant denies the allegations of infringement and invokes the defences under Section 52 of the Copyright Act 1957 and the idea-expression dichotomy, more particularly set out hereinafter."
ground_clauses:
  - "Denial of infringement — the Defendant denies that any of its acts constitute infringement within the meaning of Section 51 of the Copyright Act 1957. The acts complained of, even if proved, fall within the safe harbours of Section 52."
  - "Section 52(1)(a) — fair dealing for research / private use / criticism / review / news reporting — the impugned use is for [specify purpose: research / private study / criticism / review / news reporting] in respect of [identify the work used], with proper attribution to the author / publisher (where applicable), and falls within the fair-dealing framework as elaborated in *Civic Chandran v. Ammini Amma* (1996) 16 PTC 670 (Ker) — applying the four-factor test (nature and purpose of use, quantum and value of matter taken, possibility of competition with the original, and substantial harm to the copyright owner)."
  - "Section 52(1)(h) — reproduction of judicial proceedings — the impugned reproduction is of judicial proceedings or of a report of judicial proceedings made by any Court of Tribunal."
  - "Section 52(1)(i) — educational use — the impugned use is by a teacher or a pupil in the course of instruction, or as part of the questions to be answered in an examination, or in answers to such questions."
  - "Section 52(1)(za) — store-and-forward by electronic intermediary — the Defendant is an electronic intermediary within the meaning of the Information Technology Act 2000 read with the framework of *MySpace Inc. v. Super Cassettes Industries* (2016) 236 DLT 478 and the impugned acts fall within the intermediary safe harbour under Section 79 of the IT Act and Section 52(1)(za) / (zb) / (zc) of the Copyright Act 1957."
  - "Idea-expression dichotomy — the matter alleged to have been infringed is the underlying idea, theme, plot, or factual content of the work, not the original expression of the Plaintiff. Per *R.G. Anand v. Delux Films* (1978) 4 SCC 118, the idea-expression dichotomy bars an infringement action on the underlying idea."
  - "Originality challenge — the Plaintiff's work does not satisfy the *modicum-of-creativity* test in *Eastern Book Company v. D.B. Modak* (2008) 1 SCC 1; the matter relied upon by the Plaintiff is purely factual / lacks the modicum of creative input required to attract copyright protection."
  - "De minimis use — the quantum of matter used by the Defendant is de minimis non curat lex and does not amount to copying of a substantial part of the Plaintiff's work as required by Section 51."
  - "Section 19 assignment validity (where Plaintiff is assignee) — the deed of assignment relied upon by the Plaintiff is non-compliant with Section 19 of the Copyright Act 1957 (specify which ingredient is missing: writing / signature / identification of work / specification of rights / duration / territorial extent / royalty proviso under Section 19(3))."
  - "Subsistence challenge — the work has fallen into the public domain on expiry of the term of copyright under Section 22 of the Copyright Act 1957 (author's lifetime + 60 years from the year following the author's death)."
prayer_clauses:
  - "(a) Dismiss the Plaint with costs;"
  - "(b) Vacate any ex-parte ad-interim order granted in the suit, the basis of the said order having been displaced by the defences set out above;"
  - "(c) Pass such further and other orders as this Hon'ble Court may deem fit and proper."
mandatory_exhibits:
  - evidence_of_the_defendants_purpose_of_use
  - evidence_of_attribution_given_to_the_author_or_publisher_where_applicable
  - evidence_of_the_quantum_and_proportion_of_matter_used_relative_to_the_whole_work
  - evidence_of_no_competing_use_or_market_substitution
  - any_third_party_or_public_domain_source_for_the_underlying_idea_or_facts
  - prior_publications_or_pre_dating_works_relevant_to_the_originality_challenge
  - assignment_chain_documents_where_Section_19_validity_is_challenged
accompanying_applications:
  - "I.A. under Order 39 Rule 4 CPC for vacating the ex-parte ad-interim order obtained by the Plaintiff (where applicable)"
  - "I.A. for damages on the Plaintiff's cross-undertaking where the ex-parte ad-interim order is vacated (where the Plaintiff furnished a cross-undertaking — the *Bajaj Auto* discipline applied)"
  - "I.A. for security for costs against the Plaintiff (where applicable)"
court_fee: "Process fee on the Written Statement as per the Court's table; no ad-valorem fee on the Written Statement itself"
```

## Section 52 sub-clause-mapping note

Each of the Section 52 sub-clauses applies to a discrete factual matrix. The Drafter pleads only those sub-clauses for which `case-facts.md` provides supporting facts. Bare invocation of Section 52 without sub-clause-specific particulars is fatal. The Drafter, supported by the Verifier, applies the *Civic Chandran* four-factor test where Section 52(1)(a) is invoked:

(i) the nature and purpose of the use
(ii) the quantum and value of the matter taken in relation to the whole
(iii) the possibility of competition with the original
(iv) the substantial harm to the copyright owner's market

## Section 19 cross-challenge

Where the Plaintiff's title derives from an assignment, the Defendant's Written Statement (a) challenges the Section 19 ingredients (writing, signature, identification of work, specification of rights, duration, territorial extent, royalty proviso), and (b) puts the Plaintiff to strict proof of each ingredient. A non-compliant assignment defeats the Plaintiff's standing.

## Copyright firewall reminder

The defence pleading recites *Moral Rights* (Section 57) and *Reversionary Interests* (proviso to Section 18(1)) — where applicable as a defence-side argument — in **statutory-only paraphrase**. No proprietary clause-prose is imported.
