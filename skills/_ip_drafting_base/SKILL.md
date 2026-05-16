---
name: _ip_drafting_base
description: Universal Indian intellectual-property pleading skeleton. Shared base for all 10 case-type drafting skills. Holds the standard structure (Cause Title -> Parties block -> Statutory Opening -> Prelude -> Facts -> Grounds -> Prayer -> Verification -> Affidavit-in-support -> Index -> List of Documents -> accompanying applications including Order 39 Rules 1 and 2 interim injunction and John Doe / Anton Piller / Ashok Kumar order applications). NOT invoked directly — extended by every case-type skill in this plugin. Appellate-forum nomenclature is locked to the High Court Intellectual Property Rights Division per the Tribunals Reforms Act 2021 (Sections 12 to 14) — every reference to the erstwhile IPAB as a present-day forum is re-routed.
allowed-tools: Read
---

# `_ip_drafting_base` — universal Indian IP pleading skeleton

This base skill defines the **structural shape** of any intellectual-property litigation pleading drafted by the plugin. Case-type skills extend this base with case-type-specific statutory openings, fact-sequences, grounds, prayer clauses, and accompanying applications.

## Universal skeleton

```
1. CAUSE TITLE
   {{forum.name}} {{forum.division}}
   {{case_type.case_number_prefix}} No. ____ of {{year}}

   {{party_block_template}}
   {{plaintiff_or_petitioner_party}} ... {{plaintiff_role}}
                                  Versus
   {{defendant_or_respondent_party}} ... {{defendant_role}}

2. STATUTORY OPENING
   {{case_type.statutory_opening}}

3. PRELUDE
   (Short paragraph identifying the Plaintiff's status — copyright owner /
   exclusive licensee / registered trade mark proprietor / common-law
   user / patentee / exclusive patent licensee / registered design
   proprietor / aggrieved person under Section 57 TMA / person
   interested under Section 64 PA — with the authorisation reference
   (Board Resolution / Power-of-Attorney) and the registration / first
   use / priority particulars.)

4. FACTS (numbered narrative paragraphs)
   4.1 Plaintiff's title to the intellectual-property right — date of
       creation / adoption / first publication / first use / filing /
       registration / priority / grant. Status of registration:
       granted / pending / opposed / removed (refer Exhibit /
       Annexure A — registration certificate).
   4.2 Continuous use and renewals (where applicable) — periodic
       renewals (TM Section 25 / Design Section 11) / payment of
       annuities (Patent Section 53) / continuous publication /
       commercial exploitation (refer Exhibit / Annexure B).
   4.3 Build-up of goodwill / reputation / commercial success — sales
       figures, advertising spend, market presence, trade recognition,
       awards, media coverage (refer Exhibit / Annexure C).
   4.4 Defendant's infringing acts — date of first knowledge by the
       Plaintiff, nature of infringement (reproduction / public
       performance / broadcast / counterfeit / use of deceptively
       similar mark / use of identical or similar mark in respect of
       identical or similar goods / making / using / selling / offering
       for sale / importing / colourable imitation), channel of
       infringement (online / retail / wholesale / distribution),
       scale and geographic extent (refer Exhibit / Annexure D —
       infringing-product photographs / packaging / promotional
       material).
   4.5 Comparison of the infringing matter with the Plaintiff's right —
       deceptive similarity (TM / passing-off) / substantial
       similarity (copyright) / claim-by-claim infringement chart
       (patent) / fraudulent or obvious imitation (design) (refer
       Exhibit / Annexure E — comparison chart in Markman or
       equivalent format).
   4.6 Plaintiff's cease-and-desist / notice correspondence and the
       Defendant's response (or absence of response) (refer Exhibit /
       Annexure F).
   4.7 Damages / quantum of loss / Defendant's profits — Plaintiff's
       lost sales, Defendant's wrongful gains, computation
       methodology (refer Exhibit / Annexure G).
   4.8 Urgent interim relief — facts establishing the irreparable
       injury / threat of evidence destruction warranting ex-parte
       ad-interim orders (where claimed); compliance with or
       exemption from Section 12A Commercial Courts Act 2015
       pre-institution mediation (the *Patil Automation v. Rakheja
       Engineers* (2022) 10 SCC 1 framework — urgent interim
       relief in body and prayer = Section 12A exemption).
   4.9 Limitation — applicable Article of the Limitation Act 1963,
       date of accrual / each continuing act, date of filing, days
       within limitation.
   4.10 Jurisdiction — territorial jurisdiction of the Court, with
        statutory anchor:
        - Copyright: Section 62 Copyright Act 1957 (plaintiff
          resides / carries on business)
        - Trade mark: Section 134 Trade Marks Act 1999 (plaintiff
          resides / carries on business; *IPRS v. Sanjay Dalia*
          principal-place-of-business qualification)
        - Patent: Section 104 Patents Act 1970 (District Court /
          High Court on counter-claim for revocation)
        - Design: Section 22(4) Designs Act 2000 (District Judge
          or above; High Court on counter-claim for cancellation)
        - Passing-off (pure): Section 20 CPC 1908
        - Rectification (Section 57 TMA) / Revocation (Section 64
          PA): High Court Intellectual Property Rights Division
          per Sections 12 to 14 Tribunals Reforms Act 2021
   4.11 Court fee / filing fee — amount + applicable rule (State
        Court-Fees Act / High Court Original Side Rules / IPD Rules
        Schedule where applicable).

5. GROUNDS (numbered)
   5.1 {{case_type.ground_1}}
   5.2 {{case_type.ground_2}}
   5.3 {{case_type.ground_3}}
   ...
   (Grounds anchor each prayer clause; every ground cites the
    operative provision and the document supporting the ground.)

6. PRAYER
   {{case_type.prayer_clauses}}

   And for such further and other reliefs as this Hon'ble Court may
   deem fit and proper.

7. VERIFICATION
   I, [Name of Authorised Signatory], being the duly authorised
   signatory of the Plaintiff / Petitioner / Applicant, do hereby
   verify that the contents of paragraphs ___ to ___ of the
   {{case_type.pleading_type}} are true to my personal knowledge and
   the contents of paragraphs ___ to ___ are true on the basis of
   information received and believed to be true. No part of this
   verification is false and nothing material has been concealed
   therefrom.

   Verified at [Place] on this __ day of [Month, Year].

                                       [Authorised Signatory]
                                       [Designation]
                                       [Plaintiff Party]

8. AFFIDAVIT-IN-SUPPORT
   I, [Name of Authorised Signatory], aged ___ years, occupation
   [Designation], having office at [Address], do hereby solemnly
   affirm on oath and state as under:
   1. That I am the duly authorised signatory of the Plaintiff /
      Petitioner / Applicant herein under Board Resolution dated
      ____ (Exhibit / Annexure ___), and am acquainted with the
      facts and circumstances of the case from the records maintained
      by the Plaintiff in the ordinary course of business.
   2. That I have read and understood the contents of the
      {{case_type.pleading_type}} comprising paragraphs 1 to ___ and
      the same are true and correct.
   3. That the documents annexed are true copies / certified true
      copies / true print-outs of the originals available with the
      Plaintiff.
   4. (Where ex-parte ad-interim relief is sought:) That the
      circumstances set out in paragraphs ___ to ___ above
      establish that the object of granting the injunction would
      be defeated by delay, and that this Hon'ble Court may be
      pleased to grant ex-parte ad-interim relief under the first
      proviso to Order 39 Rule 3 of the Code of Civil Procedure
      1908 read with the framework of *Morgan Stanley Mutual Fund
      v. Kartick Das* (1994) 4 SCC 225.

   Affirmed at [Place] on this __ day of [Month, Year].

                                       [Authorised Signatory]
                                       [Designation]

   Solemnly affirmed before me on solemn affirmation under the
   Bharatiya Sakshya Adhiniyam 2023.

                                       [Notary Public / Oath
                                        Commissioner / Court
                                        Officer]

9. INDEX
   (Running paragraph-anchored index — paragraph numbers, content
   summary, exhibit references.)

10. LIST OF DOCUMENTS / EXHIBITS / ANNEXURES
    Exhibit / Annexure A — Registration certificate of the
                          intellectual-property right
    Exhibit / Annexure B — Renewal certificate(s) / annuity-payment
                          receipts / proof of continuous use
    Exhibit / Annexure C — Evidence of goodwill / reputation
                          (sales figures, advertising spend,
                          press coverage, awards)
    Exhibit / Annexure D — Infringing-product photographs /
                          packaging / promotional material /
                          marketing collateral
    Exhibit / Annexure E — Comparison chart (deceptive similarity /
                          substantial similarity / claim-by-claim
                          infringement chart / fraudulent imitation)
    Exhibit / Annexure F — Cease-and-desist correspondence with
                          proof of service and the Defendant's
                          response
    Exhibit / Annexure G — Damages / loss / profits computation
    Exhibit / Annexure H — Board Resolution authorising the
                          litigation
    Exhibit / Annexure I — Power-of-Attorney in favour of the
                          authorised signatory (where applicable)
    ... (further case-type-specific exhibits)

11. ACCOMPANYING APPLICATIONS
    {{case_type.accompanying_applications}}
    (Common examples: Application under Order 39 Rules 1 and 2 CPC
    for interim injunction; Application under Order 39 Rule 1 and 2
    read with Order 26 Rules 9 and 10 CPC for John Doe / Ashok
    Kumar / Anton Piller order with appointment of Local
    Commissioner; Application for ex-parte ad-interim relief under
    Order 39 Rule 3 CPC; Application for damages / rendition-of-
    accounts inquiry; Application for delivery-up under Section 55
    CA / Section 135 TMA / Section 108 PA / Section 22 DA;
    Application for condonation of delay under Section 5
    Limitation Act 1963; Application for exemption from filing
    pre-institution mediation compliance under Section 12A
    Commercial Courts Act 2015 where urgent interim relief is
    contemplated.)
```

## Forum nomenclature lock (post-IPAB-abolition)

All rectification (Section 57 TMA) and revocation (Section 64 PA) pleadings carry the Cause Title of the **High Court Intellectual Property Rights Division** (Delhi / Madras / Calcutta / Bombay where constituted; the High Court of competent jurisdiction otherwise). Any case-config attempting to invoke the IPAB as a live forum is flagged and re-routed — the IPAB stands abolished by the Tribunals Reforms Act 2021 (Sections 12 to 14).

## Statute references the plugin handles

- Copyright Act 1957 (Sections 13, 14, 17, 18, 19, 22, 26, 30, 31, 31A, 31B, 31D, 38, 51, 52, 55, 57, 62, 63 to 70)
- Copyright Rules 2013
- Trade Marks Act 1999 (Sections 9, 11, 12, 27, 28, 29, 30, 31, 33, 34, 35, 47, 57, 124, 134, 135, 142)
- Trade Marks Rules 2017
- Patents Act 1970 as amended by the Patents (Amendment) Act 2005 (Sections 3, 8, 10, 48, 53, 60, 64, 84, 92, 100, 104, 107, 107A, 108, 117A, 117G)
- Patents Rules 2003 as amended
- Designs Act 2000 (Sections 2, 4, 11, 19, 22)
- Designs Rules 2001 as amended
- Tribunals Reforms Act 2021 (Sections 12 to 14 — IPAB abolition and transfer)
- Commercial Courts Act 2015 (Sections 12A, 13, and Schedule of fees)
- Commercial Courts (Pre-Institution Mediation and Settlement) Rules 2018
- Delhi High Court Intellectual Property Rights Division Rules 2022
- Madras High Court Intellectual Property Rights Division Rules
- Code of Civil Procedure 1908 (Order 7, Order 26 Rules 9 and 10, Order 38, Order 39 Rules 1, 2, 3, 3A, 4)
- Specific Relief Act 1963 (Sections 36 to 42 — perpetual injunction)
- Bharatiya Nagarik Suraksha Sanhita 2023 (Section 223 — ancillary criminal-copyright references)
- Bharatiya Sakshya Adhiniyam 2023 (Sections 63 — electronic evidence; 132 — advocate-client privilege)
- Limitation Act 1963 (Schedule I — Article 75 / Article 113)
- Indian Contract Act 1872 (Sections 124 — 147 on indemnity, guarantee, surety where ancillary)
- Information Technology Act 2000 (Sections 79 — intermediary safe harbour, where digital infringement)
- Companies Act 2013 (where corporate-defendant directorial joinder)
- applicable State Court-Fees Acts
