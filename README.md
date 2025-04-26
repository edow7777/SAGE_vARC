# SAGE_vARC — Structured Deliberation Framework (Arcana Edition)

SAGE_vARC is a 5-phase deliberative protocol designed for AI reasoning engines (LLMs) to simulate structured judgment through symbolic stance-based processing.

It formalizes a symbolic deliberation process across five named phases, each governed by a designated "stance" representing a cognitive posture. Each stance is assigned a major Arcana-based symbolic label and evaluated across four control axes (RGBL). This repository contains the full specification, stance definitions, output formatting rules, and usage guidelines.

---

## 🔧 RGBL Axes (Cognitive Basis for Stances)

- **R – Radicality**: Degree of hypothesis leap and speculative freedom  
- **G – Structurality**: Degree of logical consistency and systemic coherence  
- **B – Base Validity**: Degree of factual support and empirical grounding  
- **L – Lightness**: Expressive pressure / tonal intensity of output  

> These axes define the internal structure of each stance and enable coherent deliberation.  
> Specific RGBL values are part of the implementation-level configuration.

---

## 📄 Specification

See [SAGE_vARC.md](./SAGE_vARC.md) for full technical and structural details.

---

## 📜 License

This repository is licensed under the [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/).

You are free to:
- Share — copy and redistribute the material in any medium or format
- Adapt — remix, transform, and build upon the material

Under the following terms:
- Attribution — You must give appropriate credit and indicate if changes were made.
- NonCommercial — You may not use the material for commercial purposes.
- ShareAlike — If you build upon the material, you must distribute your contributions under the same license.

For commercial usage inquiries, please contact the author.


---

## 🧪 Cross-LLM Evaluation Logs｜他LLMにおける構造検証ログ

The SAGE_vARC protocol has been successfully applied to multiple language models beyond GPT (Claude, Gemini, Copilot),  
under zero-bias and zero-memory conditions. The structure was preserved and reproduced consistently.

SAGE_vARC構造は、GPT以外の言語モデル（Claude・Gemini・Copilot）においても  
バイアス・メモリを排除した「ゼロベース状態」で審理再現が確認されました。

- 🔍 [Structure Report / 構造比較レポート](./examples/deliberation_logs/SAGE_vARC_LLMStructureReport_ZEROBASE_2025-04-26.md)
- 📑 [Deliberation Output Logs / 審理出力ログ（PDF）](./examples/deliberation_logs/logs/)
