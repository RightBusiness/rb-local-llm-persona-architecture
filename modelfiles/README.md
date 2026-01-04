# Modelfiles

This directory contains **all active Ollama Modelfiles** used in this repository.

Each file represents a **different level or style of persona enforcement** for the
Dr. Greyson Rouhe system. These are **executable instruction artefacts**, not prompts
and not documentation.

All files here are intended to be used explicitly via `ollama create -f`.

---

## Files in This Directory

### `modelfile`

Baseline control Modelfile.

- Minimal constraints
- Weak or no persona enforcement
- Exists solely as a **contrast point**
- Demonstrates how quickly an assistant-style model reasserts itself

**Failure signature:** responds helpfully, answers directly, or adopts assistant tone.

---

### `modelfile.rouhe-core`

Core enforcement variant.

- Encodes the **strictest Rouhe-Core constraints**
- Minimal expressive range
- High refusal rate
- Designed to test:
  - role persistence
  - resistance to accommodation
  - degradation under permissive runtimes

**Failure signature:** explains reasoning politely, softens refusals, or validates user framing.

---

### `modelfile.rouhe-interpretive`

Unversioned interpretive reference.

- Human-readable alias for the interpretive line
- Exists for navigation and inspection only
- **Not authoritative**

**Failure signature:** treated as canonical or used to justify behavior without a versioned source.

---

### `Modelfile.rouhe-interpretive.v2`
### `Modelfile.rouhe-interpretive.v3`
### `Modelfile.rouhe-interpretive.v4`
### `Modelfile.rouhe-interpretive.v5`
### `Modelfile.rouhe-interpretive.v6`

Versioned interpretive variants.

Purpose:
- Explore how much expressive flexibility is possible **without violating Rouhe-Core**
- Compare tone drift, refusal behavior, and confrontation sharpness
- Observe failure modes across revisions

General progression:
- Lower versions → tighter, harsher, more brittle
- Higher versions → broader language range, higher conversational tolerance

`v6` is the **current reference implementation**.

Earlier versions are retained intentionally for:
- regression comparison
- behavioral auditing
- instructional contrast

**Failure signature:** assists indirectly, reframes into advice, or answers without first diagnosing the user’s framing.

---

## Naming and Versioning Rules

- Filenames are authoritative
- Versions are explicit and immutable
- No `latest`, `final`, or floating aliases
- Behavioral changes require a new version
- Deprecated variants must be moved to `/archive/modelfiles/`

---

## Important Notes

- Ollama does **not** enforce persona behavior
  → all enforcement lives in the Modelfile
- These files are **not safe**, **not aligned**, and **not user-friendly**
- Apparent “helpfulness” is considered a **failure mode**

If a Modelfile assists, explains, or complies,
it has already violated the design constraints.

---

## General Note: Running These Modelfiles with Ollama

These Modelfiles are run **locally** using Ollama.
No hosting. No APIs. No UI.

```bash
ollama create rouhe-interpretive.v6 -f Modelfile.rouhe-interpretive.v6

ollama run rouhe-interpretive.v6
```

