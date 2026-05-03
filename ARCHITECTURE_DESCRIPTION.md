# VOTEGUARD PRO - Complete System Architecture

## Overview
This comprehensive GraphML architecture diagram represents the complete VOTEGUARD PRO voting system spanning 6 layers: Presentation, Application, Domain, Ports, Adapters, and Infrastructure. The architecture follows clean architecture principles with clear separation of concerns, dependency inversion, and hexagonal (ports & adapters) patterns.

---

## Architecture Layers

### 1. **Presentation Layer** (4 Components)
**Purpose**: User interfaces and external entry points

- **Voter UI (Tablet/Kiosk)**
  - Touch-based voting interface for voters
  - Handles vote selection and submission
  - Integrates biometric scanners and card readers

- **Election Officer Dashboard**
  - Station management and monitoring
  - Voter enrollment and verification
  - Real-time vote status tracking

- **System Auditor Console**
  - Audit trail review and analysis
  - Vote verification and integrity checking
  - Report generation and export

- **REST API Gateway**
  - External service integration point
  - Third-party result queries
  - System interoperability interface

---

### 2. **Application Layer** (5 Components)
**Purpose**: Business logic orchestration and use case implementation

- **Session Manager**
  - Manages user sessions and state transitions
  - Handles authentication and authorization
  - Tracks user lifecycle

- **Vote Casting Orchestrator**
  - Coordinates vote capture from UI
  - Manages encryption workflow
  - Enforces voting rules and validations

- **Enrollment Validator**
  - Validates voter eligibility
  - Processes biometric authentication
  - Manages voter registration workflow

- **Verification Engine**
  - Post-cast vote verification
  - Confirmation receipt generation
  - Remote verification coordination

- **Tally Calculator**
  - Aggregates all cast votes
  - Produces election results
  - Generates statistical reports

---

### 3. **Domain Layer** (5 Components)
**Purpose**: Core business entities and domain logic

- **Voter Entity**
  - Represents individual voter
  - Contains voter attributes (ID, biometric, enrollment status)
  - Immutable voter record

- **Ballot Entity**
  - Represents encrypted vote record
  - Contains candidate selections
  - Timestamp and digital signature

- **Cast Registry**
  - Tracks all cast votes with temporal ordering
  - Maintains vote history
  - Provides audit trail foundation

- **Cryptography Service**
  - End-to-end encryption (AES-256)
  - Digital signing and verification
  - Key management
  - Hash chain validation

- **State Machine**
  - Enforces valid vote state transitions
  - Prevents invalid operations
  - Manages vote lifecycle states

---

### 4. **Ports Layer** (4 Components)
**Purpose**: Abstract contracts/interfaces defining external dependencies

- **IStorage Port**
  - Abstract persistent storage contract
  - Vote data persistence abstraction
  - No implementation details

- **IAudit Port**
  - Abstract audit logging contract
  - Audit trail recording interface
  - Tamper-proof logging abstraction

- **IChainAnchor Port**
  - Abstract blockchain anchoring contract
  - Vote commitment immutability contract
  - External verification interface

- **IDevice Port**
  - Abstract hardware device interaction
  - Biometric scanner interface
  - Card reader interface
  - Printer interface

---

### 5. **Adapters Layer** (4 Components)
**Purpose**: Implementation bridges between domain and infrastructure

- **StorageHashChainAdapter**
  - Maps votes to hash chain for tamper detection
  - Implements IStorage Port
  - Ensures data integrity

- **AuditLogHashChainAdapter**
  - Chains audit logs for integrity verification
  - Implements IAudit Port
  - Prevents audit trail manipulation

- **ChainAnchorServiceAdapter**
  - Anchors vote commitments to blockchain
  - Implements IChainAnchor Port
  - Enables external verification

- **DeviceAdapter**
  - Interfaces biometric scanners and card readers
  - Implements IDevice Port
  - Handles hardware abstraction

---

### 6. **Infrastructure Layer** (7 Components)
**Purpose**: External systems, storage, and hardware resources

- **Encrypted File Store**
  - Persistent AES-256 encrypted vote storage
  - Secure vault for ballot data
  - Tamper-resistant storage

- **Audit Store**
  - Append-only audit trail with hash chain
  - Immutable operation log
  - Integrity verification support

- **Biometric Scanner**
  - Fingerprint/iris capture for voter authentication
  - Hardware integration point
  - Real-time biometric processing

- **Card Reader**
  - Voter ID verification via smartcard/RFID
  - Hardware integration point
  - Voter identification

- **Receipt Printer**
  - Voter-verified paper audit trail (VVPAT)
  - Physical vote confirmation
  - Manual recount support

- **Blockchain Service**
  - Immutable vote commitment anchoring
  - External verification support
  - Transparent ledger

- **Remote Verification**
  - External vote integrity verification API
  - Third-party verification service
  - Public auditability

---

## Data Flow and Relationships

### Vote Casting Flow (Critical Path)
1. Voter interacts with **Voter UI**
2. UI invokes **Vote Casting Orchestrator**
3. Orchestrator creates **Ballot Entity** with selections
4. Orchestrator uses **Cryptography Service** to encrypt vote
5. Ballot persists via **IStorage Port** → **StorageHashChainAdapter** → **Encrypted File Store**
6. State tracked in **Cast Registry** via **IAudit Port** → **AuditLogHashChainAdapter** → **Audit Store**
7. Vote commitment anchored via **IChainAnchor Port** → **ChainAnchorServiceAdapter** → **Blockchain Service**
8. Receipt printed via hardware → **Receipt Printer**

### Verification Flow
1. **System Auditor Console** requests verification
2. **Verification Engine** retrieves vote from **Cast Registry**
3. **Cryptography Service** validates vote signature and encryption
4. **Remote Verification** API queries **Blockchain Service** for commitment verification
5. Audit records retrieved from **Audit Store** for trail validation

### Enrollment Flow
1. **Election Officer Dashboard** initiates enrollment
2. **Enrollment Validator** authenticates via **IDevice Port** → **DeviceAdapter** → biometric scanner/card reader
3. **Voter Entity** created and stored
4. Enrollment logged in **Audit Store**

---

## Edge Types and Semantics

| Edge Type | Meaning | Example |
|-----------|---------|---------|
| **invoke** | Caller → Callee operation | UI → Vote Casting Orchestrator |
| **creates** | Service creates entity | Orchestrator → Ballot Entity |
| **uses** | Consumes service | Vote Cast → Cryptography Service |
| **uses_port** | Depends on abstraction | Ballot → IStorage Port |
| **implements** | Concrete implementation | StorageHashChainAdapter → IStorage Port |
| **writes** | Persists to storage | Adapter → Encrypted File Store |
| **appends** | Adds to audit trail | Adapter → Audit Store |
| **publishes** | Broadcasts to external | Adapter → Blockchain Service |
| **io** | Hardware I/O operation | DeviceAdapter → Biometric Scanner |
| **calls** | Invokes external API | Verification Engine → Remote Verif |
| **queries** | Reads from system | Remote Verif → Blockchain |

---

## Key Architectural Properties

### Security Principles
✅ **End-to-End Encryption** — All votes encrypted at source using cryptography service  
✅ **Digital Signatures** — Vote integrity via cryptographic signing  
✅ **Hash Chains** — Storage and audit logs chained for tamper detection  
✅ **Blockchain Anchoring** — Vote commitment immutability  
✅ **VVPAT** — Voter-verified paper audit trail  

### Clean Architecture Benefits
✅ **Separation of Concerns** — Presentation isolated from business logic  
✅ **Testability** — Business logic independent of infrastructure  
✅ **Maintainability** — Clear layer boundaries and responsibilities  
✅ **Extensibility** — New adapters added without core changes  
✅ **Dependency Inversion** — Core logic depends on abstractions (Ports)  

### Auditability
✅ **Complete Audit Trail** — All operations logged with hash chain  
✅ **Immutable Records** — Blockchain anchoring prevents tampering  
✅ **External Verification** — Remote verification API for independent audits  
✅ **Transparent Flow** — Clear relationships between all components  

---

## Component Interactions Summary

**31 Total Nodes:**
- 4 Presentation components
- 5 Application components  
- 5 Domain components
- 4 Ports abstractions
- 4 Adapter implementations
- 7 Infrastructure resources

**28 Total Edges:**
- 5 Presentation → Application invocations
- 7 Application → Domain operations
- 4 Domain → Port abstractions
- 4 Port → Adapter implementations
- 5 Adapter → Infrastructure I/O
- 2 Remote verification flows

---

## Usage in Diagramming Tools

This GraphML file is compatible with:
- **yEd** — Free diagramming tool (www.yworks.com/products/yed)
- **draw.io** — Online diagramming (www.draw.io)
- **Lucidchart** — Professional diagramming
- **OmniGraffle** — Mac-based diagramming
- **Gephi** — Network analysis and visualization

**To Import:**
1. Open tool and select "Import GraphML"
2. Select `voteguard_complete_architecture.xml`
3. Apply automatic layout (Hierarchical or Force-Directed)
4. Customize colors by layer

---

## Architecture Constraints & Decisions

**Why 6 Layers?**
- Presentation: UI/external concerns
- Application: Use case orchestration  
- Domain: Business logic isolation
- Ports: Abstraction boundaries
- Adapters: Implementation details
- Infrastructure: External systems

**Why Ports & Adapters?**
- Dependency inversion: Core logic independent of I/O
- Testability: Replace adapters with mocks
- Extensibility: Add new storage/audit/blockchain implementations
- Decoupling: Swap infrastructure without core changes

**Why Blockchain Anchoring?**
- Immutability: Vote commitment cannot be altered
- Transparency: External verification possible
- Auditability: Public ledger for democratic verification
- Non-repudiation: Vote existence provable

**Why Hash Chains?**
- Tamper Detection: Any modification detected
- Audit Trail: Complete history preserved
- Integrity: Cryptographic proof of authenticity
- Compliance: Satisfies election security standards

---

## File Location & Format
- **File**: `assets/voteguard_complete_architecture.xml`
- **Format**: GraphML (XML-based graph format)
- **Schema**: W3C GraphML 1.0 with extended attributes
- **Size**: ~350 lines
- **Nodes**: 31
- **Edges**: 28

