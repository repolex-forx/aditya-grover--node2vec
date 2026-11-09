# Repolex Knowledge Graph of aditya-grover/node2vec

RDF knowledge graph data for [aditya-grover/node2vec](https://github.com/aditya-grover/node2vec), parsed by [repolex](https://repolex.ai).

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
rlex download aditya-grover/node2vec
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 883241e825e1473ef9916ac79f6686f5ef6b1603
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 883241e825e1473ef9916ac79f6686f5ef6b1603
│           └── chunk-001.nq.gz
├── blob
│   ├── 0293411a9555c59167d47af91a2caf55ceaadddc.nq.gz
│   ├── 0790ab9cefa18b4809fe62c29a33f1da30dd56d1.nq.gz
│   ├── 07ec21a1d2cd04b9ae920804c42ad1a9d6049cea.nq.gz
│   ├── 1b83969c62887ef7f54f1dfc7a1279ab1f4a6476.nq.gz
│   ├── 43f6684f3ee409868b581e33895ea521858ee811.nq.gz
│   ├── 69fa6ec5807fa2190ce813e32ab044cd137bb7e5.nq.gz
│   ├── 82ac7357d6044a90506e3f4715b8b6520d92998b.nq.gz
│   ├── 8f7edb4525ffe443e401bd4496e5f361e63d0214.nq.gz
│   ├── 960fa8c9dbcd8437770b422666fe38d0cef75529.nq.gz
│   ├── a6c4e85d9ebf2f559530e9e08ff1fb7c5d15f68d.nq.gz
│   ├── aa209cf6534f795d1a0aed932ec322841fe193c6.nq.gz
│   ├── af4a91f64f74568d793db4d74cd42a9ae014408b.nq.gz
│   ├── b958576139df8d08ceca4e7fa2c148fe54d8de05.nq.gz
│   ├── d941e1b93b743323b4d3dacdfbb14b7a39af33bb.nq.gz
│   ├── f3494e54ee87f5d7b51ee2e8d56b143ca6a4359a.nq.gz
│   ├── fa6fc750bc808c831cb361a9743373970ac186b2.nq.gz
│   └── faa710ca36b26473e27bb1f74af311dd0b0b156d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 883241e825e1473ef9916ac79f6686f5ef6b1603.nq.gz
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

[aditya-grover/node2vec](https://github.com/aditya-grover/node2vec)

---
*Parsed on 2026-11-09 by [repolex](https://repolex.ai)*
