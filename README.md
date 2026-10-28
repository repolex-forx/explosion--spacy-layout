# Repolex Knowledge Graph of explosion/spacy-layout

RDF knowledge graph data for [explosion/spacy-layout](https://github.com/explosion/spacy-layout), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download explosion/spacy-layout
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c458ab37ba7d63dda9d11109de970346543ad502
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c458ab37ba7d63dda9d11109de970346543ad502
│           └── chunk-001.nq.gz
├── blob
│   ├── 132c827541c09ca3c552868be885d85b40bf74a7.nq.gz
│   ├── 1baab55771bf0d2d8f127561baa2a0bbd032c7bc.nq.gz
│   ├── 2f8e4ae184bbcc36121b82357130be770a508666.nq.gz
│   ├── 545542b9ea92b0bc4a6f57698d082a28275b962f.nq.gz
│   ├── 5e97e06c7ad606e8376fdf400d0e0e6b1ddd3445.nq.gz
│   ├── 6b59ddb797f5374f70068facaf19917e0efab4ed.nq.gz
│   ├── 84e424c0f9722650309c01e9f3e22f08b4b8f04f.nq.gz
│   ├── 86b5b62bd5c94b3a74cb190f6debb2af40ee5872.nq.gz
│   ├── a699230ffb919e6dd6753f7e0392c8e36dea8e6e.nq.gz
│   ├── afb19e63d8775aa1f5d9cb76f235d1f815d7a41d.nq.gz
│   ├── afcc755d17ee0c898f47f84cd2a941ea3d97ff39.nq.gz
│   ├── b2b7f1739127deafd6d1b50e87ca2e4a396dd0fd.nq.gz
│   ├── c042eb1c624f94b6b7ab8583351fb681c4ad23e0.nq.gz
│   ├── c1403922ae5b234754e5b3d95df74d9ecc5cc054.nq.gz
│   ├── cdfa1351986929e29e75227cc175526040120157.nq.gz
│   ├── cecf848946ead5d322b276ce87d611412b7f22c2.nq.gz
│   └── d20ee9bedfdda1d1785429459dd37e5df9f62f96.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c458ab37ba7d63dda9d11109de970346543ad502.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 25 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[explosion/spacy-layout](https://github.com/explosion/spacy-layout)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
