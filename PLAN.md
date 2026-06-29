# PLAN — open-pictograms

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

## Executive summary

When you cannot read the local language — because you never learned to read, because you read at
a basic level, because you have a cognitive or communication disability, or because you just
arrived in a country whose script is foreign to you — a wall of text is a locked door. In a clinic
waiting room, a shelter, a transit hub, a disaster-relief tent, or on a communication board used by
a non-speaking person, **a picture is often the only channel that works.** Good pictograms are not
decoration; they are infrastructure for being understood.

`open-pictograms` produces an **openly-licensed (CC-BY-4.0) pictogram/icon set** with one
**consistent visual style**, built for two concrete jobs: **(1) low-literacy and
cross-language communication** — including augmentative and alternative communication (AAC) for
non-speaking people — and **(2) wayfinding and signage** in public and humanitarian settings. The
deliverable is not "a folder of SVGs." It is a *tested, documented, reusable system*: a published
design spec, original vector source, multi-format exports (SVG / PNG / sprite / optional icon
font), structured per-symbol metadata, vetted multilingual labels, and — the part most icon
projects skip — **evidence that the people who need the symbols actually understand them.**

The defining constraint, and the project's identity, is **comprehension-first**: *a symbol our
target users cannot read is not a symbol, it is decoration, and it does not ship.* Every symbol is
evaluated for comprehensibility with members of the target population using the published **ISO
9186** methodology, and nothing is released as "communication-ready" below the recognized
comprehension threshold.

The project is **low risk overall**, and we say so honestly — most everyday pictograms (eat,
drink, sleep, toilet, bus, water, help) carry little hazard if imperfect. But we refuse to gloss
over the real exception: **safety-, hazard-, emergency-, and medication-related pictograms can
cause harm if misunderstood** (a misread "do not drink this water" or "emergency exit" symbol is
dangerous). That subset is treated as **medium risk**, is required to *align to* recognized
standards (AIGA/DOT public-domain symbols, ISO 7010 / ISO 7001 / GHS *concepts*), gets
**domain-expert review**, and ships with an explicit **"not certified safety signage / not medical
advice"** disclaimer. We add value; we do not certify regulatory compliance.

The hard guardrails are **originality + licensing** (every symbol is drawn as original vector
geometry — never traced from copyrighted or proprietary symbol art — and the set is kept free of
license entanglements) and **dignity** (symbols representing people, bodies, disability, gender,
and culture must not stereotype, and must be culturally reviewed).

This document is honest about what is not yet in place: **no partner organisation or beneficiary
channel is secured.** The documented *need* is real and well-evidenced; a documented need is not a
secured *delivery and validation channel*. **Partner / requestor: TO BE SECURED.** Until at least
one channel is confirmed (an AAC platform that will host the set, a facility that will install the
signage, or a humanitarian/education partner that will field-test it), all delivery- and
field-validation-dependent tasks carry `verifiedNeed = false`. M0 makes securing that channel an
exit criterion, with explicit kill/pivot rules so we never produce a beautiful, untested,
undeployed icon set.

## Problem & beneficiaries

**Who is helped (primary beneficiaries):**

- **Low-literacy and pre-literacy adults**, for whom text-only signage and instructions are
  inaccessible — in healthcare, public services, transit, and emergencies.
- **Non-speaking and minimally-speaking people who use AAC** (autism, cerebral palsy, aphasia,
  intellectual disability, stroke, ALS). They communicate by selecting symbols on boards and
  devices; the quality and openness of the symbol set directly shapes whether they can express
  themselves. Many high-quality existing sets are **non-commercial-only or share-alike licensed**,
  which limits free reuse across tools (see Data, licensing & compliance).
- **Refugees, migrants, and travelers** who do not share the local language or script, needing to
  navigate clinics, shelters, transit, and aid distribution.
- **People in disaster / humanitarian settings**, where signage must communicate across many
  languages instantly (water points, latrines, medical, registration, danger).

**Secondary beneficiaries:**

- **Clinics, shelters, schools, transit agencies, libraries, and small museums** in low-resource
  settings that need free, professional, consistent signage and communication aids.
- **The open AAC / open-design ecosystem** (board builders, signage template projects, OER) that
  can reuse a permissively-licensed, interoperable set.

**The verified need (the gap is real and documented).** That pictograms aid comprehension for
low-literacy and cross-language audiences, and that symbol-based communication is essential for
non-speaking AAC users, is well established in accessibility, public-health-communication, and AAC
literature, and is reflected in international practice (ISO 7001 public-information symbols,
healthcare symbol programs, humanitarian signage). A specific, persistent gap is the scarcity of
sets that are simultaneously **(a) openly and *permissively* licensed for unrestricted reuse,
(b) stylistically consistent, and (c) comprehension-tested with target populations.** On that
basis, the *need for the artifact type* is treated as verified.

**The partner gap (honest).** What is **not** verified is that *this* set, for *these* concepts,
meets a *specific* beneficiary's need in a *specific* deployment — because no partner is secured.
We have no AAC platform committed to host it, no facility committed to install signage, and no
community committed to comprehension-test it with real users. **Partner / requestor: TO BE
SECURED.** Task-level `verifiedNeed` is conservatively `false` for every delivery- and
validation-dependent task until a channel is confirmed; foundational, self-evidently-useful
artifacts (the design system, the metadata schema, the testing protocol) may be `true` because
they are not channel-dependent.

## Goals and non-goals

**Goals**

- Produce a **stylistically consistent** pictogram set under a single, published design system.
- Build for **two jobs done well**: low-literacy / cross-language / AAC **communication**, and
  **wayfinding / signage** — not a generic "all-purpose icon font."
- **Comprehension-first**: test every symbol with the target population (ISO 9186 method) and ship
  only symbols that meet the recognized threshold for their use.
- Keep the set **permissively open (CC-BY-4.0)**, **originally drawn**, and **interoperable** with
  the open AAC / signage ecosystem (e.g. Open Board Format export).
- Provide **vetted multilingual labels** and **culturally reviewed** representations of people and
  concepts, with regional variants where meaning differs.
- Deliver **multi-format, production-ready** assets (SVG source, PNG, sprite, optional icon font)
  with full per-symbol metadata and provenance.

**Non-goals**

- **Not** a decorative UI icon set, an emoji replacement, or a brand iconography service.
- **Not** a tracing/recoloring of any existing copyrighted or proprietary symbol set (ARASAAC,
  Noun Project paid icons, brand marks, etc.). All artwork is original.
- **Not** certified, legally-compliant safety signage. We *align to* recognized standards and
  recommend official certified signage where law requires it; we do not certify conformance.
- **Not** medical, legal, dosing, or safety *advice*. Medication / health / hazard pictograms are
  illustrative aids requiring expert review and carry a "not advice / not certified" disclaimer.
- **Not** a hosted application, board-builder, or signage-printing SaaS (we export to existing
  tools; a hosted catalog site is a static reference, not a service).
- **Not** facial likenesses, named individuals, religious/partisan iconography presented as
  neutral, or any symbol designed to deceive, shame, surveil, or exclude.
- **Not** AI raster image generation. Pictograms are authored as original vector geometry; we do
  not generate or trace bitmap art that could launder a copyrighted source.

## Success metrics (outcomes)

Outcome-based and beneficiary-centric. "Number of icons drawn" is explicitly **not** the headline
metric — **understood-and-deployed** is. Baselines are 0 (greenfield) unless noted; some targets
are deferred until M0 establishes a measured baseline rather than inventing one.

| Metric | Baseline | Target (first 2 quarters post-M0) |
|---|---|---|
| Symbols **passing comprehension testing** with the target population (ISO 9186 method) | 0 | ≥ 100 symbols at ≥ 67% correct comprehension; mean ≥ 80% |
| **Safety-aligned** symbols meeting the stricter threshold | 0 | 100% of shipped safety subset at ≥ 85% correct **and** < 5% "critical confusion" (dangerous wrong meaning); none shipped below |
| Symbols **deployed for a real beneficiary** (installed signage, AAC board, partner toolkit) | 0 | ≥ 1 confirmed deployment with a secured partner |
| **Languages with vetted labels** (reviewed by a fluent speaker, not raw MT) | 0 | ≥ 3 |
| **Beneficiary validation** sessions (low-literacy / AAC users / facility staff confirm usability) | 0 | ≥ 2 across ≥ 2 use contexts |
| **Style-conformance pass rate** (symbols passing the automated grid/stroke lint) | n/a | 100% of released symbols |
| **Cultural-review clearance** of people/body/concept symbols before release | n/a | 100% reviewed; 0 released with an unresolved cultural flag |
| **License / originality violations** (traced art, non-open dependency, missing attribution) | 0 | **0** (hard gate; any instance is a stop-the-line incident) |
| **Comprehension of redesigned symbols** after iteration (failed → retested → passed) | n/a | ≥ 70% of initially-failing symbols pass on redesign |

**Comprehension thresholds (explicit, and use-dependent).** We adopt published practice:

- **General communication / wayfinding symbols:** the ISO 9186-1 acceptance convention of **≥ 66.7%
  (two-thirds) correct comprehension** in the target population, with low "wrong-meaning" responses.
- **Safety / hazard / emergency / medication-related symbols:** the stricter bar used for safety
  signs (per ISO 3864-3 / ANSI Z535.3 practice) — **≥ 85% correct comprehension** and a **critical
  confusion rate < 5%** (no participant reads the *opposite* or a *dangerous* meaning). A safety
  symbol that fails this is redesigned or **withdrawn**, never shipped "good enough."

**Comprehension measured, not assumed.** A symbol's `comprehensionScore` records the method (ISO
9186-1 comprehension test or judgement test), sample size `n`, the target population tested,
correct/critical-confusion rates, and date — so scores are reproducible and comparable across
symbols and revisions.

## Scope

**In scope**

- Original pictograms for everyday **communication** (needs, actions, feelings, people, places,
  time, health basics) and **wayfinding** (facilities, services, directions, transport).
- A **published design system**: grid, stroke weight, corner treatment, level of abstraction,
  fill/stroke rules, color usage (and a strict monochrome variant for max contrast / printing).
- **Comprehension testing** (ISO 9186 method) and **cultural review**, with regional/directional
  variants where meaning differs.
- **Multi-format build**: normalized SVG source of truth → PNG raster (multiple sizes), SVG
  sprite, and **optional** icon font; plus **Open Board Format (OBF)** export for AAC reuse.
- **Per-symbol metadata** (concept id, category, keywords, multilingual labels, license,
  attribution, provenance, comprehension score, cultural-review status, safety class).
- A **safety-aligned subset** that references recognized standards, gets expert review, and ships
  with disclaimers.
- A static **catalog/reference site** (browse, search, download, see comprehension evidence).

**Out of scope**

- Tracing, recoloring, or "remixing" any copyrighted/proprietary/NC-licensed symbol set.
- Certified safety signage, regulated medical-device symbols, or anything claiming legal
  conformance.
- A hosted board-builder, signage SaaS, or print-fulfillment service.
- AI bitmap art generation; photoreal imagery; brand/logo iconography.
- Exhaustive coverage of every concept on day one — depth and *testing* beat breadth.
- Machine-translated labels shipped without a fluent human reviewer.
- Symbols depicting identifiable individuals, or partisan/religious content framed as neutral.

## Solution approach & architecture

This is a **content + design-system project with supporting build/tooling code**, run in the
**donated lane**: a human runs their own agent interactively to author SVGs, metadata, labels, and
docs; Elyos prepares the task workspace and opens PRs. The CLI never runs an agent headless and
never authenticates a coding agent.

**Authoring & build pipeline (per symbol)**

1. **Concept intake & dedup** — a symbol begins as a *concept* (stable `conceptId` slug, category,
   target use). Check it does not duplicate an existing concept; map it to interop identifiers
   where possible (e.g. a Concept Coding / Global Symbols reference) for downstream reuse.
2. **Originality & license pre-check** — confirm the concept will be drawn from scratch. Any visual
   reference allowed is **public domain or permissively-licensed only** (notably the public-domain
   **AIGA/DOT** symbol set, and the *idea/meaning* behind standards like ISO 7010/7001/GHS — ideas
   are not copyrightable, but their *specific artwork* must not be copied). Record an **originality
   attestation** in provenance. *If a concept can only be expressed by copying protected art → stop.*
3. **Draw (original vector)** — author an SVG conforming to the design system (grid, stroke,
   abstraction). Output is normalized (e.g. via SVGO) to a clean, accessible SVG with `<title>`/
   `role="img"` for assistive tech.
4. **Style lint (automated gate)** — the build checks the SVG against the spec: canvas/viewBox
   size, grid alignment, stroke width, allowed palette, no raster embeds, no external refs, no
   stray metadata. Non-conforming → rejected back to draft.
5. **Metadata & labels** — write the per-symbol record (below). Default label language first;
   additional languages added only with a **fluent human reviewer** (never raw MT). Mark any
   concept whose visual meaning is **culturally variable** for cultural review.
6. **Cultural & dignity review** — symbols depicting people, bodies, disability, gender, age, food,
   gestures, and religion are reviewed for stereotype/offense and for cross-cultural legibility;
   regional or directional (RTL/mirror) variants are produced where meaning differs.
7. **Comprehension test (the headline gate)** — test with members of the target population using
   the ISO 9186 method; record `comprehensionScore`. Below threshold → **redesign and retest**, do
   not ship. Safety subset must clear the stricter bar (§Success metrics).
8. **Safety/expert review (subset only)** — safety/hazard/emergency/medication symbols additionally
   require **domain-expert sign-off** and carry the "not certified / not advice" disclaimer.
9. **Export & publish** — the build emits PNG sizes, SVG sprite, optional icon font, and OBF; the
   catalog site is regenerated. A symbol is **"shipped"** only when style-conformant,
   comprehension-passed (and expert-signed for safety), with full metadata/provenance.
10. **Deploy & track to outcome** — with a secured partner, the symbol reaches a real deployment
    (installed signage / AAC board / toolkit). "Delivered, not merged": the outcome is *use by a
    beneficiary*, not a merged PR.

**Components**

- `design-system/` — the published spec (grid, stroke, palette, abstraction, accessibility,
  naming, safety-subset rules, do/don't gallery).
- `symbols/` — original SVG source of truth (one file per symbol/variant), the project's core data
  artifact.
- `metadata/` — per-symbol JSON records (schema below); the machine-readable catalog.
- `labels/` — multilingual label sets, each with reviewer provenance.
- `pipeline/` (TypeScript, ESM) — SVG normalize + **style lint**, PNG/sprite/font/OBF export,
  catalog-site generator, metadata validator.
- `adapters/` (Elyos-conformant — all ecosystem-specific logic here) —
  - `adapters/obf/` — Open Board Format export for AAC board builders.
  - `adapters/signage/` — printable signage-sheet templates (ties to existing signage-template work).
- `testing/` — the ISO 9186-based comprehension-test protocol, instruments, and (de-identified,
  aggregate) results.

**Tech stack & conventions.** TypeScript, ESM, pnpm workspaces. **Tooling/code: MIT.**
**Artwork & metadata: CC-BY-4.0** (see Data, licensing & compliance for the CC-BY-vs-CC0 open
question). Any bundled label *font* must be **SIL OFL**. SVG source is canonical; rasters/fonts are
derived. DCO sign-off (`git commit -s`) on all code and PRs; changeset for user-facing changes.

**Per-symbol metadata record (data model, draft)**

```
conceptId            stable slug, e.g. "drink-water", "exit", "feeling-sad"
category             communication | wayfinding | health | safety | people | actions | emotions | places | time | transport
interopRefs          optional cross-refs (e.g. Global Symbols / Concept Coding id) for reuse
labels               { "en": "drink water", "es": "beber agua", ... } each with reviewer provenance
svgSource            path to original SVG source of truth
variants             e.g. monochrome, directional-mirror, neutral-figure (paths)
styleConformance     pass | fail (automated lint result + version)
safetyClass          none | safety-aligned  (safety-aligned → stricter threshold + expert review)
referencedStandard   nullable, e.g. "AIGA/DOT (PD reference)", "ISO 7010 concept ref"
comprehensionScore   { method, n, population, correctPct, criticalConfusionPct, date } (nullable until tested)
culturalReview       { status: pending|cleared|flagged, notes, regionalVariants[] }
license              "CC-BY-4.0" (artwork) ; tooling MIT
attribution          required attribution string (author/creator + project)
provenance           { tool, author, originalityAttestation, date, reviewers[] }
disclaimer           nullable; required for safetyClass = safety-aligned
status               draft | style-passed | tested | cleared | shipped | withdrawn
```

**Key decisions (locked)**

- **SVG is the source of truth; everything else is a derived export.** One canonical vector per
  symbol; PNG/sprite/font/OBF are generated, never hand-edited.
- **Comprehension is a release gate, not a nice-to-have.** No symbol ships "communication-ready"
  without a recorded comprehension score meeting its threshold.
- **Original geometry only; CC-BY-4.0; OFL fonts; MIT tooling.** No license entanglement, no traced
  art, no NC/SA dependency pulled into the set.
- **Two jobs, one style.** Communication and wayfinding share a single design system so a facility
  can mix them coherently; we resist becoming a general icon library.
- **Safety is a privileged subset, not the default.** Stricter threshold + expert review +
  disclaimer; never claim certification.

## Data, licensing & compliance

**This is the critical, conservative section.**

**License of our outputs.**

- **Artwork (SVG/PNG/sprite/font glyphs) and metadata: CC-BY-4.0.** Attribution string travels with
  every symbol. *(Open question, flagged: some AAC platforms prefer fully permissive **CC0** for
  frictionless reuse; and AI-assisted artwork raises a copyrightability question — see Open
  questions. The default is CC-BY-4.0 unless a secured partner or a legal review favors CC0.)*
- **Tooling / pipeline code: MIT.**
- **Bundled label fonts (if any): SIL Open Font License (OFL) only.**

**Allowed visual references (and the hard originality gate).** Pictograms are **drawn as original
vector geometry**. We may *reference for meaning/convention only*:

- The **AIGA/DOT** symbol set — **explicitly released into the public domain** — may be used and
  adapted directly.
- The **concepts/meanings** behind standards (ISO 7001 public information, ISO 7010 safety, GHS
  hazard) — *ideas and required meanings are not copyrightable*, but the **specific artwork** in
  those (often paywalled) standards must **not** be copied or traced. We re-express the concept in
  our own style.
- **Public-domain and permissively-licensed (CC-BY / CC0)** reference imagery, with provenance.

**Hard exclusions (never ingested, traced, recolored, or "remixed"):**

- **Non-commercial-only sets** (e.g. ARASAAC is CC-BY-NC-SA) — incompatible with our free-reuse
  goal; **not** a source.
- **Share-alike sets** (e.g. Mulberry, OpenMoji are CC-BY-SA) — valuable, but we keep our set free
  of SA obligations by drawing original work rather than deriving.
- **Proprietary / paid / brand** symbol sets and any art of unclear license.

**Originality attestation.** Every symbol records, in `provenance`, that it was drawn as original
geometry, any PD/permissive reference used, and the author/tool. Inadvertent close resemblance to a
protected symbol is treated as a license incident (redesign + record).

**Privacy / PII / consent (comprehension testing).** The riskiest *data* in this project is **human
testing data**, not the art. The testing protocol:

- Collects **aggregate, de-identified** comprehension results only — no names, no faces, no
  identifying data stored with responses.
- Obtains **informed consent**; for **vulnerable populations** (people with intellectual/
  communication disabilities, children) it requires **guardian/supported consent** and accessible
  consent materials, and defers to a **partner's ethics process / IRB** where one applies.
- Never photographs or records participants beyond what consent covers; raw session media (if any)
  is ephemeral and not published — only aggregate scores are.

**Dignity & non-discrimination.** Representations of people, bodies, disability, gender, age,
religion, and culture must avoid stereotype and be culturally reviewed. We follow disability-
community norms (e.g. neutral, non-pejorative depictions) and produce regional variants rather than
imposing one culture's conventions as universal.

**Attribution requirements.** Downstream users must retain the CC-BY attribution; the catalog and
each export bundle ship a clear attribution/credit file and per-symbol author/provenance.

## Quality, review & risk gates

**Risk tier: low overall, with a medium-risk subset (honest split).**

- **low** — everyday communication and wayfinding symbols (eat, drink, toilet, bus, water, help,
  feelings, places). Standard design + comprehension review. *This is the bulk of the set.*
- **medium** — **safety / hazard / emergency / medication-related** symbols (exit, fire, "do not
  drink," poison, "call for help," medicine), and **culturally-sensitive depictions** (people,
  bodies, disability, gesture, religion). Requires the stricter comprehension threshold, cultural
  review, and **domain-expert sign-off** for the safety subset.
- **high** — *excluded by scope.* Anything that would constitute medical/legal/safety **advice** or
  **certified** signage is out of scope, not "escalated." We point to official certified resources.

**Required review before a symbol is "shipped":**

1. **Originality + license check** — original geometry; references PD/permissive only; attestation
   + attribution recorded. (Hard gate; violation = stop-the-line.)
2. **Style-conformance lint** — passes the automated design-system check (grid/stroke/palette/clean
   SVG).
3. **Comprehension test** — recorded `comprehensionScore` meets the threshold for its use
   (≥ 67% general; ≥ 85% + < 5% critical confusion for safety). Below → redesign/retest or withdraw.
4. **Cultural & dignity review** — cleared (or regional variants produced) for any people/body/
   concept symbol.
5. **Expert sign-off (safety subset)** — domain expert approves the safety-aligned symbol and the
   "not certified / not advice" disclaimer is attached.

**Definition of Shipped (project-level).** A symbol is **shipped** when it is style-conformant,
comprehension-passed at its threshold (safety: expert-signed), culturally cleared, fully
metadata'd/attributed, and exported in all formats. The deed is **delivered** when, with a secured
partner, that symbol reaches **real use by a beneficiary** (installed signage / live AAC board /
distributed toolkit). Generated-but-untested ≠ shipped; shipped-but-undeployed ≠ delivered.

## Roadmap & milestones

Phased; each milestone has measurable exit criteria. M0 is a deliberately thin, end-to-end slice —
it must prove a symbol can travel from *concept → drawn → tested with real users → exported →
(toward) deployed* before anything scales.

**M0 — Foundation & cold-start (prove one end-to-end symbol).**
Goal: publish the design system, finalize the metadata schema + comprehension protocol, secure ≥ 1
partner/validation channel, and take a tiny seed set fully end-to-end including a real comprehension
pilot.

**Sequencing — securing a channel is a hard gate.** The partner-securing research task is a
**blocking prerequisite for field validation and deployment** (not for drawing the foundational
artifacts). **Kill/pivot criteria:** if the time-boxed effort secures no partner from the candidate
list, the project **pivots** (next candidate channel) or **pauses scaling** — it does not mass-
produce untested, undeployed symbols. The design system, schema, protocol, and a small *internally*
pilotable seed set may proceed, but field validation and "deployed" metrics wait on a partner.

**Candidate partner/validation channels (priority order, with honest acceptance posture):**
1. **Open AAC platforms / symbol hubs** (e.g. Global Symbols / Open Board Format ecosystem) — clear
   reuse path; posture: *generally welcoming to permissively-licensed open sets; per-platform
   confirmation + format compliance still required.* (TO BE SECURED.)
2. **A facility or humanitarian/education partner** (clinic, shelter, school, NGO) that will
   field-test and install signage — posture: *highest-value validation, needs a named partner and a
   real site.* (TO BE SECURED.)
3. **Existing Elyos siblings** (`multilingual-signage-templates`, `emergency-phrasebooks`,
   `easy-read-plus`) as internal consumers — posture: *useful early integration, but not a
   substitute for external beneficiary validation.*

**M0 seed-set selection (must exercise every path, not 12 easy icons).** The seed set spans use and
risk: several **everyday communication** symbols, several **wayfinding** symbols, ≥ 1
**culturally-variable** concept (to exercise cultural review + a regional variant), and ≥ 1
**safety-aligned** symbol (to exercise the stricter threshold + expert review + disclaimer). A seed
set of 12 trivial icons is disallowed — it would not prove the pipeline.

Exit criteria:
- Design system v1 published (CC-BY-4.0): grid, stroke, palette, abstraction, accessibility, naming,
  safety-subset rules, do/don't gallery.
- Metadata schema + originality/license policy + comprehension-test protocol (ISO 9186-based,
  including consent/ethics for vulnerable populations) finalized and applied to the seed set.
- Build pipeline produces, from one SVG source: normalized SVG, PNG sizes, sprite, and OBF export;
  style-lint gate operational.
- ≥ 12 seed symbols drawn and **passing style lint**, spanning communication / wayfinding /
  culturally-variable / safety-aligned.
- ≥ 1 **comprehension pilot** run with members of the target population (or, if no participant
  access yet, an honestly-labeled judgement-test pilot) with recorded scores; ≥ 1 culturally
  reviewed; the safety-aligned symbol expert-reviewed.
- ≥ 1 partner/validation channel **confirmed** (closes the partner gap for that channel) **or** the
  kill/pivot criteria are formally recorded.
- Zero originality/license violations.

**M1 — Pipeline & first tested release (make it repeatable).**
Goal: turn the manual slice into a repeatable build and ship a usable, tested core release.
Exit criteria:
- Full build automation green (SVG lint → PNG/sprite/font/OBF → catalog site) in CI.
- ≥ 100 symbols **shipped**: style-conformant + comprehension-passed (≥ 67% general / ≥ 85% +
  < 5% critical confusion for safety) + culturally cleared.
- Core vocabulary covers an AAC core set + a wayfinding inventory for at least one facility type.
- Vetted labels in ≥ 2 languages (fluent-reviewed); catalog site published with comprehension
  evidence visible per symbol.
- Reviewer workflow + comprehension protocol + cultural-review checklist documented; ≥ 2 reviewers
  + ≥ 1 cultural reviewer onboarded.

**M2 — Scale, localize & validate in the field.**
Goal: grow coverage, localize, and prove real-world use with a secured partner.
Exit criteria:
- ≥ 300 symbols shipped; safety-aligned subset 100% expert-signed and at its stricter threshold.
- Vetted labels in ≥ 3 languages; regional/directional variants where meaning differs.
- ≥ 1 **confirmed real deployment** (installed signage / live AAC board / distributed toolkit) and
  ≥ 2 **beneficiary validation** sessions across ≥ 2 contexts.
- OBF + signage adapters validated by a downstream consumer; zero license/originality violations.

**M3 — Sustain, interoperate & govern.**
Goal: durable, community-maintainable, interoperable, with outcomes tracked.
Exit criteria:
- Contribution guide + governance for new symbols (intake → test → cultural → safety) published.
- Interop confirmed with ≥ 1 external ecosystem (e.g. Global Symbols import / OBF round-trip).
- Versioned releases + changelog; outcome-tracking of deployments/adoption maintained.
- Documented maintainer + reviewer rotation; sustainability plan in effect.

## Work breakdown

The itemised, schema-mapped backlog lives in **`TASKS.md`** (same directory), organised by the
milestones above: one task per work unit, stable IDs (`open-pictograms-<area>-NNN`), a
size/risk/reviewer table per milestone, acceptance criteria for the key tasks, a milestone
Definition of Done, a sized/unscheduled backlog, and a complete schema-valid example Task JSON for
the first M0 task. At production scale this project fans out: **one symbol (or small concept batch)
= one task**, drawn from a milestone-scoped concept list; the `*-draw-*` / `*-batch-*` tasks are the
templates for that fan-out.

## Governance, roles & stakeholders

- **Maintainer (Owner):** TBD — owns the design system, pipeline, metadata schema, and the overall
  quality/comprehension bar.
- **Design-consistency reviewer:** enforces the style system on every symbol (can be the
  maintainer early; rotation documented in M1).
- **Comprehension-test coordinator:** runs ISO 9186-based testing, manages consent/ethics, records
  scores; the guardian of the "tested, not assumed" rule.
- **Cultural / localization reviewers:** fluent speakers + culturally-knowledgeable reviewers per
  locale; clear people/body/concept symbols and own label translation quality.
- **Safety-domain expert(s):** required sign-off for the safety-aligned subset (the Elyos
  expert-review guardrail for safety content).
- **Steward (last-mile owner):** owns each partner relationship and shepherds symbols to **real
  deployment** — accountable for "delivered, not merged."
- **Partner / requestor:** **TO BE SECURED** — AAC platform, facility, or humanitarian/education
  org that hosts, installs, or field-tests the set.
- **Beneficiary validators:** low-literacy adults, AAC users (with supported consent), and facility
  staff who confirm symbols are actually usable.

## Dependencies & integrations

- **SVG tooling** — normalizer/optimizer (e.g. SVGO) and a custom style-lint; vector authoring.
- **Export tooling** — PNG rasterizer, SVG sprite builder, optional SVG-to-icon-font, and **Open
  Board Format (OBF)** writer for AAC interop.
- **AIGA/DOT public-domain symbol set** — permitted direct reference/adaptation.
- **Standards (methodology/concepts only, not redistributed):** **ISO 9186** (comprehension-test
  method), ISO 7001 (public information symbols), ISO 7010 (safety signs), GHS (hazard) — used for
  *method and meaning*; their paywalled artwork/text is **not** copied or redistributed.
- **Open AAC ecosystem** — Global Symbols / Open Symbols / Concept Coding references for interop;
  OBF-consuming board builders (e.g. CoughDrop-style apps).
- **Elyos siblings** — `multilingual-signage-templates`, `emergency-phrasebooks`, `easy-read-plus`
  as internal consumers; **SIL OFL** fonts for any labels.
- **Elyos platform pieces** — `packages/cli` (donated-lane workspace + PR prep), the Task schema
  (`packages/schema`), and `adapters/` for all ecosystem-specific code. The CLI never runs an agent
  headless and never authenticates a coding agent.

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Inadvertently copying/tracing a copyrighted or proprietary symbol | Medium | High | Hard originality gate: original geometry only; PD/permissive references only (AIGA/DOT PD ok); originality attestation in provenance; treat resemblance as a stop-the-line incident → redesign | Maintainer / Steward |
| Safety/hazard/emergency symbol misunderstood → real harm | Low | High | Safety = privileged subset: stricter threshold (≥85% + <5% critical confusion), domain-expert sign-off, align to ISO 7010/7001/GHS *concepts* + AIGA/DOT, "not certified / not advice" disclaimer, point to official certified signage | Safety expert / Maintainer |
| Beautiful but **unintelligible** symbols ("decoration, not communication") | High | High | Comprehension test is a release gate, not optional; redesign-and-retest loop; ship nothing below threshold; outcome metric is comprehension, not count | Comprehension coordinator |
| Cultural insensitivity / stereotype in people/body/concept symbols | Medium | High | Mandatory cultural & dignity review; disability-community norms; regional/directional variants; flag-blocks-release | Cultural reviewers |
| No partner secured → no real deployment or beneficiary validation | Medium | High | M0 exit requires a confirmed channel or recorded kill/pivot; `verifiedNeed=false` until secured; foundational artifacts proceed but "deployed/validated" metrics wait | Steward / Maintainer |
| Label mistranslation misleads users | Medium | Medium | Fluent-human review required; never ship raw MT; reviewer provenance per label; symbol must work *without* the label too | Cultural / localization reviewers |
| License entanglement (SA/NC dependency pulled in) | Low | High | Draw original work; exclude NC/SA sources as inputs; OFL fonts; MIT tooling; CC-BY artwork; license audit in CI | Maintainer |
| Consent/ethics failure when testing vulnerable populations | Low | High | Informed/supported consent; guardian consent for minors; aggregate de-identified data only; defer to partner ethics/IRB; accessible consent materials | Comprehension coordinator |
| Scope creep into a giant untested icon library | Medium | Medium | "Two jobs, one style" lock; depth+testing over breadth; milestone-scoped concept lists; non-goals enforced | Maintainer |
| AI-assisted artwork copyrightability / attribution ambiguity | Medium | Medium | Record provenance + originality attestation; flagged as Open question; consider CC0 for AI-only artwork pending legal review | Maintainer |
| Over-claiming safety/regulatory conformance | Low | High | Explicit non-goal + per-symbol disclaimer; never use words like "certified/compliant"; recommend official signage where law requires | Steward / Safety expert |

## Security & privacy

- **Threat surface.** Mostly **content integrity, IP, and human-subjects privacy** rather than
  classic infosec: traced/infringing art, misunderstood safety symbols, cultural harm, and
  comprehension-testing participant data. Pipeline/adapters may touch repo APIs and a static site
  host.
- **Secrets handling.** Any host/repo tokens are supplied via the human's own environment and never
  written into logs, receipts, metadata, or committed files (per CLAUDE.md). Donated lane: the human
  authenticates with their own account; Elyos stores no agent credentials.
- **PII / privacy.** Comprehension testing stores **aggregate, de-identified** results only;
  informed/supported consent obtained; vulnerable-population safeguards (guardian consent, partner
  ethics/IRB); no participant faces/names published; raw session media (if any) ephemeral.
- **Abuse / misuse prevention.** Refuse and flag (per Elyos guardrails) any request to make symbols
  that **deceive, target, harass, shame, surveil, or exclude** people; to misrepresent safety
  information; or to launder copyrighted art. No symbol depicting identifiable private individuals.

## Sustainability & maintenance

- **Post-delivery ownership.** The set is designed to live **beyond Elyos**: permissive CC-BY,
  interoperable (OBF / Global Symbols), versioned releases, and a contribution guide so a community
  can extend it. Deployed symbols persist in partners' signage / AAC boards.
- **Maintenance.** The maintainer keeps the design system, pipeline, and exporters current
  (format/standard changes); reviewer + cultural-reviewer rotation keeps testing capacity alive; the
  safety subset is re-checked against standard updates.
- **Outcome tracking.** A lightweight record of deployments and downstream adoption (which
  partners/tools use which symbols) keeps *delivered* impact visible after the active push.
- **Wind-down.** If a partner relationship ends, shipped symbols remain openly available; in-flight
  symbols are completed or cleanly parked; provenance records final disposition.

## Open questions

- **CC-BY-4.0 vs CC0** for the artwork — CC-BY gives credit and provenance; CC0 maximises
  frictionless AAC reuse. Which best serves the first secured partner and the AI-copyrightability
  question below? (Decide before the first major release.)
- **AI-assisted artwork copyrightability** — if a symbol is substantially AI-authored, can CC-BY
  meaningfully attach, or should such artwork be **CC0**? Needs a brief legal review; affects the
  license decision above.
- **Which partner/validation channel is secured first** — open AAC platform, a facility, or a
  humanitarian/education org? (Gates M0 field-validation/deployment exit.)
- **Which core vocabulary** anchors the communication set (which published AAC core-word list /
  concept frame), and which **facility wayfinding inventory** anchors signage? (Drives the concept
  list.)
- **Comprehension-testing access** — how do we ethically recruit and test with low-literacy adults
  and AAC users (especially with disabilities/minors) without a partner's ethics process? (Shapes
  M0's pilot honesty.)
- **Icon font vs SVG/sprite-only** — is a font worth the build complexity for our consumers, or do
  SVG + OBF suffice?
- **Safety subset: include or exclude?** Include a small expert-reviewed, disclaimered subset, or
  exclude safety entirely and point to official certified signage? (Default: small, gated subset.)

## References

- `C:\code\elyos\CLAUDE.md` — Elyos work rules, lanes, quality bar, refusal guardrails.
- `C:\code\elyos\docs\good-deed-definition.md` — good-deed criteria and risk tiers.
- `C:\code\elyos\packages\schema\src\schemas.ts` — Task JSON schema.
- `C:\code\elyos\planning\ROADMAP.md` — portfolio roadmap (open-pictograms, Track 4).
- ISO 9186 — methods for testing comprehensibility of graphical symbols (comprehension test +
  judgement test) — *method only; standard not redistributed*.
- ISO 7001 (public information symbols), ISO 7010 (safety signs), ISO 3864-3 / ANSI Z535.3 (safety
  comprehension criteria), GHS (hazard pictograms) — *concepts/criteria referenced only*.
- AIGA/DOT Symbol Signs — public-domain transportation/public-information symbols (permitted
  reference/adaptation).
- Creative Commons CC-BY-4.0 and CC0; SIL Open Font License (OFL).
- Open Board Format (OBF) — open AAC board interchange format; Global Symbols / Concept Coding —
  open AAC symbol interoperability.

---

## Appendix A — Improvements applied

Twenty-five specific improvements made to the draft, each already applied above (not deferred):

1. **Split "low risk" honestly into low + a medium safety subset** rather than accepting the
   proposal's flat "low" — safety/hazard/emergency/medication symbols are called out as medium with
   their own gate.
2. **Adopted ISO 9186 as the comprehension-test method** and made comprehension a *release gate*,
   turning "consistent style" into "consistent *and understood*."
3. **Set explicit, use-dependent thresholds** (≥67% general; ≥85% + <5% critical confusion for
   safety) instead of a vague "tested" claim.
4. **Made "deployed for a real beneficiary" the headline outcome**, demoting "icons drawn" to a
   non-metric — aligning with "delivered, not merged."
5. **Named the license trap explicitly:** ARASAAC (NC) excluded; Mulberry/OpenMoji (SA) excluded as
   *inputs*; AIGA/DOT (PD) permitted — so reviewers know exactly what may be referenced.
6. **Added an originality attestation** to provenance and a stop-the-line rule for inadvertent
   resemblance, hardening the copyright guardrail.
7. **Clarified the idea/expression line** for standards: ISO 7010/7001/GHS *concepts* are usable;
   their *paywalled artwork* is not copied — preventing both infringement and over-caution.
8. **Added cultural & dignity review** as a mandatory gate with regional/directional variants —
   addressing cross-cultural meaning and disability-representation norms.
9. **Treated comprehension-testing data as the real privacy surface**, adding consent + vulnerable-
   population (guardian/IRB) safeguards and aggregate-only storage.
10. **Chose OBF export** as a concrete AAC-interoperability deliverable, making the set reusable in
    real board builders rather than a dead folder of files.
11. **Defined SVG as single source of truth** with all other formats derived, preventing drift
    across PNG/sprite/font.
12. **Specified an automated style-lint gate** (grid/stroke/palette/clean-SVG) so "consistent style"
    is machine-enforced, not aspirational.
13. **Built a full per-symbol metadata schema** including comprehension score, cultural status,
    safety class, and provenance — making quality auditable.
14. **Added the "not certified safety signage / not medical advice" disclaimer** and an explicit
    non-goal, closing the over-claiming risk.
15. **Sequenced partner-securing as a gate for field validation/deployment** (not for foundational
    artifacts), with kill/pivot criteria — avoiding a pile of untested, undeployed symbols.
16. **Required fluent-human label review** and made symbols work *without* labels, so localization
    errors can't silently mislead.
17. **Designed the M0 seed set to exercise every path** (communication/wayfinding/cultural/safety),
    banning a "12 easy icons" cold-start.
18. **Distinguished comprehension *test* vs *judgement test*** so an honest M0 pilot is possible even
    before full participant access.
19. **Added a redesign-and-retest loop metric** (≥70% of failing symbols pass on redesign), making
    iteration a tracked behavior.
20. **Flagged the AI-artwork copyrightability question** and tied it to a CC-BY-vs-CC0 decision with
    a legal-review open question — intellectual honesty about the license.
21. **Connected to Elyos siblings** (`multilingual-signage-templates`, `emergency-phrasebooks`,
    `easy-read-plus`) as internal consumers, giving early integration value.
22. **Added accessibility of the SVGs themselves** (`<title>`/`role="img"`) so the assets are
    screen-reader-friendly, not just visually clear.
23. **Specified a monochrome/high-contrast variant** for printing and low-vision/distance
    wayfinding, plus directional (RTL/mirror) variants.
24. **Wrote reproducible comprehension scoring** (method, n, population, correct/critical-confusion,
    date) so scores are comparable across symbols and revisions.
25. **Excluded high-risk advice/certification entirely** (not "escalated"), keeping the project
    squarely within its low-risk identity while pointing users to official resources.

## Review sign-off

**Reviewed against:** the PLAN_SPEC 17-section structure, `CLAUDE.md`, the good-deed definition,
the Task schema, and the Ofelia exemplar's depth (positioning, who-for, explicit non-goals, locked
decisions, stack, phased roadmap, constraints-as-identity).

- **Completeness:** All 17 required H2 sections present and in order; Appendix A (25 applied
  improvements) and this sign-off added. TASKS.md provides the schema-mapped backlog, milestone
  tables, acceptance criteria, DoD, backlog, and a schema-valid example Task JSON. ✅
- **Correctness — schema:** Example Task JSON uses only schema-permitted fields and enum values;
  all `required` fields present; `verifiedNeed` honestly set; `outputLicense` real (CC-BY-4.0). ✅
- **Correctness — guardrails:** License/provenance (CC-BY/PD/CC0/OFL only; NC & SA excluded as
  inputs; originality attestation); privacy/consent (aggregate, de-identified, vulnerable-population
  safeguards); non-discrimination/dignity review; safety subset gated with expert sign-off and "not
  advice / not certified" framing; partner marked **TO BE SECURED**; `verifiedNeed=false` on
  delivery-dependent tasks. ✅
- **Correctness — lane:** Donated lane respected (human runs the agent; CLI preps workspace + PR;
  no headless agent; no funded budget). ✅
- **Honesty:** Outcome-based metrics (comprehension + real deployment), partner gap stated, no
  invented partner/baseline, kill/pivot criteria explicit. ✅
- **Fixes applied during review:** (a) made comprehension thresholds *use-dependent* rather than a
  single number; (b) clarified that the partner gate blocks *field validation/deployment* but not
  foundational artifacts, so M0 isn't fully blocked; (c) ensured the example task's
  `verifiedNeed=true` is justified (foundational, non-channel-dependent) while delivery tasks remain
  `false`; (d) added SVG self-accessibility and monochrome/RTL variants after a coverage pass.

**Status:** Ready for maintainer review. Blocking human decisions: secure first partner channel;
CC-BY vs CC0 (incl. AI-artwork legal review); confirm core-vocabulary + wayfinding inventory;
confirm ethics process for testing with vulnerable populations.
