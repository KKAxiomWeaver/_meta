# K.K. Whitengineering • Multi-domain OS • Axiom Weaver

This repository contains all whitepapers authored by **K.K. (Axiom Weaver)**.
No folders are used; papers are organized through **naming conventions + Master Index**.

### Repository Structure Strategy

* All files stored at root (`/`)
* Naming: `YYYY-MMDD - <WorldCode> - <OS> - <Title>.md`
* `MASTER_INDEX.md` provides cross-domain cross-references
* `_meta/` stores templates, index, version map, badges

---

**📂 建議檔名（Filename）**
`2026-0111 - WCHS - STRAT - Island Price Table (IPT).md`

---

# Island Price Table OS

## WCHS-02 • Island Price Table (IPT) — Structural Cost Distortion in High Survival Worlds

Version `0.9` — `2026-01-11`

**Author:** K.K. (Axiom Weaver)
**Affiliation:** *KKAxiomWeaver Whitepaper Research Center*
**License:** CC BY-NC-SA 4.0
© 2026 K.K.

---

## 📝 Abstract

This whitepaper defines the **Island Price Table (IPT)**—a structural model that explains why, in island-class environments, **the same product or capability costs systematically more** than in continental or low-risk regions, even when wages are lower.

IPT is a sub-OS under **WCHS（High Survival Coefficient OS）** focusing on the **price layer of reality**:
輸入端是島嶼的地理體量、物流結構、風險係數與市場規模，輸出端是：

* 同型號車輛 → 價格可達他國 **2×**
* 基本住宅（2LDK）→ 需約 **40 年中位數所得** 才能負擔
* 國內外商品 → 以「小市場 + 高風險溢價」方式定價
* 醫療保險、能源、租金 → 長期位於全球高段

IPT 不把這些現象當成「個案」或「商人黑心」，而是視為：

> **島嶼世界在高生存係數條件下，必然出現的「結構性價目表」**。

This OS provides concepts, mechanics, and architecture to compute and visualize how island-class worlds systematically overpay for **the same civilization modules**, and how this overpayment feeds back into HSC, industrial viability, and social fatigue.

---

## 01 — Problem Statement

### 1.1 現有敘事的盲點

Island societies frequently face:

* **Global comparison 羞辱感**：「你們 GDP 不低、也很先進，怎麼還一直喊累？」
* **Local體感的失語**：「同樣一台車、同樣一個品牌，我這邊就是貴一截，薪水還比較低。」

Existing tools like PPP, CPI, average wage, or generic “cost-of-living” indices fail to capture：

* **Same-model price distortion**（同款商品、不同世界價目表）
* **Small-market premium + risk premium 疊加效果**
* **Logistics and harassment-induced overhead**（海運、備援、保險、風險折價）
* **Structural asymmetry**：島嶼用全球價買東西，卻用本地薪資賣時間。

### 1.2 傳統分析的錯誤假設

1. **Assumption：市場競爭會自動壓低價格**
   → 在小島嶼、雙重風險環境中，**競爭不足 + 固定成本難分攤**，價格反而被抬高。

2. **Assumption：匯率與關稅是主要差異來源**
   → 實務上更致命的是：

   * “到達成本”（到得了、存得住、修得起）
   * 供應鍊中對島嶼市場的「利潤補償」。

3. **Assumption：島嶼可以「用效率彌補一切」**
   → 當 IPT 結構固定在不利區間，效率再高，也只能減慢失血速度。

### 1.3 IPT 想解決什麼？

* 為「為何我們這邊永遠比較貴」提供**工程化說法**，而不是情緒化對罵。
* 建立一張可計算、可比較的 **Island Price Table**，讓：

  * 傳產、服務業、家庭都能看懂自己在付什麼「島嶼稅」。
* 作為 WCHS / NodeRes / CivMesh OS 的底層價目表模組，讓任何世界／島嶼世界觀可以具象化成本。

---

## 02 — Concept Model

### 2.1 What is the Island Price Table (IPT)?

**IPT = 一個世界對「同一個文明模組」的價格映射表**。

給定一個標準化文明模組（例如：

* 一台 1.6L 家用車、
* 一間 2LDK 公寓、
* 一套標準醫療保險、
* 一套弱電工具組、
* 一個基礎伺服器機櫃），

IPT 告訴你在：

* 大陸國家 A
* 歐洲國家 B
* 島嶼國家 C

**這個模組的實際「總生活成本」是多少**，包含：

* 買入價格
* 持有與維修成本
* 風險與保險成本
* 不可見的「防不中斷成本」份額

---

### 2.2 IPT 的核心概念

We define IPT as：

> **IPT(World, Module) = BasePrice · L · S · R · H**

Where：

* **BasePrice**：全球平均出廠價 / 批發價。
* **L（Logistics factor）**：to-get-there factor，與距離、運具、港口能力、回程貨量有關。
* **S（Scale factor）**：market size / demand concentration factor，小市場 ⇒ S > 1。
* **R（Risk factor）**：政治風險、匯率、信用、戰略風險等溢價。
* **H（Harassment / Hazard factor）**：灰色地帶騷擾、可能制裁、保險與備援成本。

在島嶼高 HSC 世界中：

* L 高（島嶼、遠端）
* S 高（市場小、難分攤）
* R 中〜高（體量小、易受衝擊）
* H 高（戰機、軍艦、海纜）

=> **IPT 被整體拉高**，即便 BasePrice 相同。

---

### 2.3 為何 IPT 在 WCHS 中是關鍵模組？

In **High Survival Coefficient OS**：

* HSC 描述「活著有多難」；
* IPT 描述「每一個文明模組的價格表」。

沒有 IPT，你只能說「貴」；
有 IPT，你可以比較：

* 同一台車在「歐洲平原世界線」 vs 「島嶼高 HSC 世界線」的完整成本差距；
* 同樣薪資結構下，不同 IPT 對家庭決策與企業存活的壓力差異。

---

## 03 — Mechanics（How It Works）

### 3.1 IPT 因子展開

#### Logistics factor L

L 可以分解為：

* L₁：距離與運具結構（海運/空運比例、頻率）
* L₂：倉儲與港口費
* L₃：回程載貨率（空載越多 L 越大）

L 越高 → 「到達成本」越高。

---

#### Scale factor S

S reflects inability to spread fixed costs：

* 模組開發成本 / 設備 amortization / 認證費用
* 在小市場可售數量低 → 單件攤提成本高

小島嶼常為「規格已做，但銷量太小，必須多加一筆」的地方。

---

#### Risk factor R

R 反映：

* 匯率波動
* 信用風險
* 法規不確定性
* 政治與貿易關係

Island states under strategic pressure may see R > 1 even if技術/制度很好，只因「被夾在大國之間」。

---

#### Harassment / Hazard factor H

H captures：

* 空中/海上騷擾（飛機、軍艦）
* 灰色地帶行動引發的保險與備援成本
* 海底電纜被切斷的頻率與預期損失

對企業：

* 航線須改道
* 保費上升
* 需建第二連線、用多家供應商

全部變成單價增加的 H。

---

### 3.2 Household IPT Example

For a **2LDK apartment**：

> IPT_house = BasePrice_house · L · S · R · H

在某歐洲內地城市：

* L ≈ 1 （陸運發達）
* S ≈ 1 （市場大）
* R ≈ 1
* H ≈ 1

在島嶼高 HSC 世界線：

* L > 1 （建材、設備多仰賴進口）
* S > 1 （小市場建案，成本難攤）
* R ≥ 1
* H > 1 （地緣風險、資本猶豫）

最後體感結果是：

* 面積較小（15–20 坪）
* 總價卻逼近 **40 年中位數所得**

而這不是「開發商貪婪」這麼簡單，而是 IPT 的合成結果。

---

### 3.3 Automotive IPT Example

> IPT_car = BasePrice_car · L · S · R · H

在大陸：

* L 稍高、S 低、R 適中、H 低 → IPT 基本接近 BasePrice + 稍微溢價。

在島嶼：

* L 中〜高（整車 / CKD 進口）
* S 高（市場小、型號多）
* R 中〜高
* H 高（地緣風險、制裁風險保費）

結果就是：

> 同型號車在島嶼 ≈ 其他國家售價的 1.5～2 倍

同時，島嶼薪資往往 **低於這些參考市場**。

→ 車從「生活工具」變成「長期財務負擔」，從 IPT 角度完全合理，但對個體極度不友善。

---

## 04 — Architecture

### 4.1 IPT OS Modules

1. **IPT-Core**

   * 定義 IPT(World, Module) 計算公式
   * 實作 L, S, R, H 因子的子模型

2. **Module Catalog**

   * 定義標準化文明模組：

     * Housing 2LDK, 3LDK …
     * Small Car, EV, Scooter
     * Basic Insurance Pack
     * Entry-level Server Rack / 工具組

3. **World Profiles**

   * 為不同國家／世界線建立 L, S, R, H 檔案

4. **Interpreter / Visualizer**

   * 把 IPT 結果轉為：

     * 生涯工作年數負擔
     * 每月現金流壓力
     * 產業可行性評估

---

### 4.2 Integration with HSC OS

IPT feeds directly into **HSC’s R（Raw Material & Goods Cost）**, and indirectly into：

* H（Habitat Cost Intensity）
* M（Mobility Cost & Necessity）
* C（Healthcare）

Thus:

> **HSC(World) = f(IPT_house, IPT_car, IPT_health, …)**

Without IPT, HSC 的「貴」是抽象的；
With IPT, HSC 可以說清楚：

> 哪些模組把這個世界的生存係數拉上去。

---

## 05 — Use Cases

1. **Island Policy Simulation**

   * 比較不同政策（稅制、補貼、物流投資）對 IPT 因子的長期影響。

2. **企業市場選擇與定價**

   * 決定產品在島嶼上市與否、用何種規格與價位進入。

3. **傳產轉型評估**

   * 判斷哪些本地加工 / 製造是「IPT 不可能撐」的（直接退出），
   * 哪些高值化 / 模組化路線是「IPT 還撐得起」的。

4. **家庭理財與風險教育**

   * 用 IPT 解釋：

     * 為何買車等於扛 5 年薪資風險
     * 為何買房等於押 40 年未來現金流

5. **世界觀設計與科幻 / 世界線建構**

   * 在 K.K. Universe 中，

     * 不同星球殖民地、太空站、深空前哨可以用 IPT 定義生活成本的梯度。

---

## 06 — Risks & Limitations

* **Data Quality & Transparency**

  * 很多 IPT 因子難取得（尤其是風險、保險、騷擾相關成本）。

* **Model Oversimplification**

  * 真實世界的租稅、補貼、政治博弈極為複雜，IPT 不可能全部捕捉。

* **政治爭議**

  * IPT 可能被讀成「指責特定國家」或「抱怨世界不公平」，
    而不是本來意圖的「結構分析工具」。

* **忽略非價格因素**

  * 文化、社會支持、心理韌性也會影響生存體感，但不在 IPT 直接建模範圍。

---

## 07 — Comparative Analysis

### vs 傳統 Cost-of-Living Index

* Cost-of-living index：

  * 以消費籃子平均價格比較，
  * 沒有拆 L/S/R/H 的結構來源。

* IPT：

  * 明確拆因子，並與 HSC、風險與地緣條件連結。

---

### vs PPP（Purchasing Power Parity）

PPP 告訴你「一樣的錢在當地能買多少」，
IPT 告訴你「**同一個文明模組，在不同世界需付多少結構成本**」。

PPP 是側重貨幣購買力，
IPT 是描述**物理與風險結構**。

---

## 08 — Implementation Path

### Stage I — IPT Prototype

* 選 3–5 個代表世界：

  * 島嶼高 HSC
  * 歐陸中 HSC
  * 大陸低 HSC
* 選 5–10 個文明模組：房、車、醫療保險、工具、伺服器。
* 實作簡化版 L/S/R/H 因子與 IPT 計算。

---

### Stage II — Integration with HSC Dashboard

* 將 IPT 結果直接嵌入 HSC 介面：

  * 顯示「生存係數」以及其背後的核心價目表。

---

### Stage III — Policy & Industry Tooling

* 為 think tank / 產業協會提供簡易工具：

  * 可以玩「如果 L 降低（新港口）會怎樣」
  * 「如果 H 降低（騷擾減少）會怎樣」

---

### Stage IV — Civilization-OS Library Integration

* 在 K.K. GitHub 白皮庫中，

  * IPT 作為其他世界線／星球設計的通用模組。

---

## 09 — Appendix

### A. Example Numerical Toy Model

For a specific car model：

* BasePrice = 1.0（normalized）
* Mainland：L=1.05, S=1.0, R=1.0, H=1.0 → IPT ≈ 1.05
* Island：L=1.15, S=1.2, R=1.1, H=1.2 → IPT ≈ 1.82

→ **同一台車，島嶼價格 ≈ 1.7–1.8 倍**，
在真實世界常被體感為「差不多兩倍」。

---

## 10 — Glossary（Lexicon）

* **IPT（Island Price Table）**
  Structural mapping from world & module → effective price.

* **BasePrice**
  Factory / global baseline price before world-specific distortion.

* **L Factor（Logistics）**
  To-get-there cost multiplier.

* **S Factor（Scale）**
  Market size / demand concentration multiplier.

* **R Factor（Risk）**
  Political / financial / regulatory risk multiplier.

* **H Factor（Harassment / Hazard）**
  Harassment, gray-zone, sabotage, and related insurance / redundancy burdens.

* **Island Tax（Island Premium）**
  Colloquial term for IPT/BasePrice > 1 的溢價感受。

---

## 🔗 Related OS

* **WCHS-01 — High Survival Coefficient Framework**
* **NodeRes OS**（節點韌性）
* **CivMesh OS**（網格式文明架構）
* **Habitat OS**（棲地與住房設計）
* **Energy OS**（能源結構）
* **GeoRisk / Defense OS**（騷擾與風險建模）

---

## 📚 How to Cite

K.K. (2026). *Island Price Table OS — WCHS-02: Structural Cost Distortion in High Survival Worlds*.
*KKAxiomWeaver Whitepaper Research Center.*
[https://github.com/KKAxiomWeaver/Whitepapers](https://github.com/KKAxiomWeaver/Whitepapers)

---

## 🛡 License

This work is licensed under **Creative Commons CC BY-NC-SA 4.0**.
© 2026 K.K. (Axiom Weaver)
