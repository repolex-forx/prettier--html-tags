# Repolex Knowledge Graph of prettier/html-tags

RDF knowledge graph data for [prettier/html-tags](https://github.com/prettier/html-tags), parsed by [repolex](https://repolex.ai).

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
rlex download prettier/html-tags
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0828a65d8186a3f3063be53d1f45d9104e4a3e42
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0828a65d8186a3f3063be53d1f45d9104e4a3e42
│           └── chunk-001.nq.gz
├── blob
│   ├── 029a41251da4ecacdb858cf4feb0211cc950d452.nq.gz
│   ├── 03ddc801a657f1e6b389b92b5a866df68f70bcfa.nq.gz
│   ├── 384848fcfc4c0fc3833243ee2751b6802733e14a.nq.gz
│   ├── 502fce0c050a6c965118bd5f80888c2c09e56f79.nq.gz
│   ├── 5aff0365ddcafd2bf9dc21ad4e71233468d0a016.nq.gz
│   ├── 5e4ab772476c839b13a888ed881a9c6a79f8baa1.nq.gz
│   ├── 6313b56c57848efce05faa7aa7e901ccfc2886ea.nq.gz
│   ├── 63869a53518ede4f0e3000d887e92d23eac5b278.nq.gz
│   ├── 676f11b2c1a683d3175cf0455ee1bc8ff52da375.nq.gz
│   ├── 78a8f3b23653ea9d40390423ebcf84fcd7352244.nq.gz
│   ├── 8579f758332f252c9c3613d065c4ad4b1cb9ef14.nq.gz
│   ├── 872d2d1c1e83fabea9aa5f503b48aaa2642df677.nq.gz
│   ├── 882fcd7fdbd7abb7b83825b20fb5414acdf1ae7b.nq.gz
│   ├── 947326fde2b0fd465129479e5fb651c3250f3886.nq.gz
│   ├── b96d37b88006767e63168b431c614e7976363656.nq.gz
│   ├── bfb215112f39587d5f8cd09b63f6852ef4b5f53a.nq.gz
│   ├── d16658fd3101ad1239993ca084913505517db591.nq.gz
│   ├── d760976b32956c8c27f1caba996e2891c888f9c7.nq.gz
│   └── fff7c5ffd010d8d1f4e3decfd4783cca6aa61ade.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0828a65d8186a3f3063be53d1f45d9104e4a3e42.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[prettier/html-tags](https://github.com/prettier/html-tags)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
