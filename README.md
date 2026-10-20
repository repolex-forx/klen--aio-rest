# Repolex Knowledge Graph of klen/aio-rest

RDF knowledge graph data for [klen/aio-rest](https://github.com/klen/aio-rest), parsed by [repolex](https://repolex.ai).

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
rlex download klen/aio-rest
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d37bc4a43aaf68152ed0873a8037ce5c78606a66
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── d37bc4a43aaf68152ed0873a8037ce5c78606a66
│           └── chunk-001.nq.gz
├── blob
│   ├── 07dc45dec4393a23036b147c35bce5577a864474.nq.gz
│   ├── 0bd3e2b04e2e8115f7465f3eb301f1da68a3187e.nq.gz
│   ├── 1c6a64dfc6544042269fac2ea38ebb41bc611404.nq.gz
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 2d0b2994c46b02a5ebfe12582e049e044c291d31.nq.gz
│   ├── 3e47bc31dbcbf868e1135a6f55c8bb1f590b90d8.nq.gz
│   ├── 414eb0288be9bee8efe9f83d4ff83a736e46dd16.nq.gz
│   ├── 41b229ef981b1b2b49f28b486d4a6a817a7c6d04.nq.gz
│   ├── 68a2ba02d32a5f18fe1d9ec925b03cd5b650e996.nq.gz
│   ├── 68ee27bb43ce73ade48f962cb84bbb2ec7a528a6.nq.gz
│   ├── 85415880ea61575a9a2f9c35abf39cca4bfbd785.nq.gz
│   ├── 85e6bb5f80468f47d0f877885c49f352a4775d84.nq.gz
│   ├── 8c9687899a78c06dcbe07cf26b90cf2d530e41e0.nq.gz
│   ├── 9109dc60d087a20b62e10fcc75c0924c0e880b7b.nq.gz
│   ├── 98d5bf6ea7b671835231d7aaa907b3cfe268751e.nq.gz
│   ├── 9df1304f6aa5cf5c63eca8f0258afa48ee1aa839.nq.gz
│   ├── b3a5a14b58cbdc488b0bcca29595cf2c255db54b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f3cfe49f7d22888f0f4f66b61c20faeab950429d.nq.gz
│   ├── f64ef6747aa62408dad428c4eafa17034cf97175.nq.gz
│   └── f67f0eee14cc6b4861da581d2f8601cf72873812.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── d37bc4a43aaf68152ed0873a8037ce5c78606a66.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 27 files
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

[klen/aio-rest](https://github.com/klen/aio-rest)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
