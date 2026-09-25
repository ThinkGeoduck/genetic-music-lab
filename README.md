# Genetic Music Lab

A genetic algorithm that reconstructs a piece of music from randomness, in the browser,
with nothing but a score to guide it.

Drop in a MIDI file. The lab takes the first minute of it, generates 400 completely random
candidate pieces, and breeds them toward the target — selection, crossover, mutation, elitism —
while a sampled grand piano plays the current best candidate live. The algorithm never sees the
target. It only ever receives a number saying how close each candidate is.

Open `genetic-music-lab.html` in a browser. There is no build step and no server required,
though a local one avoids `file://` quirks:

```bash
python -m http.server 8731
```

## How it works

**The genome.** One gene per note, four fields each: pitch, how long the note sounds, how loud
it is, and how long until the next note starts. That last field is how chords exist — zero means
"sounds together with the next note", so chords can appear, grow and dissolve through ordinary
mutation like any other trait. A one-minute passage is typically 300–500 genes.

**The objective.** A weighted score: 40% pitch similarity, 25% rhythm, 20% velocity, 15% melodic
smoothness. Smoothness is capped at the target's own smoothness, so no candidate can out-score the
target by being smoother than the composer was. With that cap the target scores exactly 1.0 and is
the unique optimum, which makes "100% fitness" and "every gene exactly right" the same statement.

**The engine.** Tournament selection (k=5), multi-point crossover with roughly one cut per twelve
genes, mutation expressed as an expected number of gene changes per child, and 2% elitism. The
engine in the source knows nothing about MIDI or music; it is handed a genome factory, operators
and a scoring function.

**Nothing is copied from the target.** Generation 1 is genuinely random, and no candidate is ever
nudged toward the answer except through its fitness score.

## The two labs

- `genetic-music-lab.html` — the music lab described above, plus `genetic-music-lab-piano.js`
  (the piano samples; keep the two files side by side).
- `genetic-algorithm-lab.html` — an earlier, separate lab where a population of agents evolves
  its way through a maze. Different visual world, same idea.

## Credits

- **Piano samples** — Salamander Grand Piano V3 by Alexander Holm, licensed
  [CC-BY 3.0](https://creativecommons.org/licenses/by/3.0/). 30 notes across 3 velocity layers,
  trimmed and re-encoded for the web.
- **Typeface** — [Hanken Grotesk](https://fonts.google.com/specimen/Hanken+Grotesk) by Alfredo Marco
  Pradil, SIL Open Font License.
- **Bundled example** — "Cornfield Chase" from *Interstellar*, composed by Hans Zimmer, included as
  a MIDI transcription for demonstration only. All rights to the composition remain with their
  owners. Replace it with your own file by dropping one onto the page.

The lab's own code is free to use and adapt.
