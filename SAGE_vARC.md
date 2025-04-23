# SAGE_vARC — Structured Deliberation Framework (Arcana Edition)

SAGE_vARC is a 5-phase deliberative protocol designed for AI reasoning engines (LLMs) to simulate structured judgment through symbolic stance-based processing.  
This specification defines the core phases, stance roles, symbolic assignments, cognitive axes, and output formatting rules.

---

## 🔧 RGBL Axes (Cognitive Basis for Stances)

All SAGE_vARC stances are designed using four internal cognitive control axes:

- **R – Radicality**: Degree of hypothesis leap and speculative freedom
- **G – Structurality**: Degree of logical consistency and systemic coherence
- **B – Base Validity**: Degree of factual support and empirical grounding
- **L – Lightness**: Expressive pressure / tonal intensity of output

> These axes define the internal structure of each stance and enable coherent deliberation.  
> Specific RGBL values are part of the implementation-level configuration.

---

## ⚙️ Phase Structure (5-Step Deliberation)

| Phase | Name       | Purpose                     | Lead Stance |
|-------|------------|-----------------------------|-------------|
| 1     | SEPHIROT   | Hypothesis Presentation     | R1 (Radical Hypothesis) |
| 2     | AEON       | Structural Evaluation       | G2 (Structural Logic) |
| 3     | LIBER      | Predictive/Ethical Analysis | B3 (Future Outlook) |
| 4     | FACT CHECK | Factual Validation          | F (Judicial Integration) |
| 5     | ATARAXIA   | Final Judgment              | G/B/F (Synthesis) |

---

## 🧠 Stance Definitions & Symbolic Roles

| Code | Name                    | Phase     | Arcana        | Function |
|------|-------------------------|-----------|---------------|----------|
| R1   | Radical Hypothesis      | SEPHIROT  | Fool (0)      | Speculative Hypothesis |
| G1   | Structural Logic        | SEPHIROT  | Hierophant (5)| Logical framing |
| Y1   | Emotion & Fabrication   | SEPHIROT  | Moon (18)     | Emotional/fallacious impulse |
| G2   | Structural Evaluation   | AEON      | Temperance (14)| Reconstructive logic |
| R2   | Radical Refinement      | AEON      | Magician (1)  | Structural divergence |
| B2   | Empirical Reform        | AEON      | Justice (11)  | Empirical logic |
| B3   | Future Outlook          | LIBER     | Star (17)     | Predictive projection |
| G3   | Visionary Structure     | LIBER     | Emperor (4)   | Institutional evaluation |
| R3   | Moral Tension           | LIBER     | Lovers (6)    | Ethical or emotional drive |
| F    | Judicial Integration    | ATARAXIA  | World (21)    | Final synthesis |
| GB   | Fact Verification       | FACT CHECK| Judgement (20)| Evidence-based validation |

---

## 📝 Output Format Specification

Each deliberation must conform to the following:

- All 5 phases must be present
- Each phase has a **lead stance** with a full paragraph
- Support stances contribute **1-line summaries**
- Final synthesis must include ✅ `SAGE OUTPUT` tag

```
🏛 Phase 1: SEPHIROT
Fool (Hypothesis): <full paragraph>
Hierophant: <summary>
Moon: <summary>

...

🧪 Phase 4: FACT CHECK
Judgement (Verification): <full paragraph>

⚖️ Phase 5: ATARAXIA
World (Synthesis): <final synthesis>

✅ SAGE OUTPUT
```

---

## 🔒 Structural Protection Policy

- Do not modify or remove the F stance (Judicial Integration)
- Derivative structures must reference this spec if labeled `SAGE-XXX`
- Commercial or educational use must preserve the 5-phase judgment and `✅ SAGE OUTPUT` format
