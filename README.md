# Repolex Knowledge Graph of NousResearch/pokemon-agent

RDF knowledge graph data for [NousResearch/pokemon-agent](https://github.com/NousResearch/pokemon-agent), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/pokemon-agent
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── f8a03e4a8bc58f1d9dda6d677a7436cc832a57a9
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── f8a03e4a8bc58f1d9dda6d677a7436cc832a57a9.nq.gz
│   └── repolex
│       └── f8a03e4a8bc58f1d9dda6d677a7436cc832a57a9
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d91e3302eb0ad1d193d14c3723fe554538bfd01.nq.gz
│   ├── 0de9469352e5bc12a806b6e4fe298b9c432cc745.nq.gz
│   ├── 17d042319ef73210c40763761e7435fbbfabf0fd.nq.gz
│   ├── 1a835c55ac576f508baf8fa76f02672bef06001e.nq.gz
│   ├── 1df90e13110acbcf45fd0fc8540a8d9d4f218e80.nq.gz
│   ├── 1e8cc6f249f1d35f88e45889a90a81cc4ab40eb5.nq.gz
│   ├── 2004710624e78f681193e583a40daf9ceae92813.nq.gz
│   ├── 285c9f59b10c93a18cd4a059f05ff8024f2ff977.nq.gz
│   ├── 357f9250aaffe19f57596378f12e6809eee294ca.nq.gz
│   ├── 36af25f972a4a61df5f6d8e16264b202bef2ec53.nq.gz
│   ├── 52805a429874a14b36be9d3644b4a8b098e6cc80.nq.gz
│   ├── 5700b997827973cb0eb6d84a2782bb08a5872434.nq.gz
│   ├── 625df51b71e49dcf94b289935b4424c171749f08.nq.gz
│   ├── 78f7d709517139c632537037bf9a434bf35047d9.nq.gz
│   ├── 80421eb3e6306543a98741758569e37b87e2e93f.nq.gz
│   ├── 84322663a881c7da7e721cd6b6e34809a08016d6.nq.gz
│   ├── 8877b87a7320865c6163c6f99e48bb64d2df002b.nq.gz
│   ├── 8b15845fd8646ca8a171e1413f04a4e7231a9b44.nq.gz
│   ├── 8d77eb44c9ae44b438a7d025a82e6733d590b54b.nq.gz
│   ├── a139ff60a6f0dc487d4d2a4d6a99f0e30e41bd03.nq.gz
│   ├── a360f7c951c98952edc5e18d6143ec758601beff.nq.gz
│   ├── ad7735e8206cfd55611cef553b512882675816c6.nq.gz
│   ├── b4432e4e1ca9952a793ac86d9afb1030f7d012f3.nq.gz
│   ├── c45eb5aaacc38980e1741372f5dc151c92056e59.nq.gz
│   ├── c6c267e94f4d2ac0c2076afd01504dcdb80caef9.nq.gz
│   ├── d047d46c84f0c5f09d5808e5fbed2f664fc8fc64.nq.gz
│   ├── d76c2ac488c08d45f2b4de14cd0010b774737b9f.nq.gz
│   ├── daadea6e8a80c6ee56649c365f85f5afb6d168aa.nq.gz
│   ├── e5a27aa319cac5ab6bcc69db95ca324a409f569e.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea859ec1df2896146a0950b6a6e7ef4223ff22ed.nq.gz
│   └── f64bf5b68bf2ec2b3c64e81082305ecc85cf8112.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── f8a03e4a8bc58f1d9dda6d677a7436cc832a57a9.nq.gz
├── filetree
│   └── f8a03e4a8bc58f1d9dda6d677a7436cc832a57a9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 42 files
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

[NousResearch/pokemon-agent](https://github.com/NousResearch/pokemon-agent)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
