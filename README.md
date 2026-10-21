# Repolex Knowledge Graph of tox-dev/github-workflows

RDF knowledge graph data for [tox-dev/github-workflows](https://github.com/tox-dev/github-workflows), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/github-workflows
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── aa039a01064dc0b249793835b85ed0d3e2c2de1c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── aa039a01064dc0b249793835b85ed0d3e2c2de1c
│           └── chunk-001.nq.gz
├── blob
│   ├── 0bd6a465004836c793b076b2425d4c2d2fd7364f.nq.gz
│   ├── 2a991bfd7c6831a10de2c6598434b40d5a6ee474.nq.gz
│   ├── 364982344fbd94d55705e1f27a9a87abaa255333.nq.gz
│   ├── 3c27abf613ebf5725fd233167883713141575df0.nq.gz
│   ├── 3c7a35d84a90974edcf2aae601330999db39d37d.nq.gz
│   ├── 3c8c76c398cd18ee1614510998fd3cdafc370482.nq.gz
│   ├── 48db84aebb85d9ee63d3b7bb408d6b02e96094be.nq.gz
│   ├── 50d3feaab2651053ff28f780bff0d4238dc19854.nq.gz
│   ├── 5dd706561a7cbcd2990aa76b1afc73abb22b5a26.nq.gz
│   ├── 67cf9774f46ba4f4cf56a759561fe60ca5706065.nq.gz
│   ├── 7e20f52a0f3b264739517d1951852469e413bbf5.nq.gz
│   ├── a1c23650b5d3e0620cd70c9301bdd4dbea32e3f7.nq.gz
│   ├── a211bd8a48a95c78f866e2c5f517a23af1335c20.nq.gz
│   ├── a508bfbff5e0c2853001036bba7fa6583938cc8a.nq.gz
│   ├── aa516b03f257c8e137619cd1402a0219da77e9b4.nq.gz
│   ├── bc4f0d0871767bd8be18018de25e1eb0dcc7422c.nq.gz
│   ├── c52fc6c5e115c821756c656ae282586320b55ab6.nq.gz
│   ├── d80ba3b8d1be4cf1793f1b092732d403dc39bfa0.nq.gz
│   ├── f9f1e3c2e46bad30bcf93e4ba1903a40d5aa7567.nq.gz
│   └── fe0ea3e79c8fc2c8dcdae0784ad7d6969575a10e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── aa039a01064dc0b249793835b85ed0d3e2c2de1c.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 27 files
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

[tox-dev/github-workflows](https://github.com/tox-dev/github-workflows)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
