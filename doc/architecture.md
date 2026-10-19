# FLU 2.0 — Core + Alpha Module Architecture

**Date:** 2026-10-19

## Overview

```
BFO → IDO → VIDO
              ↓
         FLU 2.0 Core          ← public, influenza-generic
              ↓
    FLU 2.0 Alpha Module       ← PR8/A549 specialization
              ↓
   Knowledge Graph + Quantitative Layer
```

## Files

| File | Role |
|------|------|
| `FLU2_15_Core_Reuse_Matrix.md` | Reuse matrix for the general Core |
| `FLU2_16_FLU2_Core.owl` | Minimal Core ontology (imports only; no new FLU classes) |
| `FLU2_17_FLU2_Alpha_Module.owl` | Alpha module that imports the Core and adds PR8/A549 defined classes |
| Earlier Alpha artifacts | Lifecycle model, KG, parameter mapping, CQ validation (unchanged) |

## How specialization works

- The Core provides the reusable influenza A semantics (via imports of GO, Reactome xrefs, PRO, VIDO, etc.).
- The Alpha module imports the Core and adds only what is specific to the PR8/A549 system (defined classes, experimental notes).
- Anyone who wants a general influenza ontology uses only the Core.
- Your simulation use case uses the Alpha module (which brings in the Core automatically).

## What stays outside both OWL files

- Particular experimental observations and evidence → Knowledge graph (`FLU2_07`)
- Fitted rates and simulation parameters → Quantitative layer (`FLU2_06`)
- These layers reference the ontology classes but are not part of the ontology itself.

This structure gives you a general, shareable FLU 2.0 Core while preserving every Alpha-specific result you have already built.
