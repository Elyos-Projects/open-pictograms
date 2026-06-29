# TASKS — open-pictograms

> Status: Draft · Version: 0.1.0 · Last updated: 2026-06-28 · Owner: TBD (maintainer) · Lane: donated

Backlog for the `open-pictograms` good-deed project. Read alongside `PLAN.md` (same directory).

## How these tasks map to Elyos

Every task here becomes a **Task JSON** validated by `packages/schema/src/schemas.ts`. Field mapping:

- `id` — stable, e.g. `open-pictograms-design-001` (the table's ID column).
- `title` — the task title.
- `project` — `"open-pictograms"` for all tasks.
- `type` — one of `code | research | writing | data | design-spec | maintenance`. Design system /
  spec docs → `design-spec`; drawn symbols + metadata → `data` (the SVG/metadata artifact); build
  tooling/adapters → `code`; protocols/guides → `writing`; partner & standards work → `research`.
- `lane` — `"donated"` for all tasks (human runs their own agent; CLI preps workspace + PR). No
  `funded` tasks here, so `fundedBudgetUsd` is not required.
- `priority` — `high | medium | low`.
- `domain` — array, e.g. `["accessibility","communication","wayfinding","open-culture","design"]`.
- `riskTier` — `low | medium | high`. Everyday communication/wayfinding symbols are `low`; the
  **safety/hazard/emergency/medication** subset and culturally-sensitive depictions are `medium`;
  nothing here is `high` (advice/certification is out of scope, not escalated).
- `urgent` — boolean (default `false`; nothing here is time-critical).
- `deliverable` — `pr | dataset | document | translation`. Drawn symbol sets + metadata →
  `dataset`; tooling/adapters/catalog → `pr`; specs/guides/protocols → `document`; localized label
  sets → `translation`.
- `tokenEstimate` — `small | medium | large` (the table's Size column).
- `status` — `open | in-progress | review | delivered | done` (all start `open`).
- `context`, `objective`, `acceptanceCriteria[]`, `resources[]`, `output` — task body fields.
- `requestor` — proposer/maintainer; `verifiedNeed` — **`false`** for delivery- and field-
  validation-dependent tasks until a partner/channel is secured (see PLAN "partner gap"); `true`
  only for foundational, self-evidently-useful, non-channel-dependent artifacts (design system,
  metadata schema, testing protocol).
- `outputLicense` — **MIT** for tooling/code; **CC-BY-4.0** for artwork, metadata, specs, guides,
  and labels (CC0 is an open question for AI-authored artwork — see PLAN); **OFL** for any bundled
  font.

At production scale this project fans out: **one symbol (or small concept batch) = one task**, drawn
from a milestone-scoped concept list (the `*-draw-*` and `*-batch-*` tasks are the fan-out
templates).

---

## Milestone M0 — Foundation & cold-start

Prove one symbol can travel from concept → drawn → tested with real users → exported → toward
deployment, and lock the foundations (design system, schema, protocol, partner gate).

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| open-pictograms-design-001 | Author the pictogram design system v1 (grid/stroke/palette/abstraction/a11y/safety rules) | design-spec | medium | low | document | — | Maintainer |
| open-pictograms-data-001 | Define per-symbol metadata schema + originality/license policy | data | small | low | dataset | design-001 | Maintainer |
| open-pictograms-writing-001 | Write the ISO 9186-based comprehension-test + consent/ethics protocol | writing | medium | low | document | — | Comprehension coordinator |
| open-pictograms-research-001 | Secure ≥1 partner/validation channel (AAC platform, facility, or NGO) | research | medium | low | document | — | Maintainer + Steward |
| open-pictograms-research-002 | Verify license/originality rules + allowed references (AIGA/DOT PD; ISO concepts) | research | small | medium | document | — | Maintainer |
| open-pictograms-code-001 | Build pipeline v0: SVG normalize + style-lint + PNG/sprite/OBF export | code | large | low | pr | design-001, data-001 | Maintainer |
| open-pictograms-draw-001 | Draw + test the 12-symbol seed set (communication/wayfinding/cultural/safety) | data | medium | medium | dataset | design-001, data-001, writing-001, research-002, code-001 | Cultural + safety reviewer |

**Sequencing — partner-securing gates field validation, not the foundations.** `research-001` is a
**blocking prerequisite for deployment and beneficiary field-validation** (M2), not for the
foundational artifacts or the *internally pilotable* seed test. If the time-boxed effort secures no
partner, the project records its **kill/pivot criteria** (next candidate channel, or pause scaling)
rather than mass-producing untested, undeployed symbols.

**Key task acceptance criteria**

- **open-pictograms-design-001** (design system v1)
  - [ ] Specifies canvas/viewBox, grid, stroke weight, corner treatment, level of abstraction, and
        fill/stroke rules so symbols are visually consistent.
  - [ ] Defines the color palette **and** a strict monochrome/high-contrast variant for print,
        low-vision, and distance wayfinding; defines directional (RTL/mirror) variant rules.
  - [ ] Includes SVG accessibility requirements (`<title>` / `role="img"`) and a naming convention.
  - [ ] Has a dedicated **safety-subset** section (stricter threshold, expert review, "not certified
        / not advice" disclaimer) and a do/don't gallery covering dignity/cultural pitfalls.
  - [ ] Published, versioned, and licensed CC-BY-4.0.

- **open-pictograms-research-001** (secure a partner/validation channel)
  - [ ] Evaluates candidate channels in priority order (open AAC platform/Global Symbols/OBF → a
        facility or humanitarian/education partner → Elyos siblings) with each one's acceptance
        posture, and applies the PLAN decision tree.
  - [ ] Identifies ≥1 concrete channel confirmed to host, install, or field-test the set.
  - [ ] Records the channel's required format(s), license preference (CC-BY vs CC0), and any ethics/
        consent process for testing with beneficiaries.
  - [ ] States the time-box and the kill/pivot criteria if no channel is secured.
  - [ ] On success, flips `verifiedNeed=true` for tasks targeting that channel.

- **open-pictograms-writing-001** (comprehension + ethics protocol)
  - [ ] Operationalizes the ISO 9186 comprehension test and judgement test, with scoring
        (correct %, critical-confusion %, n, population, date) and the use-dependent thresholds
        (≥67% general; ≥85% + <5% critical confusion for safety).
  - [ ] Specifies informed/supported **consent**, guardian consent for minors, and deference to a
        partner's ethics/IRB; mandates aggregate, de-identified results only.
  - [ ] Defines the redesign-and-retest loop for symbols that fail.

- **open-pictograms-draw-001** (12-symbol seed set, drawn + tested)
  - [ ] Seed set spans every path: several everyday **communication** symbols, several **wayfinding**
        symbols, ≥1 **culturally-variable** concept (with a regional variant), ≥1 **safety-aligned**
        symbol — not 12 trivial icons.
  - [ ] All 12 are **original geometry** (originality attestation recorded), reference only PD/
        permissive sources, and **pass the style lint**.
  - [ ] ≥1 comprehension pilot run with target-population participants (or an honestly-labeled
        judgement-test pilot if participant access is not yet available), with recorded scores; the
        safety-aligned symbol is expert-reviewed and disclaimered; ≥1 symbol culturally cleared.
  - [ ] Each symbol exports cleanly to SVG/PNG/sprite/OBF with complete metadata + provenance.

**M0 Definition of Done:** design system v1, metadata schema, and comprehension/ethics protocol
published; build pipeline v0 produces SVG/PNG/sprite/OBF with a working style-lint gate; ≥12 seed
symbols drawn and style-passed across all four paths; ≥1 comprehension pilot run with recorded
scores; ≥1 partner channel confirmed **or** kill/pivot recorded; zero originality/license
violations.

---

## Milestone M1 — Pipeline & first tested release

Turn the manual slice into a repeatable build and ship a usable, comprehension-tested core release.

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| open-pictograms-code-002 | CI build automation (lint → PNG/sprite/font/OBF → catalog site) | code | large | low | pr | code-001 | Maintainer |
| open-pictograms-code-003 | OBF export adapter for AAC board builders | code | medium | low | pr | data-001, code-001 | Maintainer |
| open-pictograms-writing-002 | Reviewer workflow + cultural-review checklist + safety-review SOP | writing | small | low | document | design-001, writing-001 | Maintainer |
| open-pictograms-batch-001 | Draw + test core communication vocabulary (~60 symbols) | data | large | low | dataset | code-002, writing-002 | Reviewer rotation |
| open-pictograms-batch-002 | Draw + test wayfinding inventory for one facility type (~40 symbols) | data | large | low | dataset | code-002, writing-002 | Reviewer rotation |
| open-pictograms-translation-001 | Vetted labels in ≥2 languages (fluent-reviewed) | writing | medium | medium | translation | batch-001 | Cultural / localization reviewers |
| open-pictograms-code-004 | Catalog/reference site (browse/search/download + comprehension evidence) | code | medium | low | pr | code-002 | Maintainer |

**Key task acceptance criteria**

- **open-pictograms-code-002** (CI build automation)
  - [ ] One command builds, from SVG source, all formats (PNG sizes, sprite, optional font, OBF) and
        regenerates the catalog; runs green in CI.
  - [ ] Style-lint failures and metadata-schema violations **fail the build** (no untested/
        non-conformant symbol ships).
  - [ ] No secrets in logs/artifacts; DCO sign-off enforced.

- **open-pictograms-batch-001** (core communication vocabulary)
  - [ ] ~60 symbols covering an AAC/low-literacy core set (needs, actions, feelings, people, places,
        time, health basics), all original + style-passed.
  - [ ] Each shipped symbol has a comprehension score ≥67% (general threshold) with the target
        population; below-threshold symbols are redesigned/retested or held back.
  - [ ] People/body/concept symbols culturally cleared; metadata + provenance complete.

- **open-pictograms-translation-001** (vetted labels)
  - [ ] Labels in ≥2 languages, each reviewed by a fluent speaker with reviewer provenance recorded.
  - [ ] No raw machine-translation shipped; symbols remain usable without the label.

**M1 Definition of Done:** CI build green; ≥100 symbols shipped (style-passed + comprehension-passed
+ culturally cleared) across core communication + one wayfinding inventory; OBF export working;
labels vetted in ≥2 languages; catalog site published with per-symbol comprehension evidence;
reviewer workflow documented with ≥2 reviewers + ≥1 cultural reviewer onboarded; zero license
violations.

---

## Milestone M2 — Scale, localize & validate in the field

Grow coverage, localize, and prove real-world use with a secured partner. (Field-validation and
deployment tasks require `research-001`'s partner; `verifiedNeed` flips to `true` once secured.)

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| open-pictograms-batch-003 | Scale to ≥300 shipped symbols across categories | data | large | low | dataset | batch-001, batch-002 | Reviewer rotation |
| open-pictograms-batch-004 | Safety-aligned subset (expert-signed, stricter threshold, disclaimered) | data | medium | medium | dataset | writing-002, batch-001 | Safety-domain expert |
| open-pictograms-translation-002 | Localize labels to ≥3 languages + regional/directional variants | writing | large | medium | translation | batch-003 | Cultural / localization reviewers |
| open-pictograms-code-005 | Printable signage-sheet adapter (ties to multilingual-signage-templates) | code | medium | low | pr | code-002 | Maintainer |
| open-pictograms-research-003 | Field deployment + beneficiary validation with secured partner | research | medium | low | document | research-001, batch-003 | Steward |

**Key task acceptance criteria**

- **open-pictograms-batch-004** (safety-aligned subset)
  - [ ] Each safety symbol aligns to recognized concepts (AIGA/DOT PD, ISO 7010/7001/GHS *concept*
        references — no copied artwork) and is **original geometry**.
  - [ ] Meets the stricter bar: ≥85% correct comprehension and <5% critical confusion; any failure
        is redesigned/retested or **withdrawn** (never shipped "good enough").
  - [ ] Each carries the "not certified safety signage / not medical advice" disclaimer and has
        **domain-expert sign-off** recorded in provenance.

- **open-pictograms-research-003** (field deployment + beneficiary validation)
  - [ ] ≥1 **confirmed real deployment** (installed signage / live AAC board / distributed toolkit)
        with the secured partner.
  - [ ] ≥2 beneficiary-validation sessions across ≥2 contexts (e.g. a low-literacy/AAC user and
        facility staff) confirm usability; findings feed back into design/cultural reviews.
  - [ ] Consent + de-identification honored per the M0 protocol.

**M2 Definition of Done:** ≥300 symbols shipped; safety subset 100% expert-signed at its stricter
threshold; labels vetted in ≥3 languages with regional/directional variants; ≥1 confirmed
deployment + ≥2 beneficiary validations; signage + OBF adapters validated by a downstream consumer;
zero license/originality violations.

---

## Milestone M3 — Sustain, interoperate & govern

| ID | Title | Type | Size | Risk | Deliverable | Depends on | Reviewer |
|---|---|---|---|---|---|---|---|
| open-pictograms-writing-003 | Contribution guide + symbol-intake governance (test/cultural/safety gates) | writing | medium | low | document | writing-002 | Maintainer |
| open-pictograms-code-006 | Interop: Global Symbols import / OBF round-trip validation | code | medium | low | pr | code-003 | Maintainer |
| open-pictograms-maint-001 | Versioned releases + changelog + outcome-tracking of deployments | maintenance | small | low | pr | code-002 | Maintainer / Steward |

**M3 Definition of Done:** contribution guide + governance published; interop confirmed with ≥1
external ecosystem; versioned releases + outcome tracking live; maintainer + reviewer rotation
documented and in effect.

---

## Backlog / future (sized, unscheduled)

| ID | Title | Type | Size | Risk | Deliverable | Notes |
|---|---|---|---|---|---|---|
| open-pictograms-code-007 | Icon-font build (if consumers need it) | code | medium | low | pr | Pending font-vs-SVG decision (Open question) |
| open-pictograms-batch-005 | Additional facility wayfinding inventories (clinic/shelter/school/transit) | data | large | low | dataset | Per-partner demand |
| open-pictograms-translation-003 | Expand to additional low-resource languages | writing | large | medium | translation | Needs fluent reviewers per locale |
| open-pictograms-research-004 | Legal review: AI-artwork copyrightability → CC-BY vs CC0 | research | small | low | document | Resolves a headline Open question |
| open-pictograms-data-002 | Comprehension + adoption analytics (aggregate, de-identified) | data | small | low | dataset | Sustainability/outcome metric |
| open-pictograms-maint-002 | Re-check safety subset against standard updates | maintenance | small | medium | document | Ongoing post-delivery |

---

## Example task JSON

Complete, schema-valid Task JSON for the first M0 task. `verifiedNeed` is `true` here: a published,
openly-licensed design system is a foundational, self-evidently-useful artifact that does not depend
on a partner/delivery channel being secured (unlike the deployment/field-validation tasks, which are
`false` until M0's `research-001` confirms a channel).

```json
{
  "id": "open-pictograms-design-001",
  "title": "Author the pictogram design system v1 (grid/stroke/palette/abstraction/a11y/safety rules)",
  "project": "open-pictograms",
  "type": "design-spec",
  "lane": "donated",
  "priority": "high",
  "domain": ["accessibility", "communication", "wayfinding", "open-culture", "design"],
  "riskTier": "low",
  "urgent": false,
  "deliverable": "document",
  "tokenEstimate": "medium",
  "status": "open",
  "context": "People who cannot read the local language - low-literacy and pre-literacy adults, non-speaking AAC users, refugees, and people in emergencies - depend on pictograms to be understood. Existing open symbol sets are often non-commercial or share-alike licensed, stylistically inconsistent, or untested with target users. Before any symbol is drawn at scale, open-pictograms needs a single, versioned design system so that symbols authored by many parallel AI sessions are visually consistent, accessible, dignified, and safe.",
  "objective": "Write and publish version 1 of the design system that all draw/batch tasks will follow: grid, stroke, palette, abstraction level, SVG accessibility, naming, monochrome/directional variants, and the privileged-safety-subset rules.",
  "acceptanceCriteria": [
    "Specifies canvas/viewBox, grid, stroke weight, corner treatment, abstraction level, and fill/stroke rules for visual consistency.",
    "Defines the color palette plus a strict monochrome/high-contrast variant (print, low-vision, distance wayfinding) and directional (RTL/mirror) variant rules.",
    "Requires SVG accessibility (title/role=img) and a stable naming convention, and is machine-checkable by the style-lint gate.",
    "Includes a safety-subset section (stricter comprehension threshold, domain-expert sign-off, and a 'not certified safety signage / not medical advice' disclaimer) and a do/don't gallery covering dignity and cultural pitfalls.",
    "Requires original vector geometry only (no traced/copyrighted art; AIGA/DOT public-domain references permitted) and is published, versioned, and licensed CC-BY-4.0."
  ],
  "resources": [
    "C:\\code\\elyos\\planning\\projects\\open-pictograms\\PLAN.md",
    "C:\\code\\elyos\\docs\\good-deed-definition.md",
    "ISO 9186 (graphical-symbol comprehensibility method - reference only, not redistributed)",
    "AIGA/DOT Symbol Signs (public domain)",
    "Creative Commons CC-BY-4.0; SIL Open Font License"
  ],
  "output": "A versioned design-system document (design-system/design-system.md) plus the machine-checkable style rules, CC-BY-4.0, covering grid/stroke/palette/abstraction, SVG accessibility, naming, monochrome/directional variants, originality/license policy, and the safety-subset rules.",
  "requestor": "jdev1977",
  "verifiedNeed": true,
  "outputLicense": "CC-BY-4.0"
}
```
