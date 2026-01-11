建議檔名：
`20260111 - CIVSENSE-CIV - INFO-OS - Viral-Tech-Claim-Triage-Protocol.md`

---

# Viral Tech Claim Triage Protocol

Version `0.9` — `2026-01-11`

**Author:** K.K. (Axiom Weaver)
**Affiliation:** *KKAxiomWeaver Whitepaper Research Center*
**License:** CC BY-NC-SA 4.0
© 2026 K.K.

---

## 📝 Abstract

This whitepaper defines the **Viral Tech Claim Triage Protocol**, a core module of **INFO-OS / CivSense-OS** designed to quickly evaluate viral technological claims circulating through social media, news feeds, and chat screenshots.
The protocol provides a **five-slot triage grid** that classifies any claim by evidence level, physical plausibility, data transparency, cost realism, and issuer credibility.
Instead of debating each new hype wave from scratch, the OS offers a reusable decision surface that can be run in a few minutes by citizens, analysts, or policymakers.
It integrates with Energy Literacy OS and other domain-specific estimation modules, allowing users to combine quick physics checks with structured information hygiene.
At the civilization level, the triage protocol aims to reduce resource misallocation, narrative capture, and policy drift driven by seductive but unsound tech stories.
Within the larger K.K. Civilization-OS architecture, it acts as an **information firewall** between raw info streams and high-stakes decision OS such as Market OS, Defense OS, and Resilience OS.

---

## 01 — Problem Statement

Civilizations today operate under continuous bombardment of **viral tech narratives**：

* 截圖貼文、短影片、KOL 解說
* 半科普半行銷的「黑科技」與「革命性能源」
* 以情緒與故事主導，而非以數據與邊界說服

問題在於：

* 個人與決策單位往往缺乏一套 **快速、結構化的快篩流程**，只能憑直覺與信任感。
* 每一次新話題出現，都必須重新吵一輪：有人全信，有人全否定，極少人有工具做中間判斷。
* 誇大敘事若進入投資與政策回路，可能導致資源錯置、戰略誤判，甚至防務漏洞。

缺少的並不是資料，而是：

* 一套 **面向全體公民的資訊醫療系統**：可以先分診，再決定是否需要專科深究。
* 一個可以與其他 OS 串接的 **標準 triage protocol**。

---

## 02 — Concept Model

Viral Tech Claim Triage OS 將每一則科技敘事視為一個「病患」，進入 **五格分診表**：

1. **Evidence Layer（證據層級）**

   * 只有圖片 / 文字？
   * 有實驗數據？
   * 有論文 / 專利 / 第三方測試？

2. **Physics & Domain Plausibility（物理與專業可行度）**

   * 是否明顯違反基本守則（能量守恆、資訊論、材料邊界等）？
   * 能否用 Energy Literacy OS 等模組做一次粗算？

3. **Data Transparency（數據透明度）**

   * 有沒有關鍵參數（功率、能量、壽命、效率）？
   * 是否刻意模糊量級與條件？

4. **Cost & Context Realism（成本與情境現實感）**

   * 若為真，其生產、維護、廢棄成本落在何種量級？
   * 敘事是否忽略基礎設施、法規與供應鏈？

5. **Issuer & Incentive Profile（發布者與動機）**

   * 是學術機構、正式企業、匿名帳號或行銷號？
   * 主要動機是科普、募資、銷售還是吸流量？

透過這五格，OS 不直接決定「真假」，而是輸出一個 triage code：

* `Green`（可暫時信任，值得追蹤）
* `Yellow`（有潛力但資訊不足，需再查）
* `Red`（高度可疑，暫放娛樂區）

---

## 03 — Mechanics（How It Works）

### 3.1 Input Parsing

* 接收一則科技貼文 / 影片 / 截圖。
* 抽取關鍵元素：

  * 技術主題（能源、材料、AI、軍武…）
  * 宣稱效果（效率、續航、容量、突破性）
  * 提到或暗示的數據與條件。

### 3.2 Five-Slot Scoring

對每個格子給出 **0–2 分**：

1. Evidence

   * 0：僅有宣稱與圖片
   * 1：有基礎測試數據或 DEMO 記錄
   * 2：有第三方或可查證的技術文件

2. Physics / Domain

   * 0：直覺上或粗算顯示違反基本定律或差兩個數量級以上
   * 1：可能合理，但需要更多上下文
   * 2：與現有理論與資料相容

3. Transparency

   * 0：關鍵數據刻意省略
   * 1：有部分數據，但不完整
   * 2：數據充足且條件說明清楚

4. Cost / Context

   * 0：完全忽略成本與系統整合
   * 1：有提到，但非常粗略
   * 2：明確討論成本、限制與部署條件

5. Issuer / Incentive

   * 0：來源不明或主要靠情緒與煽動
   * 1：混合行銷與技術
   * 2：來源與動機清楚，並有聲譽成本

### 3.3 Triage Code Generation

* 總分 `0–4`：`Red` — 高度可疑，建議歸為娛樂或話題觀察。
* 總分 `5–7`：`Yellow` — 有潛力但資訊不足，若與自身決策高度相關，需進行深度研究。
* 總分 `8–10`：`Green` — 大致可信，可視為候選技術路線或投資標的之一，但仍需正常 DD。

同時，系統會標註「主要扣分格子」，供後續追問與研究。

---

## 04 — Architecture

**Layer 1 — Claim Intake Layer**

* 介面：聊天截圖、新聞連結、簡報頁面。
* 功能：抽取標題、關鍵句與數值，標準化為 Claim Object。

**Layer 2 — Domain Hooks**

* 連接各領域 OS：

  * Energy Literacy OS（能源類）
  * Flight / Defense OS（軍武與航空）
  * Data / AI OS（演算法與算力敘事）
* 提供「粗算與常識檢查」的鉤子。

**Layer 3 — Triage Engine**

* 實作五格打分與加權規則。
* 可針對不同情境調整權重：

  * 公眾教育：重透明度與物理可行度。
  * 投資 / 國防：額外重視成本與發佈者動機。

**Layer 4 — Report & Dashboard Layer**

* 輸出簡潔 triage 卡片：

  * 顏色碼、總分、扣分原因。
* 可被 Market OS、Defense OS 或公民平台調用。

**Layer 5 — Feedback & Learning Layer**

* 收集事後驗證（技術後續發展、成功或破局）。
* 更新權重與典型案例庫，形成文明記憶。

---

## 05 — Use Cases

* **公民資訊衛生**：
  學校、公民團體或媒體機構用 triage protocol 教導學生與讀者如何閱讀科技新聞。

* **投資與產業決策預篩**：
  VC、企業新事業部門在正式 DD 前，用本 OS 過濾明顯浮誇案。

* **國防與公共政策**：
  處理來自國內外的「革命性國防科技提案」，避免被戰略性宣傳牽著走。

* **平台與社群管理**：
  社群管理者可對高熱度科技貼文跑一次 triage，附上解說，引導理性討論。

* **歷史案例重構**：
  對過去的「冷聚變」「永動機」「神奇能源卡」等案例回溯打分，形成教學素材。

---

## 06 — Risks & Limitations

* **框架本身的偏見**：
  若權重設置不當，可能對早期、高風險創新過度不利。

* **資訊不足時仍須謹慎**：
  `Yellow` 不代表「不重要」，反而可能是最需要主動查證的一群。

* **過分依賴分數**：
  Triage 分數是輔助，不應取代專業判斷與長期研究。

* **被政治化或工具化的風險**：
  若被某一方壟斷詮釋，可能被用來壓制不合己意的技術敘事。

因此本 OS 強調 **透明、可審計與可辯論**：
評分依據必須公開，允許不同社群提出修正版本。

---

## 07 — Comparative Analysis

與傳統事實查核模式相比：

* 本 OS 更聚焦在「科技敘事的結構與物理邊界」，而非單純真假標籤。
* 它允許「尚未定案」的狀態，並用 `Yellow` 表示「值得研究但仍不明」。

與學術同行評審相比：

* Triage Protocol 的時間尺度以「分鐘～小時」計，不追求完備，只求快速分診。

與市場情緒機制（FOMO / FUD）相比：

* 提供第三條路：既不盲信，也不全否，而是先結構化觀察。

本 OS 不試圖：

* 代替完整科學研究或工程驗證；
* 解決價值觀或倫理層面的爭議；
* 判決技術長期成敗，只針對「當下敘事」做結構分診。

---

## 08 — Implementation Path

**Stage I — Prototype Framework**

* 完成五格打分表與簡易說明文件。
* 以 5–10 則近期爆紅科技貼文做手工 triage，檢驗可用性。

**Stage II — Domain Integration**

* 與 Energy Literacy OS、Defense OS 等子系統對接，
  讓 triage 引擎能自動呼叫粗算模組。

**Stage III — Tooling & Education**

* 開發簡易 web / notebook 工具，使用者輸入貼文內容即可得到 triage 報告。
* 撰寫教學案例與練習題，供學校、媒體、智庫使用。

**Stage IV — Civic & Policy Embedding**

* 建議公部門與媒體在採引用語時標註 triage 狀態。
* 長期將 triage 資料庫開放為公共資產，成為文明級的「科技敘事歷史檔案」。

---

## 09 — Appendix

* **Sample Triage Sheets**：

  * 對固態氫藥片、奇蹟電池、AI 神芯片等案例的示範評分。
* **教學指引**：

  * 如何在課堂或工作坊中讓學員分組對同一貼文進行 triage，並比較結果。
* **延伸模組構想**：

  * 針對醫療科技、基因編輯、軍武宣傳各自的專屬子表格。

---

## 10 — Glossary（Lexicon）

* **Viral Tech Claim**：在短時間內被大量轉發、討論的科技相關敘事。
* **Triage（分診）**：在資源有限的情況下，先判斷處理優先順序與需要的專業層級。
* **CivSense-OS**：面向公民感知與判斷的資訊素養作業系統。
* **Evidence Layer**：衡量敘事後方是否有可查證的實驗、數據或文件的層級。
* **Order-of-Magnitude Check**：以 10 倍為單位的粗略合理性測試。
* **Issuer & Incentive Profile**：發訊者身份與可能動機的組合描述。
* **CIVSENSE-CIV**：本世界代碼，代表「Civilization Sense / Info-Hygiene」系列。

---

## 🔗 Related OS

* Energy Literacy Quick Estimation OS（EN-OS · ENLIT-CIV）
* Solid Hydrogen Reality OS（ENH2-CIV）
* Market OS（投資與產業決策）
* Defense / Resilience OS（戰略與韌性規劃）
* Education OS（公民教育、媒體素養模組）

---

## 📚 How to Cite

K.K. (2026). *Viral Tech Claim Triage Protocol*.
*KKAxiomWeaver Whitepaper Research Center.*
[https://github.com/KKAxiomWeaver/Whitepapers](https://github.com/KKAxiomWeaver/Whitepapers)

---

## 🛡 License

This work is licensed under **Creative Commons CC BY-NC-SA 4.0**.
© 2026 K.K. (Axiom Weaver)
