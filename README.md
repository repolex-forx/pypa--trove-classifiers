# Repolex Knowledge Graph of pypa/trove-classifiers

RDF knowledge graph data for [pypa/trove-classifiers](https://github.com/pypa/trove-classifiers), parsed by [repolex](https://repolex.ai).

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
rlex download pypa/trove-classifiers
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── bc832553ebe6114e7682f09bc59bda6552da37cd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── bc832553ebe6114e7682f09bc59bda6552da37cd
│           └── chunk-001.nq.gz
├── blob
│   ├── 05374a24cd41b3e32dd6a7da3b393ff6abb74ccc.nq.gz
│   ├── 080a874995cb55b5ed1d1acc9cc0bf17a0a3ba9f.nq.gz
│   ├── 250277a27112372df28caba47c0b90552c8036e1.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2653780a62f737b216acc8683fcb79bac7a47fef.nq.gz
│   ├── 2cbf721e794ddef643acc27fdeaa8ec32ad8ead3.nq.gz
│   ├── 3b644e16a75859e7c12ffa5ddd8b2d8661988c4b.nq.gz
│   ├── 45a0ff598ea798d7f1ae01c6b183e7c46e8d7140.nq.gz
│   ├── 533f3b6320d946d4ac0a92abd458fd7ba176e78b.nq.gz
│   ├── 60f6d06e7feea006fcb63ed9c3c312f0d869d698.nq.gz
│   ├── 67f6c49b9bd4132f85773a38f9527f6fa075516a.nq.gz
│   ├── 83b8b45bdb944132804183ddfe4b8891e623e9ec.nq.gz
│   ├── 891c60a0219dfa2016e658309827a31e37544e29.nq.gz
│   ├── b662743b00656c45b7e67fb696ef7652d081a5f5.nq.gz
│   ├── d71e6f2c06c9865195ad89ceab41b623c69ffa0f.nq.gz
│   ├── d8d85e466c9b4679007370c8d99e2c0fb3c08be3.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eb28aa6e34d470da305f2bc1dd66e4f3a99b2a76.nq.gz
│   ├── f39de9221ae6e38a04780f313f988e60293edd48.nq.gz
│   └── fe11925eca7c5c2110d485994ec1c4dfae7db73c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── bc832553ebe6114e7682f09bc59bda6552da37cd.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[pypa/trove-classifiers](https://github.com/pypa/trove-classifiers)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
