# LLMs in Qualitative Reasoning — QR 2024

This document synthesizes how large language models (LLMs) and foundation models appear across the QR 2024 workshop papers, covering their roles, limitations, and integration with symbolic QR systems.

---

## Overview

Two of the nine QR 2024 papers engage directly with LLMs or foundation models:

1. **LLMs as retrieval and translation tools** — used to extract objects and processes from natural language for downstream QP model construction (paper 3)
2. **Foundation models as subjects of study** — analyzed to understand their implicit ontological commitments (paper 9)

The remaining seven papers (1, 2, 4, 5, 6, 7, 8) make no use of LLMs and do not discuss them. QR 2024 is primarily a workshop about classical QR methods and applications.

---

## Paper-by-Paper Analysis

### Paper 3 — Automating QP Model Construction (Suzuki & Yoshioka)

**Role of LLMs:** Retriever / translator for QP model formulation

Suzuki and Yoshioka use ChatGPT/GPT-4 to extract the relevant physical objects and processes from natural language problem descriptions in physics. The LLM does not reason qualitatively — it identifies *what* objects and phenomena are involved, which are then looked up in a structured physical laws database organized according to Qualitative Process Theory (QPT). The actual qualitative reasoning is performed by a QPT simulator downstream.

**Key finding:** LLMs are effective for the NL-to-structure mapping step but unreliable for formal QP reasoning. The hybrid pipeline separates LLM breadth (broad physical commonsense) from symbolic precision (QPT formal reasoning), yielding better results than either alone.

**Takeaway:** This is the clearest example in QR 2024 of LLMs playing a supporting role in a hybrid neuro-symbolic QR architecture — the same pattern seen in QR 2025 papers 0001 and 0010.

---

### Paper 9 — Ontological Commitment in CLIP (Keser et al.)

**Role of foundation models:** Subjects of qualitative ontological analysis

This paper does not use LLMs as tools but *studies* CLIP — a large vision-language foundation model — as an object of inquiry. Hierarchical clustering of CLIP's embedding space over structured image datasets reveals what ontological distinctions the model implicitly encodes. The comparison against formal ontologies (WordNet, part-whole hierarchies) finds that CLIP reliably captures basic-level object categories and some spatial relations, but is inconsistent on abstract properties and part-whole relationships.

**Key finding:** Foundation models embed implicit ontological commitments that partially but imperfectly align with formal QR ontologies. Understanding this gap is prerequisite to grounding foundation model outputs in qualitative representations.

**Takeaway:** Rather than deploying LLMs, this paper asks what LLMs "know" in a structurally precise sense. It opens a research direction: using QR ontological analysis to characterize and improve foundation models.

---

## Cross-Cutting Themes

### The hybrid pattern continues
Paper 3 follows the same hybrid architecture seen repeatedly in QR 2025: LLMs handle broad natural language understanding; symbolic QR systems handle formal, explainable reasoning. The QR community's consistent position is that LLMs are useful *front-ends* but poor *reasoning engines*.

### LLMs are conspicuously absent from most QR 2024 work
Seven of nine papers make no reference to LLMs. This reflects the breadth of QR applications — autonomous vehicles, educational modeling, belief revision, social reasoning, XAI — where LLMs play no role. The QR field encompasses far more than LLM integration.

### Foundation models as QR-analyzable systems
Paper 9 introduces a novel direction: applying QR's ontological analysis tools *to* foundation models rather than deploying them. This treats models like CLIP as empirical objects whose conceptual structure can be probed using QR methods.

### LLMs explicitly rejected as knowledge bases (adjacent work)
Forbus's paper 5, while not studying LLMs, reflects the community's prevailing view: structured ontologies (OpenCyc, NextKB) remain superior to LLMs for formal QR reasoning because LLMs lack grounding and produce statistically plausible rather than logically correct outputs.

---

## Summary Table

| Paper | LLMs / Models Used | Role | Primary Finding |
|-------|--------------------|------|-----------------|
| 3 | ChatGPT / GPT-4 | NL retriever for QP model formulation | LLM identifies objects/processes; QPT simulator does the reasoning |
| 9 | CLIP (vision-language) | Subject of ontological analysis | CLIP's embedding space partially matches formal ontologies; gaps in abstract/part-whole distinctions |
| 1, 2, 4, 5, 6, 7, 8 | None | — | No LLM involvement |
