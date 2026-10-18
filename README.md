# Repolex Knowledge Graph of ilevkivskyi/typing_inspect

RDF knowledge graph data for [ilevkivskyi/typing_inspect](https://github.com/ilevkivskyi/typing_inspect), parsed by [repolex](https://repolex.ai).

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
rlex download ilevkivskyi/typing_inspect
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ce24e24812d869e0852611cce736a1af96c876b1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ce24e24812d869e0852611cce736a1af96c876b1
│           └── chunk-001.nq.gz
├── blob
│   ├── 4d88378dac6af2ebba0575be6597a2fb6c7ccaa4.nq.gz
│   ├── 603c5e981c9716e1ba1b98943c062f57ff5c6fbb.nq.gz
│   ├── 61921d08ec398d65024317499abc13709888f531.nq.gz
│   ├── 865db0defbbf9485ba10283349117a1768466623.nq.gz
│   ├── b29e80bd3b66d513656c2e20ce845cb8b7195bd6.nq.gz
│   ├── b7da0dd3ffc64f1f3b94fc4f9bc16e52a738cf6e.nq.gz
│   ├── bdc3376315c40070dd9076f93c91a6d01d981b11.nq.gz
│   ├── c1241640901e68bdd87a6d66660ef0a96c0173b6.nq.gz
│   ├── c3f73848214886337056c2c8b9b66168908f6d31.nq.gz
│   ├── ccbb756c17de910defb448008c74ee26f61bdb63.nq.gz
│   ├── d7ad2dff4546e97f3de8f788016999afec71dd97.nq.gz
│   └── ea2569f22a9ec2402ad973abbf3a67b37301c5cd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ce24e24812d869e0852611cce736a1af96c876b1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
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

[ilevkivskyi/typing_inspect](https://github.com/ilevkivskyi/typing_inspect)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
