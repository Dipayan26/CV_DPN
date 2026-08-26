# CV Improvement Plan — Assistant Professor Recruitment

Working checklist for turning `CV_DPN.tex` from a tight 2-page CV into a full
academic CV suitable for Assistant Professor selection committees (UGC-style
scoring proformas, Indian universities).

**Status legend:** `[ ]` to do · `[~]` needs info from me · `[x]` done

---

## 0. The framing change

- [ ] **Stop enforcing the 2-page limit.** The 2-page rule is an *industry*
      convention. Academic CVs for faculty recruitment run 4–8 pages, and
      brevity actively hurts — anything not listed scores zero.
- [ ] Keep the tight 2-page version on the `industry_cv` branch; let the
      academic version grow.
- [ ] **Before finalizing:** pull the scoring proforma from the actual
      advertisement. Committees often score strictly by proforma row, so every
      scored row should have a matching CV heading. This varies by university
      and by state.

---

## 1. Highest priority — the biggest gap

### Teaching & Mentoring (section does not exist)

This is the single most damaging omission. It is a **teaching** post and the CV
currently contains zero teaching evidence.

- [ ] Create a `Teaching & Mentoring` section.
- [~] List lab/practical demonstration for B.Sc./M.Sc. batches — course name,
      level, semester, batch size, hours.
- [~] List tutorials, guest lectures, seminar sessions delivered.
- [~] List M.Sc. dissertation students supervised or co-supervised (names,
      year, project title).
- [~] List workshop / hands-on sessions taught (e.g. demos of the web tools).
- [ ] **Koushik Bardhan** is a co-author on Deep-Interact Studio — if he was a
      student I mentored, state that explicitly. Supervision experience is scored.

---

## 2. Missing sections that recruitment proformas score

- [x] **Fellowships** — section added to `CV_DPN.tex`, placed above
      Awards & Certificates. *Was* buried inside a Grants description line.
      - [x] Collapsed to a **single** CSIR-UGC JRF entry, dated 2021 to match
        the NET qualification. The inferred SRF dates were dropped, so there is
        nothing left to verify here.
      - [ ] **Resolve duplication (now near-verbatim).** CSIR-NET JRF + AIR 216
        + June 2021 appears in *both* Fellowships and Awards, four lines apart
        on page 2. Pick one:
        - **A** — delete the Awards line, leaving GATE alone there.
        - **B** *(recommended)* — reframe Awards as eligibility:
          "CSIR-UGC NET qualified in Life Sciences (June 2021) — eligibility for
          Assistant Professor under UGC regulations". Each heading then does
          distinct work: Fellowships = funding won, Awards = statutory hiring
          condition met.
- [~] **Workshops / FDPs / Refresher & Orientation courses** — list everything
      attended with dates and organizers. Directly scored in most API proformas.
- [~] **Professional Memberships** — societies (ISCB, BIOCLUES, Indian Science
      Congress, etc.).
- [~] **Academic Service** — journal peer reviews (even one), session chairing,
      organizing committee roles.
- [~] **References / Referees** — 2–3 with designation, affiliation, email.
      Indian applications routinely require these; currently absent entirely.

---

## 3. Improve existing sections

### Publications

- [ ] **Split into `Peer-Reviewed Publications` and `Preprints (Under Review)`.**
      Currently 1 journal article + 3 bioRxiv preprints sit under one heading.
      Splitting is more honest *and* more favorable — "under review" signals an
      active pipeline.
- [ ] **Add volume/issue to AttnSeq-PPI** — verified against Crossref:
      `1874(1), 141102`. Currently only the article number is listed.
- [~] **Decide the AttnSeq-PPI year: 2025 or 2026.** Crossref says
      `published: 2026-01`, `published-print: 2026-01`, journal issue 1. The
      record was *created* 2025-10-25 (online-first), which is where 2025 and
      the `j.bbapap.2025` DOI slug come from. The citable year of record is
      **2026**. Ordering is unaffected either way.
- [ ] **Add indexing + impact factor** to the BBA paper (SCIE-indexed). Indian
      committees score indexed journals differently, and some proformas award
      marks by impact factor. Nothing currently signals this.
- [ ] **State author position.** First author on all 4 — consider noting
      "First author on 4 of 5 publications" in the summary. First-authorship is
      a distinct scoring criterion.
- [ ] Add corresponding-author markers if applicable.

### Metrics

- [~] **Add citation metrics near the top:**
      `Citations: N · h-index: N (Google Scholar, <month year>)`.
      The Scholar link is there but the numbers are not — committees want them
      without clicking.

### Education

- [ ] **State the formal PhD thesis title.** Currently only "Focus: …".

### Awards

- [ ] **Make NET eligibility unmissable.** CSIR-NET JRF (AIR 216) is not merely
      an award — under UGC regulations it is the *statutory eligibility
      condition* for an Assistant Professor post. Flag it as eligibility, not
      just an honour.

### Talks & Presentations

- [~] Add any posters from earlier in the PhD, tagged "Poster". A single-entry
      section invites the question of whether I present often.
- [~] Confirm: was SARANSH a presentation *competition* I placed in? If so it
      belongs under Awards, which is a stronger signal than a talk.

---

## 4. Structural reordering (academic convention)

Current order is industry-flavoured (Work Experience before Education).
Target order:

1. Research Summary / Research Interests
2. **Education**
3. Research Experience
4. **Peer-Reviewed Publications**
5. **Preprints**
6. **Teaching & Mentoring**
7. Grants, Fellowships & Computing Resources
8. Awards & Certificates
9. Talks & Presentations
10. Research Software Developed
11. **Academic Service**
12. **Professional Memberships**
13. Technical Skills
14. **References**

- [ ] Move Education above Work Experience.
- [ ] Move Skills and Software lower — publications and teaching outrank tooling
      for AP recruitment.
- [ ] Consider adding a short **Research Interests** keyword line so committees
      can slot me into a specialization quickly.
- [ ] Consider renaming `Software & Tools` → `Research Software Developed`, and
      note usage/users if any.

---

## 5. Keep exactly as-is

- **Software & Tools with live URLs** — a genuine differentiator. Most
  bioinformatics applicants have papers but no deployed, working tools.
- **IndiaAI Compute Initiative + Google TRC awards** — demonstrate ability to
  attract resources; early evidence of grant-worthiness.

---

## 6. Optional / by convention

- [~] Some Indian universities expect personal details on the CV: DOB,
      nationality, gender, category, languages known, permanent address. Check
      the advertisement; include only if asked.
- [ ] Prepare separately (not CV content): teaching statement, research
      statement — commonly required alongside the application.
*