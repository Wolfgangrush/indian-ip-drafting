---
name: copyright-infringement-suit-draft
description: Draft a civil suit for infringement of copyright under Section 51 read with Section 55 of the Copyright Act 1957. Jurisdictional anchor under Section 62 of the Copyright Act 1957 (plaintiff resides / carries on business / works for gain within the local limits of the court — displaces Section 20 CPC). For a copyright owner / exclusive licensee suing for infringement of a literary / dramatic / musical / artistic / cinematograph / sound-recording / software work. Encodes the Section 51 acts-constituting-infringement framework, the Section 55 civil remedies (injunction, damages, rendition of accounts, delivery-up of infringing copies), the Section 14 rights-conferred framework, the Section 17 first-ownership framework, the Section 18 / Section 19 assignment framework (statutory-only paraphrase per the Copyright firewall), the Section 22 term-of-copyright framework, and the Section 52 fair-dealing anticipation. Auto-fires on "draft copyright infringement suit", "draft Section 51 copyright suit", "draft copyright violation suit", and similar trigger phrases.
allowed-tools: Read, Write, Edit, Bash, Glob
---

# Copyright Infringement Suit Draft Skill

Extends: `${CLAUDE_PLUGIN_ROOT}/skills/_ip_drafting_base/SKILL.md`
Common rules: `${CLAUDE_PLUGIN_ROOT}/skills/_drafting_common/SKILL.md`

## Case-type metadata

```yaml
case_type_line: SUIT FOR PERMANENT INJUNCTION RESTRAINING INFRINGEMENT OF COPYRIGHT, DAMAGES OR RENDITION OF ACCOUNTS, DELIVERY-UP, AND COSTS UNDER SECTION 51 READ WITH SECTION 55 OF THE COPYRIGHT ACT 1957
case_short_code: COPYRIGHT_INFRINGEMENT_SUIT
case_number_prefix: CS (COMM) / CS (COMM.IPD) / CS (OS)
pleading_type: Plaint
typical_forum: District Court of competent pecuniary jurisdiction OR High Court Commercial Division OR High Court Intellectual Property Rights Division — Section 62 Copyright Act 1957 anchors jurisdiction at the place where the Plaintiff resides / carries on business / personally works for gain (displaces Section 20 CPC)
typical_parties: Plaintiff (copyright owner / exclusive licensee / assignee) + Defendant(s) (alleged infringer / publisher / distributor / online intermediary)
statutory_opening: "This suit is filed under Section 51 read with Section 55 and Section 62 of the Copyright Act 1957 read with the Code of Civil Procedure 1908, the Specific Relief Act 1963, and the Commercial Courts Act 2015, for permanent injunction restraining the Defendants from infringing the Plaintiff's copyright in the [Copyright Work], damages of Rs. ___ OR rendition of accounts of the Defendants' wrongful profits at the Plaintiff's election, delivery-up of all infringing copies for destruction / erasure, and costs."
ground_clauses:
  - "Subsistence of copyright — copyright subsists in the [Copyright Work] under Section 13 of the Copyright Act 1957 (literary / dramatic / musical / artistic / cinematograph / sound-recording / software work; original within the meaning of Section 13(1)(a) and the *modicum-of-creativity* test in *Eastern Book Company v. D.B. Modak* (2008) 1 SCC 1)."
  - "Ownership — the Plaintiff is the first owner of the copyright under Section 17 / the assignee under a Section 18 / 19 deed of assignment dated ____ (Exhibit ___) / the exclusive licensee under a deed dated ____ (Exhibit ___)."
  - "Infringement under Section 51 — the Defendants have, without the Plaintiff's licence, done or caused to be done acts that constitute exclusive rights of the Plaintiff under Section 14, namely reproduction / public performance / broadcast / communication to the public / adaptation / translation / distribution of copies — particulars set out in paragraphs ___ to ___ above and Exhibits ___ to ___."
  - "Jurisdiction — under Section 62 of the Copyright Act 1957 the Plaintiff is entitled to file this suit in this Hon'ble Court within whose local limits the Plaintiff resides / carries on business / personally works for gain — Section 62 displaces Section 20 CPC and the *IPRS v. Sanjay Dalia* (2015) 10 SCC 161 principal-place-of-business qualification is satisfied as set out in paragraph ___ above."
  - "Limitation — the suit is filed within 3 years of each continuing act of infringement (Article 113 of the Schedule to the Limitation Act 1963); each continuing act of infringement constitutes a fresh cause of action."
  - "Section 12A Commercial Courts Act 2015 exemption — urgent interim relief is contemplated and prayed for in this suit (Application No. ___ for ex-parte ad-interim injunction and appointment of Local Commissioner), pleading the exemption from pre-institution mediation under the *Patil Automation v. Rakheja Engineers* (2022) 10 SCC 1 framework."
prayer_clauses:
  - "(a) Pass a decree of permanent injunction restraining the Defendants, by themselves, their servants, agents, distributors, retailers, online intermediaries, and all persons claiming through them, from reproducing, publishing, distributing, communicating to the public, broadcasting, performing in public, adapting, translating, importing, or in any manner infringing the Plaintiff's copyright in the [Copyright Work] more particularly described at Exhibit ___;"
  - "(b) Pass a decree for damages of Rs. ___ OR direct the Defendants to render accounts of the wrongful profits earned from the infringing acts and decree the amount so ascertained in favour of the Plaintiff, at the Plaintiff's election;"
  - "(c) Pass a decree directing the Defendants to deliver up to the Plaintiff for destruction / erasure all infringing copies of the [Copyright Work] in their possession, custody, or control, including all plates / digital masters / source files;"
  - "(d) Pass a decree for costs of the suit;"
mandatory_exhibits:
  - copyright_registration_certificate_where_registered  # copyright subsists without registration per Section 13 read with Section 44 — registration is permissive
  - assignment_or_licence_deed_where_plaintiff_is_assignee_or_licensee  # Section 19 ingredients to be verified
  - evidence_of_first_publication_authorship
  - evidence_of_continuous_commercial_exploitation_of_the_work
  - infringing_copy_or_photograph_of_infringing_use
  - comparison_chart_showing_substantial_similarity  # for substantial-similarity analysis under R.G. Anand framework
  - cease_and_desist_correspondence_with_proof_of_service
  - damages_quantum_computation_or_evidence_of_defendants_profits
  - board_resolution_authorising_the_litigation_where_corporate_plaintiff
  - power_of_attorney_in_favour_of_the_authorised_signatory_where_applicable
accompanying_applications:
  - "I.A. under Order 39 Rules 1 and 2 CPC for interim injunction restraining the Defendants from the infringing acts pending the suit (with American Cyanamid / Gujarat Bottling three-limb pleading)"
  - "I.A. under Order 39 Rule 3 CPC for ex-parte ad-interim relief (with Order 39 Rule 3 first-proviso affidavit on why notice would defeat the purpose, the *Morgan Stanley Mutual Fund v. Kartick Das* (1994) 4 SCC 225 discipline)"
  - "I.A. under Order 26 Rules 9 and 10 CPC for appointment of Local Commissioner (where seizure of infringing stock / digital masters is sought)"
  - "I.A. under Order 39 Rules 1 and 2 read with Order 26 CPC for John Doe / Ashok Kumar order against unknown infringers (in cinematograph piracy / broadcast theft / software-piracy ring contexts) — *Taj Television v. Rajan Mandal* (2003) 26 PTC 627 (Del) framework"
  - "I.A. for exemption from pre-institution mediation under Section 12A Commercial Courts Act 2015 (urgent interim relief contemplated)"
court_fee: "Ad valorem under the applicable State Court-Fees Act on the damages quantum or as per the High Court Original Side Rules / IPD Rules Schedule (Delhi HC IPD Rules 2022 Schedule)"
```

## Section 62 jurisdiction-at-plaintiff note

Section 62 of the Copyright Act 1957 is a *suis generis* jurisdictional provision. It displaces Section 20 CPC and confers jurisdiction on the District Court within whose local limits the **Plaintiff** resides / carries on business / personally works for gain — irrespective of where the cause of action arose or where the Defendant resides. The *IPRS v. Sanjay Dalia* (2015) 10 SCC 161 qualification requires the Plaintiff to plead the **principal place of business** connection (not a subordinate office where the Plaintiff has its head office elsewhere).

## Section 52 fair-dealing anticipation

Every copyright infringement plaint must anticipate the Defendant's Section 52 fair-dealing defence. The Drafter, in the Grounds, pleads pre-emptively that the Defendant's use does not fall within any of the Section 52 sub-clauses (Section 52(1)(a) fair dealing for research / private use / criticism / review / news reporting / Section 52(1)(h) reproduction of judicial proceedings / Section 52(1)(i) educational use / Section 52(1)(za) / (zb) / (zc) intermediary safe harbours). The Drafter does not invent factual particulars — it adds the prophylactic ground based on `case-facts.md`.

## Copyright firewall reminder

References to *Moral Rights* (Section 57 CA — right of paternity / right of integrity) and *Reversionary Interests* (proviso to Section 18(1) CA — assignment of future work reverts on non-exercise within 1 year) are recited in **statutory-only paraphrase**. No proprietary clause-prose from any commentary or precedent collection is imported.

## Section 19 assignment-validity reminder (where Plaintiff is assignee)

Where the Plaintiff's title derives from an assignment under Section 18 of the Copyright Act 1957, the Drafter pleads — and the Verifier checks — that the assignment satisfies all the Section 19 ingredients:

(a) in writing
(b) signed by the assignor
(c) identifies the work
(d) specifies the rights assigned
(e) specifies the duration
(f) specifies the territorial extent
(g) (per the 2012 amendment) the second proviso to Section 19(3) on the author's right to share of royalties (where applicable)

A non-compliant assignment is voidable and may be challenged by the Defendant.

## Cross-references

For the interim-injunction application accompanying this plaint, see the `interim-injunction-application-ip-draft` skill. For a John Doe / Anton Piller application against unknown infringers (cinematograph piracy, software piracy, broadcast theft), see the `john-doe-anton-piller-order-application-draft` skill.
