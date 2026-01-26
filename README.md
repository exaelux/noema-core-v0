# Noema Core

**Noema** is a minimal, neutral, and universal semantic standard for interpreting tokenized objects across blockchain systems (assets, identities, rights, certificates, etc.).

Its sole function is to translate **verifiable on-chain facts** into **operational semantic readings** that are legible to humans and machines, without executing logic, enforcing policy, or embedding value judgments.

* **Version:** v0.1 (Core Pure) + v0.1 (Reference Profile)
* **Status:** Experimental / Conceptual
* **Design orientation:** Move-compatible, chain-agnostic

---

## Core Philosophy

> Noema is not a protocol that *does* things.
> Noema is a common language to *understand* what protocols already do.

* Data without meaning is incomplete.
* Meaning without privacy is dangerous.
* Privacy without interoperability is ineffective.

Noema addresses this by enforcing a strict separation between **existence**, **meaning**, and **content**, enabling deterministic and privacy-preserving semantic interpretation.

---

## Noema Core Pure v0.1

The **Core Pure** is the irreducible semantic nucleus of Noema. It is intentionally minimal, neutral, and non-normative. Nothing may be removed without breaking universality; nothing may be added without introducing bias.

### Core Principles

1. **Neutrality** — describes states, never judgments.
2. **Radical minimalism** — only what is strictly necessary.
3. **Determinism** — identical inputs yield identical readings.
4. **Strict separation** — existence ≠ meaning ≠ content.
5. **Extensibility** — all domain logic lives outside the core.
6. **Safe readability** — sufficient to operate, insufficient to exploit.

---

### Core Semantic Structure

A Noema Semantic Object is any tokenized object that is addressable and verifiable on-chain.

The Core requires only three abstract components:

* **existence**
  Implicit confirmation that the object exists and is referenceable on-chain.

* **meaning**
  An opaque semantic descriptor derived exclusively from declared states or verifiable proofs. The Core imposes no structure, taxonomy, or ontology.

* **visibility_abstract**
  A non-normative semantic hint describing general visibility conditions (e.g. public, restricted). This is *not* access control and has no fixed enumeration.

```json
{
  "existence": true,
  "meaning": "opaque-semantic-descriptor",
  "visibility_abstract": "restricted"
}
```

---

### Core Privacy Principle

**Noema reads proofs and declared states, not raw or sensitive data.**

* No personal or confidential data is accessed.
* Only verifiable outcomes are interpreted (e.g. valid / invalid, active / revoked).
* Native compatibility with zero-knowledge proofs, selective disclosure, verifiable credentials, and oracles.

---

### What Noema Core Explicitly Does *Not* Do

* Execute logic or workflows
* Custody keys or assets
* Enforce permissions or access control
* Decide legality, trust, or compliance
* Replace existing identity, privacy, or execution standards

---

## Noema Reference Semantic Profile v0.1 (Non‑Normative)

The **Reference Semantic Profile** is an optional, non-normative extension that provides a commonly useful ontology for practical interoperability. It does not modify the Core and may be replaced or ignored entirely.

### Recommended Semantic Fields (extensions of `meaning`)

* `object_type` — high-level classification (e.g. Physical Good, Identity, Certificate)
* `semantic_state` — current operational semantic state (e.g. Verified, Restricted, Expired)
* `functional_role` — primary role in context (e.g. Proof, Access, Ownership)
* `validity_status` — declared acceptability (e.g. Valid, Conditional)
* `operability` — current usability (e.g. Usable, Limited)

### Optional Derived Evaluation (External)

Evaluative signals such as trust or risk **never belong to the Core**. When used, they are always contextual, model-dependent, and externally derived.

```json
"trust": {
  "level": "High",
  "model": "reference_trust_v1",
  "derived_from": "issuer_reputation + proof_consistency"
}
```

---

### Example (Core + Reference Profile)

```json
{
  "noema_version": "0.1",
  "object_id": "urn:noema:asset:abcdef123456",
  "existence": true,
  "meaning": {
    "object_type": "Identity",
    "semantic_state": "Verified",
    "functional_role": "Access",
    "validity_status": "Valid",
    "operability": "Usable"
  },
  "visibility_abstract": "public",
  "derived_from": "VC + ZK-proof"
}
```

---

## Relationship to Existing Standards

Noema does not implement or replace existing standards. It operates strictly as a **semantic interpretation layer** over their declared outputs.

Compatible sources include:

* DID / Verifiable Credentials
* Zero-Knowledge proof systems
* Privacy-preserving pools and shields
* Oracles and verifiable external data
* Sector-specific certifications

Noema consumes **outcomes**, not internal data or private content.

---

## Repository Structure

* `README.md` — conceptual overview
* `spec/move-mapping.md` — conceptual Move mapping (non‑normative)
* `spec/reference-model.md` — reference semantic profile and layers

---

## Status

* Version: v0.1
* Stability: experimental
* Next steps: conceptual validation, minimal JSON schemas, domain-specific profiles

---

## License

To be defined 
