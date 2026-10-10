# Repolex Knowledge Graph of samuelcolvin/pydantic-ai-pii

RDF knowledge graph data for [samuelcolvin/pydantic-ai-pii](https://github.com/samuelcolvin/pydantic-ai-pii), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/pydantic-ai-pii
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2ff638b7cdcfbeea34acf0773b7112024c2d03cc
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 2ff638b7cdcfbeea34acf0773b7112024c2d03cc
│           └── chunk-001.nq.gz
├── blob
│   ├── 10a159f7fc0bb3fe3e72b48c851d2d410c859629.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── ba07f138f5d63f30d02cf0d9baf13c55e049b331.nq.gz
│   ├── bc1a1a00ea78f97b0a1da7bc9f16658849eaca65.nq.gz
│   ├── cf26ae97b8772fa6b1a0c0df415d077af7f3f1a2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── faca77c59c13a0c5baaa46c667c96de0dbfdbcb8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 2ff638b7cdcfbeea34acf0773b7112024c2d03cc.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 13 files
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

[samuelcolvin/pydantic-ai-pii](https://github.com/samuelcolvin/pydantic-ai-pii)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
