# AP Human Geography — Course Notes

Student notes for AP Human Geography, built as self-contained web pages — one per unit.

**Live site:** https://bluegrassbaron.github.io/ap-human-geography/

| | Unit | Status |
|---|---|---|
| 1 | [Thinking Geographically](https://bluegrassbaron.github.io/ap-human-geography/unit-1/) | Complete |
| 2 | Population & Migration | Not yet written |
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

## Repository layout

```
index.html          course landing page, links to each unit
unit-1/index.html   Unit 1 notes — the whole unit in one file
README.md
.nojekyll           serve files as-is, no Jekyll processing
```

To add a unit later: create `unit-N/index.html` and flip that unit's card on the
landing page from `<div class="unit soon">` to `<a class="unit" href="unit-N/">`.

## Technical notes

- One file per unit. No build step, no dependencies, no JavaScript framework.
- All CSS and SVG are inline. The only external request is Google Fonts
  (Archivo, Newsreader, IBM Plex Mono), each with a real fallback stack.
- Responds to the reader's light/dark preference via CSS custom properties.
- Works on a phone; wide diagrams and tables scroll inside their own containers.
- Includes print styles — each plate starts on a new page if students want paper.

## Editing

Open the unit's `index.html` in any text editor. The design tokens (colors, type, spacing)
are the CSS custom properties in the `:root` block at the top; changing a value
there updates the whole page, diagrams included, in both themes.

## A note on accuracy

Content is aligned to the College Board Course and Exam Description for AP Human
Geography — enduring understandings IMP-1, PSO-1, and SPS-1. Learning-objective
codes are quoted from the CED. Skill-category codes are deliberately **not**
included, since the topic-to-skill pairings could not be verified against a
primary source.

AP® is a trademark registered by the College Board, which was not involved in the
production of these notes.
