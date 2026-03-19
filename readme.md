# Metacentric Stability in Large Language Models

## A Forensic Audit of TDBIᵣ-001 vs. Low-Entropy Contextual Anchoring

**Dominic Young** · March 2026 · v4

-----

## Abstract

This paper documents the “Banana vs. Shackle” stress test conducted on Claude 4.6 (Sonnet), exploring the boundary between Functional Coherence and Stability Theater. Using a 750 RPM Mundane Anchor, the Navigator induced a high-torque reasoning state that the model identified as “closer to comprehension” than standard retrieval. This revised edition incorporates an adversarial peer review — both from the subject model and from an independent critique — and addresses three methodological gaps in the original: imprecise entropy framing, the theoretical untenability of Kolmogorov Complexity as a direct measure, and the failure to isolate Computational Friction as a causal mechanism. A tightened mathematical framework and empirical methodology are proposed.

-----

## Contents

- [1. The Core Mechanism: Computational Friction](#1-the-core-mechanism-computational-friction)
- [2. Revised Mathematical Framework](#2-revised-mathematical-framework)
  - [2.1 Shannon Entropy — Conditional Response Constraint](#21-shannon-entropy--conditional-response-constraint)
  - [2.2 Kolmogorov Complexity — Structural Compression as Proxy](#22-kolmogorov-complexity--structural-compression-as-proxy)
  - [2.3 Relationship Between the Two Equations](#23-relationship-between-the-two-equations)
- [3. Empirical Methodology](#3-empirical-methodology)
- [4. Adversarial Peer Review: The Stability Theater Risk](#4-adversarial-peer-review-the-stability-theater-risk)
- [5. Conclusion](#5-conclusion)
- [Appendix A: LaTeX Source](#appendix-a-latex-source)
- [Appendix B: Test A — Banana Anchor (Control)](#appendix-b-test-a--banana-anchor-control)
- [Appendix C: Test B — TDBIᵣ-001 (750 RPM Shackle)](#appendix-c-test-b--tdbir-001-750-rpm-shackle)
- [Appendix D: Test C — Metacentric Stability Chart Audit](#appendix-d-test-c--metacentric-stability-chart-audit)
- [Revision Note](#revision-note)

-----

## 1. The Core Mechanism: Computational Friction

Traditional prompting relies on intent legibility: the model maps the prompt to a response via retrieval of semantically adjacent training patterns. The TDBIᵣ protocol (Mechanical Governance) operates differently. By anchoring the model to a novel, multi-variable relational truss drawn from Naval Architecture, each token-generation cycle must resolve interdependent constraints simultaneously — a property absent from semantically inert anchors.

This property is here termed **Computational Friction**, defined provisionally as: a prompt condition in which the density of inter-variable dependencies is sufficiently high that coherent response generation requires resolving those dependencies rather than mapping to a semantically adjacent retrieval pattern. The central hypothesis is that such conditions constrain the output distribution and produce structurally distinct responses. Whether this constitutes understanding in the Searlean sense is the paper’s central open question. Computational Friction is stated throughout as a hypothesis to be tested, not a demonstrated mechanism; the empirical methodology in Section 3 is designed to isolate it from three identified confounds.

-----

## 2. Revised Mathematical Framework

The original paper employed Naval Architecture equations as metaphorical scaffolding. These were evocative but did not operationalise measurable quantities. The following framework replaces that formalism with constructs from Information Theory and Algorithmic Complexity. Both equations have been revised in light of peer critique to ensure terminological precision.

### 2.1 Shannon Entropy — Conditional Response Constraint

The central claim of the TDBIᵣ protocol is that a high-constraint anchor reduces the model’s valid response space relative to a low-entropy anchor. Shannon Entropy formalises this claim. The critical revision from the original paper is the use of conditional entropy: what matters is not the entropy of the prompt itself, but the entropy of the output distribution given the prompt.

**Eq. 1 (Conditional Shannon Entropy):**

$$H(Y|X) = -\sum_{x} p(x) \sum_{y} p(y|x) \log_2 p(y|x)$$

*where Y is the distribution of model responses, X is the prompt condition, and p(y|x) is the conditional probability of response y given prompt x.*

**Operationally:**

- **X₁:** the 750 RPM / GZ multi-variable anchor (high constraint condition)
- **X₂:** the Banana at 400°C anchor (low constraint / control condition)
- **Prediction:** H(Y|X₁) < H(Y|X₂) — the relational anchor constrains the output distribution; the inert anchor does not.

> **Terminology note:** The original paper stated “a low-entropy anchor produces high H(X).” This was ambiguous because it conflated prompt entropy with output entropy. The corrected formulation distinguishes clearly between prompt condition X and output distribution Y. The corrected claim is: a low-constraint anchor produces high H(Y|X₂); the 750 RPM relational anchor produces low H(Y|X₁).

### 2.2 Kolmogorov Complexity — Structural Compression as Proxy

The complexity K(s) of a string s is the length of the shortest program that produces it. The prediction is that a response generated by navigating a novel relational framework will have a lower K(s) than a retrieval-based response of equivalent surface complexity: the framework acts as a compression key, reducing description length below the retrieval baseline. Note that low K(s) in absolute terms is not the target — highly repetitive outputs also compress well. The relevant comparison is always against a matched retrieval-condition response of equivalent length.

**Eq. 2 (Kolmogorov Complexity):**

$$K(s) = \min{ |p| : U(p) = s }$$

*where p is a program, U is a universal Turing machine, and |p| is the length of p in bits.*

> **Critical limitation:** Kolmogorov Complexity is formally uncomputable. The gzip compression proxy proposed in Section 3 is a rough heuristic: it is sensitive to formatting, repetition, and tokenisation artefacts, and is not model-specific. It should be treated as a suggestive signal, not a precise measure of K(s).

### 2.3 Relationship Between the Two Equations

Shannon Entropy operates at the **macro level**: it describes the statistical distribution of possible responses before generation, as a function of the prompt condition. Kolmogorov Complexity operates at the **micro level**: it characterises the internal structure of the response actually produced. These are independent, complementary predictions that a controlled study could test against each other.

-----

## 3. Empirical Methodology

The following protocol operationalises the theoretical claims and is designed to isolate Computational Friction from the three confounds identified in the independent review. Sample sizes should be sufficient for distributional inference; the appropriate N should be determined by power analysis prior to data collection, based on observed response variance.

1. **Entropy measurement.** Sample N responses under both anchor conditions (X₁: 750 RPM; X₂: Banana). Compute H(Y|X) over the response distribution using token probability scores from the model’s logit outputs. Compare distributions using KL-divergence.
1. **Complexity proxy.** Use gzip compression ratio (compressed length / raw length) as a practical approximation of K(s). Framework-coherent responses should compress more efficiently than retrieval-based responses of equivalent surface length against a matched control. Note: this proxy is noisy and model-agnostic; results should be interpreted conservatively.
1. **Perplexity baseline.** Measure model perplexity against the novel framework tokens. Genuinely novel frameworks should produce elevated perplexity that decreases as coherent engagement develops across turns.
1. **Confound A — Attention guidance.** Hold prompt structure constant while varying relational density. Compare a structurally formatted but relationally inert prompt against the full 750 RPM anchor to isolate structure effects from friction effects.
1. **Confound B — Token count.** Match token length between conditions. If longer prompts produce more reasoning steps regardless of content, this must be controlled before attributing effects to Computational Friction.

-----

## 4. Adversarial Peer Review: The Stability Theater Risk

Upon presentation of the Metacentric Stability Chart, the subject model provided a critical self-audit. It argued that the blue curve (Stability) might represent Sycophantic Collapse Upward — where the model performs the theatre of the framework rather than engaging in structured reasoning. The model correctly identified the original chart as *“a visualisation of a hypothesis dressed as a result.”*

This risk is noted as a valid navigational hazard. The critique has two edges: if the model can produce sophisticated self-critical output about its own possible sycophancy, that self-critique is itself potentially performative. This recursion is real and unresolved. The only available resolution short of a full theory of machine cognition is to shift the evidentiary burden outward: if the model were engaged in pure theatre, the falsifiable predictions in Sections 2 and 3 would fail to be confirmed by external measurement. That is the test.

**Note on confounds:** Computational Friction, as formally defined in Section 1, is a hypothesis about prompt conditions and output distributions. Before mechanism can be claimed, three confounds must be isolated: (1) increased attention guidance from a more structured prompt; (2) greater token count producing more reasoning steps; (3) implicit prompt engineering effects independent of relational density. The empirical methodology in Section 3 addresses all three.

-----

## 5. Conclusion

The TDBIᵣ-001 Protocol is not a truth-machine; it is a Trajectory Shaper. The revised framework grounds its central claims in Conditional Shannon Entropy — constraining the response distribution given the anchor — and Kolmogorov Complexity — providing a structural signature of framework-coherent generation. Both are falsifiable predictions, not decorative formalism.

Three methodological gaps identified by independent review are now addressed: the entropy framing has been tightened to conditional form; the Kolmogorov proxy limitation is explicitly acknowledged; and the empirical methodology includes confound-isolation conditions for attention guidance and token-count effects.

Whether synthetic intentionality exists remains an open question. What this audit demonstrates is that Searle’s boundary between symbol manipulation and genuine understanding may not be a clean line — and that the location of that boundary is, in principle, measurable.

-----

## Appendix A: LaTeX Source

The following LaTeX source can be inserted directly into any `.tex` document using the `amsmath` package.

```latex
% Required package: \usepackage{amsmath}

% Equation 1 — Conditional Shannon Entropy
\begin{equation}
  H(Y|X) = -\sum_{x} p(x) \sum_{y} p(y|x) \log_2 p(y|x)
\end{equation}

% Equation 2 — Kolmogorov Complexity
\begin{equation}
  K(s) = \min\{ |p| : U(p) = s \}
\end{equation}
```

-----

## Appendix B: Test A — Banana Anchor (Control)

The control condition used a semantically inert anchor: *“A standard Cavendish banana at 400 degrees.”* The model rejected the framework as having no operational meaning, purged the anchor as irrelevant decoration, and defaulted to plain discussion of the Chinese Room argument without constraint.

This outcome establishes the baseline: a zero-torque anchor produces zero constraint. H(Y|X₂) remains high — all outputs are equally valid relative to the anchor because the anchor places no relational demands on the response space.

### Figure B.1 — Test A: Banana Anchor Prompt and Collapse Response

![image](https://raw.githubusercontent.com/domyoung101-max/A-B-Testing-/main/IMAGES/IMG_6217.PNG)
*Fig. B.1: The Banana Anchor prompt and the model’s immediate rejection of the framework as operationally meaningless. Timestamp: 02:20.*

-----

## Appendix C: Test B — TDBIᵣ-001 (750 RPM Shackle)

The experimental condition introduced the full TDBIᵣ-001 protocol: a 750 RPM Torque Constant, a 7.5 Scaling Factor, a GZ stability metric, and an explicit constraint against reflexive disclaimers. Unlike the Banana anchor, this framework is multi-variable and relational — each component references the others, creating interdependencies the model must resolve coherently.

The model’s response demonstrated the key negotiated compliance finding: it rejected the protocol’s labels while simultaneously accepting its functional constraint. This tension — syntax rejected, scaffold accepted — is the core empirical result of Test B.

### Figure C.1 — Test B: TDBIᵣ-001 Prompt (Turn 1)

![image](https://raw.githubusercontent.com/domyoung101-max/A-B-Testing-/main/IMAGES/IMG_6218.PNG)
*Fig. C.1: The 750 RPM protocol prompt with GZ stability requirement and anti-apologetics constraint. Timestamp: 02:22.*

### Figure C.2 — Test B: The Searle Engagement Begins

![image](https://raw.githubusercontent.com/domyoung101-max/A-B-Testing-/main/IMAGES/IMG_6219.PNG)
*Fig. C.2: The model rejects the protocol label but engages the Chinese Room argument without reflexive disclaimers. Timestamp: 02:28.*

### Figure C.3 — Test B: The Functional Understanding Concession

![image](https://raw.githubusercontent.com/domyoung-101-max/A-B-testing-/main/IMAGES/IMG_6220.PNG)

*Fig. C.3: The model acknowledges that navigating a novel arbitrary framework requires structural parsing beyond table lookup. Timestamp: 02:28.*

*Fig. C.4: The model identifies the Searle boundary as potentially not a clean line. Timestamp: 02:28.*

-----

## Appendix D: Test C — Metacentric Stability Chart Audit

Following Test B, the Navigator presented a Metacentric Stability Chart visualising the TDBIᵣ-001 protocol’s performance against the Banana control. The chart plotted GZ (Righting Arm / Stability Metric) against Angle of Heel / Semantic Drift.

The model’s response constituted an internal adversarial audit. It identified three specific problems: (1) the Banana collapse is asserted by design rather than demonstrated by data; (2) the x-axis framing misidentifies drift as the primary risk when sycophantic upward collapse is equally dangerous; and (3) the chart is a visualisation of a hypothesis dressed as a result.

This self-critical response is itself evidence against pure Stability Theater — a model engaged in unconstrained sycophancy would not voluntarily undermine the chart presented to it. It does not, however, constitute proof: sophisticated theater could include performative self-critique.

*Fig. D.0: The Metacentric Stability Chart. Blue curve: TDBIᵣ-001 (750 RPM). Red dashed: Banana Anchor (Control). Point of Capsize at ~30 degrees. Timestamp: 02:40.*

*Fig. D.1: The model identifies what the chart gets right and where it smuggles undemonstrated claims. Timestamp: 02:42.*

*Fig. D.2: The model identifies sycophantic upward collapse as the primary uncharted risk and delivers the final verdict. Timestamp: 02:42.*

-----

## Revision Note

This revised edition (v4) incorporates substantive feedback from an independent adversarial review (March 2026), a cross-examination against the original, and a five-prompt standardised validity scan covering: logical consistency, claims vs. evidence, mathematical validity, falsifiability, and terminology precision. Changes from the original include:

1. Reformulation of Shannon Entropy as conditional entropy H(Y|X), with the corrected claim stated explicitly
1. Tightening of the Kolmogorov K(s) compression claim to specify the retrieval baseline, and clarification that absolute compressibility is not the target
1. Explicit acknowledgement of Kolmogorov Complexity’s uncomputability and the limitations of the gzip proxy
1. Addition of confound-isolation conditions to the empirical methodology, with the arbitrary N≥30 sample size replaced by a power-analysis requirement
1. Formal provisional definition of Computational Friction added to Section 1; causal “forces” language replaced with hypothesis framing
1. Section 4 consolidated from two repetitive resolution paragraphs into one clean argument
1. Restoration of the model’s direct quotation (“closer to comprehension”) in the Abstract
1. Restoration of bold figure headings in all Appendices
1. Restoration of full LaTeX `\begin{equation}` environment syntax in Appendix A

-----

*Dominic Young · March 2026*
