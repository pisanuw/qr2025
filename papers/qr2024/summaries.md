# QR 2024 Paper Summaries

---

## 1 — Qualitative Modelling of Melatonin Regulation
**Authors:** Nihal Fawzi, Marco Kragten, Bert Bredeweg (Amsterdam University of Applied Sciences / University of Amsterdam)

**Summary:** This paper develops a qualitative reference model of the melatonin production cycle in the human brain using DynaLearn, situated within the Stargazing Live! astronomy education project. The model captures the light-driven suppression and nocturnal release of melatonin via the retinohypothalamic tract, the suprachiasmatic nucleus (SCN), and the pineal gland. The complete model involves entities including light, the SCN, pineal gland, and melatonin, with quantities for light intensity, nerve impulses, and melatonin levels. The simulation produces a 12-state cycle representing the diurnal rhythm of melatonin regulation. The paper describes the pedagogical decomposition of the model into sequential construction steps, each scaffolded with workbook explanations and simulation exercises. Student evaluation is planned. The model connects scientific domain knowledge to qualitative reasoning methodology for use in secondary and higher education.

---

## 2 — Qualitative Reasoning for Comparative Media Analysis
**Authors:** Ahmad Abuasaker, Queralt Prat-i-Pubill, Núria Agell (ESADE Business School, Ramon Llull University)

**Summary:** This paper applies qualitative reasoning methods to compare news media coverage of the Israel-Gaza war across four European countries (Spain, Germany, France, and the UK) using the GDELT Event Database. The approach uses linguistic perceptual maps — a qualitative representation technique based on Hesitant Fuzzy Linguistic Term Sets (HFLTS) — to encode and compare editorial stances across outlets over time. GDELT data is filtered for relevant conflict events and mapped to qualitative categories reflecting tone, framing, and intensity of coverage. The centroid and consensus measures from prior HFLTS work are applied to identify similarities and divergences in media framing across national contexts. The paper demonstrates that QR-based qualitative aggregation can surface geopolitical and editorial patterns that classical statistical approaches miss. This is a novel application of QR to computational social science and media analysis.

---

## 3 — Automating Qualitative Model Construction with LLMs and Physical Laws
**Authors:** Hiroyuki Suzuki, Fumihito Yoshioka (Tohoku University)

**Summary:** This paper proposes a pipeline for automating the construction of Qualitative Process (QP) models from natural language problem descriptions. ChatGPT/GPT-4 is used as a *retriever*: given a text description, the LLM identifies the relevant physical objects and phenomena (processes, quantities, influences). These are then matched to a formal physical laws database structured according to QPT. A QPT simulator then performs the actual qualitative reasoning. The approach is evaluated on introductory physics problems involving heat flow, fluid dynamics, and projectile motion. The key insight is that LLMs have sufficient physical commonsense to name the relevant objects and processes, but lack the formal representational precision to perform QR directly. Separating the NL-to-structure step (LLM) from the formal reasoning step (QPT simulator) allows the pipeline to leverage LLM breadth while preserving the correctness and explainability of symbolic QR.

**Key finding:** LLMs are effective for identifying the components of a QP model from natural language but cannot perform QPT reasoning reliably on their own.

---

## 4 — Qualitative Constraints for Autonomous Vehicle Parallel Parking
**Authors:** Luka Šoberl, Matej Kristan, Ivan Bratko (University of Ljubljana)

**Summary:** This paper applies qualitative constraint learning to the task of parallel parking in autonomous vehicles. The approach uses Q-constraints — qualitative specifications of feasible state-action relationships — learned via the Padé algorithm, which fits rational polynomials to observed trajectories and extracts qualitative constraints on valid maneuver regions. The learned constraints define a qualitative envelope of feasible parking trajectories without requiring an explicit numerical parking model. The controller selects actions consistent with the learned constraints at each timestep. Experiments on a simulated vehicle achieve an 89% success rate on parallel parking tasks, outperforming a purely numeric baseline in terms of generalization to novel initial positions. The paper contributes a methodology for deriving human-interpretable qualitative driving constraints from data, with implications for safety verification and explainable autonomous vehicle behavior.

---

## 5 — Qualitative Process Theory for Social Reasoning
**Authors:** Kenneth D. Forbus (Northwestern University)

**Summary:** This work-in-progress paper extends Qualitative Process (QP) theory to the domain of social reasoning, with a focus on modeling friendship dynamics. Forbus argues that social phenomena involving relationships between agents — including trust, affinity, shared experience, and conflict — can be captured using QP-style model fragments with episodic memory and event representations. The OpenCyc/NextKB ontology provides the conceptual vocabulary for social entities and events. Partial model fragments are proposed for processes such as trust accumulation, affinity decay, and social reinforcement. The paper illustrates how a QP-based account of friendship could be used to predict qualitative changes in relationship strength over time. The challenge of grounding social quantities (trust, affinity) in observable behavioral cues is discussed. The work connects to Forbus's broader agenda of using QP theory for commonsense reasoning across diverse domains.

---

## 6 — KANs and Qualitative Color Description for Explainable AI
**Authors:** Ricardo Sanz, Carlos Hernández-Corbato, Raúl Arrabales (Universidad Politécnica de Madrid)

**Summary:** This paper investigates the use of Kolmogorov-Arnold Networks (KANs) in combination with Qualitative Color Description (QCD) as a tool for Explainable AI (XAI). KANs, unlike standard neural networks, place learnable activation functions on edges rather than nodes, making their symbolic structure more transparent. QCD provides a qualitative vocabulary for describing color regions and transitions, grounded in perceptual color theory. The paper applies this combination to a watermarking detection case study: a KAN is trained to detect digital watermarks, and QCD is used to characterize the qualitative visual properties that the network responds to. The resulting explanations are expressed in qualitative terms (e.g., "detects a shift from warm to cool hue in the mid-frequency band") rather than gradient attribution maps. The paper argues that the compositional symbolic structure of KANs makes them naturally suited for qualitative post-hoc explanation.

---

## 7 — GarpN: Bridging Qualitative and Quantitative Modelling
**Authors:** Marco Kragten, Jan Wielemaker, Bert Bredeweg (Amsterdam University of Applied Sciences / Vrije Universiteit Amsterdam / University of Amsterdam)

**Summary:** This paper presents GarpN, a software tool that bridges qualitative and quantitative modeling for educational use. GarpN operates in three phases: (1) *Translation* — converting a DynaLearn qualitative model into a numerical simulation script using differential/algebraic equations, supporting four translation modes (full, derivatives, values, mixed); (2) *Simulation* — parsing and executing the numerical script using Euler or RK4 methods, detecting quantitative states; (3) *Matching* — automatically aligning qualitative states (from DynaLearn simulation) with intervals in the quantitative output. A worked example models a spring-mass system step-by-step, progressively adding force, acceleration, velocity, and position quantities, demonstrating that a qualitative 8-state oscillation cycle maps correctly to the corresponding sinusoidal numerical output. Challenges discussed include proposing equations for proportional relationships, handling simultaneous state transitions, and detecting asymptotic steady-state behavior. GarpN is a work in progress intended to deepen students' understanding by allowing them to see the same system in both qualitative and quantitative terms.

---

## 8 — Belief Base Revision for Qualitative Simulation Models
**Authors:** Moritz Bayerkuhnlein, Diedrich Wolter (University of Lübeck)

**Summary:** This paper presents a principled framework for updating Qualitative Simulation Models (QSMs) in response to new observations, framed as a *belief base revision* problem. The authors adapt the classic AGM belief revision postulates (Success, Inclusion, Consistency, Vacuity, Relevance, Uniformity) to the non-monotonic, non-deterministic nature of QSM simulation. A QSM is represented as a graph M = ⟨Q, P, C⟩ of quantities, causal processes, and constraints. A revision operator is defined using logic-based abduction and a pseudo-distance measure over model components (symmetric difference), minimizing structural changes while restoring consistency with new observations. The operator is proven to satisfy all adapted rationality postulates. The framework is applied to diagnosing learner mental models: given a student's QSM that diverges from a reference model, abductive revision generates contrastive explanations identifying what the student's model incorrectly includes or excludes. Applications include model debugging, alignment with human mental models, and incremental learning in commonsense reasoning systems.

---

## 9 — Extracting Ontological Commitment from Foundation Models
**Authors:** Tuna Keser, Diedrich Wolter, Mehul Bhatt (University of Lübeck / Stockholm University)

**Summary:** This paper investigates the ontological commitments implicit in large vision-language foundation models, specifically CLIP (Contrastive Language-Image Pretraining). Rather than using CLIP as a tool, the paper *studies* it: what categories and distinctions does CLIP implicitly encode in its embedding space? The methodology applies hierarchical clustering to CLIP's visual embedding space over a carefully constructed image dataset spanning object categories, spatial relations, and abstract properties. The structure of the resulting dendrogram is compared against formal ontologies (e.g., WordNet, part-whole hierarchies) to identify where CLIP's implicit category structure aligns with or diverges from human-specified ontological distinctions. Key findings include that CLIP reliably encodes basic-level categories and some spatial relations, but inconsistently represents abstract properties and part-whole relationships. The paper argues that understanding foundation models' ontological commitments is essential for grounding their outputs in formal qualitative representations.
