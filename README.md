# Repolex Knowledge Graph of simonw/python-lib

RDF knowledge graph data for [simonw/python-lib](https://github.com/simonw/python-lib), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/python-lib
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 46ad133e8c15ba8a78488dd2d9f97b6136e3a384
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 46ad133e8c15ba8a78488dd2d9f97b6136e3a384
│           └── chunk-001.nq.gz
├── blob
│   ├── 00cd3624cfc646825b3ca9cd826c7e3363f593b2.nq.gz
│   ├── 038a3d49125dda98b3efa8eb368eee42108c7fe1.nq.gz
│   ├── 1a03aacff6b65e7a7e4578a206767fde5307fd67.nq.gz
│   ├── 1d24a1b02ab050b4f2c8e33b05ad5e32b10731c5.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 33ecc5bacd8f4f4ab95531e8e90cf617c67b9f68.nq.gz
│   ├── 49efa25ce83d3709d35f5f589dbc69b8de511a8d.nq.gz
│   ├── 5a5d6ca20df7ee525fe81bba5a27bbada87a6656.nq.gz
│   ├── 6090908934c2a028d46f4f9277734f25a85e08af.nq.gz
│   ├── 923334ef15a25c993476fbb163a15b5d4a9451d5.nq.gz
│   ├── bb068b35c5f985549642c6bd4b91aaf9e9e195bd.nq.gz
│   ├── c3fb10120f2529d61217d285a9479a11f8315e32.nq.gz
│   ├── d034a581277491b3e9b04dfbc036672ef5dde8a4.nq.gz
│   └── db00e6fb015e0a34f5c5b069360a9a7bda8ba1ab.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 46ad133e8c15ba8a78488dd2d9f97b6136e3a384.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[simonw/python-lib](https://github.com/simonw/python-lib)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
