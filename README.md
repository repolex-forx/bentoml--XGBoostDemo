# Repolex Knowledge Graph of bentoml/XGBoostDemo

RDF knowledge graph data for [bentoml/XGBoostDemo](https://github.com/bentoml/XGBoostDemo), parsed by [repolex](https://repolex.ai).

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
rlex download bentoml/XGBoostDemo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 27bf18a2229783c828701da9a68fac44492491d3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 27bf18a2229783c828701da9a68fac44492491d3
│           └── chunk-001.nq.gz
├── blob
│   ├── 00ed085af980721d35d3d1677a0f25dbd1f7a11a.nq.gz
│   ├── 07070297099f1672fad1b342dec2ffbfb5e322dc.nq.gz
│   ├── 273847b80d24502db04b8434d09905d7d3f14712.nq.gz
│   ├── 3c28ad6b4b84b5e8c6f54c23ad7c4d49e7a3a0c1.nq.gz
│   ├── 48dd93ce8a877a551b18a32478b0199707854290.nq.gz
│   ├── 4a1535137e0af7c753dcababfdf2614eb9718fbc.nq.gz
│   ├── 8a6a67135cde94b7bcdcbf3f0d459bc1105cff28.nq.gz
│   ├── 987d91954fa9a9b5b2f7f7785da027ff0838a7b7.nq.gz
│   ├── 9adf02e69103ddc1a3d55bee7118f638c8639991.nq.gz
│   ├── a6d550a842657c93c6691a74c2a575bce56d9fce.nq.gz
│   ├── a71513c926ed2b6d164b2c4e14abb44865ee12b4.nq.gz
│   ├── a9d02a8c0fb22afe0761594c0ed950232b207e3a.nq.gz
│   ├── b6a649dc5630b4e549a7a0c23ec1cae4c9666285.nq.gz
│   ├── c9a020ace96ba0e820f1724ef1e51528468edf92.nq.gz
│   ├── d25a2828cafae119f6e070a97e1019a73046d626.nq.gz
│   └── fdc7566bde15b765346545d65b4ffda8629ca87d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 27bf18a2229783c828701da9a68fac44492491d3.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 23 files
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

[bentoml/XGBoostDemo](https://github.com/bentoml/XGBoostDemo)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
