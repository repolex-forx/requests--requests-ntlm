# Repolex Knowledge Graph of requests/requests-ntlm

RDF knowledge graph data for [requests/requests-ntlm](https://github.com/requests/requests-ntlm), parsed by [repolex](https://repolex.ai).

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
rlex download requests/requests-ntlm
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 717339ff800830e60fbd62294cb3033ee9a04a66
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 717339ff800830e60fbd62294cb3033ee9a04a66
│           └── chunk-001.nq.gz
├── blob
│   ├── 08d13749b14025389b761d5a12704c32ee775e5f.nq.gz
│   ├── 14dc70ed412f7535d369921b63de2cfcc63a355b.nq.gz
│   ├── 20e8d94be7adeebd3855af74bc1066b4247291c4.nq.gz
│   ├── 253db38a07e49873ac10ff0a071c4c3b3baa2154.nq.gz
│   ├── 3b4f60bc386825555fbc3edf92c2967e64907c56.nq.gz
│   ├── 587828a998393e62ab99909dbd78d11d5da5a88f.nq.gz
│   ├── 5f3e18de12c5280b712b91c345eb28063c24c720.nq.gz
│   ├── 6da52f65a05c15fbb7febc1df1a5aec1f71f032b.nq.gz
│   ├── 72fe8098454fc54b20faa4fa1a17a6c4aec54f58.nq.gz
│   ├── 735ceebf048cbc678a9793d99c413b8f415fb18e.nq.gz
│   ├── 79c59f80766dd21fdda919e56eeb3232381ce39f.nq.gz
│   ├── 88aac14c17381ea19da453786c2395bd61fcc3ca.nq.gz
│   ├── 89a0106941ff398844f23a965c5b755ca12eef97.nq.gz
│   ├── 9579279d32a024fc524ec79ea82a388433c7ab42.nq.gz
│   ├── a868cf7fab80e6c25b1645904e6865820b9438f2.nq.gz
│   ├── ba45e7f3c71a08167401cbb335a6ce0c24ffa68b.nq.gz
│   ├── c776b48f83e9e1f3fa970708f3e643808c6a2b9b.nq.gz
│   ├── d56b011500958d94743c4dc9d40592ede4981c5d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── eccda324bcd57bd33fc764bca49cc8fa3be7c5e8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 717339ff800830e60fbd62294cb3033ee9a04a66.nq.gz
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

[requests/requests-ntlm](https://github.com/requests/requests-ntlm)

---
*Parsed on 2026-10-12 by [repolex](https://repolex.ai)*
