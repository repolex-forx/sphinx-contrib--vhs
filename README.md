# Repolex Knowledge Graph of sphinx-contrib/vhs

RDF knowledge graph data for [sphinx-contrib/vhs](https://github.com/sphinx-contrib/vhs), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/vhs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5cc9b2666488329f462a1c7b3e62b4239ccfc6a4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5cc9b2666488329f462a1c7b3e62b4239ccfc6a4
│           └── chunk-001.nq.gz
├── blob
│   ├── 03c8e6e054d4909e7de2b078b148aefd8c67893f.nq.gz
│   ├── 051664d63e73ac36c6ab11d9fa17293a389890a1.nq.gz
│   ├── 061f32f91b96f05f8fa2b52b2edcdcc19aa33d50.nq.gz
│   ├── 07c0d82678a57a78ec390c068535603bc1e05de5.nq.gz
│   ├── 0c0320a8b5cfc6be424be1032658cd7abbf8d9ad.nq.gz
│   ├── 0d6977c9de8d1c9611832147c976a5134cb69bd7.nq.gz
│   ├── 0f41def38afcab3000c577eb0e651273b63026ba.nq.gz
│   ├── 10f62abd172fc6b5a5b6d8b200f947efbc5e5897.nq.gz
│   ├── 1b3d746eeacc8092ae7b9c3c4c50c041b8b2fdec.nq.gz
│   ├── 1f6e93178278ff856f188883f01438dd42c153a1.nq.gz
│   ├── 2b55c5242238b473ea7c3e8fcd6afb980b3bdafc.nq.gz
│   ├── 37695284d1c3d184667b168968ac0b455374914b.nq.gz
│   ├── 3938dde46c6b043d70b77612fd7765d0f9a7bd18.nq.gz
│   ├── 3aab02d59e5ceb1f43c493206db4b9a152020c08.nq.gz
│   ├── 440723feedacaefde895c38bbff70a510ee5679b.nq.gz
│   ├── 49ef5eb696388d82021147d642ba702601bcc3f4.nq.gz
│   ├── 5c2c1a988b75a8209684043a988a49372ec67e30.nq.gz
│   ├── 5efb2058f9208fee1d5576401cb9bf0242177d1b.nq.gz
│   ├── 64e4e429b5487a5b729c322a488679a1f50de671.nq.gz
│   ├── 6e538e029c6fbd5a99340bbd23b0a7702cc6c12c.nq.gz
│   ├── 7301d5dcdb78e272145f66a3f94f14a8ce270cb7.nq.gz
│   ├── 8013d0b16be0d940f84cd46c8301d5feebc60f41.nq.gz
│   ├── 9291da01074828608b889245dde9288b29068b73.nq.gz
│   ├── bae363808f91458def57133236f0a6f4a8aca001.nq.gz
│   ├── d7456fd07e6bb464b1ce6a6a3a0f8a3bd272ef59.nq.gz
│   ├── da0100cdd9a268adc8abcb7b0e86fb302b5ae1d7.nq.gz
│   ├── e3681c231d50149694e9afbf97f1c4ffe8c82f3d.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ec0cb36ee46d6a472b1ca3facd8a030965285d53.nq.gz
│   ├── eee93da8abf37ab3afd57b39fca614c1fb08785e.nq.gz
│   └── f9dcf20dc7c47b53495a88e7e0a58ae258931dfc.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5cc9b2666488329f462a1c7b3e62b4239ccfc6a4.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[sphinx-contrib/vhs](https://github.com/sphinx-contrib/vhs)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
