# Mentu

**Traceable work for humans and agents.**

Intelligence that moves across time, devices, and contexts.
Mentu keeps work traceable with a simple protocol and a commitment ledger, so every promise and closure can be reconstructed.

## What is a commitment ledger?

A commitment ledger is an append-only record that links observations to commitments, and commitments to evidence, so accountability is reconstructable.

### The core loop

- **Carry context:** move across devices and threads without losing continuity
- **Make intent explicit:** commitments are named, owned, and reviewable
- **Close with proof:** done means evidence, not a checkbox

Observation (memory)  →  Commitment  →  Evidence  →  Closure

### The protocol, in one minute

Mentu is designed around two invariants:

- **Append-only ledger:** nothing is edited, nothing is deleted
- **State by replay:** current state is computed from the ledger, not stored elsewhere

A typical workspace contains:

- `.mentu/ledger.jsonl` (the ledger)
- `genesis.key` (optional workspace constitution for identity, permissions, and validation tiers)

### Get started (CLI)

If you want to try the protocol locally:

```npm install -g mentu
mentu init``

mentu capture "Customer reported checkout bug"
mentu commit "Fix checkout bug" --source <memory_id>
mentu claim <commitment_id>

// do the work...

mentu capture "Fixed null check in payment.ts:42" --kind evidence
mentu close <commitment_id> --evidence <evidence_memory_id>

### Repositories
	•	mentu: the protocol specification and core design
	•	mentu-cli: the official CLI implementation

### Design notes
	•	Evidence-based closure: closures require proof, not a flag
	•	Review airlock: optional in_review flow for agent workflows and higher-risk work
	•	Tiered validation: optional policies in genesis.key to gate what can auto-close
	•	Multi-agent accountability: patterns like the Dual Triad help separate creation from verification

### Contributing

Issues and PRs are welcome. If you are proposing a new operation, state transition, or validator, include:
	•	the intent
	•	expected ledger operations
	•	replay semantics
	•	failure modes and auditability

### License

See each repository for licensing details.
