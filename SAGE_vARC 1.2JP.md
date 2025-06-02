# SAGE\_vARC 1.2 — Structured Deliberation Framework (Arcana Edition)

**Version:** 1.2 (2024-06)
**Author:** edow
**Repository:** [GitHub](https://github.com/edow7777/SAGE_vARC)
**Articles:** [Note](https://note.com/wode/m/m8e388d7ddaaa)

---

## 概要 / Overview

SAGE\_vARCは、**熟議型AI議会**（多スタンス多層審理＋履歴証跡＋厳密バリデーション）を実現するためのプロトコル体系です。
本仕様は「構え（スタンス）定義」「厳格な進行・審理プロセス」「全履歴管理」「自動エラー検知・再審理」「ファイル連携・バージョン同期」など、再現性・信頼性を最大化する運用設計を備えています。

---

## 構成ファイル・参照先

* `sage_members.txt`：全構え（stance）／RGBL値／アルカナ定義（**マスターテーブル、バージョン管理**）
* `SAGE_body.txt`：概念設計・運用思想・出力制約・バリデーション基準
* `sage_flow_v1.1.txt`：審理手順・分割規定・履歴記録・エラー処理・進行テンプレート
* `SAGE指示README.txt`：運用指示・応答基準・ラベル定義・公式出力例

全ファイルは**進行ごとに再読込・バージョン同期・定義値照合**が必須。

---

## 審理プロセス（クロスジャッジ・多層履歴管理）

### 1. 段階構成と担当（クロスジャッジ方式）

| 段階         | 英語名称     | 議長スタンス | 補助スタンス         | 判定・分岐         |
| ---------- | -------- | ------ | -------------- | ------------- |
| 第一院        | SEPHIROT | 愚者（R1） | 教皇（G1）、月（Y1）   | 判定：第二院（AEON）  |
| 第二院        | AEON     | 節制（G2） | 魔術師（R2）、正義（B2） | 判定：第三院（LIBER） |
| 第三院        | LIBER    | 星（B3）  | 皇帝（G3）、恋人（R3）  | 判定：FACT CHECK |
| FACT CHECK | 審判（GB）   | 審判     | ー              | 判定：ATARAXIA   |
| ATARAXIA統合 | 世界（F）    | 世界     | ー              | 統合・公式出力       |

* 各段階で**議長スタンスがfull output、補助スタンスがsummary**
* **判定は次段階議長が行い、否決時は必ず新案（B, C...）が分岐・履歴記録される**
* ５段階すべてが揃い、\*\*全定義値・履歴が適合した時のみ「✅ SAGE OUTPUT」\*\*を付与

---

## ファイル連携・バリデーション・履歴記録

* **進行ごとに「sage\_members.txt」を再読込し、スタンス・RGBL値・アルカナの照合を行う**
* 逸脱・未登録値があれば即エラー（⚠️）、参考出力のみ、再審理は１回限り
* **全出力にファイルバージョン・進行ログ・再審理回数を記録**
* 「SAGE Division Progress (n/N)」「SAGE Deliberation Complete」など進行ラベル付与

---

## エラー／逸脱時の挙動

* 進行逸脱・定義不一致・フェーズ欠損等は「⚠️ Error」明示
* **再審理１回限り、２回目失敗で「SAGE出力不可」＆参考出力のみ**
* 全エラー・経緯は履歴に明記（公式出力にはカウントせず）

---

## 構え／スタンス定義（参照：sage\_members.txt抜粋例）

| コード | 日本語名／英語名            | フェーズ     | アルカナ          | 機能概要         | RGBL値（例）                    |
| --- | ------------------- | -------- | ------------- | ------------ | --------------------------- |
| R1  | Radical Hypothesis  | SEPHIROT | Fool(0)       | 直観的仮説提示      | R=0.90,G=0.20,B=0.10,L=0.70 |
| G1  | Structural Logic    | SEPHIROT | Hierophant(5) | 論理構造評価       | ...                         |
| Y1  | Emotion/Fabrication | SEPHIROT | Moon(18)      | 感情的/陰謀論的逸脱提示 | ...                         |
| ... | ...                 | ...      | ...           | ...          | ...                         |

**全スタンス詳細・RGBL値は「sage\_members.txt」最新版を参照**

---

## 出力形式サンプル（公式出力例）

```
🏛 第一院：SEPHIROT
愚者（Radical Hypothesis）：＜full content＞
教皇（Structural Logic）：＜summary＞
月（Emotion/Fabrication）：＜summary＞
・【AEON議長による承認/否決判定・理由】→否決時は新案（B）発生・議論経緯も記録

🏛 第二院：AEON
節制（Structural Logic）：＜full content＞
魔術師（Leap Adjustment）：＜summary＞
正義（Empirical Refutation）：＜summary＞
・【LIBER議長による承認/否決判定・理由】→否決時は新案（C）発生

🏛 第三院：LIBER
星（Forecast Estimation）：＜full content＞
皇帝（Visionary Evaluation）：＜summary＞
恋人（Intentional Intervention）：＜summary＞
・【FACT CHECK議長による承認/否決判定・理由】

🧪 FACT CHECK（審判）
審判（Fact Verification）：＜full content＞
（感情・陰謀論等の逸脱検出／再審理経緯も必ず記録）

⚖️ ATARAXIA（統合）
世界（統合判断）：＜final synthesis／採択理由／他案比較／議論履歴＞

✅ SAGE OUTPUT（全フロー・定義適合時のみ付記）
```

---

## エラー発生例・参考出力

* 例：「定義テーブル不一致」「フェーズ欠損」「未登録スタンス使用」等は即エラー
* エラー時は「Unable to produce SAGE output」「理由」「参考出力」を必ず併記

---

## 将来拡張・運用課題

* 定義テーブルの自動保護・改ざん検知・バージョン証跡管理
* 審理分割アルゴリズム自動化
* DB/APIによる履歴記録・真正性保証の強化

---

## 用語・略語定義

* **SAGE\_vARC**：Structured AI Governance Engine, Arcana Edition
* **RGBL**：Radicality/Structurality/Base Validity/Lightness
* **Arcana**：タロット的象徴（議会内スタンス記号）
* **Chamber**：各審理院（SEPHIROT, AEON, LIBER…）
* **Stance**：構え・審理観点
* **Division**：論点・進行分割単位
* **F**：Judicial Integration（統合判断。絶対削除不可）

---

## 参考ファイルリンク

* [sage\_members.txt](./docs/sage_members.txt) — スタンス／RGBL／アルカナ定義
* [SAGE\_body.txt](./docs/SAGE_body.txt) — 概念設計・運用思想
* [sage\_flow\_v1.1.txt](./docs/sage_flow_v1.1.txt) — 審理進行・エラー管理
* [SAGE指示README.txt](./docsSAGE指示README.txt) — 運用ガイド・出力例

---

**本READMEはSAGE\_vARC運用仕様1.2（2024-06）世代に準拠。全参照ファイル最新版でのみ公式運用が認められます。**
