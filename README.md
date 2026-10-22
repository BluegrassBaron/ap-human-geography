# AP Human Geography — Course Notes

Student notes for AP Human Geography, built as self-contained web pages — one per unit.

**Live site:** https://bluegrassbaron.github.io/ap-human-geography/

| | Unit | Status |
|---|---|---|
| 1 | [Thinking Geographically](https://bluegrassbaron.github.io/ap-human-geography/unit-1/) | Complete |
| 2 | [Population & Migration](https://bluegrassbaron.github.io/ap-human-geography/unit-2/) | Complete |
| 3 | Cultural Patterns & Processes | Not yet written |
| 4 | Political Patterns & Processes | Not yet written |
| 5 | Agriculture & Rural Land Use | Not yet written |
| 6 | Cities & Urban Land Use | Not yet written |
| 7 | Industrial & Economic Development | Not yet written |

---

## Unit 1 — what's in it

Seven "plates," one per CED topic, each opening with the College Board learning
objective it covers:

| Topic | Learning objective | |
|---|---|---|
| 1.1 | `IMP-1.A` | Introduction to Maps |
| 1.2 | `IMP-1.B` | Geographic Data |
| 1.3 | `IMP-1.C` | The Power of Geographic Data |
| 1.4 | `PSO-1.A` | Spatial Concepts |
| 1.5 | `PSO-1.B` | Human–Environmental Interaction |
| 1.6 | `PSO-1.C` · `PSO-1.D` | Scales of Analysis |
| 1.7 | `SPS-1.A` | Regional Analysis |

Plus an **exam kit** appendix: a one-page topic summary, a guide to what the command
verbs (identify / describe / explain / compare) actually require, a vocabulary
self-quiz checklist, and four synthesis questions that cross topics.

Every plate contains a big-idea framing, vocabulary keys, a "common trap" callout
naming the specific mistake that costs points, an exam-technique note, and
expandable check-yourself questions with model answers.

**22 diagrams**, all hand-authored inline SVG — no libraries, no image files.
Highlights: Tissot's indicatrix across three projections; six thematic map types
drawn on one imaginary country; a 25-voter gerrymandering demonstration where three
legal districting plans produce three different governments; environmental
determinism vs. possibilism drawn as a difference in arrows; a nested
global → national → regional → local scale zoom.

**35 self-check questions** with full answers.

## Unit 2 — what's in it

Twelve plates, one per CED topic, each opening with its learning objective(s) and a
"Read to answer" box that turns the plate's headings into questions — guided notes
for students who need a purpose before they read:

| Topic | Learning objective | |
|---|---|---|
| 2.1 | `PSO-2.A` · `PSO-2.B` · `PSO-2.C` | Population Distribution |
| 2.2 | `PSO-2.D` | Consequences of Population Distribution |
| 2.3 | `PSO-2.E` · `PSO-2.F` | Population Composition |
| 2.4 | `IMP-2.A` | Population Dynamics |
| 2.5 | `IMP-2.B` | The Demographic Transition Model |
| 2.6 | `IMP-2.B` | Malthusian Theory |
| 2.7 | `SPS-2.A` | Population Policies |
| 2.8 | `SPS-2.B` | Women and Demographic Change |
| 2.9 | `SPS-2.C` | Aging Populations |
| 2.10 | `IMP-2.C` | Causes of Migration |
| 2.11 | `IMP-2.D` | Forced and Voluntary Migration |
| 2.12 | `IMP-2.E` | Effects of Migration |

Plus an **exam kit** appendix: one sentence per topic, every formula in the unit on
one card each (three densities, RNI, doubling time, dependency ratio, sex ratio,
gravity model), the command verbs, a term checklist, and four synthesis questions.

Same plate anatomy as Unit 1 — vocabulary keys, "common trap" and exam-technique
callouts, check-yourself questions — plus worked-calculation boxes.

**27 diagrams**, all inline SVG. Highlights: one imaginary country's arithmetic,
physiological, and agricultural density drawn on a single grid; an annotated
pyramid plus six more showing growth shapes and migration fingerprints; the DTM
with natural increase shaded and a pyramid silhouette under each stage; Malthus
vs. Boserup as opposite arrows; a policy map from persuasion to coercion; a
same-dependency-ratio, opposite-problems pictograph; a refugee / IDP / asylum
seeker decision tree.

**52 self-check questions** with full answers.

**Review game:** `unit-2/jeopardy.html` — Geo Jeopardy on the Unit 1 engine, seven
categories covering all twelve topics, 35 multiple-choice clues plus a final round,
each with an explanation. Linked from the Unit 2 rail, the exam kit, and the landing page.

Current figures (UN World Population Prospects 2024, UNHCR mid-2025, World Bank
2024 remittances, national statistics for China, Japan, South Korea, and the U.S.)
are dated in the text and listed in the page footer.

## Repository layout

```
index.html          course landing page, links to each unit
unit-1/index.html   Unit 1 notes — the whole unit in one file
unit-1/jeopardy.html  Unit 1 review game (Geo Jeopardy, 1–8 players, multiple choice)
unit-2/index.html   Unit 2 notes — the whole unit in one file
unit-2/jeopardy.html  Unit 2 review game (Geo Jeopardy, same engine as Unit 1)
README.md
.nojekyll           serve files as-is, no Jekyll processing
```

To add a unit later: create `unit-N/index.html` and flip that unit's card on the
landing page from `<div class="unit soon">` to `<a class="unit" href="unit-N/">`.

## Technical notes

- One file per unit. No build step, no dependencies, no JavaScript framework.
- All CSS and SVG are inline. The only external request is Google Fonts
  (Archivo, Newsreader, IBM Plex Mono), each with a real fallback stack.
- Works on a phone; wide diagrams and tables scroll inside their own containers.

### Light by default, dark on request

Every page loads on paper-colored stock regardless of the device's system
setting — what a student sees on screen is what comes out of the printer. A
toggle in the masthead switches to dark, and the choice is kept in
`localStorage` under `aphug-theme` and applied by a tiny inline script in the
`<head>`, so there is no flash of the wrong theme on the next page load.

### Printing

The pages are built to print correctly with the browser's **"Background
graphics" box left off**, which is how it ships. Nothing that carries meaning
lives in a CSS background: tinted callouts become heavy left rules, filled
chips become outlined ones, the dark "check yourself" bar becomes a ruled
heading, and the maroon masthead becomes a slug line. Backgrounds left *on*
also look right — the print sheet forces the light palette either way, so a
student reading in dark mode still gets black on white.

Diagrams are inline SVG, so their fills are page content and print regardless
of that setting.

Other print behavior:

- Each plate starts on a new sheet; the exam kit starts its own.
- Every collapsed self-check answer opens on paper, so the printout is a
  complete study guide. Handled twice over: a `beforeprint` listener sets
  `open` on each `<details>` (and `afterprint` puts them back), and the print
  sheet also overrides `::details-content` for the JavaScript-off case.
- Type is set in points, margins in inches, with orphan/widow control and
  `break-inside: avoid` on figures, tables, callouts and question blocks.
- The rail, the back link and the theme toggle drop out.

## Editing

Open the unit's `index.html` in any text editor. The design tokens (colors, type, spacing)
are the CSS custom properties in the `:root` block at the top; changing a value
there updates the whole page, diagrams included. There are three sets of those
tokens: `:root` (light, the default), `:root[data-theme="dark"]`, and a third
set inside `@media print` that forces paper-white whatever the reader chose.

## A note on accuracy

Content is aligned to the College Board Course and Exam Description for AP Human
Geography — enduring understandings IMP-1, PSO-1, and SPS-1. Learning-objective
codes are quoted from the CED. Skill-category codes are deliberately **not**
included, since the topic-to-skill pairings could not be verified against a
primary source.

AP® is a trademark registered by the College Board, which was not involved in the
production of these notes.
