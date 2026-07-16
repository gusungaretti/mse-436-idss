# Maple Moving — Canada Relocation Decision Support System

An interactive IDSS that helps a person decide **where to live in Canada**. It ranks **38 Census Metropolitan Areas** across **9 quality-of-life factors** based on the priorities the user sets, and re-ranks in real time as those priorities, budget, and preferences change.

Built for MSCI 436 — Decision Support Systems.

## Model

A transparent multi-criteria scoring engine (`lib/scoring.ts`): each factor is normalized to 0–100, the user's factor priorities become weights, and cities are ranked by the weighted sum. Full details are in-app at `/methodology`. The controls are load-bearing — changing priorities, budget, unit type, or climate changes the model output and the ranking.

## Getting started

Requires Node.js 18.18+ (Node 20+ recommended).

```bash
npm install
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

## Project structure

```
app/          Routes: landing, explore (main DSS), search, city/[slug], methodology
components/   Map, priority controls, ranking list, comparison, word cloud
data/         Static datasets (cities, suburbs, subreddit words)
lib/          scoring.ts (scoring engine), types, factor definitions
```

Built with Next.js 16, React 19, TypeScript, and Tailwind CSS. Computation is fully client-side; no backend required.
