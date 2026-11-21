# Repolex Knowledge Graph of seanmonstar/spmc

RDF knowledge graph data for [seanmonstar/spmc](https://github.com/seanmonstar/spmc), parsed by [repolex](https://repolex.ai).

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
rlex download seanmonstar/spmc
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 47deaaa59ea5eea8f16e178920047f9ca5f53dea
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 47deaaa59ea5eea8f16e178920047f9ca5f53dea.nq.gz
│   └── repolex
│       └── 47deaaa59ea5eea8f16e178920047f9ca5f53dea
│           └── chunk-001.nq.gz
├── blob
│   ├── 3f3bbb0dd11fa32773181d2148962ff205685241.nq.gz
│   ├── 6b45410e13ce09760f2f11c529b8e5024e4fd071.nq.gz
│   ├── 83da933eb739071fd5aa85b091869716ccd098e8.nq.gz
│   ├── 8765d5f9da5a04d4ed42833f205f0edde0b73bfc.nq.gz
│   ├── 8d40c69575101c9834aeacae1a68c46a94c4e760.nq.gz
│   ├── 908d1842a14c64854fda781c6fe0dfb890e42949.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── c24cf22729a5a979175496a7aae7718b0c9fdc88.nq.gz
│   ├── d6c5ffa7415a8c1e592c98996042935a16e94be5.nq.gz
│   └── f62775d2bc695876b2d1995b12c0409649824459.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 47deaaa59ea5eea8f16e178920047f9ca5f53dea.nq.gz
├── filetree
│   └── 47deaaa59ea5eea8f16e178920047f9ca5f53dea.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 20 files
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

[seanmonstar/spmc](https://github.com/seanmonstar/spmc)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
