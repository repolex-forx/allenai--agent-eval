# Repolex Knowledge Graph of allenai/agent-eval

RDF knowledge graph data for [allenai/agent-eval](https://github.com/allenai/agent-eval), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/agent-eval
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 28fb1751e6d989a29a3eb99e8a51a336ac1b63c3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 28fb1751e6d989a29a3eb99e8a51a336ac1b63c3
│           └── chunk-001.nq.gz
├── blob
│   ├── 04749bc8cd48e4daa85d8d0e351afacbd6259b2b.nq.gz
│   ├── 07fba9f076066e9b0873c49debfd80a863d89a68.nq.gz
│   ├── 09a181d8a482f9e2feccf560490c8f828090b175.nq.gz
│   ├── 0aa3653073c0037e82772bbd160634adb32e74dc.nq.gz
│   ├── 0dfe8c7240c601936058a8100f52ccf6858407ea.nq.gz
│   ├── 1bc71051b15e388107785a4b4a0ecb6ec1c12c28.nq.gz
│   ├── 26f09bc01f2291a85358d5981007635206a418d7.nq.gz
│   ├── 280095083c72fbfde0569601b8abd31909dd5ba1.nq.gz
│   ├── 2be94514f93924f37790296b07fbd11ff2bf103d.nq.gz
│   ├── 31f959e24ef32dd96f53d8b05c48cc6169c2a664.nq.gz
│   ├── 5cd7cc0389f9c42e6a7d9870198157443c6eec48.nq.gz
│   ├── 5ed48aefcf4c6b687b0ee1970bf299a302b01c48.nq.gz
│   ├── 608a49f6113a34cac89451b99fa0e7949a518d73.nq.gz
│   ├── 644ef44727ec0bfafe55fb88e464d80964e6470e.nq.gz
│   ├── 64875d3bbc47f4ee1370dcd3f08fd34ec1128d67.nq.gz
│   ├── 6e99b7b551fe6d60465f1884fb75eb1e17ec748b.nq.gz
│   ├── 6eb37c715681a147e54a9160b56bca543f695ff9.nq.gz
│   ├── 83ef5e7dd47fe168f42f40e0df9138a8c1ad0f63.nq.gz
│   ├── 8721ca0a2573cc2d1baa6e2839e1e3f675d09a92.nq.gz
│   ├── 90401139802e15154c1a3d69243358275947129f.nq.gz
│   ├── 9528586da3a415ee43bf12b93c6eca18a24da626.nq.gz
│   ├── 96bb6375bd32a2a63c03a941dceeb1ba30a00cc4.nq.gz
│   ├── a0a19e11606b3ec437f45c95cf6dfa3d50478785.nq.gz
│   ├── a1bd6b48f4a766456085d910e84fcba77e071d14.nq.gz
│   ├── a2dcd42393c6a37f7ebeb83a059021e17101ef4b.nq.gz
│   ├── a5887a4b499dd46711e2f440f53e25f31f0078a7.nq.gz
│   ├── a7c821f7d73b31e6d0058c79e64ac290226e0b14.nq.gz
│   ├── a87896fe968de2975e1fd4186ece9308a88cb5be.nq.gz
│   ├── b17e11a4937062bf7f5ccf06903ddbeb41f7b7b8.nq.gz
│   ├── b89b24ed22e04a4e927db7ded5cfe8d10be7a4af.nq.gz
│   ├── d77461e8c879e7ea55e5f3de08ed24d856483219.nq.gz
│   ├── d7f47b504ada5cb34ffe5684c78659dd480c126c.nq.gz
│   ├── d819e434768a30ed09d6fd1d412a865ba20c8926.nq.gz
│   ├── e633ddd95f5d5f3145f01b85d2d327171eba9465.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e727d1470fb073e5c3e67498ca1ce28370391073.nq.gz
│   ├── e9b2db00b7a5cfbe309de4a82d8cd83e692c9818.nq.gz
│   ├── f1f3bfc1ed644c2989b55167bd5473a60cca733e.nq.gz
│   ├── f34980a6aee392aee5cc5cdbdf39ca6ffe169ed3.nq.gz
│   └── fe1880e1b5e0a87734c6e621a2854a39298f0fab.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 28fb1751e6d989a29a3eb99e8a51a336ac1b63c3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 48 files
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

[allenai/agent-eval](https://github.com/allenai/agent-eval)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
