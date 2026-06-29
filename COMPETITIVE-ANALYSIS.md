# Competitive + Improvement Analysis — `open-pictograms`

> Scope: an openly-licensed (CC-BY-4.0) pictogram/symbol set for AAC, Easy Read, low-literacy /
> cross-language communication, and wayfinding. Analysis grounded in web research with cited
> sources. Reviewed against `PLAN.md` (v0.1.0, 2026-06-28) and `TASKS.md`.

---

## 1. Correctness & completeness review of PLAN.md

The plan is unusually strong for a draft. It already does the things most icon projects skip:
it makes **comprehension a release gate** (ISO 9186), it correctly identifies the **license trap**
that defines the whole category, and it is honest about the **unsecured partner/beneficiary
channel**. Below are the substantive findings, ordered by importance.

**A. The license value-prop is correct and is the single most important thing the plan gets right.**
The plan's central thesis — that the dominant *open* set (ARASAAC) is **CC-BY-NC-SA**, and that
NC + SA together block frictionless reuse in commercial/mixed AAC tools and derivatives — is
factually accurate and is the real, defensible gap (see §2). ARASAAC is CC-BY-NC-SA
([ARASAAC via Global Symbols](https://globalsymbols.com/symbolsets/arasaac?locale=en);
[OpenAssistive](https://openassistive.org/item/arasaacpictograms/)); Mulberry is CC-BY-SA
([mulberrysymbols.org](https://mulberrysymbols.org/)); Sclera is **CC-BY-NC** and explicitly
requires a signed agreement for any commercial use
([sclera.be/copyright](https://www.sclera.be/en/picto/copyright)); OpenMoji is CC-BY-SA
([openmoji.org/faq](https://openmoji.org/faq/)). A genuinely permissive (CC-BY-4.0, or CC0) set is
**not currently available at scale** in this category. This is the plan's strongest foundation and
should be stated even more loudly than it is.

**B. AAC efficacy / co-design with AAC users + SLPs is under-specified relative to its importance.**
The plan commits to ISO 9186 comprehension testing — good, and correctly the headline gate. But
ISO 9186 tests *whether a symbol communicates its referent to a general/target population*; it is
**not the same as AAC efficacy**, which concerns whether a symbol set, organized into a board,
supports *expressive language generation* by a non-speaking person (iconicity for the user,
learnability, motor/visual access, core-vs-fringe balance, internal consistency of a visual
"grammar"). The plan should explicitly:
  - Add **co-design with AAC users and SLPs/AAC specialists** as a named role and gate (it lists
    "beneficiary validators" and "cultural reviewers" but no AAC/SLP clinical reviewer). Current
    best practice in the field is participatory design *with* AAC users, not testing *on* them.
  - Distinguish **comprehension (does it read as X?)** from **AAC iconicity/learnability (can a
    user find and use it to say X in connected speech?)** — these need different evidence.
  - Reference a **published AAC core-vocabulary frame** as the anchor (the plan flags this as an
    open question but M1 already promises "an AAC core set" — the dependency should be resolved
    before drawing fans out, or the seed set risks being fringe-heavy).

**C. Visual grammar / consistency is named but thin.** The plan has a strong *style* lint (grid,
stroke, palette) but consistency in AAC is also **semantic/compositional**: consistent ways to show
plural, negation/"not", tense/time, possession, question, and consistent figure/skin/clothing
conventions so that a user generalizes. Proprietary sets win partly on this systematic visual
grammar. Recommend a "visual grammar" section in the design system (how negation, plurality,
person, and category-color are encoded), not just stroke/grid lint.

**D. Cultural inclusivity (skin tone, context) is present but should be operationalized.** The plan
mandates cultural review and regional/directional variants — correct. But it does not state a
**skin-tone / figure policy**. Proprietary SymbolStix and PCS, and OpenMoji, ship skin-tone and
figure-diversity variants; ARASAAC offers skin-tone and hair customization via its API. The plan
should decide: neutral non-human/abstracted figures (Bliss/Sclera-style) vs. realistic figures with
selectable skin tones (the modern AAC expectation). This is a load-bearing design decision, not a
detail, and it interacts with the "dignity" guardrail.

**E. Multilingual labels — methodology is right, scope is modest.** "Fluent human reviewer, never
raw MT; symbol must work without the label" is exactly correct (ARASAAC ships ~17+ language label
sets; this is table stakes, not a differentiator). Targets (≥3 languages) are honest but small;
the differentiator must be *quality + provenance per label + RTL handling*, not language count,
where ARASAAC dominates.

**F. Coverage / core vocabulary — the plan correctly demotes count, but lacks a concept-list anchor.**
"Depth + testing beats breadth" is the right posture given ARASAAC's ~13k+ symbols
([ARASAAC](https://arasaac.org/pictograms/search?tab=1)). But "100 then 300 symbols" only delivers
value if those 300 are the *right* 300 (a real AAC core board + one facility's wayfinding
inventory). Recommend committing to a named core-word list and a named facility wayfinding
inventory as an M0 exit artifact (currently an open question).

**G. Accessibility of the SVGs themselves** (`<title>`/`role="img"`, monochrome/high-contrast,
RTL/mirror variants) is well handled — a genuine strength most sets ignore.

**H. Scope vs `easy-read-plus`.** The boundary is slightly fuzzy: Easy Read is
text-simplified-plus-images; this project is the *image layer*. The plan names `easy-read-plus` as a
consumer (good) but should state explicitly that `open-pictograms` ships the **symbol + metadata**
and Easy Read document assembly lives in the sibling — otherwise both projects will drift into
producing "illustrated simple documents."

**I. Smaller corrections.**
  - ISO 9186 threshold framing is accurate (~66.7% / two-thirds general acceptance is the
    conventional bar; [ISO 9186-1](https://www.iso.org/standard/59226.html)), but cite that the
    66% figure is itself contested as *too low* for high-stakes wayfinding — supports the plan's
    stricter safety bar.
  - The plan adopts ANSI Z535.3 / ISO 3864-3 for the safety subset (≥85% + <5% critical
    confusion) — reasonable, but ANSI Z535.3's own criterion is ≥85% correct **with ≤5%
    opposite/critical confusion**; the plan states this correctly. Keep it.
  - "Optional icon font" — for AAC/wayfinding, an icon *font* is low-value and adds build
    complexity (monochrome-only, single-color, no metadata). The plan already flags this as an
    open question; recommend **dropping the font** in favor of SVG + PNG + OBF.
  - `interopRefs` should name a concrete scheme: **Concept Coding Framework (CCF) / BCI Bliss
    reference numbers / Global Symbols concept IDs** — currently vague.

---

## 2. Competitive landscape (researched, with sources)

| Set | License | Scale / scope | Strengths | Weaknesses |
|---|---|---|---|---|
| **ARASAAC** | **CC-BY-NC-SA** | ~13k–18k symbols, color + B/W, ~17+ language label sets, API w/ skin-tone & customization | The dominant *open* AAC set; huge coverage; multilingual; active gov-funded maintenance (Govt of Aragón); ecosystem default | **NC blocks commercial/mixed reuse; SA forces derivatives to copy the license** — exactly the reuse friction this project targets. Style is illustrative/variable. |
| **Mulberry Symbols** | **CC-BY-SA 2.0 UK** | ~3.9k SVG, adult-oriented | Clean SVG, designed for adults (not childish), genuinely libre, on Global Symbols & GitHub | **SA (copyleft)**; smaller coverage; UK-centric; limited multilingual depth |
| **Sclera** | **CC-BY-NC** (commercial needs signed agreement) | ~4.8k–11k high-contrast white-on-black | Excellent high-contrast/low-vision & print legibility; free for education | **NC + signed commercial agreement**; austere B/W style; Dutch-origin; limited color/multilingual |
| **Blissymbols (BCI)** | BCI holds **exclusive license**; not openly licensed for free derivative reuse | ~5k symbol-words, a true semantic language | Compositional *visual grammar* (the gold standard for systematic meaning-building); ISO/Unicode work | Steep learning curve; controlled by BCI; **not permissively open**; not pictographic/iconic for novices |
| **OpenMoji** | **CC-BY-SA 4.0** | ~4k+ emoji | Beautiful, consistent system, SVG/PNG/font, skin tones, open | **SA**; *emoji*, not AAC vocabulary (no "toilet/help/I want"); not comprehension-tested for AAC |
| **Widgit (WLS)** | **Proprietary, licensed** | ~20k+, schematic | Strong systematic visual grammar; clinical adoption; multilingual | **Paid/closed**; license fees; not reusable in open tools ([widgit.com/licensing](https://www.widgit.com/symbol-services/licensing.htm)) |
| **PCS (Mayer-Johnson / Tobii Dynavox)** | **Proprietary, licensed** | ~45k+ | Market-leading clinical familiarity; huge library | **Paid/closed**; per-seat licensing; reuse forbidden |
| **SymbolStix (n2y / Everway)** | **Proprietary, licensed** | ~40k+ | Lively figures, skin-tone/diversity, frequent updates | **Paid/closed**; ~$250 CAD/yr-class app licensing ([AT HelpDesk](https://athelpdesk.org/symbolstix-prime-an-aac-app/)) |
| **Global Symbols** | Aggregator (hosts many licenses) | Portal + Board Builder + OBF export | The **distribution hub & interop layer**; multilingual dictionary; not a competitor but the channel ([globalsymbols.com/about](https://globalsymbols.com/about?locale=en)) | Hosts others' sets; quality/style varies by set; not itself a consistent designed set |
| **Noun Project** | CC-BY **or** paid royalty-free | ~5M+ icons | Massive coverage, search | **UI icons, not AAC**; mixed per-icon licensing; not comprehension-tested ([thenounproject pricing](https://thenounproject.com/pricing/)) |
| **Cboard / OpenAAC apps** | App = open (OBF) | Consumers, not symbol sets | **The interoperability target**: OBF-consuming open AAC apps ([openboardformat.org](https://www.openboardformat.org/)) | Not symbol producers — they need a good open set; this is our channel, not rival |

**The structural picture:** the category splits into **(a) proprietary, clinically-dominant,
systematic, paid** (PCS, SymbolStix, Widgit) and **(b) open but copyleft/NC** (ARASAAC, Mulberry,
Sclera, OpenMoji). **No set occupies "open *and* permissive (CC-BY/CC0) *and* comprehension-tested
*and* stylistically consistent."** That empty quadrant is the entire opportunity.

Sources: [ARASAAC](https://globalsymbols.com/symbolsets/arasaac?locale=en) ·
[Mulberry](https://mulberrysymbols.org/) · [Sclera license](https://www.sclera.be/en/picto/copyright) ·
[Blissymbolics](https://www.blissymbolics.org/) · [OpenMoji FAQ](https://openmoji.org/faq/) ·
[Widgit licensing](https://www.widgit.com/symbol-services/licensing.htm) ·
[SymbolStix Prime pricing](https://athelpdesk.org/symbolstix-prime-an-aac-app/) ·
[Global Symbols](https://globalsymbols.com/about?locale=en) · [OpenBoardFormat](https://www.openboardformat.org/) ·
[OpenAAC symbol libraries](https://www.openaac.org/symbols.html) · [Noun Project](https://thenounproject.com/pricing/).

---

## 3. Gaps we can fill

1. **The permissive-license gap (primary).** A CC-BY-4.0 (or CC0) set usable in *commercial and
   open* AAC tools, signage vendors, OER, and humanitarian print without NC/SA entanglement.
   Nothing at scale fills this today.
2. **Comprehension-evidence gap.** Almost no open set ships **per-symbol, reproducible
   comprehension scores** (method, n, population, correct%, critical-confusion%). Shipping
   *evidence* as metadata is a category-first.
3. **Consistency gap among open sets.** Open sets (especially aggregated ones on Global Symbols)
   vary in style; a single, documented design system + automated style-lint is rare in the open
   world. (Mulberry is consistent but small/UK; OpenMoji is consistent but emoji.)
4. **Safety-aligned-but-honest gap.** A small, expert-reviewed, *disclaimered* safety subset that
   aligns to AIGA/DOT (public domain) + ISO 7010/7001/GHS *concepts* — most open sets either avoid
   safety or include unvetted hazard icons.
5. **Curation/coverage gap vs ARASAAC's sprawl.** ARASAAC's strength (13k+) is also a weakness:
   it's a sprawling, inconsistently-styled, NC library. A **tightly curated, tested, permissive
   "core that actually works"** beats a giant untested catalog for first-time deployers.
6. **Provenance & interop metadata gap.** Per-symbol originality attestation + interop refs (CCF /
   Global Symbols IDs) + cultural-review status — auditable quality most sets lack.

---

## 4. Differentiators to win (vs ARASAAC, the dominant open set)

ARASAAC wins on **coverage, multilingual labels, and incumbency**. We will not out-scale it; we
out-*license*, out-*evidence*, and out-*consistency* it:

1. **License: CC-BY-4.0 (or CC0).** The one thing ARASAAC structurally *cannot* do without
   re-licensing 13k symbols. This is the durable moat — it unlocks commercial AAC apps, signage
   vendors, and downstream derivatives that ARASAAC's NC/SA forbids.
2. **Comprehension evidence as a shipped artifact.** "Every symbol carries a reproducible
   comprehension score" is a claim no major open set makes. Trust through evidence, not volume.
3. **One documented design system + machine-enforced consistency.** A facility can mix
   communication + wayfinding symbols coherently; ARASAAC's style is illustrative and variable.
4. **Co-designed with AAC users + SLPs and culturally reviewed.** Lead with *process integrity*
   (participatory design, dignity review, skin-tone policy) as a quality signal.
5. **Interop-native (OBF + Global Symbols + CCF refs).** Be born into the open ecosystem ARASAAC,
   Mulberry, and Cboard already share — frictionless adoption path.
6. **Honest safety subset + "not certified / not advice" discipline** — a differentiator of
   *trustworthiness* vs. sets that ship unvetted hazard icons.

**Positioning line:** *"The open symbol set you can actually reuse — permissively licensed,
comprehension-tested, and consistent — co-designed with the people who use it."*

---

## 5. Claude API leverage — and the hard limits

**Where Claude adds real leverage (text/metadata/analysis, never the artwork or the verdict):**

1. **Vocabulary-coverage & gap analysis.** Compare a draft concept list against published AAC
   core-word lists and an open set's index (e.g. ARASAAC's public concept list) to find *missing
   core* and *over-represented fringe*; propose a prioritized, milestone-scoped concept backlog.
2. **Multilingual label drafting + provenance scaffolding.** Draft candidate labels and
   *back-translations* to flag ambiguity, generate the reviewer worksheet, and structure the
   per-label provenance record — **then a fluent human reviewer signs off** (never ship raw MT;
   the plan is already correct here).
3. **Metadata / tagging / keyword enrichment.** Generate keywords, synonyms, category assignments,
   interop-ref candidates (CCF / Global Symbols IDs), and validate metadata JSON against the
   schema — high-volume, low-judgment work.
4. **Design briefs (text, not pixels).** Turn a concept into a written design brief: intended
   referent, known iconographic conventions, cultural pitfalls to avoid, AIGA/DOT PD reference to
   consult, candidate visual grammar — a brief the *human designer* then draws.
5. **Comprehension-test instrument & protocol drafting**, distractor-option generation for ISO
   9186 tests, and aggregate (de-identified) results write-up.
6. **License/originality triage assistant.** Flag concepts that risk resembling protected art and
   surface the PD/permissive reference to use instead — a first-pass net, not the decision.

**Where Claude must NOT decide (hard guardrails, must be human/expert-owned):**

- **AAC efficacy and final design** — must be co-designed/validated with AAC users + SLPs, not
  inferred by a model. Claude does not judge whether a drawn symbol "works" for a user.
- **No AI-generated/traced icons shipped without review** — the plan's "no AI bitmap generation /
  original vector geometry only" stays hard. Any AI involvement in artwork triggers the
  copyrightability + CC0 question (already flagged) and a human originality attestation.
- **Cultural appropriateness** — final clearance is a human cultural reviewer's call, not the
  model's; Claude may only *surface* candidate concerns.
- **License/originality verdicts** — a human records the originality attestation; Claude triages
  only.
- **Comprehension pass/fail and safety sign-off** — determined by *measured* test data and a
  domain expert, never by model judgment.
- **Translation final sign-off** — fluent human reviewer, per the plan.

This division (Claude on text/metadata/analysis; humans+experts on efficacy/design/culture/
license/safety) maps cleanly onto Elyos' donated-lane rule and the plan's existing gates.

---

## 6. Ten concrete optimizations

1. **Add a named "AAC/SLP clinical reviewer" role and a co-design gate** distinct from
   comprehension testing — close finding §1B.
2. **Add a "Visual grammar" chapter to the design system**: how negation, plural, tense/time,
   person, possession, and category-color are encoded — so the set teaches a generalizable system
   (the thing Bliss/Widgit win on).
3. **Decide and document the figure/skin-tone policy** explicitly (neutral-abstract vs. realistic
   with selectable skin tones) — it's a load-bearing dignity + adoption decision.
4. **Commit to a named core-vocabulary anchor and a named facility wayfinding inventory** as an M0
   exit artifact (resolve the open question before draw-fan-out).
5. **Drop the optional icon font**; standardize on SVG (source) + PNG + OBF. Reduces build
   complexity for zero AAC value.
6. **Default to CC-BY-4.0 but pre-clear a CC0 fast-path** for any AI-assisted artwork and for
   partners who require CC0 — make the decision tree explicit now (don't defer to "before first
   release"; OBF/Global Symbols partners may ask immediately).
7. **Publish a per-symbol comprehension-evidence badge on the catalog site** (method, n,
   population, correct%, critical-confusion%, date) — turn the plan's metadata into a visible
   trust differentiator.
8. **Add a "license-compatibility matrix" doc** stating exactly why ARASAAC (NC-SA), Mulberry/
   OpenMoji (SA), Sclera (NC) are excluded *as inputs* and what PD/permissive references are
   allowed — onboard reviewers fast and make the value-prop legible to adopters.
9. **Seed-set selection: pin it to the interop layer.** Choose seed concepts that already have
   Global Symbols / CCF concept IDs so M0 can demonstrate OBF round-trip and Global Symbols
   import on day one (validates the channel cheaply).
10. **Add an automated "duplicate/near-duplicate concept" check and an SVG accessibility lint**
    (`<title>`/`role="img"`, no raster embeds, no external refs) into the existing style-lint
    gate — cheap CI wins that protect consistency and a11y.

---

## 7. Parallel & perpendicular spin-offs

**Parallel (same engine, adjacent output):**
- **`easy-read-plus`** — consumes symbols to illustrate simplified text; `open-pictograms` is the
  image layer, Easy Read does document assembly (keep the boundary per §1H).
- **`multilingual-signage-templates`** — the `adapters/signage/` printable sheets feed directly
  into signage template packs (clinic/shelter/transit wayfinding kits).
- **`vital-info-translations` / `emergency-phrasebooks`** — pair vetted multilingual labels +
  comprehension-tested symbols for humanitarian "vital info" sheets (water/latrine/medical/
  registration) that work across scripts.

**Perpendicular (new capability the asset enables):**
- **`sign-glossary`** — link pictograms to sign-language glosses/video for Deaf + AAC overlap;
  pictogram concept IDs become the join key.
- **An "open AAC board ecosystem" play** — ship not just symbols but *starter OBF boards* (core
  board, topic boards) so deployers get a working board, not raw SVGs; positions the set inside
  Cboard/CoughDrop/Global Symbols Board Builder.
- **An MCP server (`open-pictograms-mcp`)** — expose concept search, multilingual label lookup,
  comprehension-evidence, and OBF export over MCP so *any* agent/tool can pull
  permissively-licensed, tested symbols on demand. This is a natural, high-leverage distribution
  surface and fits Elyos' adapter/agent-neutral architecture.
- **Comprehension-testing-as-a-service protocol** — the ISO 9186 instrument + ethics protocol is
  itself a reusable open artifact other open-symbol projects lack.

---

## 8. Open questions

1. **CC-BY-4.0 vs CC0** (plan's own Q) — decide *now*, not at first release; OBF/Global Symbols
   partners and the AI-artwork copyrightability question both press on it. Consider **CC0 for
   AI-assisted artwork, CC-BY-4.0 for hand-authored** as a default split.
2. **Which AAC core-vocabulary frame anchors the communication set?** (Unresolved; blocks
   draw-fan-out.)
3. **Figure/skin-tone policy** — neutral-abstract vs. realistic-with-skin-tones? Interacts with
   dignity guardrail and adoption.
4. **Co-design access** — how do we recruit AAC users + SLPs ethically without a secured partner?
   This is the same gate as the comprehension-pilot access question and may be the true critical
   path, not "drawing."
5. **Is the differentiator durable if ARASAAC re-licenses?** Low risk (gov-funded NC-SA is sticky),
   but the comprehension-evidence + consistency moat should be defensible even if license parity
   closes.
6. **Interop ref scheme** — commit to CCF / Global Symbols IDs / BCI numbers explicitly.
7. **Safety subset: keep the small gated subset or exclude entirely?** (plan's Q) — recommend keep
   small + gated; it's a trust differentiator if done honestly.
8. **Does the project ship starter OBF boards** (not just symbols)? Big adoption lever; scope
   decision.

---

### Sources
ARASAAC: [Global Symbols](https://globalsymbols.com/symbolsets/arasaac?locale=en),
[OpenAssistive](https://openassistive.org/item/arasaacpictograms/),
[arasaac.org](https://arasaac.org/pictograms/search?tab=1) ·
Mulberry: [mulberrysymbols.org](https://mulberrysymbols.org/),
[GitHub](https://github.com/mulberrysymbols/mulberry-symbols) ·
Sclera: [copyright](https://www.sclera.be/en/picto/copyright),
[downloads](https://www.sclera.be/en/picto/downloads) ·
Blissymbolics: [blissymbolics.org](https://www.blissymbolics.org/) ·
OpenMoji: [openmoji.org/faq](https://openmoji.org/faq/) ·
Widgit: [licensing](https://www.widgit.com/symbol-services/licensing.htm) ·
SymbolStix: [AT HelpDesk](https://athelpdesk.org/symbolstix-prime-an-aac-app/) ·
Global Symbols: [about](https://globalsymbols.com/about?locale=en) ·
OBF/Cboard: [openboardformat.org](https://www.openboardformat.org/),
[OpenAAC symbols](https://www.openaac.org/symbols.html) ·
Noun Project: [pricing](https://thenounproject.com/pricing/) ·
ISO 9186: [ISO 9186-1:2014](https://www.iso.org/standard/59226.html).
