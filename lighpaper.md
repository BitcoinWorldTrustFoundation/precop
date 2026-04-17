# PRECOP : The Sovereign Introspection Lightpaper 

> "We didn't plan to change the world. We just wanted to stop signing blind."

## TECHNICAL ABSTRACT
An engineering-grade, formally verified Bitcoin introspection framework for the Simplicity language. Verified through a comprehensive 12-cycle validation suite for bit-perfect consensus parity and fail-closed security invariants.

---

## Ⅰ. SHADOW AUDIT DISCLAIMER (READ THIS OR REGRET IT)
This document is **self-signed by the machine's own entropy**. It has not been blessed by a suit at a Big Four audit firm. If you're looking for a centralized stamp of approval, you're in the wrong repo. We don't want your trust; we want your verification.

The hashes provided below are the direct outputs of our 12-cycle Divine Gauntlet. They represent the current state of the PRECOP Gold Master. If you don't believe the results, the Haskell specification and the Rust runner are in the same folder. Run them. Derive the truth yourself.

**Vires in Numeris. No gods, no masters, just math.**

---

## Ⅱ. ARCHITECTURAL AGNOSTICISM
The protocol enforces a "Zero-Waste" FFI boundary. By using `MaybeUninit::zeroed()` and strict `repr(C)` alignment, we achieve a memory isomorphism that is independent of architecture-specific padding. This approach ensures deterministic consensus hashes across x86_64 and ARM64 platforms.

| Offset (Bytes) | Field | Size | Axiomatic Status |
| :--- | :--- | :--- | :--- |
| `0` | `CTransaction*` | 8 | Fully Hydrated |
| `8` | `CTapEnv*` | 8 | Context-Aware |
| `16` | `sigAllHash` | 32 | Native Midstate |
| `48` | `ix` | 4 | Input Bound |
| `52` | `_padding` | 4 | Aligned (8) |

> **Observed 64-bit Layout : 56 Bytes.** The bridge is narrow, invisible, and unbreakable.

---

## Ⅲ. FFI SAFETY PROXIES (Fail-Closed)
- **Panic containment**: All exported FFI functions employ `std::panic::catch_unwind` to prevent undefined behavior (UB) during Rust-side panics.
- **Trap semantics**: Introspection jets (`InputValue`, `OutputValue`, etc.) enforce strict bounds checking, triggering an immediate BitMachine TRAP on out-of-bounds access.
- **Deterministic state**: Precomputed transaction midstates (O(1) access) to ensure consistent performance in high-assurance execution environments.

---

## Ⅳ. COMMITMENT MERKLE ROOT (CMR) PARITY
Parity has been certified across Haskell, C, and Rust layers for the following core introspection primitives:

| Jet Entry Point | Commitment Merkle Root (CMR) | Status |
| :--- | :--- | :--- |
| `TotalInputValue` | `0xba032f3e62f8fcb04b0429a253b5ec57e4c87ae2e951e145d7650e7f0c63e555` | 🟢 Verified |
| `TotalOutputValue` | `0xa7e0bcd9d25d1d936bdec72cd24df491eb711bd4fefcb48fb47e08efb2d71a51` | 🟢 Verified |
| `InputUtxosHash`  | `0x71c99f44c10a34a692be0bb4308258e12f6f52b98c8585bb92d5fde0a2f499eb` | 🟢 Verified |

---

## Ⅴ. THE CHAOS GAUNTLET (Fail-Closed Proof)
To prove the system is sovereign, we don't just test success; we force failure. Under the Chaos Gauntlet, we flip a single satoshi in a spent UTXO. The result?

- **Simplicity Halt**: YES
- **Trap Triggered**: YES
- **Signature Leak**: NO

The machine doesn't negotiate with corrupted data. It traps. This is the **Citadelle** pattern in action: code as immutable law.

---

## Ⅵ. NATIVE L1 EYES (Ordinals & Runes)
PRECOP enables native introspection of inscriptions and tokens. By using the `InputScriptHash` and `OutputValue` jets, the BitMachine reconstructs the state of BRC-20 and Runes directly from the Taproot context.

**No indexer. No API. Just the L1 truth, verified before you sign.**

---
**Status: ALPHA RELEASE (SELF-CERTIFIED)**  
**Documentation: FFI SAFETY EVIDENCE PACK**  
**Observed Integrity Checksum: `17d8c7dcbbd44c92f9620262f6a9474bf113e5831056361890ed21f962ba3a27`**  
**Don't trust. Derive.**