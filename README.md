# Repolex Knowledge Graph of jupyter/jupyter_console

RDF knowledge graph data for [jupyter/jupyter_console](https://github.com/jupyter/jupyter_console), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/jupyter_console
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 29f882adec78a60a0891c69087436503493905ce
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 29f882adec78a60a0891c69087436503493905ce
│           └── chunk-001.nq.gz
├── blob
│   ├── 02bbfd1490125d565996ba383474601e2747f3a6.nq.gz
│   ├── 076177a497fae1482179137af028465c4f6b9c94.nq.gz
│   ├── 1028683b540bcbdf2b7f4270e5b97bda5d0a5c60.nq.gz
│   ├── 1574852dfc8fc371fc0a257410b7abf96b7e8367.nq.gz
│   ├── 1eda15d28a74eb45ec62fd7604ac6c3b8554e0a3.nq.gz
│   ├── 28773b551d8acb6e46633dbb22150b3681821e57.nq.gz
│   ├── 2f9035b761b88ac80da925f1f39b0b58b35892bd.nq.gz
│   ├── 35cee1baed667af0bcf88ee0fe190ee10c6b1a9d.nq.gz
│   ├── 387392c8aadfa85c5c35851b404db2050f1416de.nq.gz
│   ├── 4956dfc94c591cb9e27c04f06a93c55f66c38724.nq.gz
│   ├── 49614cad4f888d8a2d14da681ba918089b6534a9.nq.gz
│   ├── 510e1a85d852e298ae858cfc22ce36b9bf7a8733.nq.gz
│   ├── 5831d50b9ef5bb79d052374d196db1218c779f75.nq.gz
│   ├── 58be2a8da46778fa0a5a470c4a4096c0acc1611b.nq.gz
│   ├── 661136d13571555a3efee3a3386ad2cbf3a65d5d.nq.gz
│   ├── 6b73dbf317a5add1b78176f6e895ed3c618f2739.nq.gz
│   ├── 8130a7896bac0f74a85b474ea8f995ddee20af1d.nq.gz
│   ├── 83b5ee65aa679a2c2987c823072d724d8b8a77a8.nq.gz
│   ├── 877d94f067adf81704a4d44abd65179240168fa3.nq.gz
│   ├── 98d96cc2ab7604eff85a1e9e800d257f83719ac1.nq.gz
│   ├── 9c15e130e8c8480dd6eefd5b1c69f1f4a8f030e8.nq.gz
│   ├── a2a5b545e4bdf84f7adceb0b387338c82ceddb43.nq.gz
│   ├── aa7880b8c8375d67776c99b51a580d8ff8d016c5.nq.gz
│   ├── b68b4d7d35e5b8a4745e97351f79383664408ec1.nq.gz
│   ├── bd1b6b22b00578773fe77f7f72494412e1eac407.nq.gz
│   ├── bd6544e25c853e38195485909ebe8c4a6a56ec3f.nq.gz
│   ├── bf728124ed62ea29648d7fe96a33bd153d12534d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ee50fbf4d46eea65694555fbea2e0b4a49f5b3f3.nq.gz
│   ├── f206fd07647bf34d56b68af887e6d075c8bf2d1c.nq.gz
│   ├── f6151fc0f0cd5eb0ff1becd6e76cbae0b0471b03.nq.gz
│   └── fd95bf277db8c41e8d4165b1a935259fea7fb1e8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 29f882adec78a60a0891c69087436503493905ce.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 40 files
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

[jupyter/jupyter_console](https://github.com/jupyter/jupyter_console)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
