# Resume Guide — How to Make It Shine

A short, durable checklist. Read it once before each application; trust it more than your gut on layout questions.

The goal is to **get an interview**. The reader spends 20–40 seconds on the first pass. Make every line earn its place.

---

## 1. Tailor every application

- Read the job description twice. Highlight the 5–8 words/phrases they repeat most.
- Mirror those words in your bullets and skills section. ATS systems and humans both scan for them.
- For each requirement they list, ask: *do I have a bullet that proves I've done this?* If not, write one.
- Don't send the same CV to two roles. Spend 20 minutes per application personalising.

## 2. Lead with impact

Every bullet has the shape: **Verb → what you did → measurable result**.

Bad: *Worked on remote-sensing classification.*
Good: *Trained a Random Forest classifier on Sentinel-1/2 imagery, reaching 92% overall accuracy across 10,000 km² of citrus orchards.*

The result is what gets you the interview. If you don't have a number, don't fake one — describe scale instead (study area, number of scenes processed, partners served, citations).

## 3. Quantify, quantify, quantify

Numbers to fish for in your work:
- Accuracy / precision / recall / kappa.
- Area covered (km², hectares).
- Volume (number of images, scenes, samples, stations).
- Time saved (pipeline reduced from N hours to M hours).
- People affected (institutions, farmers, decision-makers reached).
- Citations, conference acceptances.
- Funding amount, grant size.

If a paper has been cited 50+ times, say so.

## 4. ATS-safe formatting

Applicant Tracking Systems parse your PDF as plain text. Break the parser and your CV is invisible.

The templates in `academic/` and `industry/` are ATS-safe. **Don't add:**

- Photos of yourself.
- Tables for layout (single-column flow only).
- Two-column layouts.
- Text inside text-boxes, TikZ pictures, or graphics.
- Important content in headers/footers (parsers often miss this).
- Decorative fonts (we use Charter, which is text-extractable).
- Coloured backgrounds behind text.

If you're not sure your PDF is ATS-safe: open it in a plain text editor (or `pdftotext main.pdf -`) and read what comes out. That's what the ATS sees.

## 5. Length

- **Academic CV** — as long as needed. Full publication list. Multi-page is normal and expected.
- **Industry resume** — one page if you have <10 years post-PhD; two pages absolute maximum. Recruiters won't read page 3.
- **Cover letter** — one page. Always.

## 6. Section ordering

| Audience            | Order                                                                        |
| ------------------- | ---------------------------------------------------------------------------- |
| Academic            | Header → Research interests → Position → Education → Publications → Talks → Teaching → Awards → References |
| Industry (R&D)      | Header → Profile → Skills → Experience → Selected publications → Education |
| Industry (non-R&D)  | Header → Profile → Skills → Experience → Education (publications optional)   |

Put what they care about most in the top third of page 1 — that's the prime real estate.

## 7. UK / EU conventions

Don't include any of these — they invite bias and aren't expected:
- Photo
- Date of birth or age
- Marital status
- Nationality (unless visa status is genuinely relevant — then say "Right to work in the UK" or similar)
- Home address (city is fine — "Leeds, UK" — full address isn't)

Do include:
- Phone (optional but helpful)
- Email
- LinkedIn / personal site / Scholar / ORCID
- City + country

## 8. Action verbs bank

Use these to start bullets. Vary them — don't open every bullet with "Developed".

**Built / created:** Built, Designed, Developed, Engineered, Implemented, Authored, Architected, Prototyped.
**Analysed:** Analysed, Evaluated, Modelled, Quantified, Validated, Measured, Benchmarked, Investigated.
**Improved:** Optimised, Reduced, Accelerated, Streamlined, Automated, Refined, Increased.
**Led:** Led, Coordinated, Supervised, Mentored, Trained, Directed, Organised.
**Domain (EO/ML):** Trained, Classified, Mapped, Retrieved, Detected, Segmented, Calibrated, Deployed.

## 9. What to cut

These phrases add nothing — replace them with concrete evidence or delete:

- "Responsible for…" → just say what you did.
- "Duties included…" → same.
- "Team player" / "hard worker" / "passionate" → show, don't tell.
- "Excellent communication skills" → your CV either reads well or it doesn't.
- "Familiar with X" → if you're only familiar, leave it out; mention only what you're competent in.
- "Various / multiple / several" → name them or quantify them.
- Hobbies, unless genuinely relevant or interesting.

## 10. Cover letter — rule of three

One page, three paragraphs:

1. **Hook.** Why this specific role and this specific organisation. One sentence proving you've actually read about them — a paper they published, a product they shipped, a mission you align with.
2. **Evidence.** Three bullets or three short claims, each matching one of their top requirements. Each backed by a result.
3. **Close.** A specific ask ("I'd welcome a conversation about how the iSPARK methods could extend to the X programme"), then sign off.

## 11. Working with this repo

- Don't edit the canonical `academic/main.tex` or `industry/main.tex` for a specific application. Instead:
  ```
  cp -r cv/industry cv/applications/my-target-role
  ```
  and edit there. Treat the templates as the master copy.
- Update `cv/academic/publications.bib` AND `cv/industry/publications.bib` whenever a new paper is accepted (keep them identical — `cp` from one to the other).
- Keep the website (`index.html`) in sync with the bibs. They are all your public record.

## 12. Final checklist before sending

- [ ] Tailored to the JD's vocabulary.
- [ ] Every bullet has a verb and a result (or a measurable scale).
- [ ] No typos. Read it out loud once.
- [ ] No widows/orphans, no awkward page breaks.
- [ ] PDF text is selectable (try copying a paragraph — if it pastes as garbage, the layout is broken).
- [ ] Filename is professional: `Amal_Chakhar_CV.pdf`, not `cv_v17_FINAL_FINAL.pdf`.
- [ ] Industry resume fits on one page.
- [ ] Cover letter named after you and the role: `Amal_Chakhar_Cover_Letter_<Org>.pdf`.
