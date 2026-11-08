# Repolex Knowledge Graph of canonical/fprintd-snap

RDF knowledge graph data for [canonical/fprintd-snap](https://github.com/canonical/fprintd-snap), parsed by [repolex](https://repolex.ai).

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
rlex download canonical/fprintd-snap
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 91f564a46b0ccad88502cac8e0a89ca4d34bded6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 91f564a46b0ccad88502cac8e0a89ca4d34bded6
│           └── chunk-001.nq.gz
├── blob
│   ├── 05872d3bd2658094d655e00b9650d474c6948a1b.nq.gz
│   ├── 2051c072ac41adc0af5ca2e4de138e337d407737.nq.gz
│   ├── 2ba6d99bb74b129f8addd1124566a508b9cfff45.nq.gz
│   ├── 694d0f26d29cb17f52f5e7c714a9f30e1d2b13cd.nq.gz
│   └── e5f64e229ea486f95677c18babdc667537559e83.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 91f564a46b0ccad88502cac8e0a89ca4d34bded6.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 12 files
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

[canonical/fprintd-snap](https://github.com/canonical/fprintd-snap)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
