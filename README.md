# LogiLambda

**A Framework for Verb-Density-Based Reasoning Quality Control in LM Pipelines**
*(Also known as: SFN Protocol)*

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18755293.svg)](https://doi.org/10.5281/zenodo.18755293)
[![License: MIT](https://img.shields.io/badge/Code-MIT-blue)](LICENSE)
[![Paper: CC BY 4.0](https://img.shields.io/badge/Paper-CC%20BY%204.0-green)](https://doi.org/10.5281/zenodo.18755293)

---

## Overview

Language models produce inconsistent output quality. LogiLambda addresses this by enforcing **structural constraints on reasoning fields** — not just on prompt content.

The core insight: **verbs define depth**. Rigorous reasoning uses action verbs (*analyze, compare, verify*); shallow output relies on adjectives (*interesting, concerning, complex*). LogiLambda measures this distinction and enforces it computationally.

---

## The Lambda Metric

```
Λ = N_verb / N_adj
```

Measured on intermediate reasoning fields only (DIRECTION + EXECUTION).

| Λ ≥ 1.0 | High-density mode — logical reasoning |
|---------|--------------------------------------|
| Λ < 1.0 | Descriptive mode — narrative, description |

---

## Five-Field Protocol

```
[1] CAPABILITY_BASELINE  →  Establishes required expertise level
[2] DIRECTION [AUDIT]    →  Defines scope, criteria, methodology  ← Λ measured here
[3] EXECUTION            →  Step-by-step reasoning with atomic ops ← Λ measured here
[4] OUTPUT               →  Final conclusions
```

Atomic operators: *extract, compare, filter, verify, calculate, transform*

---

## Key Result

Framework-constrained **Gemini 2.5 Flash** (lightweight) produced structurally richer reasoning than unstructured **Gemini 3 Thinking** (flagship) — suggesting structural constraints can partially compensate for model tier differences.

---

## Implementation

- **v6.8** validated prototype
- Built on **DSPy** with spaCy POS tagging
- Tested: Ollama (llama3.1 8B local) + Google Vertex AI (Gemini 2.5 Flash)
- Modes: Interactive analysis + Prompt optimization

---

## Paper

📄 **LogiLambda: A Vision for Verb-Density-Based Reasoning Quality Control**
Yang, Shih-Hung (Independent AI Research); Lin, Tzu-Ching
March 2026 · v4

**DOI:** https://doi.org/10.5281/zenodo.18755293
**Visual abstract:** https://doi.org/10.5281/zenodo.18872551

---

## Roadmap

- ✅ Phase 1: Core implementation + prototype validation (v6.8)
- 🔄 Phase 2: DSPy optimizer integration + expanded testing
- ⏳ Phase 3: Formal LLM-as-judge evaluation
- ⏳ Phase 4: Domain-specific applications

---

## Contact & Collaboration

Seeking collaborators for: expanded testing, formal evaluation, Chinese-language support, DSPy Phase 2.

📧 basazak1@ai-iw-synchub.com

---

*This work emerged from iterative dialogue between an independent researcher and AI assistants (Claude by Anthropic).*
