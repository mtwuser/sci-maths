# sci-maths — Sovereign Epistemic Knowledge Corpus (`v1.0.0`)

[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](VERSION)
[![ZeroCloudGravity](https://img.shields.io/badge/ZeroCloudGravity-v1.0.0-0F766E.svg)](https://github.com/mtwuser/zero-cloud-gravity)
[![Epistemic Grade](https://img.shields.io/badge/epistemic_grade-E3..E1-1D4ED8.svg)](docs/README.md)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

> **Formal & Applied Mathematics Knowledge Corpus (`MSC 2020`: Linear Algebra, PDEs, Probability & Convex Optimization)** (`layer_role: knowledge`, `precedence: 20`, `stewardship_stage: public-community`).

## 1. Epistemic Corpus Index (`1:1:1` Progressive Disclosure)

All sections expose deterministic `rcap1` (`L0 -> L3`) capsules and cryptographic `citation_receipt` anchors (`<layer>::<file>#<slug>@<sha256_16>:<E3..E0>`):

| Tier | Credibility | Document |
| :--- | :--- | :--- |
| **Index** | `E2` | [`docs/README.md`](docs/README.md) |
| **Guide (`M1 -> M4`)** | `E1` | [Socratic Mathematics Curriculum & Proof Verification Guide (`M1 -> M4` — `E1`)](docs/guides/01_socratic_math_foundations.md) |
| **Architecture & Taxonomy** | `E3` | [Formal & Applied Mathematics Taxonomy, Deductive Hierarchy & Numerical Conditioning (`E3`)](docs/architecture/01_formal_mathematics_taxonomy_and_branch_map.md) |
| **Primary Reference** | `E3/E2` | [Formal Mathematical Axioms, Spectral Theory, PDEs & Convex Optimality (`E3`)](docs/reference/01_linear_algebra_and_calculus_axioms.md) |

## 2. Mounting & Querying from Any `ZeroCloudGravity` Node

Link or mount this corpus into a personal (`<persona>-pc`, `<persona>-tutor`), research, or enterprise node without cloud dependencies:

```bash
zcg link <your-node-dir> --target https://github.com/mtwuser/sci-maths.git --relation knowledge-feed
zcg consult-layer <your-node-dir> --layer sci-maths --query "<topic>" --tier flash
```

## 3. Layer Setup Blueprint (`State U2: configured`)

- **Node ID & Role**: `sci-maths` (`knowledge`, `precedence: 20`, `surface_veracity_mode: full-open-source`)
- **1-Hop Upstream Engine**: [`mtwuser/zero-cloud-gravity`](https://github.com/mtwuser/zero-cloud-gravity)
- **Active Template Packs**: `science-base`, `scientific-methodology`, `sci-maths`, `knowledge-stewardship-portal`
- **Mission, Scope & Core Invariants**: Formal mathematical deductive corpus (`E3..E1`) covering `MSC 2020` branch taxonomy, spectral linear algebra, differential forms, PDE well-posedness, probability bounds, and KKT convex optimality.
- **Downstream Topology**: Consumed read-only via `knowledge-feed` links or `layers/*` subtrees across academic, scientific, public-sector, and enterprise nodes.
- **Authorized Layer Steward**: `sci-maths Knowledge Steward <mtwuser@users.noreply.github.com>`
