# CLAUDE.md

Guidance for Claude Code when working in this repository.

## What this repo is

This is **RepositorioJAR4**, a fork of a large collective collection of n8n
workflow exports (`n8n-workflows-esp` by DragonJAR). It is a **data
repository, not a software project**: there is no build, no test suite, no
package manager, and no application code. The content is:

- `workflows/` — 10,000+ n8n workflow exports as standalone `.json` files.
- `README.md` — Spanish documentation, including a generated catalog listing
  every workflow file with a short description and complexity rating.
- `README-ENGLISH.md` — English counterpart, structurally identical to
  `README.md`.

## Repo layout

- `workflows/*.json` — Each file is a raw n8n workflow export (nodes, edges,
  parameters, credentials placeholders). Filenames follow a
  `NNNNN-Descriptive-Slug.json` pattern (5-digit zero-padded sequence number,
  currently `00001`–`10405`, plus a hyphenated description). Many titles
  reference the AI tools/services the workflow integrates with (OpenAI,
  Claude, Gemini, etc.) — that's the workflow's subject matter, not anything
  about this coding environment.
- `README.md` / `README-ENGLISH.md` — **Very large files (~2.5 MB, ~41.7k
  lines each)**, most of which is the auto-generated "Listado de Workflows"
  section (one entry per file in `workflows/`). Do not `Read` these files in
  full — use `Grep`/`offset`+`limit` to look up specific entries.

## Working in this repo

- There's nothing to compile, lint, or run. Changes are typically: adding new
  workflow JSON files, fixing/renaming existing ones, or updating the catalog
  entries in the two README files to match.
- If you add, rename, or remove a file in `workflows/`, keep the catalog in
  **both** `README.md` and `README-ENGLISH.md` in sync (same entries, Spanish
  vs. English descriptions) and keep the `_Total de workflows: N_` count
  accurate.
- Preserve the `NNNNN-` numeric prefix convention when naming new workflow
  files; pick the next unused number.
- These are credential-free exports intended for others to import into their
  own n8n instance — don't add real secrets, tokens, or webhook URLs when
  editing workflow JSON.
