# QR 2023 Paper Summaries

---

## 01 — Analogical Quantity Estimation
**Authors:** Beau Hancock, William Demel, Kenneth D. Forbus (Northwestern University)

**Summary:** This paper presents the Analogical Quantity Estimation (AQE) algorithm, which learns to estimate continuous quantities by combining analogical reasoning with qualitative representations. AQE uses the SAGE analogical generalization engine to construct exemplar-based models of quantity distributions from labeled examples. Quantities are encoded qualitatively: rather than raw numbers, the algorithm works with qualitative categories (e.g., small/medium/large) derived from distributional partitions. Given a new entity, AQE retrieves the most analogically similar cases via MAC-FAC and SME, then estimates the target quantity by interpolating within the qualitative partition. The system is evaluated on predicting numeric properties of 197 Wikidata countries (e.g., population, GDP, area) and university rankings. AQE achieves competitive accuracy compared to linear regression while offering the interpretability benefits of analogical reasoning — each estimate comes with an explanation referencing the most similar known cases.

---

## 02 — Qualitative Models of Stars for Astronomy Education
**Authors:** Bert Bredeweg, Dennis Vaendel, Joris Hanse, Stef Bloemen (Amsterdam University of Applied Sciences / University of Amsterdam / Radboud University)

**Summary:** This paper develops three interconnected DynaLearn qualitative models for teaching stellar physics in the Stargazing Live! mobile planetarium project. The three models address: (1) stellar properties — the relationships among a star's mass, temperature, luminosity, and radius; (2) stellar lifecycle states — qualitative descriptions of the main sequence, red giant, and white dwarf phases; and (3) the hydrostatic equilibrium — the balance between gravitational contraction and radiation pressure from fusion, modeled as a negative feedback loop. The full reference model produces an 8-state simulation cycle capturing the dynamic balance within a main-sequence star. Each model is designed for guided construction by secondary and higher education students, accompanied by workbooks and reflection questions. The paper demonstrates how qualitative modeling can make abstract astrophysics accessible through active knowledge construction rather than passive information transfer.

---

## 03 — BamBirds: Angry Birds AI with Qualitative Physics
**Authors:** Diedrich Wolter, Viviana Mascardi, Pablo Barra, Fabio Tardella (University of Lübeck / University of Genoa)

**Summary:** This paper presents BamBirds, an AI agent for the Angry Birds game that uses qualitative physics to plan and execute shot trajectories. BamBirds takes a hybrid GOFAI+ML approach: qualitative reasoning handles high-level scene interpretation and strategic planning (identifying targets, estimating reachability), while machine learning components handle lower-level perception and trajectory refinement. The qualitative model represents objects and their spatial relations, physical properties (mass, fragility), and qualitative force-motion relationships. A qualitative planner selects target sequences and shot types based on this model, then passes parameters to a numerical trajectory calculator for execution. The paper describes the architecture and evaluates BamBirds in the AIBirds competition setting. The key contribution is demonstrating that a qualitative physics backbone enables more generalizable, interpretable agent behavior than purely data-driven approaches on novel level configurations.

---

## 04 — Qualitatively Constrained Reinforcement Learning for Control
**Authors:** Luka Šoberl, Matej Kristan, Ivan Bratko (University of Ljubljana)

**Summary:** This paper presents a method for learning reinforcement learning policies that satisfy qualitative constraints derived from domain knowledge. Q-constraints — qualitative specifications of valid state-action relationships, represented as sign-definite regions in the state-action space — are learned from expert trajectories using the Padé algorithm, which fits rational polynomials and extracts qualitative boundary conditions. These constraints are then enforced as action masks during RL policy learning, ensuring the agent never selects actions outside the qualitatively feasible region. The approach is demonstrated on the inverted pendulum control task. Qualitatively constrained RL learns faster and produces more stable policies than unconstrained RL, because the constraint mask prevents the agent from exploring physically meaningless or dangerous state-action combinations. The paper contributes a methodology for integrating expert qualitative knowledge into data-driven control, with implications for safe and sample-efficient reinforcement learning in physical systems.

---

## 05 — Qualitative Novelty Detection in Physical Game Environments
**Authors:** Tiago Pinto, Lara Brandão, Pedro Sequeira, Rui Prada, Santiago Ontañón (INESC-ID / Instituto Superior Técnico / SRI International / Drexel University)

**Summary:** This paper studies the difficulty of novelty detection in the Angry Birds game environment within the DARPA SAIL-ON program, which aims to develop AI systems capable of detecting and adapting to novel situations. The paper constructs qualitative physics models of the game world and uses them to define novelty — a deviation from what the model predicts. Novelty types are characterized along qualitative dimensions: structural novelties (new object types), relational novelties (new interaction patterns), and quantitative novelties (unexpected physical magnitudes). The paper systematically evaluates which types of novelty are hardest to detect and explains why: novelties that are qualitatively consistent with the existing model (they produce no violated qualitative prediction) are invisible to qualitative detectors, even though they change the numerical game dynamics. The paper identifies this "qualitative blindspot" as a fundamental limitation and proposes a taxonomy of novelty difficulty grounded in qualitative model coverage.

---

## 06 — Qualitative Modelling of Circular and Elliptical Motion
**Authors:** Marco Kragten, Bert Bredeweg (Amsterdam University of Applied Sciences / University of Amsterdam)

**Summary:** This paper develops qualitative models of circular and elliptical orbital motion using DynaLearn for secondary and higher education contexts. The circular motion model captures the relationships among orbital radius, orbital velocity, centripetal acceleration, and gravitational attraction, producing an 8-state simulation cycle representing uniform circular orbit. The elliptical model extends this to include the varying distance between the orbiting body and the central mass, the corresponding changes in velocity (Kepler's second law), and the alternating states of approach and recession, producing a 12-state simulation cycle. The paper describes the pedagogical decomposition of both models, the entity-quantity-relation structures used, and the simulation scenarios designed for students. The work is situated within a broader curriculum that uses DynaLearn to teach celestial mechanics concepts in an active, model-building style.

---

## 07 — Evaluating ChatGPT on Qualitative Spatial Reasoning
**Authors:** Anthony G. Cohn (University of Leeds / Alan Turing Institute)

**Summary:** This paper conducts the first systematic evaluation of a large language model (ChatGPT-4) on region-based qualitative spatial reasoning tasks drawn from the RCC-8 (Region Connection Calculus) formalism. Three task types are evaluated: (1) composition table queries — given two RCC-8 relations r1 and r2, what is the possible set of relations r3 such that (A r1 B) ∧ (B r2 C) → (A r3 C)? ChatGPT achieves 71.94% accuracy; (2) preferred compositions — when multiple relations are possible, which is most likely in typical spatial contexts? ChatGPT achieves 40.82% accuracy; (3) conceptual neighborhood queries — which RCC-8 relations are "nearest" to a given relation in the topology of spatial transitions? ChatGPT achieves approximately 90% accuracy. Analysis of errors reveals that ChatGPT has learned surface-level patterns in RCC-8 terminology but lacks a robust geometric model: it fails systematically on composition cases that require transitivity reasoning across complex topological configurations.

**Key finding:** LLMs perform reasonably on recognizing and near-neighbor retrieval tasks in QSR but poorly on genuine compositional reasoning, suggesting pattern matching rather than spatial model reasoning.

---

## 08 — Combining Qualitative Models with Bayesian Networks
**Authors:** Stefan Münch, Diedrich Wolter (University of Lübeck)

**Summary:** This paper proposes a methodology for combining DynaLearn qualitative simulation models with Bayesian Networks (BNs) to bridge qualitative causal structure with probabilistic uncertainty. The QR model provides the causal skeleton — entities, quantities, influences, proportionalities — and defines the qualitative state space. A Bayesian Network is then constructed whose nodes correspond to the qualitative states and whose conditional probability tables encode empirical uncertainty over which states are realized given observations. A container/tank filling example illustrates the approach: the qualitative model defines valid flow patterns and state transitions, while the BN models the probability of each qualitative state sequence given partial observations (e.g., a noisy level sensor). The combined model supports probabilistic inference over qualitative states, enabling soft reasoning about system behavior when the qualitative model alone would produce too many qualitatively consistent interpretations. The paper contributes a principled integration strategy and discusses challenges in eliciting CPTs from qualitative models.

---

## 09 — KNACK v2: Analogical Quantity Estimation with Qualitative Partitions
**Authors:** William Demel, Beau Hancock, Kenneth D. Forbus (Northwestern University)

**Summary:** This paper presents KNACK v2, an extension of the KNACK analogical learner that incorporates qualitative distributional partitions for quantity estimation. KNACK v2 uses the SAGE analogical generalization engine to build case libraries of entities described with both qualitative and quantitative features. For a target entity, SAGE retrieves structurally similar cases via SME (Structure-Mapping Engine) and estimates quantities by analogical interpolation within qualitatively defined partitions. The qualitative partitions serve as a coarse but robust scaffold for interpolation, preventing the numerical instabilities that arise when raw values are interpolated across semantically dissimilar cases. The system is evaluated on estimating 13 numeric properties of 197 Wikidata countries and achieves performance competitive with linear regression on most tasks, while providing richer, analogically grounded explanations. The paper demonstrates that qualitative representations enhance the robustness and interpretability of analogical learning for quantitative estimation.

---

## 10 — DynaLearn Level-5 Lessons: Photoelectric Effect, Thermoregulation, Global Warming
**Authors:** Marco Kragten, Tessa Hoogma, Bert Bredeweg (Amsterdam University of Applied Sciences / University of Amsterdam)

**Summary:** This paper presents three lesson activities developed for upper secondary and higher education that use DynaLearn level-5 qualitative representations — the most advanced level, supporting conditional expressions alongside influences, proportionalities, calculi, and inequalities. The three topics are: (1) the *photoelectric effect* (physics) — modeling how light frequency and amplitude affect electron kinetic energy and current, with a conditional expression capturing the threshold frequency; (2) *thermoregulation* (biology) — modeling the hypothalamic negative feedback loop controlling body temperature, with conditional activation of shivering (below norm) and sweating (above norm); and (3) *global warming* (geography) — modeling CO₂ emissions, atmospheric uptake, and the nonlinear effect of temperature on economic production, including a conditional expression for the optimum temperature threshold. Each lesson follows a step-by-step pedagogical approach with workbooks and cloze-response questions. The lessons were developed within Project Denker, which has produced over 30 DynaLearn lesson activities across biology, physics, geography, and economics.

---

## 11 — Emotional Dimensions of Food Waste Perception
**Authors:** Konstantina Zacharaki, Jennifer Nguyen, Queralt Prat-i-Pubill, Núria Agell (ESADE Business School, Ramon Llull University)

**Summary:** This paper applies Hesitant Fuzzy Linguistic Term Sets (HFLTS) — a qualitative reasoning methodology for aggregating imprecise linguistic judgments — to analyze emotional responses to food waste in a controlled experiment. 181 undergraduate participants tasted two apple slices labeled as "supermarket" and "Too Good To Go" (actually identical) and rated six emotions (angry, ashamed, guilty, happy, indifferent, sad) while imagining throwing away food, using a 1–5 scale with hesitancy (range responses permitted). The HFLTS approach represents responses as linguistic intervals, computes a group centroid (the most representative collective opinion), and measures consensus. Compared to classical mixed-ANOVA, the HFLTS approach detected differences across fruit preference groups that statistical tests missed. Key findings: guilt is the dominant emotion; females and participants with prior knowledge of "Too Good To Go" report stronger negative emotions and lower indifference. The paper demonstrates that QR-based linguistic aggregation methods are better suited than classical statistics for capturing hesitancy and polarity in subjective emotional data.

---

## 12 — Qualitative Monitoring of AI Solutions in Safety-Critical Systems
**Authors:** Mark Tappe, Benjamin Kelm, Oliver Niggemann, Stephan Myschik (Helmut Schmidt University Hamburg / University of the Bundeswehr Munich)

**Summary:** This paper presents a qualitative monitoring agent for supervising AI/ML reconfiguration decisions in safety-critical Cyber-Physical Systems (CPS), demonstrated on the ISS COLUMBUS module's Environmental Control and Life Support System (ECLSS). The agent uses QSIM-based Qualitative Differential Equations (QDEs) to model the CPS's continuous behavior, extended with F+ and F- constraint functions that handle binary input activation (open/closed valves, on/off fans). Given a candidate reconfiguration produced by the AutoConf SAT-based algorithm, the monitoring agent runs a qualitative prediction forward through a Qualitative Analysis Tree (QuAT) — a decision-tree-like structure of reachable qualitative states. Each state is assigned a risk score based on whether qualitative variable values exceed operating limits; risk propagates upward via predecessor states. For a simulated fault case (Cooling Core 1 failure with cabin overpressure), five candidate reconfigurations are evaluated and ranked; the optimal choice (b3) is identified by minimum cumulative risk. The paper contributes a methodology for providing interpretable, model-based safety analysis of black-box ML decisions in critical systems.

---

## 13 — Preliminary Experiments Using LLMs for Design
**Authors:** John T Maxwell III, Johan de Kleer, Ion Matei, Maksym Zhenirovsky (PARC / SRI International)

**Summary:** This paper investigates using ChatGPT-4 as a topology generator in an automated physical system design pipeline. Rather than designing from scratch, the pipeline uses ChatGPT-4 to propose component connection topologies in Modelica (an equation-based modeling language), a Sizer optimizer to find valid parameter values for the proposed topology, and a Repair module to fix syntactically or topologically invalid designs. Three experiments are reported: (1) *low-pass filter design* — ChatGPT generates mostly valid RC topologies, but with incorrect parameter values that the Sizer corrects; (2) *power train design* — ChatGPT generates correct-looking but often behaviorally incorrect topologies (missing brake, wrong flange connections), requiring behavioral repair guided by qualitative component analysis; (3) *behavioral repair using qualitative analysis* — missing components are diagnosed by comparing the qualitative behavior of the candidate design against qualitative unit tests for library components (e.g., if brake pedal press never causes deceleration, a brake is missing). The key insight is that qualitative behavior analysis of candidate designs enables principled diagnosis of LLM-generated topology errors.

**Key finding:** ChatGPT is a "sloppy but general" designer — often approximately correct, rarely exactly correct. Pairing it with qualitative simulation and symbolic repair transforms it into a useful design starting point.

---

## 14 — Building Domain Theories from Language-Grounded Ontologies
**Authors:** Kenneth D. Forbus (Northwestern University)

**Summary:** This paper proposes using the NextKB/OpenCyc commonsense ontology as a scaffold for building broad QP domain theories. The idea is to identify *anchor concepts* in the ontology — existing concepts (e.g., FluidFlow-Translation, PrecipitationProcess, Movement-TranslationProcess) that correspond to QP-style continuous processes. Pre-existing QP model fragments from prior work are then linked to these anchor concepts via the genls inheritance relation, so that all sub-concepts of the anchor automatically inherit the model fragment schema. This provides enormous breadth: the anchor concept for Motion has 355 sub-classes (including snowboarding, parkour, and projectile motion) and 170 associated English words. The approach is analyzed for eight phenomena (liquid flow, heat flow, boiling, evaporation, precipitation, floating, motion, friction), showing that anchoring yields substantial increases in the range of phenomena and natural language terms covered. The paper explicitly argues against LLMs as knowledge bases: LLMs lack grounding and optimize for statistical plausibility rather than correct reasoning.

---

## 15 — Knowledge-Based Decision Support for Water Treatment
**Authors:** Peter Struss (Technical University of Munich)

**Summary:** This paper is a research proposal for a web-based decision support system (DSS) for water treatment facilities, motivated by UN Sustainable Development Goal 6 (Clean Water and Sanitation). The DSS uses process-oriented QR modeling — specifically Forbus-style QP model fragments — to represent water treatment steps (coagulation, flocculation, sedimentation, filtration) and natural processes as formal cause-effect implications. The knowledge repository contains context-free process types whose preconditions and effects on water quality can be assembled into complete plant models. Four DSS functions are proposed: (1) *plant design* — assembling process types to satisfy input/output quality requirements; (2) *trouble-shooting* — consistency-based abductive diagnosis of observed deviations from nominal behavior; (3) *intervention proposal* — generating corrective actions by searching for process types whose effects counteract diagnosed faults; (4) *education and training* — supporting non-expert plant operators through model-based what-if analysis. Open AI research challenges discussed include the frame problem (transporting unaffected water constituents), bounded abductive reasoning, and temporal snapshot limitations. A collaboration between TU Munich and Vellore Institute of Technology is implementing the prototype.
