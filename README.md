# Repolex Knowledge Graph of debug-js/debug

RDF knowledge graph data for [debug-js/debug](https://github.com/debug-js/debug), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download debug-js/debug
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6b2c5fbdb7d414483d9e306ef234acb4cd7ea67c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 6b2c5fbdb7d414483d9e306ef234acb4cd7ea67c.nq.gz
│   └── repolex
│       └── 6b2c5fbdb7d414483d9e306ef234acb4cd7ea67c
│           └── chunk-001.nq.gz
├── blob
│   ├── 141cb578b7722324d8e1799b2a41bac473f6a9c1.nq.gz
│   ├── 15be220882c09a7e9898b7d79846c6a72e105bf6.nq.gz
│   ├── 1a9820e262b26b60fe71a4dcd9bc9cfd0a01f26e.nq.gz
│   ├── 40103cfcdccd5440774321d1f6c7cda98005233b.nq.gz
│   ├── 4cc3c0515a24e6b4d902b71988b1fe7dc4aeaa54.nq.gz
│   ├── 5993451b82e6b27d981e202b349641816d867ccf.nq.gz
│   ├── 6e835858c7ea7f99ec21ac097f10c73c2a222f58.nq.gz
│   ├── 715560a4ca8fb4c8dd6353eafdde6e83af28f05e.nq.gz
│   ├── 9ebdfbf1491ef8bdffb942ee0b475e38a65379bf.nq.gz
│   ├── a1d6f63332fa011f252d0281cfa1ebb65d02b3da.nq.gz
│   ├── a2be815976aecfbb2abf5d6aed86222bc4a9cc91.nq.gz
│   ├── bf4c57f259df2e16761b45e2636db307c89ba419.nq.gz
│   └── ee8abb523dbe0ad51949ad8f864207164f38b051.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 6b2c5fbdb7d414483d9e306ef234acb4cd7ea67c.nq.gz
├── filetree
│   └── 6b2c5fbdb7d414483d9e306ef234acb4cd7ea67c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 23 files
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

## Source repository

[debug-js/debug](https://github.com/debug-js/debug)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
