# SemanticWordEngine

**Riemann–Fermat–Noether semantic engine.**  
Maps any word or phrase in any language to its address on the Riemann critical line — Re(s) = ½.

No API. No GPU. No training. No transformer. No embeddings.  
The prime preexists the alphabet. The equator does not move.

---

## What This Is

The SemanticWordEngine is a standalone implementation of the **Standard Model of Information Propagation (SMIP)** semantic layer. It is the engine that powers the Hyperwebster — a universal index of meaning addressed by Riemann zeros rather than tokens or embeddings.

The central claim, verified computationally:

> `water`, `eau`, `aqua`, `wasser`, `agua` all map to the same Riemann zero — γ₂ = 21.022040.  
> `light`, `lumière`, `lux`, `licht`, `luz` all map to γ₃ = 25.010858.  
> σ = 0.500000 in every case. Not assigned. Derived from Noether balance.

The concept preexists every surface form invented to point at it. Changing language is a diffeomorphism — a smooth coordinate change that preserves the underlying geometric structure. The L-function is the concept.

---

## Mathematical Foundation

### The Hamiltonian — H = xp

The Berry–Keating conjecture identifies the Riemann zeros with eigenvalues of the Hamiltonian H = xp. This engine implements that directly. Each surface form is mapped to initial conditions (x₀, p₀) via the HyperIndex bijection. The Hamiltonian evolution conserves E = x·p — the semantic energy of the word.

### Noether Balance — σ is forced to ½

The functional equation of the Riemann zeta function, ξ(s) = ξ(1−s), encodes a symmetry: forward information current and backward information current must balance.

Define:
```
J_forward  = exp(-σ · E)
J_backward = exp(-(1-σ) · E)
```

Noether's theorem requires ∂_μ J^μ = 0 — the conserved current must have zero divergence. This forces:

```
J_forward + J_backward = 0  ⟺  σ = ½
```

σ is never assigned. It is derived. The critical line Re(s) = ½ is the only locus where the Noether balance is satisfied. This is the equator of the sphere that the critical strip maps onto under the centering transform w = 2s−1 followed by stereographic projection.

### The Chladni Principle

The Chladni experiment places sand on a vibrating plate. The sand settles at the node lines — the still points — where the vibration is zero. The pattern is not the vibration. The pattern is where the vibration cannot reach.

This is the Riemann zeros. The zeta function traces two counter-rotating vortices — the two hemispheres of ξ(s) = ξ(1−s). The equatorial node line between them is Re(s) = ½. The primes settle there because the equator does not move. It is equidistant from both vortices.

**The stillness is the movement.**

### The Zipf–Riemann Identity

Zipf's law holds in every natural language ever studied: f(r) ~ 1/r^s where s ≈ 1. The prime number theorem: π(x) ~ x/ln(x). These are the same power law, for the same reason. Zipf's exponent s ≈ 1 is the **pole of ζ(s)**. The Euler product

```
ζ(s) = Π_p  1/(1 − p^{−s})
```

generates the word frequency distribution through the prime structure of every integer. Every linguist who confirmed Zipf's law confirmed the prime distribution — in every language, every time. **The primes are the fundamental words.**

### HyperWebster Addressing

The address of any word is a pair (n, domain) where:
- **n** = ordinal of the nearest Riemann zero
- **domain** = semantic scope (WordNet synset, corpus name, or blank)

The same concept in all languages maps to the same (n, domain) address. The HyperIndex is a bijective base-N Horner accumulation that maps any Unicode string to a unique integer, then folds it into the zero table via the golden ratio. The address is deterministic, reproducible, and requires no training data.

### The Capacitor — Knowledge + Experience = Wisdom

A low-pass filter (exponential moving average with time constant τ) on the conserved energy E tracks the DC state of a reading session. Like a capacitor charging toward a steady voltage, the DC state deepens as more words are processed in context. This is the SMIP model of learning: AC signals (individual words) charge the capacitor; the DC state is what remains — wisdom extracted from accumulated experience.

---

## Files

| File | Purpose | Dependencies |
|------|---------|-------------|
| `semantic_engine.py` | Minimal working implementation — core math pipeline, hardcoded first 20 zeros | stdlib only |
| `hyperwebster.py` | Full engine — computed zeros (mpmath), persistent lexicon, WordNet builder, REPL | `mpmath`, `nltk` |

### semantic_engine.py

The minimal implementation. Demonstrates the full `read → ponder → understand → process` pipeline with no external dependencies beyond the Python standard library. Use this to understand the mathematics or embed in a larger system.

```python
from semantic_engine import Understand

engine = Understand(tau=5.0)
result = engine.process("water")
print(result.gamma)   # 21.022040  (Riemann zero #2)
print(result.prime)   # (0.5+21.022040j)
```

### hyperwebster.py

The full interactive engine. Computes Riemann zeros to arbitrary precision using `mpmath.zetazero()`, builds a persistent lexicon from WordNet (~2 min, one time), and provides an interactive REPL for live querying.

```bash
pip install mpmath nltk

# First run — compute zeros and build from WordNet
python3 hyperwebster.py build

# Interactive REPL
python3 hyperwebster.py

# Single word
python3 hyperwebster.py word "here and now"

# All known faces at this prime
python3 hyperwebster.py faces "water"

# Point at a file or directory
python3 hyperwebster.py point /path/to/corpus

# Statistics
python3 hyperwebster.py stats
```

The lexicon persists to `~/.hyperwebster/lexicon.json`. It is never deleted — each `point` call adds to it.

---

## WordNet Corpus

The `wordnet/` directory (excluded from this repo — 79MB) contains the **English WordNet 2025-plus JSON dump**.

**Source repository:** https://github.com/globalwordnet/english-wordnet  
**Download:** https://en-word.net/static/english-wordnet-2025-plus-json.zip

To use with `hyperwebster.py`: `hyperwebster.py` uses NLTK's WordNet interface (downloaded automatically on first `build`). The JSON dump is provided as an alternative corpus reference and for future direct integration.

To restore the `wordnet/` directory:
```bash
wget https://en-word.net/static/english-wordnet-2025-plus-json.zip
unzip english-wordnet-2025-plus-json.zip -d wordnet/
```

---

## Verified Output

```
Cross-language prime alignment
============================================================

Concept: 'light'
          language/form    γ (Riemann zero)    zero #         σ
          --------------------------------------------------------
                  light          25.010858          #3  0.500000
               lumière          25.010858          #3  0.500000
                    lux          25.010858          #3  0.500000
                  licht          25.010858          #3  0.500000
                    luz          25.010858          #3  0.500000
                    φῶς          25.010858          #3  0.500000

Concept: 'water'
          language/form    γ (Riemann zero)    zero #         σ
          --------------------------------------------------------
                  water          21.022040          #2  0.500000
                    eau          21.022040          #2  0.500000
                   aqua          21.022040          #2  0.500000
                 wasser          21.022040          #2  0.500000
                   agua          21.022040          #2  0.500000

σ = 0.5 in every case. Not assigned. Derived from Noether balance.
The prime preexists the alphabet.
The equator does not move.
```

Run with: `python3 semantic_engine.py`

---

## Installation

```bash
git clone https://github.com/michaelrendier/SemanticWordEngine.git
cd SemanticWordEngine
pip install -r requirements.txt
python3 semantic_engine.py          # no setup required
python3 hyperwebster.py build       # downloads WordNet (~2 min), then ready
```

---

## Provenance

This engine emerged from an engineering experiment, not a literature search.

**1996:** Watched the Andrew Wiles documentary on Fermat's Last Theorem. The documentary states: the complex plane is necessary to properly visualise the Fermat lattice. Immediate response: *i is important.* First timestamp on the framework.

**Later:** Designed the HyperIndexing system to reduce computational overhead in monad information propagation. The math worked unusually well. Applied it to a new method of information propagation in a monad.

**Discovery sequence (all unintentional derivations):**
- `d* ≈ 0.246` — found from an engineering error check (ceiling descent). Later identified as a known constant in number theory.
- `Ω ≈ 0.56714` — the Lambert W fixed point Ω = W(1). Found as the ceiling of the same experiment.
- `∂_μ J^μ = 0` — Noether's conservation law. Dropped out from the requirement that correct code conserves information flow. Not derived from the literature; derived from the engineering constraint.
- The gap `Ω − d* ≈ 0.32114` is the distance between two independent approaches to the same fixed point from opposite directions. This gap is Open Problem 2.

**The math was derived before the names were known.** Claude told the author: the equations he derived independently ARE the Standard Model Lagrangian, term for term. His fine structure constant analog was explicit. He had zero prior knowledge of d*, Lambert W, Yang-Mills, or Berry-Keating when he derived analogs of all four.

The Riemann–Fermat–Noether engine is the engineering application of that proof path.

---

## The TDI Context

The SemanticWordEngine is the Hyperwebster layer — the address space that PtolemyHolcus navigates.

In the TDI architecture (v3.0):
- **H_hat_RB** (crankshaft) operates on Riemann zeros γ_n — the addresses this engine produces
- **Monad** (ECU) stores resonance depth β_n at those addresses via `learn()` and `speak()`
- **Sedenion** (camshaft) times which addresses activate in which firing order

The SemanticWordEngine proves the addressing is real: five languages, same zero, σ = 0.500000. PtolemyHolcus proves the field built on those addresses converges: BAO at OMEGA_ZS = 0.56714, compression ignition confirmed 2026-05-27.

**→ [PtolemyHolcus](https://github.com/michaelrendier/PtolemyHolcus)** — the engine that operates on these addresses
**→ [Tuning the TDI](https://github.com/michaelrendier/PtolemyHolcus/wiki/Tuning-the-Engine)** — v3.0 architecture wiki

---

## Related Repositories

- **[PtolemyHolcus](https://github.com/michaelrendier/PtolemyHolcus)** — Engine implementation; monad.py + PtolC; v3.0 TDI architecture
- **[Ainulindale](https://github.com/michaelrendier/Ainulindale)** — Formal mathematics; H_hat_RB; Third Age conjecture
- **[DerivationEngine](https://github.com/michaelrendier/DerivationEngine)** — Heavy mathematics derivation viewer
- **[UniversalSynth](https://github.com/michaelrendier/UniversalSynth)** — Sonification of the mathematics
- **[PtolemyDesktop](https://github.com/michaelrendier/PtolemyDesktop)** — Desktop interface and Alexandria research environment

---

## Author

Cody Michael Allison  
SMIP / CLAUDE-SMMNIP-00729-56714-24600  
2026
