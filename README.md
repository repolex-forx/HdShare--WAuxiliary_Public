# Repolex Knowledge Graph of HdShare/WAuxiliary_Public

RDF knowledge graph data for [HdShare/WAuxiliary_Public](https://github.com/HdShare/WAuxiliary_Public), parsed by [repolex](https://repolex.ai).

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
rlex download HdShare/WAuxiliary_Public
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5a5fbed4b8f74925da0619b348103f05b5de853f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5a5fbed4b8f74925da0619b348103f05b5de853f
│           └── chunk-001.nq.gz
├── blob
│   ├── 17cd12b12347bbfb6f1093e8657b85c11d7c0b97.nq.gz
│   ├── 1d7dc3a6ef70faf0faeb867c3eb77a7e044b249e.nq.gz
│   ├── 3ba13e0cec6cbbfd462e9ebf529dd2093148cd69.nq.gz
│   ├── 4e07f46fe1b6d895479dd977bb063e48fd15f07a.nq.gz
│   ├── 4ea67a731bc291fe2afcd2cc4eed79d58245ae27.nq.gz
│   ├── 580eb21f2d3f555a939a8281a726776d3e5cd3c8.nq.gz
│   ├── 5eb3e353ef612daabe35051b1c277d3dd8856e5e.nq.gz
│   ├── 68fc8c857217d70b371724d6aa0656df2117149e.nq.gz
│   ├── 9c64c9c3e6a32750b4bc9bfcb0dae8e435ac2dcf.nq.gz
│   ├── a228a723b965a284474362b08c216cd4c480b1c5.nq.gz
│   ├── a68d2ffdaca62da84d948e3be9777619af7b5969.nq.gz
│   ├── b277ee7639690c684e7407fcc71b6d4a58d9ea13.nq.gz
│   ├── b84cc71be0ea944e50a5426d4f703c26ff7abdf5.nq.gz
│   ├── b87d8933f3cf0c77bcc0890610951cae39692c04.nq.gz
│   ├── ccdec1b289b6ed1dbb34de794d0d3c77bb388b0b.nq.gz
│   ├── d3bd574ed626892834958db247f16b160f933ab9.nq.gz
│   ├── d674fe8cc337908c62fd33b5fea057c138db0908.nq.gz
│   ├── d7df1bbe40ad95c2f2956fddd36668367fe9289d.nq.gz
│   ├── d93b357f0947e3a051718d9a878397e7a3d4f4ca.nq.gz
│   ├── ee75480fc31655a87d6f8989885ed14ad9470ae0.nq.gz
│   └── f983355bac4912129586539f58771083c31a30b5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5a5fbed4b8f74925da0619b348103f05b5de853f.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 27 files
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

[HdShare/WAuxiliary_Public](https://github.com/HdShare/WAuxiliary_Public)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
