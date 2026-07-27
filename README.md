# pantry-data — public read-only mirror

This repository is a **public, read-only mirror of food nutrition data** ("The Pantry").
It exists for one reason: so an AI assistant in a chat session can read the current food
database over a plain, unauthenticated URL.

**Read the data:**
`https://raw.githubusercontent.com/glsyme/pantry-data/main/pantry.json`

## What's here

- `pantry.json` — the food database. Per-100g figures are canonical; per-serve values are
  derived (`per100g × serveG ÷ 100`). Net carbs (`carb − fibre`) and unsaturated fat
  (`monoFat + polyFat`) are computed by the reader, not stored.
- `schema.json` — JSON Schema for `pantry.json`.

## What's NOT here — and never will be

This mirror contains **food nutrition reference data only**. No personal data of any kind
— no body measurements, no food logs, no daily targets, no config, no service code. The
private source project pushes only an explicit allow-list of files here
(`pantry.json`, `schema.json`, `README.md`); the sync fails closed on anything else.

Public means permanently public. Nothing personal is ever committed to this repo.

## How it updates

Automatically. A private project (the source of truth) writes new food entries and pushes
the allow-listed files here. This repo is never edited by hand and accepts no contributions.
