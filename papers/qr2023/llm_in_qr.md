# LLMs in Qualitative Reasoning — QR 2023

This document synthesizes how large language models (LLMs) appear across the QR 2023 workshop papers, covering their roles, limitations, and the community's views on their relationship to symbolic QR systems.

---

## Overview

Three of the fifteen QR 2023 papers engage directly with LLMs or take explicit positions on them:

1. **LLMs as subjects of a QSR benchmark** — ChatGPT-4 evaluated on RCC-8 spatial reasoning tasks (paper 07)
2. **LLMs as topology generators in a hybrid design pipeline** — ChatGPT-4 used to propose physical system component structures (paper 13)
3. **LLMs explicitly critiqued as poor QR knowledge bases** — Forbus argues for ontology-grounded QP theory as the alternative (paper 14)

The remaining twelve papers make no use of LLMs and do not discuss them substantively.

---

## Paper-by-Paper Analysis

### Paper 07 — Evaluating ChatGPT on RCC-8 Spatial Reasoning (Cohn)

**Role of LLMs:** Subjects of a QSR benchmark

Anthony Cohn conducts the first systematic evaluation of an LLM (ChatGPT-4) on region-based qualitative spatial reasoning using the RCC-8 formalism. Three task types are evaluated:

- **Composition table queries:** Given relations r1(A,B) and r2(B,C), what are the possible relations r3(A,C)? Result: **71.94% accuracy**
- **Preferred compositions:** When multiple relations are possible, which is most likely in typical spatial configurations? Result: **40.82% accuracy**
- **Conceptual neighborhood:** Which RCC-8 relations are topologically adjacent to a given relation? Result: **~90% accuracy**

**Key findings:**
- ChatGPT performs best on recognition/neighborhood tasks, which may rely on memorized spatial vocabulary
- ChatGPT performs worst on preferred compositions, which require geometric judgment about typical spatial configurations
- Composition accuracy at 71.94% appears respectable but error analysis shows systematic failures on transitive composition chains — exactly the cases requiring genuine spatial inference rather than pattern matching

**Takeaway:** LLMs have absorbed enough spatial reasoning terminology to perform reasonably on RCC-8 recognition tasks, but their performance on genuine compositional QSR falls well short of symbolic RCC-8 reasoners. The results establish a baseline and motivate hybrid approaches.

---

### Paper 13 — LLMs for Physical System Design (Maxwell et al.)

**Role of LLMs:** Topology generator in a hybrid design pipeline

Maxwell, de Kleer, Matei, and Zhenirovsky (PARC/SRI) use ChatGPT-4 as a "sloppy but general" component for automated physical system design. The pipeline has three layers:

1. **ChatGPT-4:** Given a natural language description and a Modelica component library, generates candidate component connection topologies
2. **Sizer (Modelica optimizer):** Finds numerical parameter values for the topology via gradient-free optimization
3. **Repair module:** Detects and fixes syntactically invalid or topologically broken designs (disconnected ports, type mismatches)

Two design tasks are demonstrated:
- *Low-pass filter:* ChatGPT generates correct RC topologies with wrong parameter values; the Sizer corrects parameters
- *Power train:* ChatGPT mostly generates incorrect topologies; behavioral repair is needed, guided by **qualitative component analysis**

The qualitative repair insight is particularly notable: missing components are diagnosed by comparing the *qualitative behavior* of a candidate design against qualitative unit tests for library components. If brake-pedal activation never qualitatively decreases speed in the candidate, a brake is likely missing — and the system searches for a library component whose qualitative behavior matches the missing pattern.

**Key findings:**
- ChatGPT generates approximately-correct topologies far more often than random, making it a useful starting point
- Pure generate-and-test performs poorly; repair is essential
- Qualitative behavior analysis (not numeric simulation) is the right tool for diagnosing which components are missing or misconnected
- ChatGPT cannot reliably assign correct parameter values — this must be delegated to optimization

**Takeaway:** The most LLM-centric paper in QR 2023. It proposes a direct productive role for LLMs in physical design while clearly delineating what LLMs cannot do (assign parameters, reason formally about behavior). Qualitative simulation serves as the verification and repair oracle for LLM-generated designs.

---

### Paper 14 — LLMs as Poor QR Knowledge Bases (Forbus)

**Role of LLMs:** Explicitly critiqued; not used

Forbus's paper on building QP domain theories from the NextKB/OpenCyc ontology contains a direct argument against LLMs as knowledge bases for QR:

> *"LLMs make poor knowledge bases for two reasons. First, their exposure to language is not grounded in the everyday world. Second, their success criterion is generating statistically plausible text, not correct reasoning. As the confabulation problems with LLMs show, these are at best only correlated."*

The paper proposes instead to build broad commonsense QR domain theories by *anchoring* QP model fragments to concepts in a large formally-represented ontology (OpenCyc, with 82,000+ collections). This yields both formal correctness (inherited from the QP model fragments) and broad language coverage (inherited from the ontology's 190,000+ lexical entries).

**Key finding:** The ontology-anchoring approach produces far more breadth than hand-engineering domain theories, without the unreliability of LLMs — the Motion anchor alone yields 355 sub-classes and 170 English words, all inheriting a correct qualitative motion model.

**Takeaway:** Forbus represents the QR community's strongest rejection of LLMs as reasoning systems. He acknowledges LLMs may be useful for *expanding the range of texts* that can be processed to build knowledge bases, but insists the knowledge base itself must be formally grounded.

---

## Cross-Cutting Themes

### LLMs as approximate tools, not reasoners
Papers 07 and 13 converge on the same finding: LLMs have absorbed enough domain knowledge to produce approximately correct outputs, but fail on tasks requiring genuine formal inference. ChatGPT achieves 72% on RCC-8 composition and generates "mostly wrong but plausible" power train topologies. In both cases, a symbolic QR system (RCC-8 reasoner, Modelica optimizer, qualitative simulator) is needed to correct or validate the LLM output.

### Qualitative reasoning as the error-detection layer
Paper 13 introduces a novel role for QR: as a *diagnostic oracle* for LLM-generated designs. Rather than checking outputs numerically (expensive) or syntactically (insufficient), qualitative behavior analysis of candidate designs reveals missing components and structural errors. This is a new application of QR principles to LLM pipeline engineering.

### The grounding critique is a consistent theme
Forbus (paper 14), Cohn (paper 07), and the broader community share a consistent diagnosis: LLMs do not have the grounded spatial or physical models needed for reliable QR. They perform on tasks where pattern matching on language suffices, but fail where genuine continuous world reasoning is required.

### QR 2023 is largely pre-LLM-integration
Twelve of fifteen papers make no reference to LLMs at all. The workshop's primary concerns in 2023 — educational modeling, physical system control, novelty detection, analogical reasoning, belief revision — are addressed with classical QR methods. LLM integration is nascent and largely confined to two exploratory papers.

---

## Summary Table

| Paper | LLMs Used | Role | Primary Finding |
|-------|-----------|------|-----------------|
| 07 | ChatGPT-4 | RCC-8 QSR benchmark subject | 72% on composition table; ~90% on conceptual neighborhoods; fails on preferred compositions — pattern matching, not spatial reasoning |
| 13 | ChatGPT-4 | Topology generator for physical design | Sloppy but useful as a starting point; qualitative simulation needed for repair and validation |
| 14 | None (discussed critically) | Explicitly rejected as QR knowledge base | Ontology-anchored QP theory preferred; LLMs lack grounding and produce statistically plausible, not logically correct, outputs |
| 01–06, 08–12, 15 | None | — | No LLM involvement |
