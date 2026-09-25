# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Primary (and currently only) user is the developer themself. These are personal sandbox/learning tools for exploring genetic algorithms, with no outside audience designed for.

## Product Purpose

Two experimental "labs" that visualize genetic algorithms in action:

- **Genetic Algorithm Lab** (`genetic-algorithm-lab.html`): a population of agents, each carrying a list of random movement instructions, evolves via selection, inheritance, and mutation to solve a maze. No route is programmed and no agent can see the maze — improvement emerges purely from evolutionary pressure.
- **Genetic Music Lab** (`genetic-music-lab.html` + `genetic-music-lab-piano.js`): applies genetic-algorithm evolution to music generation, played back via sampled piano audio and visualized on a piano roll.

Success means clearly demonstrating evolutionary improvement — fitness rising, behavior/music changing — in a way that's legible generation-by-generation, not just a solved end state.

## Positioning

Not a general-purpose GA library, pathfinding demo, or music tool — it's a first-person demonstration of evolutionary computation, valued for making the *process* of evolution watchable (population state, fitness, mutation, generational change) rather than for delivering a solved maze or a finished song.

## Operating Context

Run locally as static files via `python -m http.server` (see `.claude/launch.json`, port 8731); opened directly in a browser during solo experimentation sessions. Not deployed or shared with anyone else.

## Capabilities and Constraints

Current implementation is plain HTML/CSS/JS with no build step or framework. There is no constraint to stay framework-free — a framework or build step may be introduced later if it meaningfully improves the work (explicitly left open/undecided by the user).

`genetic-music-lab-piano.js` bundles Salamander Grand Piano V3 samples (CC-BY 3.0, Alexander Holm) as base64 audio; the lab falls back to a built-in piano if that file is missing.

## Evidence on Hand

None. No testimonials, usage data, or case studies exist or should be fabricated — this is a personal project with no external claims to substantiate.

## Product Principles

- Make evolution watchable: generation-by-generation change (fitness, population state, mutation) should be visually legible in real time, not only the end result.
- Favor the moment of emergence over the artifact: the interesting output is agents learning to navigate, or music improving, across generations — not merely a solved maze or a finished track.
- Keep the iteration loop fast and local: no deployment or external audience to design for; the personal experimentation loop stays the priority.
- Stay open to tooling changes: the current no-framework stack is a starting point, not a constraint — future work can adopt better tools when they genuinely improve the experience of watching evolution happen.
