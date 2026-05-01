#  Blockchain Indexer & State Replay Engine

A high-performance **blockchain indexing and deterministic state reconstruction engine** built in Go, designed to process raw blockchain logs, handle chain reorganizations (reorgs), and ensure consistent on-chain state through replay and validation.

---

##  Problem

Blockchain data is not strictly linear — **chain reorganizations (reorgs)** can invalidate previously processed blocks, leading to inconsistent or incorrect state in downstream systems.

This project solves this by implementing a **reorg-aware indexing system with deterministic replay**, ensuring correctness and auditability.

---

##  What This System Does

- Processes raw blockchain logs and events  
- Detects and handles chain reorganizations (reorgs)  
- Reconstructs blockchain state deterministically via replay  
- Validates invariants to ensure state correctness  
- Enables full auditability of on-chain data  

---

##  Architecture

Raw Logs → Indexer → Reorg Handler → State Store
↓
Replay Engine
↓
Invariant Validator

---

---

##  Key Features
- Reorg detection with rollback & reprocessing  
- Deterministic state reconstruction  
- Invariant validation (balances, liquidity, swaps)  
- Modular CLI-based design  

---

##  Performance
- ~10–15 blocks/sec (local)  
- Consistent state across reorg scenarios  

---

##  Tech Stack
- Go (Golang)  
- JSON-based blockchain logs  
- CLI tools  

---

##  Usage
```bash
# Run Indexer
go run main.go logs.go reorg.go

# Replay State
go run ./cmd/replay_state

# Validate Invariants
go run ./cmd/invariants



### Run Indexer
```bash
go run main.go logs.go reorg.go


### Sample Output
Processed Block: 17000001
State Hash: 2378a57a2e5e24b25f29b94c70d4ec88766da1f6
Pair State: Reserve0=150, Reserve1=250

###Use Cases
Blockchain indexing
On-chain analytics
Audit & verification systems
👤 Author

Prasanna
https://github.com/Prasanna25-20
