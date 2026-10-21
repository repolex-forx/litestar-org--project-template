# Repolex Knowledge Graph of litestar-org/project-template

RDF knowledge graph data for [litestar-org/project-template](https://github.com/litestar-org/project-template), parsed by [repolex](https://repolex.ai).

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
rlex download litestar-org/project-template
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 47f05bd5aaaa6473aef42fbb586f759beb57d43f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 47f05bd5aaaa6473aef42fbb586f759beb57d43f
│           └── chunk-001.nq.gz
├── blob
│   ├── 02b4dd0c499a3222d225dfda03ac6177d984b8c6.nq.gz
│   ├── 0676c8bc4018af5aa5072af99c89b59602abf890.nq.gz
│   ├── 0d6173793aa8e88a51e3fdf14d068327e51cb322.nq.gz
│   ├── 123014908bebbfb7ecfa1d15daaceb272fabe05b.nq.gz
│   ├── 1a1fa0bcdc7467694a9504516c4f9dcdcacf1eac.nq.gz
│   ├── 1d27fd298befe01c50206e70480a41bdad0b8269.nq.gz
│   ├── 21cb5c8cc362ae3042299e607ae5cce77f3e2a02.nq.gz
│   ├── 39c55e6275faa5d695d8699272cd62225b352440.nq.gz
│   ├── 3ba13e0cec6cbbfd462e9ebf529dd2093148cd69.nq.gz
│   ├── 3f02104fe21f3ff6aa1963ee550528548774ba74.nq.gz
│   ├── 4e58f77a5603d469b738db232743e40442dbc96d.nq.gz
│   ├── 5b0078495f326f864ae663a42f825f6aebce88a4.nq.gz
│   ├── 5f4d945df9a2ea6129b8b41ab194cdb860cebbb6.nq.gz
│   ├── 6b3c486724bf938a62af9482556512608fbe7fa6.nq.gz
│   ├── 7941f6aa65c2fcc73500e7bb900931f8a4844173.nq.gz
│   ├── 798101a09d02a96bfc0f20fb78fbdd5d6a3df129.nq.gz
│   ├── 7cdb49f299170cfc082529f3d1d34c7080a0fc51.nq.gz
│   ├── 7e10b27120b92c347d5e189bbf174cd2ec41347e.nq.gz
│   ├── 7f0547b684509aac91b93fff98eeb9d5de80eacd.nq.gz
│   ├── 8a104b3053cd4501513a4670147050214fb4d457.nq.gz
│   ├── 90446afc3da119a8cdeadaee892c7a70768b84d9.nq.gz
│   ├── 91e6dcb697e4278938ded29b9ae8e17a12512136.nq.gz
│   ├── 9a60dc628cbf9520330a57545b9e5c3df68ecb7a.nq.gz
│   ├── a3c98e09941b3fc870e0c688d587ebf091e272ba.nq.gz
│   ├── a70afa7831596380266ef3918f9e652210059e55.nq.gz
│   ├── a9c36f957b9d4d21b690882de464cf5b0477c535.nq.gz
│   ├── b3450b821343219962b2637be932b53a1dc02c25.nq.gz
│   ├── b666f2cc0226e12e2944bf775ab50a0d7487a096.nq.gz
│   ├── b692c07b1cf4126e0d62c09c4353d1a191d1f8e6.nq.gz
│   ├── d0a7a44246b5cc4cf8de4f32577c5cfa91cc11e8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e7b666c4aae34385192884d45b02f2c3d4121efd.nq.gz
│   ├── e940da078c6b6706a120f984d7d21c3bc6255ac3.nq.gz
│   └── fe913e87fa1830aa54557cbf8ba51f7bdb8d13a0.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 47f05bd5aaaa6473aef42fbb586f759beb57d43f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[litestar-org/project-template](https://github.com/litestar-org/project-template)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
