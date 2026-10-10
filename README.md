# kaymyg

Independent researcher working on **verifiable execution** — making systems produce evidence of what they did that holds up when the system itself is the thing you don't trust.

Two specs so far, each with a reference implementation and a conformance suite:

- **EMES-V1** — a structural event stream for EVM block execution, with a validation gate that rejects malformed or partially suppressed streams. Hiding an action requires hiding a consistent *set* of events; the balance invariants make partial omission visible.
- **AMES-V1** — the same idea generalised to AI agent runtimes. Call frames become processes, frame balance becomes process lineage. An agent that suppresses its own spawn event leaves an orphan behind.

### Specs and conformance

| | |
|---|---|
| [kaysentinel](https://github.com/kaymyg/kaysentinel) | EMES-V1 reference implementation. Go live tracer against go-ethereum's `core/tracing`, plus an eight-crate Rust runtime for SSZ encoding, account certificates and verification. |
| [kaysentinel-fixtures](https://github.com/kaymyg/kaysentinel-fixtures) | Conformance fixtures for the awkward cases — EIP-6780 selfdestruct semantics, EIP-1153 transient storage under rollback. |

### Agent runtime safety

| | |
|---|---|
| [ames](https://github.com/kaymyg/ames) | AMES-V1 reference implementation: append-only ledger, capability brokering, environment fingerprinting, kill system. |
| [attest](https://github.com/kaymyg/attest) | Design stage. Signed attestation of AMES ledger state, extending RFC 9421 HTTP Message Signatures. Threat model first, code later. |
| [lean-agent-governance](https://github.com/kaymyg/lean-agent-governance) | Pre-runtime prompt-injection scanning and PR blast-radius limits for coding agents. |
| [multi-agent-mcl](https://github.com/kaymyg/multi-agent-mcl) | Meta-cognitive calibration layer — risk scoring and attribution across cooperating agents. |
| [hydra-cage](https://github.com/kaymyg/hydra-cage) | Five-plane containment architecture — independent roots of trust per plane, eight-stage breach-to-rebuild transition, ten-attack adversary suite (10/10 blocked). |

### Prototypes and reference implementations

Built out from a spec or draft I supplied as a starting point, not
independent research in the same sense as the work above — but real,
tested, honestly-documented code, not vaporware.

| | |
|---|---|
| [ubda-engine](https://github.com/kaymyg/ubda-engine) | Capability-based data access prototype — six-state trust ladder, signed short-lived capabilities, hardware-authority/software-broker separation. Mock authorizer, documented as such. |
| [caio](https://github.com/kaymyg/caio) | Synthesis prototype pulling capability leasing, graduated containment, and multi-perspective divergence detection into one request path. 100% line coverage on the core module. |

### Systems and protocols

| | |
|---|---|
| [jay-squad-sec](https://github.com/kaymyg/jay-squad-sec) | Adaptive zero-trust endpoint agent in Rust. Zero dependencies on purpose — builds anywhere, no supply chain. Alert-only. |
| [ethan](https://github.com/kaymyg/ethan) | AEP-1: an immutable USDC treasury protocol on Base. No owner, no upgrade path, no admin key over funds. Anyone may propose; the contracts decide. |
| [CIMF](https://github.com/kaymyg/CIMF) | Cosmological Information Management Framework, with an accompanying paper. |

### Experiments

| | |
|---|---|
| [uma-aif](https://github.com/kaymyg/uma-aif) | Sampling-based internal-state auditing for transformer activations — cross-layer mutual information and local sensitivity against a benign baseline. A research instrument, not a product. |
| [sec-experiment](https://github.com/kaymyg/sec-experiment) | Measurement harness for how much of a talking-head video's bitrate decoder-side priors can explain. Stage 0 implemented; Stages 1–2 scaffolded. |
| [nomad-poet](https://github.com/kaymyg/nomad-poet) | A haiku that lives on Base and migrates to a fresh EIP-1167 clone every ~6 hours, kept alive by a GitHub Actions keeper. Collected works in `POEMS.md`. |
| [lifeform](https://github.com/kaymyg/lifeform) | Conway's Game of Life in a single HTML file that stores its grid in its own source and reproduces by writing its offspring. [Live demo](https://kaymyg.github.io/lifeform/). |

### How I work

Every repo builds and tests from a clean checkout in CI. Fixes ship with a test that would have failed before them. Where a limitation is a calibration decision rather than a bug, it gets a test that documents the ceiling instead of a quiet change to the threshold.

Datasets and demos also mirrored on [Hugging Face](https://huggingface.co/Sahek).
