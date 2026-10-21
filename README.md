# Repolex Knowledge Graph of networkx/branding

RDF knowledge graph data for [networkx/branding](https://github.com/networkx/branding), parsed by [repolex](https://repolex.ai).

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
rlex download networkx/branding
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ae3bf51c7e52d37ab592c7ec3119467f84f5d43b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ae3bf51c7e52d37ab592c7ec3119467f84f5d43b
│           └── chunk-001.nq.gz
├── blob
│   ├── 9e8d8053c351330aa7930f524b2653f1b387f7f8.nq.gz
│   ├── a6559b1e3a24f6aeef2046b6b7efb118ac3199a2.nq.gz
│   ├── aa20bf8b902e4e7ea5f0deb75dea1f3b13bd7533.nq.gz
│   └── d07283e7f9228a0380495c1cc89c18a25b355ec5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ae3bf51c7e52d37ab592c7ec3119467f84f5d43b.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 11 files
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

[networkx/branding](https://github.com/networkx/branding)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
