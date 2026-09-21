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

[Platform](#a-unified-data-foundation) · [Architecture](#architecture) · [Documentation](https://github.com/PLOMID/plomid) · [Source](https://github.com/PLOMID/plomid)

![Applications, data workloads, PLOMID, common data layer, data infrastructure](../assets/diagrams/hero-data-infrastructure.svg)

</div>

---

## A unified data foundation

Modern applications work across relational data, documents, time-series streams, vectors, graphs, blobs, and distributed data. These are frequently handled through separate systems and infrastructure layers.

PLOMID explores a unified architecture where these workloads share a common underlying data foundation — a single infrastructure layer designed to support multiple data models and access patterns.

## Multiple models. One foundation.

<div align="center">

![SQL, JSON, time series, vector, and graph converging on PLOMID](../assets/diagrams/data-models.svg)

</div>

PLOMID brings SQL, JSON, time-series, vector, graph, and distributed data workloads toward a common data infrastructure.

## One data layer

Applications increasingly combine different forms of data in a single workflow — a transaction that touches documents, a query that spans relational and analytical shapes, an agent that retrieves vectors alongside records.

Instead of treating every data model as an isolated system, PLOMID is designed around a shared infrastructure foundation: common storage, shared data management, a common transactional foundation, common metadata, and multiple access patterns over the same underlying data.

## Architecture

<div align="center">

![Data access, PLOMID core, storage foundation](../assets/diagrams/data-flow.svg)

</div>

Applications connect through familiar interfaces — including a PostgreSQL-compatible wire interface — and the platform is responsible for execution, transactions, and durable storage beneath them.

## Built from the storage layer up.

PLOMID is approached from the underlying data infrastructure upward: durable pages and persistence first, then transactions and data management, then query and access.

<div align="center">

![Storage architecture layers with signal travelling upward](../assets/diagrams/storage-stack.svg)

</div>

## Engineered as infrastructure.

PLOMID is engineered in Rust around the concerns of a storage-backed data system: query execution, transactions and MVCC, page management and persistence, write-ahead logging, checksums, indexing, and networked access.

The emphasis is on correctness at the foundation — durability, transactional behavior, and clean layering — so that higher-level data models rest on infrastructure that is easy to reason about.

## Data access

Different workloads require different access structures. The architecture distinguishes point lookups, ordered range access, and set filtering as separate access paths over shared stored data. Each structure serves its access pattern; the stored data beneath them remains part of the same foundation.

## The system, in the terminal

<div align="center">

![Illustrative boot sequence — see screenshot below for real server output](../assets/diagrams/terminal-boot.svg)

<img src="../assets/terminal.png" alt="PLOMID server boot — storage engine, write-ahead log, query executor, network listener" width="800">

<sub>PLOMID is built from the systems layer upward, with the development environment and runtime exposed directly through the command line.</sub>

</div>

## Data where it belongs.

PLOMID is intended as infrastructure that deploys according to application and data requirements.

<div align="center">

![PLOMID deployed across cloud, on-premises, and edge](../assets/diagrams/deployment.svg)

</div>

The design centers on flexible deployment and data placement — spanning deployment, residency, replication, access, and storage — giving infrastructure teams a foundation that can operate across cloud, on-premises, edge, and controlled environments.

## Built in the open.

The engineering work behind PLOMID lives in this organization:

- [Source](https://github.com/PLOMID/plomid) — explore the PLOMID implementation.
- [Architecture](https://github.com/PLOMID/plomid) — understand the system design.
- [Documentation](https://github.com/PLOMID/plomid) — explore the technical documentation.
- [Issues](https://github.com/PLOMID/plomid/issues) — follow development and discussions.

## Explore PLOMID

[Source](https://github.com/PLOMID/plomid) · [Architecture](https://github.com/PLOMID/plomid) · [Documentation](https://github.com/PLOMID/plomid) · [Issues](https://github.com/PLOMID/plomid/issues)

---

<div align="center">

PLOMID
<br><sub>Platform for Modern Intelligence and Data</sub>
<br><br><sub>Unified data infrastructure for modern applications.</sub>

</div>
