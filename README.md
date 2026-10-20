# Repolex Knowledge Graph of coleifer/cysqlite

RDF knowledge graph data for [coleifer/cysqlite](https://github.com/coleifer/cysqlite), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/cysqlite
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 24fddb3bfffd5e6f8f3220c33961aea9abe59c50
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 24fddb3bfffd5e6f8f3220c33961aea9abe59c50
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ba9f54a32faf0a9b405db671157bb98f9871cb3.nq.gz
│   ├── 0cb58f727221d68f7b8fb440099fef4531d92d66.nq.gz
│   ├── 0def884f1a0ffa94e90fbe2d65e4e93a938b7188.nq.gz
│   ├── 0f25d2c60a95e23b686f7f7e9730f82cc5e017ab.nq.gz
│   ├── 0f4cb8ab045db9b37f107a4ee78b53f1d011de9f.nq.gz
│   ├── 1a6efbb974697c07ff7af62cb28bcf94cbfb8c7c.nq.gz
│   ├── 1bd98f8f01add10ef7955064e8216c6fa7804eb8.nq.gz
│   ├── 1cf7181d3be8248c8f71be272cc7025e952d3289.nq.gz
│   ├── 1db9b4ecb13f186f4391b018fcba05c88f039ba3.nq.gz
│   ├── 273b7355ae78973d057ea086e303bc7183104768.nq.gz
│   ├── 293c4e6c957c44b8ed0398c56e3b16cd53153ea7.nq.gz
│   ├── 32bb24529f92346af26219baed295b7488b77534.nq.gz
│   ├── 45c9030dd6176dd1b56ac4e703d723e41c754994.nq.gz
│   ├── 4ddd0bb12aafc6542da1a9d5392a6ac1eae0ab45.nq.gz
│   ├── 54bdbe21fd43481ce93b878bd6f64815bb3e14fc.nq.gz
│   ├── 5cb31fe09fb12b42ee29ebb75d7c77868e5d82e6.nq.gz
│   ├── 67496ef1044f4547cec67253ab9c370b1b3f75a8.nq.gz
│   ├── 6baea0c9a3fcdddd01672c69f2208d21bf8a72eb.nq.gz
│   ├── 6bddfe16d3cb2d63a9d9ec18c729701dd7381157.nq.gz
│   ├── 6c5b8f25998f38b510770965097be2e6bf0d273b.nq.gz
│   ├── 80f8ede3174dbb74d356a63efa14a615196a219c.nq.gz
│   ├── 864e5031f75b3682971aaa70562af6059163a93f.nq.gz
│   ├── 86c014e771fdfca7e087f26ceaad2ed676ff6249.nq.gz
│   ├── 8c73734c0d54b107124e1c5435a06e95de2d2180.nq.gz
│   ├── 96df384be24f881a682b2c645dc007d8cc6306ff.nq.gz
│   ├── 9abd060ea3c112079f4b28db9927dc0a01d8c2a8.nq.gz
│   ├── a7f200fdde84a5344e06e54b91389f1fb8fb6363.nq.gz
│   ├── b48c48a2669543263466a1ea1f7e3d58623712c3.nq.gz
│   ├── bb5844fa152068c435830e641fb8e5cd02b1aed8.nq.gz
│   ├── c661043d47d873913341fd507579a1491c982ee2.nq.gz
│   ├── c9b0d610b98f11612ed1ef50047c268e5e81d5e5.nq.gz
│   ├── d4bb2cbb9eddb1bb1b4f366623044af8e4830919.nq.gz
│   ├── dd77cf1d232a8afccc3d85de5a348406f8bdf6bd.nq.gz
│   ├── e303eb1ec1717b214621f7cef6a9dac8905d7355.nq.gz
│   ├── e4336e6949948f95b674c9dfeee586912de7d053.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eac5b4d9b1e567e394d8207f8abbad0f89708c9c.nq.gz
│   └── f62c5797917e3777ffb721d2411c127e1377fda0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 24fddb3bfffd5e6f8f3220c33961aea9abe59c50.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[coleifer/cysqlite](https://github.com/coleifer/cysqlite)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
