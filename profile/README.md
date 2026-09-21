<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="../assets/logo_White.png">
  <source media="(prefers-color-scheme: light)" srcset="../assets/logo_BLACK.png">
  <img src="../assets/logo_BLACK.png" alt="PLOMID" width="220">
</picture>

<p><sub>DATA INFRASTRUCTURE</sub></p>

# PLOMID

## Unified data infrastructure for modern applications.

<p>PLOMID is building a unified data layer for SQL, JSON, time-series, vector, graph, and distributed workloads.</p>
<p><sub>PLOMID — Platform for Modern Intelligence and Data</sub></p>

[Foundation](#01-foundation) · [Architecture](#03-architecture) · [Storage](#04-storage) · [System map](#system-map) · [Source](https://github.com/PLOMID/plomid) · [Issues](https://github.com/PLOMID/plomid/issues)

![Applications, data workloads, PLOMID, common data layer, data infrastructure](../assets/diagrams/hero-data-infrastructure.svg)

</div>

---

## 01 Foundation

### A unified data foundation

Modern applications work across relational data, documents, time-series streams, vectors, graphs, blobs, and distributed data. These are frequently handled through separate systems and infrastructure layers.

PLOMID explores a unified architecture where these workloads share a common underlying data foundation — a single infrastructure layer designed to support multiple data models and access patterns.

## 02 Data models

### Multiple models. One foundation.

<div align="center">

![SQL, JSON, time series, vector, and graph converging on PLOMID](../assets/diagrams/data-models.svg)

</div>

PLOMID brings SQL, JSON, time-series, vector, and graph workloads toward a common data infrastructure.

### One data layer

Applications increasingly combine different forms of data in a single workflow — a transaction that touches documents, a query that spans relational and analytical shapes, an agent that retrieves vectors alongside records.

Instead of treating every data model as an isolated system, PLOMID is designed around a shared infrastructure foundation: common storage, shared data management, a common transactional foundation, common metadata, and multiple access patterns over the same underlying data.

<sub>STORAGE · TRANSACTIONS · METADATA · ACCESS · PERSISTENCE</sub>

## 03 Architecture

<div align="center">

![Client, PostgreSQL wire, data access, PLOMID core, storage foundation](../assets/diagrams/data-flow.svg)

</div>

Applications connect through familiar interfaces — including a PostgreSQL-compatible wire interface — and the platform is responsible for execution, transactions, and durable storage beneath them.

### Query → execution → storage

<div align="center">

![Query lifecycle: query, parse, plan, execute, access, persist](../assets/diagrams/query-lifecycle.svg)

</div>

A request enters as a query, is parsed and planned, then executed; access and persistence resolve against the shared storage foundation.

## 04 Storage

### Built from the storage layer up.

PLOMID is approached from the underlying data infrastructure upward: durable pages and persistence first, then transactions and data management, then query and access.

<div align="center">

![Storage architecture layers with signal travelling upward](../assets/diagrams/storage-stack.svg)

</div>

### Pages and persistence

PLOMID stores data in fixed-size 16 KiB pages, each protected by a 48-byte header and a 4-byte CRC32C trailer. Writes move through the buffer pool into pages and blocks, then on to persistence.

<div align="center">

![Fixed-size storage page: header, data region, checksum trailer](../assets/diagrams/storage-page.svg)

![Storage write path: request, buffer, page, block, persistence](../assets/diagrams/storage-flow.svg)

</div>

## 05 Engineering

### Engineered as infrastructure.

PLOMID is engineered in Rust around the concerns of a storage-backed data system: query execution, transactions and MVCC, page management and persistence, write-ahead logging, checksums, indexing, and networked access.

<sub>RUST · STORAGE · TRANSACTIONS · MVCC · WAL · RECOVERY · INDEXING · QUERY EXECUTION · NETWORKING · PERSISTENCE</sub>

The emphasis is on correctness at the foundation — durability, transactional behavior, and clean layering — so that higher-level data models rest on infrastructure that is easy to reason about.

### Transactions and MVCC

PLOMID implements a transaction lifecycle — active, committed, aborted — over multi-version concurrency control. Row versions resolve by snapshot visibility, and committed data becomes durable.

<div align="center">

![Transaction lifecycle and MVCC row versions](../assets/diagrams/transaction.svg)

</div>

### Implementation

**RUST** — type-safe systems programming. `unsafe` is forbidden workspace-wide.

## 06 Access

### Data access

Different workloads require different access structures. The architecture distinguishes point lookups, ordered range access, and set filtering as separate access paths over shared stored data. Each structure serves its access pattern; the stored data beneath them remains part of the same foundation.

<div align="center">

![Access structures: B+tree, filters, and columnar pruning](../assets/diagrams/access-paths.svg)

</div>

## 07 Runtime

### The system, in the terminal

<div align="center">

<img src="../assets/diagrams/terminal-frame.svg" alt="PLOMID server" width="800"><br>
<img src="../assets/terminal.png" alt="PLOMID server boot — storage engine, write-ahead log, query executor, network listener" width="800"><br>
<img src="../assets/diagrams/terminal-base.svg" alt="Real server output" width="800">

<sub>PLOMID is built from the systems layer upward, with the development environment and runtime exposed directly through the command line.</sub>

</div>

## 08 Deployment

### Data where it belongs.

PLOMID is intended as infrastructure that deploys according to application and data requirements.

<div align="center">

![PLOMID deployed across cloud, on-premises, edge, and controlled environments](../assets/diagrams/deployment.svg)

</div>

The design centers on flexible deployment and data placement — spanning deployment, residency, replication, access, and storage — giving infrastructure teams a foundation that can operate across cloud, on-premises, edge, and controlled environments.

<sub>DATA PLACEMENT · RESIDENCY · REPLICATION · ACCESS · JURISDICTION · STORAGE</sub>

<div align="center">

![Data placement control plane: location, residency, replication, access, storage, jurisdiction](../assets/diagrams/placement.svg)

</div>

## 09 Open engineering

### Built in the open.

The engineering work behind PLOMID lives in this organization:

- [Source](https://github.com/PLOMID/plomid) — the PLOMID implementation.
- [Issues](https://github.com/PLOMID/plomid/issues) — engineering discussion.



## System reference

<div align="center">

![System layers and diagram legend](../assets/diagrams/system-reference.svg)

</div>

## Explore PLOMID

[Source](https://github.com/PLOMID/plomid) · [Issues](https://github.com/PLOMID/plomid/issues)

---

<div align="center">

![PLOMID system signature](../assets/diagrams/system-signature.svg)

PLOMID
<br><sub>Platform for Modern Intelligence and Data</sub>

</div>
