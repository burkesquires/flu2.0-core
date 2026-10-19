# FLU 2.0 Core Ontology

**Version:** 0.1.0  
**Date:** 2026-10-19  

Self-contained, MIREOT-based ontology for the influenza A virus lifecycle.  
Reuse-first design; no new top-level identifiers are minted for core processes or proteins.

## Contents

| File | Description |
|------|-------------|
| `flu2_core.owl` | Self-contained OWL (MIREOT extract + defined-class patterns) |
| `docs/reuse_matrix.md` | Mapping of internal labels to external identifiers |
| `docs/architecture.md` | Relationship to the PR8/A549 Alpha module |
| `docs/competency_questions.md` | Priority questions the Core supports |
| `LICENSE` | CC-BY 4.0 |
## Quick start

1. Load `flu2_core.owl` in [Protégé](https://protege.stanford.edu/).
2. The defined classes `Influenza_A_attachment`, `Influenza_A_nuclear_import`, and `Influenza_A_release` specialize standard GO terms.
3. Reactome cross-references are stored as annotation properties.

## Design principles

- Reuse before invention (BFO, RO, GO, NCBITaxon)
- Layered architecture (ontology ≠ knowledge graph ≠ simulation parameters)
- Influenza-generic Core; strain- or cell-line-specific content lives in separate modules

## Citation

If you use this ontology, please cite:

> Squires, R. B. et al. (2026). FLU 2.0 Core Ontology (v0.1.0). Zenodo. https://doi.org/10.5281/zenodo.23483442

(DOI will be assigned on Zenodo deposit.)

## Contact

For questions or contributions, open an issue in this repository.
