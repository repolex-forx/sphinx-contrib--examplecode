# Repolex Knowledge Graph of sphinx-contrib/examplecode

RDF knowledge graph data for [sphinx-contrib/examplecode](https://github.com/sphinx-contrib/examplecode), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/examplecode
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a4d9028857244b2eba9bb906956e915871050a88
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a4d9028857244b2eba9bb906956e915871050a88
│           └── chunk-001.nq.gz
├── blob
│   ├── 47aacfcf82fe9d07345bc562cb65362d27da2fcb.nq.gz
│   ├── 553691b33cbfecad6236797596755027d617f4ed.nq.gz
│   ├── 56e1649c90a833c6b7466ee9c88e385741102837.nq.gz
│   ├── 58b91887cd53a3cce9fb9f87969e68d311266287.nq.gz
│   ├── 8e7e2bc0d26ebc39199523caf9850ff62f3d650a.nq.gz
│   ├── a7540a0a2100d385034c828b05814e5410cd3722.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── f0908b85ac10a6e30f6aac8afed31eb0fb1d3214.nq.gz
│   └── f49c65644c50bf2a7328f2c4f9a8f97cbc8a2a2a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a4d9028857244b2eba9bb906956e915871050a88.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[sphinx-contrib/examplecode](https://github.com/sphinx-contrib/examplecode)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
