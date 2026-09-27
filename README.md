# Repolex Knowledge Graph of asimov-systems/asimov-platform-workshop

RDF knowledge graph data for [asimov-systems/asimov-platform-workshop](https://github.com/asimov-systems/asimov-platform-workshop), parsed by [repolex](https://repolex.ai).

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
rlex download asimov-systems/asimov-platform-workshop
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 954eb7c6b5bfecc658789f0575b0a5dfd0afea0c
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 954eb7c6b5bfecc658789f0575b0a5dfd0afea0c.nq.gz
│   └── repolex
│       └── 954eb7c6b5bfecc658789f0575b0a5dfd0afea0c
│           └── chunk-001.nq.gz
├── blob
│   ├── 688c611f8e81ed12a4fdf672bf2071a00095ea1f.nq.gz
│   ├── 8116dde0e5986785ef574b1ffb5b5f88751f4d1a.nq.gz
│   ├── 884954d1ff6f6c89e76cf1ac03ab3d8adbee3410.nq.gz
│   ├── a990e900f907eb7c6e3f63a35ce6144986d8dd3d.nq.gz
│   ├── b4ec8c54c1b3bd8703f0cd8a6ca9604ac2c61e3b.nq.gz
│   ├── bb67c988519445888ae76a7c7c4041de9dee75cf.nq.gz
│   ├── e3e57a8ce4ccbf74759a6df8fa4a3980ff1c9209.nq.gz
│   ├── e7d5d82843e20ffdbdd53b3d56a6ffe30e5bc8a7.nq.gz
│   └── ecee426f9ece9d872172b7aa889317df52e41f5a.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 954eb7c6b5bfecc658789f0575b0a5dfd0afea0c.nq.gz
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

[asimov-systems/asimov-platform-workshop](https://github.com/asimov-systems/asimov-platform-workshop)

---
*Parsed on 2026-09-27 by [repolex](https://repolex.ai)*
