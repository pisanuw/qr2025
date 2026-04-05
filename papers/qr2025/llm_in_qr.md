# LLMs in Qualitative Reasoning — QR 2025

This document synthesizes how large language models (LLMs) appear across the QR 2025 workshop papers, covering their roles, limitations, and integration with symbolic QR systems.

---

## Overview

Six of the ten QR 2025 papers engage directly with LLMs or vision-language models (VLMs). Their roles fall into three broad categories:

1. **LLMs as reasoning engines** — used to perform QR tasks directly (papers 0004, 0007, 0008)
2. **LLMs as translators** — used to parse natural language into formal representations for downstream symbolic reasoning (papers 0001, 0010)
3. **LLMs as modeled agents** — studied as epistemic actors whose reasoning may diverge from human reasoning (paper 0005)

---

## Paper-by-Paper Analysis

### 0001 — Hybrid Model Formulation (Forbus)

**Role of LLMs:** Translator / front-end for symbolic QR

Forbus tests Phi4, LLaMA 3.3, and Olmo2 on the QuaRel dataset of comparative analysis problems. LLMs are *not* asked to reason qualitatively — instead, they are used to decompose natural language problem descriptions into structured intermediate representations (extracting situations, building Qualitative Process models, extracting cross-situation facts) that are then handed off to the symbolic Companion Natural Language Understanding (CNLU) system for formal QR.

**Key finding:** LLMs can handle broad NLU but exhibit systematic failure modes — verbosity, sensitivity to prompt wording, and occasional mistranslation of qualitative relationships. The hybrid architecture (LLM + symbolic QR) is proposed precisely because pure LLM reasoning suffers from confabulation and opacity.

**Takeaway:** LLMs are useful as a natural language front-end but unreliable as QR engines on their own.

---

### 0004 — Multi-Agent Collaboration with Qualitative Supervision (Peng & Lai)

**Role of LLMs:** Reasoning agents and qualitative evaluators

This paper builds a multi-agent system where LLMs (DeepSeek-Chat, GPT-4o-mini, Grok-3) take on distinct epistemic roles: a Bold Explorer (generates candidate reasoning chains) and a Cautious Verifier (challenges them). A supervisor LLM evaluates each reasoning trace *qualitatively* — scoring coherence, plausibility, and completeness using semantic judgment rather than numeric metrics — and triggers retry loops when quality is insufficient.

**Key findings:**
- Supervisor-guided collaboration improves Exact Match and F1 scores over solo agents for DeepSeek and GPT-4o-mini.
- Model compatibility matters: Grok-3 performs better as a *worker* than as a supervisor; swapping its supervisor role to DeepSeek restored performance.
- Three-agent setups did not improve over two-agent setups, suggesting returns diminish with agent count.
- Best result: 52.0% EM / 67.8% F1 on HotpotQA.

**Takeaway:** Qualitative evaluation of LLM reasoning traces (rather than numeric scoring) is a viable supervision mechanism, and role assignment significantly affects multi-agent performance.

---

### 0005 — Epistemic Divergence Simulation (Liza)

**Role of LLMs:** Modeled agent whose causal beliefs are compared to a human agent's

Rather than using LLMs as tools, this paper *studies* GenAI agents as epistemic actors. Each agent (human or GenAI) maintains an epistemic graph encoding facts, beliefs, causal rules, and goals. The paper formally proves that agents sharing the same goal but holding incompatible causal beliefs will consistently choose divergent actions — producing high epistemic risk — and implements a Python/NetworkX simulation to confirm this.

**Key finding:** LLMs that reason from different causal models than humans will persistently diverge in action selection even when observing identical world states, because neither agent revises its core causal reasoning model.

**Takeaway:** Behavioral alignment with LLMs is insufficient; *epistemic alignment* (shared or mutually understood causal reasoning models) is required for safe human-AI collaboration.

---

### 0007 — Cardinal Direction Reasoning Benchmark (Cohn & Blackwell)

**Role of LLMs:** Subjects of a qualitative spatial reasoning benchmark

28 LLMs are evaluated on 5,760 questions testing cardinal direction reasoning (e.g., "if you walk along the east shore of a lake heading south, which direction is the lake?"). Models vary across locomotion types, person forms, and cardinal/intercardinal directions.

**Key findings:**
- No model achieves perfect accuracy. Best: OpenAI o1 at 0.92.
- Large Reasoning Models (LRMs) dominate the top-22 results; all are commercially hosted.
- LLMs perform *worse* on intercardinal directions than cardinal ones, mirroring the human "oblique effect."
- LRMs allocate more reasoning tokens to intercardinal questions and to incorrect answers.
- GPT-4.5 preview's anomalous pattern (all non-T4 correct, all T4 wrong) suggests possible benchmark contamination.
- No model fully generalizes across locomotion type or person form — reasoning is not truly abstract.

**Takeaway:** LLMs have made dramatic progress on spatial QR tasks (+50% relative improvement in one year), but reasoning remains brittle and template-dependent rather than genuinely abstract.

---

### 0008 — VLMs on Mechanical Comprehension (Ansah et al.)

**Role of LLMs/VLMs:** Subjects of a qualitative mechanical reasoning benchmark

Two small vision-language models — Gemma-3 (4B) and Qwen2.5-VL (7B) — are tested on 30 problems from the Bennett Mechanical Comprehension Test (BMCT-II) covering hydraulics, gears, acoustics, and heat/radiation. Models generate chain-of-thought (CoT) reasoning before answering.

**Key findings:**
- Overall accuracy: Gemma 36.67%, Qwen 46.67%.
- Four failure modes identified:
  - *Flawed reasoning → wrong answer* (most common): models hallucinate physical dependencies.
  - *Missed visual cues → wrong answer*: models misread static diagrams as dynamic scenes.
  - *Correct answer despite flawed reasoning*: "lucky hits."
  - *Correct answer with sound reasoning*: only on straightforward problems.
- Answer-level accuracy is insufficient; reasoning chain evaluation reveals deeper failures.

**Takeaway:** Small VLMs have significant gaps in qualitative mechanical reasoning. Neuro-symbolic hybrid architectures with verifiable proof steps are recommended to address hallucination and spatial reasoning failures.

---

### 0010 — Commonsense Reasoning with s(CASP) (Gupta et al.)

**Role of LLMs:** One component in a hybrid neuro-symbolic architecture

While the paper primarily advocates for s(CASP) (predicate Answer Set Programming) as a QR engine, it mentions a real-world NLU chatbot application that *combines GPT-3 with ASP*: GPT-3 handles natural language understanding and intent extraction, while s(CASP) provides the formal reasoning backend. This mirrors the hybrid approach in paper 0001.

**Takeaway:** LLMs serve as a natural language interface to formal symbolic reasoners; the combination addresses both language flexibility (LLM strength) and sound, explainable reasoning (ASP strength).

---

## Cross-Cutting Themes

### LLMs struggle with genuine abstract reasoning
Papers 0007 and 0008 both show that LLM performance is brittle: spatial and mechanical reasoning breaks down when surface features change (new locomotion type, intercardinal directions, ambiguous diagrams). Reasoning is template-matching rather than abstract inference.

### Hybrid architectures outperform pure LLM approaches
Papers 0001, 0004, and 0010 all propose integrating LLMs with symbolic systems. The pattern is consistent: LLMs handle language; symbolic systems handle formal reasoning and verification. Pure LLM QR suffers from confabulation, opacity, and instability.

### Qualitative evaluation of LLM reasoning is underexplored but promising
Paper 0004 demonstrates that LLMs can usefully *evaluate the quality of other LLMs' reasoning traces* using qualitative (semantic) rather than numeric scoring. This is a novel application of qualitative reasoning principles to LLM supervision.

### Epistemic alignment is a new concern
Paper 0005 raises a dimension absent from benchmark-focused work: even if an LLM answers correctly on average, its underlying causal model may diverge from a human's in ways that produce systematic action disagreements. Alignment must go deeper than behavioral outputs.

### Reasoning models (LRMs) represent a step change
Paper 0007 documents that Large Reasoning Models (chain-of-thought at inference time) improved cardinal direction accuracy from 0.60 to 0.92 in one year. All top performers are LRMs, suggesting that extended reasoning time is currently the most effective intervention for QR tasks.

---

## Summary Table

| Paper | LLMs Used | Role | Primary Finding |
|-------|-----------|------|-----------------|
| 0001 | Phi4, LLaMA 3.3, Olmo2 | NL translator for symbolic QR | Hybrid beats pure LLM; verbosity and prompt sensitivity are key failure modes |
| 0004 | DeepSeek, GPT-4o-mini, Grok-3 | Reasoning agents + qualitative supervisor | Role-based collaboration with qualitative supervision improves multi-hop QA |
| 0005 | GenAI agent (generic) | Modeled epistemic actor | Causal belief divergence → persistent action divergence despite identical observations |
| 0007 | 28 LLMs incl. o1, GPT-4.5 | Spatial QR benchmark subjects | LRMs dominate; oblique effect reproduced; no model fully abstracts |
| 0008 | Gemma-3 (4B), Qwen2.5-VL (7B) | Mechanical QR benchmark subjects | 37–47% accuracy; hallucination and visual misreading are dominant failure modes |
| 0010 | GPT-3 (in hybrid system) | NL interface to ASP reasoner | LLM + symbolic ASP is a viable production architecture (CHeF medical system) |
