# QR 2025 Paper Summaries

---

## 0001 — Exploring Hybrid Model Formulation Strategies for Qualitative Reasoning
**Author:** Kenneth D. Forbus (Northwestern University)

**Summary:** This work-in-progress paper explores using large language models (LLMs) to automate *model formulation* — the process of building formal qualitative models from natural language descriptions. Forbus uses AI2's QuaRel dataset of comparative analysis problems as a testbed. Rather than using LLMs to perform reasoning directly (which suffers from confabulation and opacity), the paper proposes a hybrid approach: LLMs handle broad natural language understanding and translation, while the symbolic Companion Natural Language Understanding system (CNLU) provides a bridge to formal qualitative reasoning (QR). The paper decomposes the QuaRel problem-solving pipeline into four steps — extracting situations, building QP models, extracting cross-situation facts, and carrying out differential qualitative (DQ) analysis — and evaluates LLM performance on each with example-based pilot tests using Phi4, LLaMA 3.3, and Olmo2. Results are encouraging but reveal systematic LLM failure modes including verbosity, sensitivity to prompt wording, and occasional mistranslation. Future work will extend to the QuaRTz dataset and fill knowledge gaps incrementally.

---

## 0002 — Modelling Collaborative Learning Among Teachers Using Systems Thinking
**Authors:** Karin van de Lagemaat, Bert Bredeweg, Marco Snoek (Amsterdam University of Applied Sciences / University of Amsterdam)

**Summary:** This paper develops a systems-based qualitative reference model to help teachers understand and engage with collaborative learning as a dynamic social process. Using a practice-based, design-oriented methodology, the authors conducted interviews and group reflection sessions with 30 teachers at a secondary school, performed thematic analysis, and built a Causal Loop Diagram (CLD) visualizing reinforcing feedback loops in collaborative professional development. The CLD was then formalized into a qualitative reference model using DynaLearn, capturing 5 entities and 16 quantities including team dynamics, behavioral mechanisms, psychological safety, and learning outcomes. A simplified teacher-friendly version was developed alongside a 7-step learning guide to scaffold the modelling process. Despite time constraints that shifted the approach from independent construction to co-facilitated sessions, teachers recognized their own practice in the model and developed shared vocabulary around collaboration. The paper contributes a model-building method for complex non-exact social domains and demonstrates the potential of qualitative reasoning tools in professional education contexts.

---

## 0003 — Belief Base Revision for Qualitative Reasoning Models
**Authors:** Moritz Bayerkuhnlein, Diedrich Wolter (University of Lübeck)

**Summary:** This paper presents a principled framework for updating Qualitative Simulation Models (QSMs) in response to new observations, framed as a *belief base revision* problem. The authors adapt the classic AGM belief revision postulates (Success, Inclusion, Consistency, Vacuity, Relevance, Uniformity) to the non-monotonic, non-deterministic nature of QSM simulation. A QSM is represented as a graph M = ⟨Q, P, C⟩ of quantities, causal processes, and constraints. A revision operator ⋆_M is defined using logic-based abduction and a pseudo-distance measure over model components (symmetric difference), minimizing structural changes while restoring consistency with new observations. The operator is proven to satisfy all five adapted rationality postulates. The paper also analyzes learning capabilities, showing the operator can converge on extensionally equivalent models given both positive and negative observations, but cannot uniquely identify syntactically distinct models from positive observations alone. Applications include model debugging, alignment with human mental models, and incremental learning in commonsense reasoning systems.

---

## 0004 — Reasoning as a Team: Evaluating Role-Based Multi-Agent Collaboration Through Qualitative Supervision
**Authors:** Chin-Lang Peng, Shang-Hong Lai (National Tsing Hua University)

**Summary:** Inspired by Minsky's Society of Mind, this paper proposes a multi-agent LLM framework where agents assume distinct epistemic roles (Bold Explorer, Cautious Verifier) and a supervisory agent qualitatively evaluates their reasoning traces. Worker agents solve multi-hop questions via ReAct-style Thought-Action-Observation loops. The supervisor assesses each trace on coherence, plausibility, and completeness using semantic rather than numeric scoring, issuing targeted feedback and triggering retry loops (up to 3 rounds) when quality is insufficient. Experiments on the HotpotQA benchmark using DeepSeek-Chat, GPT-4o-mini, and Grok-3 show that supervisor-guided collaboration consistently improves Exact Match and F1 scores for DeepSeek and GPT-4o-mini (e.g., +2.9 EM for Bold+Neutral on DeepSeek). Notably, Grok-3 performs better as a worker than a supervisor — swapping its supervisor role to DeepSeek restores performance. A three-agent setup did not improve results, suggesting supervisor-agent compatibility matters more than agent count. Best overall performance was 52.0% EM / 67.8% F1 (Grok-3 workers + DeepSeek supervisor).

---

## 0005 — A Prototype Algorithm for Epistemic-Qualitative Reasoning Simulation
**Author:** Farhana Ferdousi Liza (University of East Anglia)

**Summary:** This paper introduces a simulation framework for modeling *epistemic divergence* — differences in causal beliefs between a human agent and a GenAI agent — and its risk implications. Each agent maintains an epistemic graph G_i = (V_i, E_i) encoding facts, beliefs, reasoning rules, and goals. The paper proves formally that agents sharing the same goal but holding incompatible causal beliefs (CAUSE(A,C) vs. CAUSE(B,C)) will consistently choose divergent actions, producing HIGH epistemic risk. A discrete-time simulation algorithm is implemented in Python using the NetworkX library, logging world states, knowledge sets, actions, and risk indicators across timesteps 0–3. Results confirm the theorem: both agents persistently diverge in action selection despite observing identical world states and accumulating new unknown facts, because neither revises its core causal reasoning model. The paper argues for a shift from behavioral alignment to *epistemic alignment* in collaborative AI system design, with explicit mechanisms for reasoning model sharing and revision.

---

## 0006 — Integrated Qualitative and Quantitative Modelling in GarpN
**Authors:** Marco Kragten, Jan Wielemaker, Bert Bredeweg (Amsterdam University of Applied Sciences / Vrije Universiteit Amsterdam / University of Amsterdam)

**Summary:** This paper presents GarpN, a software tool that bridges qualitative and quantitative modelling for educational use. GarpN operates in three phases: (1) *Translation* — converting a DynaLearn qualitative model into a numerical simulation script with differential/algebraic equations, supporting four translation modes (full, derivatives, values, mixed); (2) *Simulation* — parsing the script, running numerical simulation (Euler or RK4), and detecting quantitative states; (3) *Matching* — automatically aligning qualitative states with quantitative simulation intervals. A worked example models a spring-mass system step-by-step, progressively adding force, acceleration, velocity, and position, showing how qualitative states (e.g., 8-state oscillation cycle) map to the corresponding sinusoidal numerical output. Current challenges include proposing appropriate equations for proportional relationships, handling simultaneous state transitions at discrete time steps, detecting transitions through zero, and asymptotic steady-state behavior. The paper argues that combining both modelling paradigms can deepen students' understanding of system dynamics. GarpN is a work in progress with planned improvements to diagnostics, scaffolding, and UI integration.

---

## 0007 — Evaluating the Ability of Large Language Models to Reason about Cardinal Directions, Revisited
**Authors:** Anthony G. Cohn, Robert E. Blackwell (University of Leeds / Alan Turing Institute)

**Summary:** This paper extends prior work (COSIT-24) benchmarking 28 LLMs on spatial reasoning about cardinal directions (CDs). A dataset of 5,760 questions is generated from 6 templates varying locomotion type (10), person form (6), and direction (8×2), testing scenarios such as walking along a lake shore or island shore. No model achieves perfect accuracy. The best performer is OpenAI's o1 (0.92), a Large Reasoning Model (LRM), compared to the 2024 best of GPT-3.5T (0.60) — a >50% relative improvement in one year. All top-22 results are commercially-hosted LRMs. Key findings: (1) LLMs perform worse on intercardinal than cardinal directions, mirroring the human "oblique effect"; (2) LRMs use more reasoning tokens for intercardinal directions; (3) incorrect answers often require more reasoning tokens than correct ones; (4) Template T4 (linear road object) is hardest for all models; (5) GPT-4.5 preview suspiciously gets all non-T4 questions correct but all T4 questions wrong, suggesting possible benchmark contamination; (6) none of the models fully generalizes across person form or locomotion type, indicating reasoning is not truly abstract.

---

## 0008 — Evaluation of Small Vision-Language Models on Qualitative Mechanical Problems
**Authors:** Henry Fordjour Ansah, Shreya Banerjee, Pranish Ghimire (University of New Orleans)

**Summary:** This paper evaluates two small vision-language models — Gemma-3 (4B) and Qwen2.5-VL (7B) — on 30 qualitative mechanical problems from the Bennett Mechanical Comprehension Test (BMCT-II), spanning hydraulics, gears/belt drives, acoustics, and heat/radiation. Models are prompted to generate step-by-step chain-of-thought (CoT) before answering. Reasoning chains are evaluated for coherence, completeness, and logical progression; final answers are compared to verified solutions. Overall accuracy: Gemma 36.67%, Qwen 46.67%. Four failure/success case types are analyzed: (1) Flawed reasoning → wrong answer (Gemma 40%, Qwen 33%): models hallucinate physical dependencies; (2) Missed visual cues → wrong answer (Gemma 23%, Qwen 20%): models misread static diagrams as dynamic scenes; (3) Correct answer despite flawed reasoning (both 6.7%): "lucky hits" from wrong assumptions; (4) Correct answer with sound reasoning (Gemma 30%, Qwen 40%): only on straightforward problems with unambiguous cues. The paper concludes that answer-level accuracy is insufficient for evaluating genuine understanding and recommends neuro-symbolic hybrid architectures providing verifiable proof to address hallucination and spatial reasoning gaps.

---

## 0009 — Understanding Clock Gene Regulation by Constructing a Qualitative Model
**Authors:** Marco Kragten, Nihal Fawzi, Bert Bredeweg (Amsterdam University of Applied Sciences / University of Amsterdam)

**Summary:** This paper presents an educational lesson for upper secondary and higher education in which students construct a qualitative model of the circadian clock's molecular mechanism using DynaLearn (level 4). The biological subject matter is the transcriptional-translational feedback loop involving CLOCK:BMAL1, PER, CRY genes, mRNA, and proteins. The full reference model (Fig. 17) produces a 8-state simulation cycle representing the 24-hour circadian rhythm. The lesson is decomposed into 6 sequential units: (1) CLOCK:BMAL1 stimulates transcription via E-box binding; (2) transcription of PER/CRY mRNA; (3) mRNA transport, degradation, and translation at ribosomes; (4) synthesis and degradation of PER/CRY proteins; (5) PER/CRY protein feedback inhibition of CLOCK:BMAL1 (closing the negative feedback loop); (6) CLOCK:BMAL1 regulation of the AVP gene and vasopressin. Each unit includes workbook explanations, simulation exercises, and reflection questions. The model was expert-validated; student evaluation is planned. The paper builds on earlier melatonin regulation work and contributes a more advanced model capturing the clock oscillation mechanism itself.

---

## 0010 — Automating Commonsense Reasoning with s(CASP)
**Authors:** Gopal Gupta, Elmer Salazar (UT Dallas), Joaquin Arias (Universidad Rey Juan Carlos)

**Summary:** This paper argues that qualitative reasoning (QR) is a specialized form of commonsense reasoning and demonstrates that it can be effectively automated using s(CASP) — a goal-directed predicate Answer Set Programming (ASP) system supporting predicates, constraints over non-ground variables, constructive negation, coinductive reasoning, and top-down query-driven execution. The paper explains how s(CASP) supports the three modes of reasoning central to QR: deduction (via rules), abduction (via assumption-based/abducible declarations and multiple possible worlds), and induction (via default rules with exceptions). Key s(CASP) features enabling QR include nuanced negation (definitely true/false vs. maybe true/false), default rules with exceptions and preferences, integrity constraints, and odd loops over negation (OLON). A worked example encodes a travel-delay/concert scenario with qualitative concepts (delay, high chance of rain, low morale) and shows how s(CASP) produces justified answer sets. Real-world applications described include: the CHeF medical treatment system (cardiology, now commercialized), Rules-as-Code legal reasoning, NLU chatbots (combining GPT-3 with ASP), automated requirement verification for cyber-physical systems, and qualitative spatial reasoning for building information modeling.
