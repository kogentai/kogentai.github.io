# Lights toggle as the offering split

Date: 2026-08-18
Status: rev 4, built and verified in browser on 2026-08-18.
Scope: `index.html` only

Rev 4 follows three adversarial reviews (copy/positioning, front-end/a11y,
grounding fact-check). Changes from rev 3 are marked **[R4]**.

## The idea

Today the Lights toggle is a theme switch. It changes colors and nothing else,
which wastes the strongest metaphor on the page.

This change makes the toggle the argument. The site carries two readings of the
same offering:

- **Lights off** is the half that runs without you: context supply,
  verification, unattended operation up to the review gate.
- **Lights on** is the half that will not start without you: requirements,
  product direction, knowledge work.

## The correction this makes **[R4]**

The grounding review found a verbatim contradiction between the live site and
the product:

&gt; "**Human review, then PR.** Version one is deliberately *lights-on*: every run
&gt; routes to a human review gate."
&gt; — `understanding-majordomo.md:133`

The site says the factory "runs lights-out" and "doesn't stop to ask." The
product deliberately stops for a person on every run. That was the single
highest-risk line on the page, and it shipped before this plan existed.

So the dark half gets the honesty pass too. The factory runs dark from intake
through generation, verification, and repair, and comes to you at the review
gate **by design**. That is a more credible story than full autonomy and it is
the actual differentiator against vendors claiming lights-out. It also makes
the toggle the point rather than a contradiction.

## The load bearing distinction

- A machine can prove a change **matches its specification**: spec-derived
  tests authored before the change, hidden from the generator, run on a
  pristine clone. This is lights off.
- A machine cannot tell you the **specification was worth writing**, or that
  what came back is **any good**. This is lights on: requirements and taste.

Verification therefore sits on the dark side without conflicting with the light
side owning the specification it checks against, **provided the dark copy says
"matches the spec" and not "is right"** — rev 3 said "is right" and contradicted
its own light-mode prose one toggle away. **[R4]**

## Grounding in Majordomo

| Source | What it grounds |
|---|---|
| `understanding-majordomo.md`, "coding got fast, delivery didn't" | The bottleneck moved off the keyboard onto specification and validation. The spine of the light argument. Verbatim support. |
| `understanding-majordomo.md:133` | Version one is deliberately lights-on, every run routes to a human review gate. Forces the honest dark rewrite. **[R4]** |
| `understanding-majordomo.md`, Factory steps 3 to 5 | One acceptance test per functional criterion, proven to fail on the untouched repo, generator-blind, run on a pristine clone; reward guard routes cheating runs to a human. All Shipped. Grounds the Verification card. |
| `understanding-majordomo.md`, intake and admission | Deterministic admission refuses empty specs, specs below a completeness threshold, and specs with no testable criteria. "The load-bearing decision, refuse fuzzy specs, is made by deterministic code, not by a model." Grounds the Requirements card. |
| Offering overview, Mode:Research | Knowledge graph, release brief, personas, journey maps, evidence over instinct, traceable to source. Grounds Product direction and Knowledge work. |
| `understanding-majordomo.md:137` | "Every run is recorded as a replayable run record, so *why did the agent do that?* is always answerable." Shipped. Grounds the Knowledge work payoff line. **[R4: replaces the rev 3 citation, which quoted the sources' problem statement about the status-quo tool pile as if it were a capability claim.]** |

**Dropped in rev 4.** Rev 3 cited the roadmap's "two layers a machine consumes
versus the two a person consumes" as the product stating the requirements-and-
taste split itself. It does not. Those two layers are executable scenarios and
a conformance scorecard, which T1 and T2 exist to **automate**. The marketing
distinction stands on the specification/validation framing; it does not get to
claim that citation.

## Claims deliberately not made **[R4]**

- Not "it does what the spec said" as a behavioral claim. `spec-to-solution:72`
  says "Nothing above L2 exists today"; verification against the *running*
  product is T1 and unbuilt.
- Not "reward hacking gets caught." The guard is Shipped, but T3 exists to
  publish a catch rate that has never been measured and to close the open
  "green-means-correct was never red-teamed" finding.
- Not "starts from certainty." Admission enforces a completeness threshold and
  the validator "proposes" completeness. A threshold-passing spec is a strong
  start, not certainty.
- Not "runs lights-out." See above.

## Copy: lights off (dark)

| Slot | Copy |
|---|---|
| Eyebrow **[R5]** | The factory floor `·` agentic engineering era |
| H1 | The dark factory stops for one thing: *context*. |
| Lede **[R4]** | Kogent builds solutions for knowledge work in the agentic engineering era. We supply the *context* a fleet of agents needs, so the line runs dark from intake to review without stopping to ask. |
| Quiet link | What we build |
| Mode invitation **[R4]** | Turn the lights on. See where you come in. |
| Floor status | Lights off `·` the line is running |
| Shift label | The shift |
| Shift H2 | Software production is going dark. |
| Shift prose | unchanged, both paragraphs |
| Build label | What we build |
| Bridge line **[R4]** | This is the half that runs without you. Turn the lights on for the other half. |
| Contact H2 | Where does your factory still stop? |
| Contact prose | Tell us where agents wait on people, and we'll show you what context can close. |

Lede changes: drops "runs lights-out" (unsupported), drops "resolve the
*ambiguity*" so that ambiguity has one owner on the page rather than being
claimed by the vendor in dark mode and by the reader in light mode.

### Cards

**Card 1** `CONTEXT SUPPLY` — unchanged.
**Everything the factory needs to know**
We capture intent, decisions, constraints, and domain knowledge, then keep it
current in a form agents consume without asking a human.

**Card 2** `VERIFICATION` — replaces Knowledge work.
**Proof the change matches the spec, before anyone looks**
Tests derived from the criteria, written before the change and hidden from the
agent that writes it. One that games its tests gets routed to a person, not
merged.

**Card 3** `UNATTENDED OPERATION` — replaces Lights-out operations. **[R4]**
**It runs dark until it needs you**
Intake, generation, verification, and repair proceed with nobody in the loop.
The line comes to you at the review gate, by design, and nowhere else.

## Copy: lights on (bright)

| Slot | Copy |
|---|---|
| Eyebrow **[R4]** | Control room `·` agentic engineering era |
| H1 | The lights come on for two things: *requirements* and *taste*. |
| Lede | Coding got fast. Deciding what to build, and knowing whether what came back is any *good*, did not. Kogent builds the instruments for that work, at the pace of an agent fleet. |
| Quiet link | Where you come in |
| Mode invitation **[R4]** | Turn the lights off. See what runs without you. |
| Floor status | Lights on `·` the line is waiting on you |
| Shift label | The bottleneck |
| Shift H2 | The bottleneck moved off the keyboard. |
| Build label | Where you come in |
| Bridge line **[R4]** | This is the half that needs you. Turn the lights off for the other half. |
| Contact H2 | What is your factory waiting on you for? |
| Contact prose | Tell us where the answer still has to come from a person, and we'll show you what to hand the line instead. |

Eyebrow changed from "Requirements and taste" because it announced the H1's
payload one line before the reveal. The dark side does not make that mistake.

### Shift prose

**Prose 1**
Agents now write, test, and review faster than any team can keep up with. Yet
delivery has barely sped up, because the constraint was never typing. It sits
on either side of the keyboard: deciding precisely what to build, and knowing
what to make of what came back.

**Prose 2** **[R4]**
Gates can prove a change matches its specification. Nothing can prove the
specification was worth writing, or that the result is any good. Lights that
come on because a question went unanswered are a **failure**. Lights on because
it is your turn are the **design**.

The last two sentences are the signpost the copy review asked for. The dark
shift section says "every question turns the lights back on," treating
lights-on as failure, while this H1 celebrates it. Without the signpost the same
metaphor carries opposite valence on one page.

### Cards

**Card 1** `REQUIREMENTS`
**Say what to build, precisely enough**
Ambiguity is cheap to resolve now and ruinous later. Intent becomes a
specification with criteria a machine can hold you to, and a fuzzy spec gets
refused before a run starts.

**Card 2** `PRODUCT DIRECTION` — rewritten. **[R4]**
**Decide with evidence, not instinct**
A release brief built from research. Personas, trade-offs, and journey maps you
can trace to their source. What separates a good release from a busy one gets
decided before the first agent runs.

Rev 3's version ("Decide what is worth building" over four abstract nouns) was
a category slogan any roadmap vendor could run unchanged, and it discarded the
concrete artifacts the grounding table had already found.

**Card 3** `KNOWLEDGE WORK`
**The record the factory reads and writes**
Decisions, domain knowledge, and the documents that carry them, captured as
durable artifacts traceable to their source. Ask why the agent did that and get
an answer.

## Head metadata **[R4]**

Both reviews flagged that the head tells only the dark story, so every link
preview omits half the offering forever.

- `<title>` unchanged.
- `meta description` and `og:description` rewritten to carry both halves.
- Add `<meta name="color-scheme" content="dark light">`.
- Record the decision: `prefers-color-scheme` is deliberately **not** honored.
  The reader is meant to arrive in the dark. Rev 3 left this unstated, which
  made it an accident rather than a choice.

## Making the toggle findable

1. **Pill the control.** `.lights` gains `background: var(--bg-raised)`, a
   hairline border, `border-radius: 999px`, `padding: 0.4rem 0.85rem`, and
   `color: var(--text)` in place of `--muted`.

2. **Attention pulse until first use.** If no `kogent-lights` key exists, the
   dot and border pulse slowly. Removed on first click. See the storage
   hardening note below, which is not optional.

3. **A mode invitation in the hero**, in `.cta-row`, naming the control and the
   destination. Split into two sentences rather than joined by a colon **[R4]**,
   because the em-dash purge in 993fad7 left the page with a colon habit and
   rev 3 put a colon in both H1s and the invitation, visible in one viewport.

4. **A bridge line above the cards** **[R4]**, mode-aware and also wired to the
   toggle. Its tail is kept short and `.bridge` is `max-width: 76ch` so the
   sentence and the button hold **one line in both modes**. The button is an
   inline-block and cannot break internally, so a longer tail drops the whole
   control onto its own line, which reads as a deliberate two-line layout in
   one mode and not the other. Measured: one line at 1280px in both modes,
   two lines at 390px in both modes. This is a second discovery path, and it fixes the copy review's
   first insist: without it the default page shows three cards that any agent
   infrastructure vendor could claim and hides the differentiated half entirely,
   with nothing on screen admitting the other half exists.

## Implementation

### Content swap

Both copies in the DOM, CSS decides which is visible.

```css
html[data-lights="off"] [data-mode="on"],
html[data-lights="on"]  [data-mode="off"] { display: none; }
```

Verified against the file: the inline script at `index.html:13-18` is
synchronous in `<head>` and no body content exists yet, so the correct copy is
the only copy painted. `body`'s `transition` at line 56 does not fire on initial
style computation. **No flash, confirmed.**

`display: none` removes the hidden half from the accessibility tree.

**Correction to rev 3 [R4]:** rev 3 claimed "the page needs no JS to be readable
and both readings are crawlable." Half wrong. With JS disabled the light half is
unreachable, since nothing can flip the attribute. And a rendering crawler sees
the hidden half as `display:none` duplicated content, which is indexed but
discounted. The dark reading is the canonical one; the light reading is not an
equal SEO surface. Accepted, not fixed.

### Duplication granularity **[R4]**

Element level only. Explicitly:

- **Never** duplicate `<section id="what-we-build">`. Duplicating it would give
  two elements the same id and let the hero anchor at line 390 resolve to a
  `display:none` copy, scrolling nowhere.
- **Delete** `id="floor-status"` (line 392) rather than copying it onto both
  spans. The id exists only so the JS at line 453 can find it, and that JS is
  going away.
- Two `<h1>`s, one hidden, is fine. Multiple h1s are valid and the hidden one
  is out of the a11y tree.

### Motion: rewritten **[R4]**

**Rev 3's motion section was unimplementable.** `rise` is bound at lines 344-350
to `.hero .eyebrow, .hero h1, .hero p, .hero .cta-row, .hero .floor-status` with
staggered `animation-delay`. Those are the exact elements being duplicated, and
`animation` is a shorthand, so a second declaration cascades against the first
rather than adding to it:

- `.hero [data-mode]` has specificity (0,2,0) and beats `.hero h1` at (0,1,1),
  resetting `animation-delay` to 0s and killing the load stagger.
- Bare `[data-mode]` at (0,1,0) loses in the hero and is inert there, while
  firing on the shift, cards, and contact blocks on **first paint**, animating
  sections that do not animate today.

There is no pure-CSS way to distinguish "just became visible" from "first
paint."

**Replacement: `document.startViewTransition`.** It snapshots before and after
and crossfades, which solves the cascade problem and the layout jump in one
move. Feature-detect and fall back to a plain instant swap. Skip it entirely
under `prefers-reduced-motion: reduce`. The `rise` block at 344-350 is not
touched.

### Layout jump **[R4]**

Rev 3 waved this through as "slight." Measured: `h1` is
`clamp(2.6rem, 7vw, 4.8rem)` at `line-height: 1.02`, `max-width: 21ch`. The
light H1 is about 25% longer than the dark one, so at desktop width it wraps
roughly one line taller and shifts everything below by around 77px; at 390px
the shift is 42 to 84px.

The problem this creates: the hero invitation sits **below** the h1 and lede, so
clicking it moves it out from under the cursor. The view transition crossfade
largely absorbs this visually. Accepted with that mitigation, not ignored.

### The hero invitation button **[R4]**

Rev 3 said "styled as a `quiet-link` but rendered as a `<button>`" and budgeted
no CSS. `.quiet-link` at lines 229-237 sets only six properties and has no
`:focus-visible` rule. On a bare `<button>` that yields: UA default typeface
(buttons do not inherit `font-family`, and the `*` reset at line 46 touches only
margin, padding, and box-sizing), a gray `ButtonFace` background, the UA's top,
left, and right borders alongside `.quiet-link`'s single `border-bottom`, no
`cursor: pointer`, no focus ring, and misalignment against `align-items: center`
in `.cta-row`.

Required: `appearance: none; background: none; border: none; font: inherit;
cursor: pointer`, re-add `border-bottom`, and add a `:focus-visible` matching
`.btn` at line 228. Add the focus rule to `.quiet-link` generally, since its
absence is a pre-existing gap on the existing anchor too.

### Focus and announcement **[R4]**

The largest a11y gap in rev 3, which covered the hidden half and said nothing
about the event.

- **One button, two label spans.** Every toggle control is a single persistent
  `<button>` whose *label* swaps, never two `[data-mode]` buttons. If the
  focused button itself were hidden, focus would drop to `<body>` and strand
  the keyboard user mid-page. This applies to the header toggle, the hero
  invitation, and the bridge line.
- **Announce the swap.** A visually hidden `aria-live="polite"` region reports
  the new reading on toggle. Otherwise a screen reader hears "pressed" while
  the h1, lede, section, three cards, and contact copy all change silently.
- **Stable accessible name.** Keep `aria-pressed` but stop swapping
  `aria-label` (lines 456-457). Changing an accessible name on state change is
  a known antipattern and double-encodes state against `aria-pressed`. The name
  becomes a constant, "Factory lights."
- `role="switch"` is rejected: a switch implies a setting, and this plan's whole
  argument is that the toggle is not a preference.

### Storage hardening **[R4]**

The hint branch is new code in the bottom IIFE, where the existing reads and
writes are individually guarded. If it reads storage unguarded and access
throws, which Chromium does with cookies blocked, the exception kills the IIFE
before `addEventListener` and **the toggle it advertises stops working.**

Rule: wrap the read, and treat a throw as "key present" so the pulse simply
never shows. Also note honestly that when storage is blocked, `setItem` no-ops,
so "never seen again" is false for those users and the pulse returns each load.

### The warm wash **[R4]**

`.hero::before` carries `transition: opacity 0.6s ease` (line 170) **and**
`animation: warmup 1.4s ease both` (line 343) whose final keyframe is
`opacity: var(--cone-opacity)` (line 353). Forwards fill holds the animated
value at animation cascade level, and a property under animation does not
transition. So the cone already snaps rather than eases today, and rev 3's wash
would have inherited that, plus a second snap because `background-image`
gradients do not transition.

Fix: drop `both` from the `warmup` shorthand so the transition governs after the
animation completes, and add the tungsten wash as a separate `.hero::after`
layer with its own opacity transition and no animation, rather than swapping the
gradient on `::before`.

### Print **[R4]**

No `@media print` exists. Printing today puts `#E9EDF5` text on white paper,
near invisible. Add a print rule forcing the light copy and light tokens.
Pre-existing defect, cheapest to fix in this pass.

## Files

- `index.html` — the only file changed
- `docs/2026-08-18-lights-mode-split-plan.md` — this plan

## Verification

1. Screenshot both modes at desktop width and at 390px.
2. Reload with the preference set to `on`; confirm light copy is the first
   paint with no dark flash.
3. Console clean on load and on toggle.
4. Confirm the hero load stagger still runs, and that no section animates on
   first paint that did not before.
5. Keyboard: tab to each of the three controls, activate, confirm focus is
   retained on the control and not dropped to body.
6. Confirm the hidden half is absent from the a11y tree and that the live region
   announces the swap.
7. Confirm no duplicate ids and that `#what-we-build` still scrolls in both
   modes.
8. Simulate blocked storage; confirm the toggle still works.
