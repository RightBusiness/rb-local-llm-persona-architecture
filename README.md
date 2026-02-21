# rb-local-llm-persona-demo

© 2025–2026 Right Business Pte. Ltd.
All rights reserved.

Reference implementation demonstrating persona enforcement for locally run large language models using a fixed Modelfile execution surface.

**Status:** Stable reference implementation. Not intended for production deployment.

## Scope

- Local LLM only (bring your own runtime and model)
- No UI
- No hosting
- No APIs
- No compatibility guarantees

Intended Audience
- Engineers familiar with local LLM runtimes
- Developers evaluating persona enforcement architecture
- System designers exploring Modelfile-based control surfaces

## Assumptions

You already know how to:
- Run a local LLM (e.g. Ollama, llama.cpp, LM Studio)
- Inspect and adapt Modelfiles
- Resolve model- or runtime-specific differences yourself

## Purpose

The goal is to demonstrate how a fixed persona can be enforced
at the Modelfile and behavioral-architecture level
across permissive local LLM runtimes.

The canonical active Modelfile is:

- `Modelfile-rouhe`

All other Modelfiles in this repository are archived under
`/archive/modelfiles` and are retained strictly for lineage
and auditability. They are deprecated and must not be used
for deployment.

This repository is **not**:
- A product
- A framework
- A supported chatbot
- A turnkey solution

## Architecture

The authoritative behavioral specification for the persona
implemented in this repository is defined in:

- `docs/ROUHE_ARCHITECTURE.md`

This document is platform-agnostic and supersedes earlier
prompt-bound or GPT-specific persona artefacts, which are
preserved under `/archive/gpt-era` for historical reference only.

## License

All rights reserved.

See [LICENSE](LICENSE.md) and [NOTICE](NOTICE.md) for full legal terms.
