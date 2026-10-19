# FLU 2.0 Core — Reuse Matrix

**Version:** 0.1.0  
**Date:** 2026-10-19  
**Scope:** Influenza A (generic) lifecycle and core entities. No strain- or cell-line-specific content.

This matrix is the foundation for the public-facing FLU 2.0 Core ontology.  
New FLU identifiers are still avoided; everything is reuse or a thin defined pattern.

## Lifecycle processes (influenza-generic)

| Process | External source | Identifier | Preferred label | Reuse type |
|---------|-----------------|------------|-----------------|------------|
| Attachment | GO | GO:0019062 | viral attachment to host cell | direct |
| Attachment | Reactome | R-HSA-168272 | Attachment of influenza virion | xref |
| Endocytosis | GO | GO:0046718 | viral entry into host cell via endocytosis | direct |
| Endocytosis | Reactome | R-HSA-168275 | Endocytosis of influenza virus | xref |
| Endosomal acidification | GO | GO:0007035 | vacuolar acidification | annotation |
| Membrane fusion | GO | GO:0039654 | viral membrane fusion | direct |
| Membrane fusion | Reactome | R-HSA-168270 | Fusion of influenza virion with late endosome | xref |
| Uncoating | GO | GO:0019061 | viral uncoating | direct |
| Uncoating | Reactome | R-HSA-168270 | Uncoating of influenza virion | xref |
| vRNP nuclear import | GO | GO:0075732 | viral penetration into host nucleus | direct |
| vRNP nuclear import | Reactome | R-HSA-168271 | Import of influenza vRNPs into nucleus | xref |
| Viral transcription | GO | GO:0019083 | viral transcription | direct |
| Viral transcription | Reactome | R-HSA-168273 | Transcription of influenza genome | xref |
| Viral protein synthesis | GO | GO:0019081 | viral protein synthesis | direct |
| Viral genome replication | GO | GO:0019079 | viral genome replication | direct |
| Viral genome replication | Reactome | R-HSA-168273 | Replication of influenza genome | xref |
| vRNP nuclear export | Reactome | R-HSA-168274 | Export of influenza vRNPs from nucleus | xref |
| Genome packaging & assembly | Reactome | R-HSA-168303, R-HSA-168316 | Packaging / Assembly of influenza virion | xref |
| Budding | Reactome | R-HSA-168302 | Budding of influenza virion | xref |
| Release | GO | GO:0019076 | viral release from host cell | direct |
| Release | Reactome | R-HSA-168298 | Release of influenza virion | xref |

## Viral entities (influenza-generic)

| Entity | External source | Identifier / pattern | Notes |
|--------|-----------------|----------------------|-------|
| HA, NA, NP, M1, M2, PB1, PB2, PA, NS1, NEP | PRO | gene-level / family-level classes | Annotate with UniProt; no new FLU class |
| PB1-F2 | annotation | alternative product of PB1 | Well-established accessory protein (mitochondrial apoptosis, virulence). Include as annotation. |
| PB1-N40 | annotation | alternative product of PB1 | Well-established accessory protein (alternative start). Include as annotation. |
| PA-X | annotation | alternative product of PA (+1 frameshift) | Well-established accessory protein (host shutoff, virulence, transmission). Actively studied 2023–2026. Include as annotation. |
| PA-N155, PA-N182 | annotation | N-terminally truncated PA | Conserved; affect replication/pathogenicity. Optional annotation only. |
| vRNP | cross-product | vRNA + NP + polymerase complex | Pattern, not a new named class |
| Influenza A virion | NCBITaxon + VIDO | Influenza A virus + virion | Reuse |

## Pathway cross-references

| Resource | Identifier | Status / notes |
|----------|------------|----------------|
| Reactome | R-HSA-168255 (Influenza Infection) and child pathways | Valuable backbone. Authored 2006 (Luo, Squires, Scheuermann). Limited biological updates since; last major content touch ~2020–2023. Does not include post-2012 accessory proteins. Use as cross-reference only. |
| KEGG | map05164 (Influenza A) | Open. Includes PB1-F2. Broader host-response focus. |
| WikiPathways | WP1438 (Influenza A virus infection) | Open, community-maintained. Includes PB1-F2. Last edited Dec 2025. |
| FluMap (Matsuoka et al. 2013) | Comprehensive literature-curated map | Open (CC-BY). Integrated Reactome/KEGG skeleton + literature. 960 factors, 456 reactions. Site status uncertain but paper and SBML remain available. |
| ViralZone | Influenza molecular biology sheets | Open (SIB). Process-oriented, UniProt-linked. |

## Relations & upper level

| Relation | Source | Identifier |
|----------|--------|------------|
| precedes | RO | RO:0002090 |
| occurs in | BFO | BFO:0000066 |
| participates in | RO | RO:0000057 |

## Notes
- No A549, PR8, or simulation-parameter content appears in the Core.
- Reactome identifiers are cross-references, not OWL classes.
- The Core is intended to be imported by more specific modules (Alpha, future surveillance, vaccine, etc.).
