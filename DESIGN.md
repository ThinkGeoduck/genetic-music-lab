---
name: Genetic Music Lab
description: A concert poster being typeset in front of you, the programme for a piece the algorithm has not yet found.
colors:
  paper: "#ffffff"
  ink: "#111111"
  ink-2: "#4d5257"
  faint: "#e4e6e8"
  ghost: "#9a9fa4"
  accent: "#e63b1e"
  accent-pressed: "#c42a10"
typography:
  display:
    fontFamily: "Hanken Grotesk, Helvetica, Arial, sans-serif"
    fontSize: "clamp(88px, 40cqw, 260px)"
    fontWeight: 800
    lineHeight: 0.86
    letterSpacing: "-0.05em"
    fontVariation: "tabular-nums lining-nums"
  headline:
    fontFamily: "Hanken Grotesk, Helvetica, Arial, sans-serif"
    fontSize: "clamp(44px, 7vw, 112px)"
    fontWeight: 800
    lineHeight: 0.92
    letterSpacing: "-0.03em"
  title:
    fontFamily: "Hanken Grotesk, Helvetica, Arial, sans-serif"
    fontSize: "clamp(30px, 3vw, 56px)"
    fontWeight: 700
    lineHeight: 1
    letterSpacing: "0.02em"
  body:
    fontFamily: "Hanken Grotesk, Helvetica, Arial, sans-serif"
    fontSize: "clamp(14px, 0.95vw, 17px)"
    fontWeight: 400
    lineHeight: 1.5
    letterSpacing: "normal"
  label:
    fontFamily: "Hanken Grotesk, Helvetica, Arial, sans-serif"
    fontSize: "clamp(14px, 1vw, 18px)"
    fontWeight: 700
    lineHeight: 1.35
    letterSpacing: "0.08em"
rounded:
  none: "0px"
spacing:
  gutter: "clamp(16px, 2vw, 32px)"
  margin: "clamp(20px, 5vw, 96px)"
  rule-gap: "14px"
  block: "clamp(20px, 3vh, 36px)"
  section: "clamp(28px, 5vh, 56px)"
components:
  control:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.35em 0"
  control-active:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.35em 0"
  control-inactive:
    backgroundColor: "transparent"
    textColor: "{colors.ink-2}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.35em 0"
  control-disabled:
    backgroundColor: "transparent"
    textColor: "{colors.ghost}"
    typography: "{typography.label}"
    rounded: "{rounded.none}"
    padding: "0.35em 0"
  command-primary:
    backgroundColor: "transparent"
    textColor: "{colors.accent}"
    typography: "{typography.title}"
    rounded: "{rounded.none}"
    padding: "0.05em 0"
  command-primary-live:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.title}"
    rounded: "{rounded.none}"
    padding: "0.05em 0"
  drop-field:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.paper}"
    typography: "{typography.headline}"
    rounded: "{rounded.none}"
    padding: "clamp(28px, 5vw, 72px) clamp(24px, 4vw, 64px)"
  drop-field-hover:
    backgroundColor: "{colors.accent-pressed}"
    textColor: "{colors.paper}"
    typography: "{typography.headline}"
    rounded: "{rounded.none}"
    padding: "clamp(28px, 5vw, 72px) clamp(24px, 4vw, 64px)"
  slider-thumb:
    backgroundColor: "{colors.ink}"
    rounded: "{rounded.none}"
    size: "18px"
  slider-thumb-hover:
    backgroundColor: "{colors.accent}"
    rounded: "{rounded.none}"
    size: "18px"
---

# Design System: Genetic Music Lab

## Overview

**Creative North Star: "The Tonhalle Programme"**

The lab is a Zürich concert poster in the Müller-Brockmann manner, typeset live. A white sheet, one flat vermilion, and a heavy black grotesk at poster scale sit on a grid drawn only in hairline rules; the algorithm's progress is the poster being finished. Nothing is decorated: musical structure is carried by geometry (notes as flat bars, fitness as a ranked bar field), and hierarchy is carried by scale jumps rather than by weight of chrome. The page is meant to be projected and read from the back of a room, so every meaningful element is either enormous or uppercase and tracked.

Density is editorial rather than dashboard. There are no cards, stat tiles, shadows, gradients, or icons anywhere in the built page; sections are divided by 1px and 2px rules and by whitespace alone. Controls are words. The whole colour budget is spent on one hue, and that hue is reserved for the poster's geometry and its largest type: the withheld target is a solid vermilion field, wrong notes stay vermilion, the fitness bars are vermilion, the primary command is vermilion, and the finished generation count turns vermilion. Everything else is black on white with one mid-grey for secondary text.

Confirmed rejections from the build: SaaS-dashboard cards and stat tiles, dark-and-neon, moody black rooms, playful or gimmicky ornament, icon glyphs, and any depth cue.

**Key Characteristics:**
- White ground, black ink, one flat vermilion; a single mid grey for secondary text and a construction grey for hairlines
- One variable grotesk (Hanken Grotesk, self-hosted) at four scale jumps, from 14px labels to a 260px generation number
- Rigid two-column poster grid (4fr / 8fr) with rule-divided sections; zero border radius everywhere, including slider thumbs
- Controls are uppercase tracked words with a 3px rule under the active state (4px under the primary command)
- Geometry carries data: flat bars for notes, a ranked vermilion bar field for fitness, a 1px hairline playhead
- Tabular lining numerals across the whole document

## Colors

A three-value palette (paper, ink, vermilion) with two greys doing structural work; the vermilion is the only chroma on the page.

### Primary
- **Poster Vermilion** (`accent`): the one colour. Used for the solid field that hides the target, for every wrong note bar in the candidate roll, for the fitness bars, for the primary command word (START / RUN IT AGAIN), for the 3px underline of an active typographic control, for the generation number once the run has converged, for the error rule, and for text selection. It is applied to geometry and poster-scale type only; never to body copy, labels, or borders that merely divide.
- **Pressed Vermilion** (`accent-pressed`): the drop field's hover and drag-over state, a darker step of the same hue. The only place a second red appears.

### Neutral
- **Paper** (`paper`): the page, the scrollbar track, the enlarged-chart overlay, and the text set on top of vermilion (the drop field's headline, the "Target withheld" caption).
- **Ink** (`ink`): all primary text, every rule and border, the correct (exact) note bars, the revealed target's bars, the lane base line, the population-average line, the playhead, the slider track and thumb, the scrollbar thumb, and the 3px focus outline.
- **Programme Grey** (`ink-2`): secondary text at 7.2:1 on white. Programme metadata, inactive segmented options, parameter hints, the programme notes body, the roll lane labels (drawn on canvas), and the axis captions in the enlarged chart.
- **Construction Grey** (`faint`): hairline construction lines only: one vertical rule every eight bars in the piano roll lanes and the four quarter rules across the fitness field.
- **Ghost Grey** (`ghost`): disabled typographic controls only.

### Named Rules
**The One Colour Rule.** Vermilion goes on geometry and on poster-scale type (the command word, the finished count, the hidden-target field). It never goes on body text, on dividing rules, on backgrounds behind copy, or on more than one control's underline per group.

**The Ink Prints Rule.** In the roll, vermilion means "not yet right" and black means "set". A bar changes from vermilion to black once, in 420ms, when a note becomes exact; nothing else in the page animates colour.

**The Canvas Reads the Stylesheet Rule.** Canvas drawing reads `--ink`, `--ink-2`, `--faint`, `--accent`, `--paper` from `:root` at layout time; no colour is hard-coded in script except the white caption on the vermilion field.

## Typography

**Display Font:** Hanken Grotesk, variable 100-900, self-hosted (with Helvetica, Arial, sans-serif)
**Body Font:** Hanken Grotesk (same family)
**Label/Mono Font:** none distinct; numerals use `font-variant-numeric: tabular-nums` on the body

**Character:** One neutral grotesk carries the entire page, set at wildly different sizes. Big type is tight and heavy (800, negative tracking, line-height under 1); small type is bold, uppercase, and loosely tracked. Regular-weight text exists only in the programme notes and hints.

### Hierarchy
- **Display** (800, `clamp(88px, 40cqw, 260px)`, 0.86, -0.05em, tabular lining nums): the generation counter. Sized by its container's width (container query units) so it always fills the poster's left column. Ink while running, vermilion when converged.
- **Headline** (800, `clamp(44px, 7vw, 112px)`, 0.92, -0.03em): the drop field's instruction, white on vermilion, balanced to 12ch. The "Target withheld" caption on canvas is the same voice at up to 64px.
- **Title** (700, `clamp(30px, 3vw, 56px)`, 0.02em, uppercase): the primary command word in the command line, with a 4px rule.
- **Sub-headline** (700, `clamp(24px, 1.9vw, 30px)`, 1.3): the drop field's second sentence, white on vermilion.
- **Masthead** (800, `clamp(18px, 1.4vw, 24px)`, 0.12em, uppercase): the programme title at top left.
- **Label** (700, `clamp(14px, 1vw, 18px)`, 0.08em, uppercase): every typographic control, the parameter names, the segmented options. The "generations" unit and the roll lane labels use the same size with 0.12em / hair-space tracking in Programme Grey.
- **Body** (400, `clamp(14px, 0.95vw, 17px)`, 1.5, max 70ch): the programme notes in Programme Grey, with bolded lead-ins in Ink. The base body size is `clamp(16px, 1.1vw, 20px)` at 1.35; the live status line uses it at weight 500 with 800 numerals.
- **Caption** (700, `clamp(13px, 0.9vw, 16px)`, 0.02em): the fitness field's explanatory line.

### Named Rules
**The Scale Jump Rule.** Hierarchy is made by size, not by colour or weight alone. Adjacent levels differ by at least 2x; the counter is 10x the labels beside it.

**The Tabular Numerals Rule.** Every numeral on the page, in HTML or on canvas, is tabular and lining so the counter and the status line never reflow as they count.

## Layout

A single sheet, max width 1800px, centred, with a fluid horizontal margin (`margin` token, 20-96px) and a fluid gutter (`gutter`, 16-32px) that every flex and grid gap is derived from (1x, 1.2x, 1.6x, 2x). Vertical rhythm is rule-based: each section opens with a 1px or 2px Ink rule and 14px of padding beneath it (`rule-gap`), and sections are separated by fluid vh-scaled blocks (`block`, `section`).

The poster body is a two-column grid, `minmax(260px, 4fr) 8fr`, with a 2x-gutter column gap: the generation counter and its unit on the left, the two piano-roll lanes on the right. The roll canvas height is 70% of its width clamped between 380px and 820px, or 74% of the viewport height if larger. Beneath it the command line runs full width, then the fitness field (canvas height 20vh, 140-240px), then a two-column parameter grid (1fr 1fr, 2x-gutter gap), then two-column programme notes (CSS columns).

Breakpoints, both observed: at 880px the poster grid and the notes collapse to one column and the rolls get their own top rule and 28px of separation; at 700px the parameters stack. The masthead, programme line, and command line all wrap by flex rather than by breakpoint.

The enlarged fitness field is a full-viewport Paper overlay (position fixed, inset 0) using the same margin token, with a 2px rule under its heading and a 1px rule above its readout line.

**The Rules Divide Rule.** Sections are separated by horizontal rules and whitespace only. Heavy rules (2px) mark the masthead, the programme notes, and the error message; hairlines (1px) mark everything in between. No box ever encloses content.

## Elevation & Depth

Entirely flat. There are no box shadows, text shadows, gradients, blurs, or backdrop filters anywhere in the built page, and the enlarged chart overlay is an opaque Paper sheet rather than a dimmed modal. Depth is conveyed only by the solid vermilion field (which reads as a printed plate on the page) and by the ordering of ink weights: 2px rules over 1px rules over Construction Grey hairlines. Focus is a 3px Ink outline offset 4px (8px on sliders).

**The Flat Print Rule.** Surfaces never lift. State is shown by colour (Ink / Programme Grey / Ghost Grey / Vermilion) and by rules under text, never by shadow, elevation, or background tint.

## Shapes

Square everywhere. Border radius is 0 on every element including range-slider thumbs (18px square Ink blocks on a 2px Ink track). Bars in the rolls and the fitness field are unrounded rectangles at integer pixel positions; the playhead and construction lines are 1px rects; the population-average line is a 1.5px stroke. The only "shape" in the system is the rectangle, at four weights: field, bar, rule, hairline.

## Components

Every control is a word. The build has no card, chip, input-text, or icon component.

### Typographic Control (`control`)
- **Shape:** none; text with a 3px transparent bottom border reserved for state
- **Default:** Ink, Label typography (700, uppercase, 0.08em), padding 0.35em 0
- **Hover:** bottom border becomes Ink (150ms colour and border transition)
- **Active / Playing:** bottom border becomes Vermilion, text Ink
- **Disabled:** Ghost Grey text, no border, not-allowed cursor
- **Segmented group (`.seg`):** options inline with a 0.9x gutter gap; the inactive option is Programme Grey and turns Ink on hover; exactly one option carries the vermilion rule

### Primary Command (`command-primary`)
- **Shape:** the same typographic control at Title scale with a 4px bottom border
- **Rest:** Vermilion text ("START" / "RUN IT AGAIN")
- **Hover:** Ink text
- **Live (running):** Ink text with the vermilion rule

### Drop Field (`drop-field`)
- **Shape:** full-width square block, minimum height `min(56vh, 560px)`, contents pushed to top and bottom
- **Colour:** Vermilion ground, Paper text; Headline instruction plus a 700-weight sub-line with a 2px underline on the "choose a file" link
- **Hover / drag-over:** Pressed Vermilion
- **Focus:** Ink outline

### Range Slider (`slider-thumb`)
- **Track:** 2px Ink line, full width, 18px top margin
- **Thumb:** 18px square Ink block, radius 0; Vermilion on hover
- **Frame:** sits under a rule-topped parameter block with an uppercase Label name left and an 800-weight value right, and a Programme Grey hint below (max 52ch)

### Navigation (masthead)
- 2px rule beneath; uppercase 800 title at left tracked 0.12em; typographic controls (Load MIDI, Use the example) at right with a 1.2x gutter gap. Wraps by flex on narrow viewports; no hamburger, no icons.

### Piano Roll (signature)
Two lanes on one canvas, 34px apart, each with a hair-spaced uppercase Programme Grey label 8px above it, a Construction Grey vertical every eight bars, and a 1px Ink base rule. Notes are flat rectangles at least 2px wide and 3px tall, one row per semitone. The hidden target lane is a solid Vermilion field carrying "Target withheld" in Paper at 800 weight, bottom-left, 22px in. The revealed target prints in Ink. In the candidate lane a note is Vermilion until every gene is exact, then eases (cubic ease-out, 420ms, instant under reduced motion) to Ink. The playhead is a 1px Ink hairline the full height of the lane being played.

### Fitness Bar Field (signature)
One Vermilion bar per bucket of generations (bar width from the field width at 7px per bar, minimum 8 bars, 2px between bars), rising from a 1px Ink base rule; four Construction Grey quarter rules behind; the population average as a 1.5px Ink line across the bar tops. The inline field opens (zoom-in cursor) to the full-viewport enlarged version, where hovering draws a 1px Ink cursor line and prints the generation, best, and average as a rule-topped readout line with 800-weight numbers.

## Do's and Don'ts

### Do:
- **Do** set every control as an uppercase, tracked word (700, 0.08em) with a 3px bottom rule that turns vermilion when active; 4px under a Title-scale primary command.
- **Do** divide with 1px Ink hairlines and 14px of padding beneath; use 2px only for the masthead, the notes, and error rules.
- **Do** spend vermilion on geometry (bars, fields) and poster-scale type only; keep small text Ink or Programme Grey.
- **Do** derive every gap from the gutter token (1x, 1.2x, 1.6x, 2x) and every outer margin from the margin token.
- **Do** read canvas colours from the `:root` custom properties so drawn geometry and CSS never disagree.
- **Do** keep numerals tabular and lining, and let the largest number size itself from its column with container query units.
- **Do** keep radius at 0 on every element, including slider thumbs and canvas bars.

### Don't:
- **Don't** add cards, panels, stat tiles, or any bordered or tinted box around content.
- **Don't** use shadows, gradients, blurs, glows, or a dimmed modal scrim; the enlarged chart is an opaque Paper sheet.
- **Don't** introduce icons or glyphs; the masthead, commands, and navigation are words.
- **Don't** add a second hue or a tint of vermilion beyond the single pressed step used on the drop field's hover.
- **Don't** animate anything except the 150ms control-state transitions and the one 420ms vermilion-to-ink print in the roll.
- **Don't** put vermilion on body copy, hints, labels, or dividing rules.
