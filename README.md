# Repolex Knowledge Graph of google-deepmind/deep-verify

RDF knowledge graph data for [google-deepmind/deep-verify](https://github.com/google-deepmind/deep-verify), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/deep-verify
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ad74b938b28a6f2fde2273b07f5d305767e7833a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ad74b938b28a6f2fde2273b07f5d305767e7833a
│           └── chunk-001.nq.gz
├── blob
│   ├── 02063516deb00cb3ee0e041f12bacd9013df27c9.nq.gz
│   ├── 06d63ef249d85ab9023fa74b69d184ac1740836c.nq.gz
│   ├── 0cefa9379a584f5514c560d89a9573fe96cb0293.nq.gz
│   ├── 15c03f1bd3e91ea30a439df2566515e40cb0031d.nq.gz
│   ├── 2f7b25c29afebfe4a5bd62ea2f91cbba9dcee7ad.nq.gz
│   ├── 3297ca41df84f91e50d1fa6e54def90f539964ff.nq.gz
│   ├── 37ddcf16856150e7a65c656bfcfabb3705c7acf4.nq.gz
│   ├── 42894f765b8f2d72f45f661d9c07f5e23dc4e267.nq.gz
│   ├── 4781033260b32900f041f9cc0a7d80ef59028fbb.nq.gz
│   ├── 5471dc10377b76db85a2feca7a99a7eef4980ba8.nq.gz
│   ├── 5532c5cfbf35b4cb91f9bf0d1aea08f53c55d5d7.nq.gz
│   ├── 59897e769356b74acaf131fa7c311d5ee1ebe638.nq.gz
│   ├── 5cfb2752698a093fd7e1b4a4c35487b4488b8268.nq.gz
│   ├── 5e0e54b3fd9200e27e5ea2c55d59b533e9c1cff5.nq.gz
│   ├── 5fc7eef7ba38ff76a140e5fec9a3bebdea5e20d4.nq.gz
│   ├── 634caf5f6b68e4832c846be7b104e4ed2300a1e2.nq.gz
│   ├── 8156eb2aa01cd6eb9187ca98ccdd0671706c6b8c.nq.gz
│   ├── 87c6855b175b5aa7068be52a90614565be1fdcce.nq.gz
│   ├── 940ea2cddd066a01d11c44058515d904eddda58d.nq.gz
│   ├── 98a1548305340be0c2c2a1c8297a960cd9ba439d.nq.gz
│   ├── 9a4049dc267e1ce99d85022d858c3254b5bbae77.nq.gz
│   ├── a5bc25f8e215b0f58f7e3b5a0f62b4a75938098e.nq.gz
│   ├── b6f77899b0216313d76c4bb395fe77ed12c0904a.nq.gz
│   ├── bad81ddedb8c29f806e9c8158a817d56f9a5deb0.nq.gz
│   ├── c1e7370e5dd6e3618748bab1bc0aabb065a6fdb2.nq.gz
│   ├── c380c8975b6b0af436ab1b625b8cd2d12bb3a518.nq.gz
│   ├── cfe7d25e53284c2b52b9246b2d98d83839fee64f.nq.gz
│   ├── db177d4ac70f76c2172ce65ca33c830d6cbd3ac5.nq.gz
│   ├── dcf9311527c7cc3d2c0f9b7c9252086c38569015.nq.gz
│   ├── de12ca814f210e5467ed7944b77a1673a98d5725.nq.gz
│   ├── e7026b5458291302dcf06d57886e66d307ca07a4.nq.gz
│   ├── eb7a2f476db93bce25be29feeedaaa7b1b9a0e6c.nq.gz
│   ├── ed62ebc405433d6bd82ef62e651eb8b65b05ea52.nq.gz
│   ├── ee0f0bba0ca8a0c28222da7d09d029130b9da46f.nq.gz
│   ├── f0438292599a1254e0f8accd64430642138c075c.nq.gz
│   ├── f189794d0d18f9850e9162a45281b171173523f0.nq.gz
│   └── fbe6be2a85dab1a0ccfe1f5564a051782df5eecb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ad74b938b28a6f2fde2273b07f5d305767e7833a.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 44 files
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

[google-deepmind/deep-verify](https://github.com/google-deepmind/deep-verify)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
