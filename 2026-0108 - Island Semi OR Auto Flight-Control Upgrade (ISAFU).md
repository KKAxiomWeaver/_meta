# Island Semi/Auto Flight-Control Upgrade (ISAFU)

Version `1.0` — `2026-01-08`

**Author:** K.K. (Axiom Weaver)
**Affiliation:** *KKAxiomWeaver Whitepaper Research Center*
**License:** CC BY-NC-SA 4.0
© 2026 K.K.

---

## 📝 Abstract

This whitepaper proposes the **Island Semi/Auto Flight-Control Upgrade (ISAFU)**, a terrain- and micro-climate–aware semi/automatic flight-control layer for **mountainous island airspaces** (with Taiwan as the canonical reference).

現代戰機在工程本質上，依然接近「手排跑車」：
人類飛官需在毫秒級變化的 **高山地形＋亂流＋雲牆空域** 中，
以 600–900 ms 的生理反應鏈，對應 300–500 ms 甚至更短的安全修正窗口。

在這種結構下，試圖透過「菁英飛官訓練」去彌補人類神經系統與島嶼物理之間的時間落差，是一場 **定義錯誤的競賽**。

ISAFU 將問題重新定義為：

> 人類飛官決定「要不要進入這片空域」；
> 半自排／自排飛控 OS 決定「進去之後要怎麼不死」。

本白皮：

* 將 **峽谷風場、山脈幾何、小氣候亂流** 視為「島嶼物理 OS」的一部分；
* 定義一層可疊加於既有戰機上的 **半自排／自排飛控腦**（ISAFU），
  與既有 **AFDC（極限下降 AI）、Island Air Denial Doctrine（空拒學說）、Conic Defense Geometry（錐形偏折幾何）、Terrain-Induced Attrition System（TIAS）** 整合；
* 提出 0–3 四種操作模式（Monitor → Assist → Passive Override → Auto-Mode），
  讓戰機在指定高風險走廊中由系統接管姿態與安全包絡；
* 說明如何將 **高山島嶼空域** 打造成一個 **對本島友善、對外來敵機敵意、且會隨 sortie 數量持續進化的主場物理武器系統**。

在長期演化下，ISAFU／AFDC 與 TIAS 結合，將導致：

* 對本島飛官而言：同一片空域 **越飛越簡單**；
* 對外來飛官而言：永遠缺乏足夠實測資料，**持續處於適應不良狀態**。

本白皮將 ISAFU 正式化為一個 **國家級空防 OS 模組**，而非單純「安全加裝配備」。

---

## 01 — Problem Statement

### 01.1 結構性落差：手排戰機 vs 高山島嶼空域

傳統空戰假設：

* 空域相對開闊、地形起伏有限；
* 氣象變化時間尺度 **大於** 戰機操縱節奏；
* 飛行員有足夠時間完成 **OODA loop（Observe–Orient–Decide–Act）**。

在這些前提下，「手排戰機」是合理的：

* 飛行員直接操控姿態、下降率與能量；
* 安全系統主要在「大錯誤」時介入（如 GCAS）。

然而，以臺灣為代表的 **高山島嶼空域** 具有完全不同的結構特徵：

* **空間壓縮**：
  峽谷、斷層山脈、陡峭海岸線交疊，
  安全飛行走廊被壓縮在狹窄體積內。
* **時間壓縮**：
  峽谷風切、山谷亂流、白牆雲層等現象，
  以秒級甚至百毫秒級出現與消失，
  **安全修正窗口顯著短於人類完整反應鏈**。
* **認知負荷極限化**：
  外來飛官缺乏對地形與小氣候的身體記憶，
  在高負荷任務中被迫在陌生氣流場做高速判斷。
* **下降與山後機動成為致命瓶頸**：
  真正困難的不在於「飛得上去」，
  而是在複雜地形中 **安全地降回來、進出山後、重返掩蔽**。

在這樣的環境條件下，延續「手排戰機」邏輯，
意味著：

* 訓練成本與壓力長期偏高；
* 訓練期事故風險難以下降；
* 實戰運用必須保守，空域優勢無法發揮。

### 01.2 人類生理 vs 島嶼物理：錯誤的競賽項目

AFDC 系列白皮已指出：

* 人類視覺→辨識→判斷→操作之完整反應鏈
  約在 **600–900 ms** 區間；
* 特定山後下降與極限修正的安全窗口，
  可能落在 **300–500 ms** 甚至更短。

這代表存在一個 **結構性不等式**：

[
T_{\text{human_reaction}} > T_{\text{safe_correction_window}}
]

這種級別的落差，
**不是菁英化訓練可以解決的問題**。

真正的問題不是：

> 「飛官要多強？」

而是：

> 「飛控 OS 要如何與島嶼物理同步？」

如果國防政策持續把重點壓在：

* 補貼飛行時數、
* 提高淘汰率以尋找「超人飛官」、
* 或強調個人英雄主義，

將導致 **錯誤的資源投入方向**，
也讓高山島嶼空域的優勢無法被工程化使用。

---

## 02 — Concept Model

### 02.1 定義：Island Semi/Auto Flight-Control Upgrade（ISAFU）

**Island Semi/Auto Flight-Control Upgrade（ISAFU）** 被定義為：

> 一層可疊加於現役戰機之上的
> **島嶼空域專用半自排／自排飛控 OS**，
> 專責在特定高風險空域與機動模式中，
> 以 AI 輔助或全自動方式管理機體姿態與安全包絡，
> 將「不該給人類處理的高頻物理反應」
> 從飛官工作負荷中剝離。

ISAFU 的定位：

* **非** 取代人類飛行員；
* **非** 全域全時自駕；
* **是** 在「島嶼危險空域」中，
  將 **極短時間、高複雜度的姿態決策** 改由系統負責。

### 02.2 與 AFDC 的關係：OS vs 模組

* **AFDC（Autonomous Flight Descent Controller）**：
  專注於「極限下降段」的 AI 操控 ——
  像是戰機在最危險幾秒鐘內的「自動防撞大腦」。
* **ISAFU**：
  為更上層的 **作業系統（OS）**，
  將相同理念 **擴展到整個島嶼危險空域**：

  * 山後進出、
  * 峽谷穿越、
  * 貼山飛行、
  * 特定 Auto-Descent 走廊。

關係可視為：

[
\text{ISAFU} = \text{Island Flight-Control OS} \supset \text{AFDC (Extreme Descent Module)}
]

### 02.3 系統目標（System Goals）

1. **同步島嶼物理（Synchronize with Island Physics）**

   * 讓飛機控制迴路的頻率與 **地形＋小氣候** 的特徵頻率相容，
   * 避免人類神經系統在「物理上必敗」的頻段硬撐。

2. **分離「戰術決策」與「姿態維生」**

   * 人類：決定任務目標、進出空域時機、交戰／退出判斷；
   * 系統：在指定空域內，維持機體在 **安全能量與姿態包絡** 中。

3. **強化空拒學說的可執行性**

   * Island Air Denial Doctrine 的核心是「不搶空優、專注存活與拖時間」；
   * ISAFU 提供在複雜地形下「活得下來」的工程實作基礎。

---

## 03 — Mechanics（How It Works）

本章從工程角度說明 ISAFU 的內在運作：
自下而上分為 **感知（Sensing）→預測（Prediction）→決策（Decision）→控制（Control）**。

### 03.1 感知層（Sensing Layer）

1. **地形／障礙物資料庫**

   * 高解析 DEM（Digital Elevation Model）：

     * 山脈、峽谷、河谷、陡坡海岸線。
   * 人工結構：

     * 塔台、輸電線、橋梁、高層建物、防禦錐體等。

2. **氣象與小氣候資料**

   * 峽谷風場統計模型、
   * 熱對流區域與典型雲牆生成帶、
   * TIAS 所定義的 **「高風險氣流區」** 與季節性變化。

3. **機載感測器**

   * INS／IMU；
   * 雷達高度計；
   * 機載雷達回波；
   * 其他可用氣象探測模組。

### 03.2 預測層（Prediction Layer）

輸入：

* 當前姿態、速度、方向；
* 周邊地形、障礙物分布；
* 即時或近似的風場／亂流估計。

輸出：**未來 3–5 秒時間窗內的風險預估與安全帶建議**：

* 撞擊風險（地形／障礙物）；
* 失速風險（高仰角、高載重、低能量組合）；
* 過載風險；
* 能量耗盡風險（尤其在山後爬升段）。

同時給出：

* 建議下降高度帶；
* 安全姿態變化範圍；
* 預期亂流強度與風切風險。

### 03.3 決策層（Decision Layer）

根據預測層輸出與飛官設定之模式，
選擇 **不同介入等級**：

* **Monitor**：僅觀測，發出警示。
* **Assist**：在接近風險邊界時，輸出微調建議或輕度介入。
* **Passive Override**：

  * 當預測短期內存在高撞擊／失速風險，
  * 系統在有限軸向（如俯仰／下降率）強制修正。
* **Auto-Mode**：

  * 在特定「Auto-Descent／Hillside Mode 走廊」內，
  * 系統於路徑內全程管控姿態與下降曲線。

### 03.4 控制層（Control Layer）

將決策層輸出轉換為具體飛控命令：

* 微調俯仰率（pitch rate）、
* 滾轉率（roll rate）、
* 推力設定、
* 下降率／爬升率。

設計原則：

* 控制輸出需 **平滑、可預期**，避免與飛官操作產生對抗感；
* 必須保留 **Emergency Cutout（緊急斷開）** 機制，
  讓飛官在極端情況下能一鍵中止系統介入。

---

## 04 — Architecture

### 04.1 Layered View（分層架構視圖）

在更大一層的 **島嶼空防 OS** 中，可粗略分為：

* **Doctrine Layer**：Island Air Denial Doctrine（空拒學說）、作戰構想；
* **Geometry & Terrain OS Layer**：Conic Defense Geometry（CDG）、TIAS 等；
* **Flight-Control OS Layer**：本白皮之 ISAFU；
* **Module Layer**：AFDC（極限下降 AI 模組）、其他專用控制器；
* **Hardware Layer**：實際戰機平台與感測器。

ISAFU 居於 **Flight-Control OS Layer**：

* 向上：接收任務／空域模式（例如：啟用某 Auto-Descent Corridor）。
* 向下：調用 AFDC 等專用模組處理最危險幾秒鐘。

### 04.2 模組構成（Modules）

* **Terrain & Micro-climate Engine**

  * 對接 DEM 與 TIAS，生成地形＋小氣候風險地圖。

* **Risk Prediction Engine**

  * 以當前狀態與環境，預估 3–5 秒內各類風險。

* **Mode Manager**

  * 負責管理 Monitor／Assist／Passive Override／Auto-Mode 狀態切換；
  * 與 Doctrine & ROE 對接（哪些區域允許自動接管）。

* **Control Adapter**

  * 將決策轉換為該機種可執行之飛控命令；
  * 負責與既有 FBW（fly-by-wire）系統協調。

* **Pilot Interface Module**

  * 呈現風險、建議、模式狀態；
  * 提供飛官啟動／關閉特定模式之介面。

### 04.3 Dependencies（依賴與前提）

* 必須有足夠精度的 DEM 與基礎氣象／小氣候資料庫；
* 需具備能與 ISAFU 整合的 FBW／飛控介面；
* 需有訓練與模擬環境，讓飛官熟悉此 OS 行為模式。

---

## 05 — Use Cases

### 05.1 島嶼山後進出（Hillside Entry/Exit）

情境：

* 戰機利用山脈後側掩蔽，
* 需在短時間內完成對地形敏感的低空機動與爬升。

ISAFU 角色：

* 在 **Mode 2/3** 下，自動管理貼山高度與爬升曲線，
* 確保機體不因亂流或誤判而撞山或失速。

### 05.2 峽谷穿越與貼山飛行（Valley Transit / Ridge Skimming）

情境：

* 需經由峽谷或地形壓縮走廊進出某作戰區；
* 峽谷風切與亂流頻繁。

ISAFU 角色：

* 在指定「Valley Corridor」中啟用 Auto-Mode；
* 系統參照 DEM＋TIAS 模型，事先規劃安全包絡，
  飛官專注於任務情勢與通信，
  姿態安全由 OS 負責。

### 05.3 極端天候下降（Adverse-weather Island Descent）

情境：

* 回航時遭遇瞬變雲牆、山區突發風切；
* 飛官負荷已高（疲勞、夜間、任務後）。

ISAFU 角色：

* 以 AFDC 模組為核心，在 Auto-Descent Corridor 中接管下降姿態；
* 將下降任務視為 **「非人類適合處理之高頻控制」**，
  由系統執行，人類監看。

### 05.4 教學與訓練空域（Training & Safety Corridor）

情境：

* 教練機在本島特定訓練區操作，
* 學員尚未完全掌握山區飛行節奏。

ISAFU 角色：

* 在訓練空域中啟用 Monitor／Assist／Passive Override 模式；
* 既讓學員感受真實地形與亂流，
* 又由系統在「最後一道安全線」拉回機體，
  降低訓練事故率。

---

## 06 — Risks & Limitations

### 06.1 技術風險

* **模型誤差與資料不足**：
  DEM 或小氣候資料若不完整，
  可能導致預測層對風險估計不準確。
* **感測器失效／漂移**：
  若 INS／雷達高度計等發生故障，
  系統可能做出錯誤姿態決策。

### 06.2 人機互動風險

* **飛官對系統不信任**：
  初期若介入方式不透明或過於突兀，
  會導致飛官抗拒使用，甚至在關鍵時刻關閉系統。
* **控制權爭奪**：
  系統與飛官可能在某些情境下互相「打架」，
  必須嚴謹設計優先權與斷開機制。

### 06.3 Doctrine & 政策層風險

* **過度依賴自動系統**：
  若訓練過度依賴 ISAFU，
  飛官在系統失效情境下的手動能力可能下降。
* **軍種文化與飛官崇拜**：
  將焦點從「個人英雄」轉為「系統工程」，
  必須跨越文化與心理阻力。

### 06.4 適用邊界

* 不適用於缺乏 FBW 或無足夠改裝空間的老舊機種；
* 在完全陌生戰區（非本島）運用時，
  若無對應 DEM／氣象資料，系統效能將顯著下降。

---

## 07 — Comparative Analysis

### 07.1 與傳統 Auto-GCAS / Safety Systems 對比

| 面向         | 傳統 Auto-GCAS / TAWS | ISAFU                 |
| ---------- | ------------------- | --------------------- |
| 主要目標       | 避免地面撞擊（最後防線）        | 在「整個危險空域」內持續維持姿態／能量安全 |
| 啟用時機       | 極端危險、接近 CFIT        | 依任務模式，在指定走廊與空域主動工作    |
| 對 Doctrine | 多為平台安全附加            | 直接成為空拒學說與地形 OS 的一層    |

### 07.2 與傳統飛官訓練路線對比

* 傳統思維：

  * 提高飛行時數、
  * 加強山區飛行技巧、
  * 強調個人能力。

* ISAFU 思維：

  * **重新分工**：人類負責任務與戰術決策，系統負責高頻姿態維生；
  * **降低對「超人飛官」的結構依賴**；
  * 將「主場優勢」內建到飛控 OS。

### 07.3 與「大國空優思維」對比

* 大國：追求制空權，強調數量與技術世代。
* 小島嶼：難與大國在空優維度硬碰硬。

ISAFU 所屬的 OS 家族（空拒＋錐形幾何＋TIAS＋AFDC）
提供一條 **「空存＋時間戰＋主場物理偏壓」** 的替代路線。

---

## 08 — Implementation Path

### Stage I — 數位孿生與模擬

* 建立 **本島空域數位孿生**：

  * DEM、歷史氣象、事故紀錄、飛行軌跡。
* 在模擬環境中，對比：

  * 純人手 vs 各模式（0–3）運作下的事故率與工作負荷；
  * 測試不同門檻與介入力度對飛行員感受的影響。

### Stage II — 訓練環境導入

* 優先在 **教練機與模擬器** 上啟用 Mode 0/1：

  * 蒐集飛官與學員對警示與輔助的反應；
  * 微調介入策略與人機介面。
* 逐步引入 Mode 2（Passive Override），
  以降低訓練事故風險。

### Stage III — 作戰機種限定空域部署

* 選定若干 **高風險且戰略關鍵的走廊**，標註為 Auto-Mode 測試區；
* 在該區逐步開啟 Mode 2 → Mode 3：

  * 全程記錄軌跡與系統介入事件；
  * 持續更新模型與 Doctrine 使用準則。

### Stage IV — 大規模整合與 Doctrine 固化

* 將 ISAFU 納入國防規劃文件與戰術教範；
* 與空軍訓練體系、維修體系、氣象與地形單位整合；
* 明確界定：

  * 哪些任務必須使用 ISAFU；
  * 哪些情境下禁止關閉；
  * 如何在盟軍合作中解釋此主場 OS。

---

## 09 — Appendix

### 09.1 時間尺度推演（示意）

* 人類反應鏈：
  [
  600–900\ \text{ms}
  ]
* 峽谷風切／亂流事件的有效修正窗口：
  [
  300–500\ \text{ms（甚至更短）}
  ]

在這個框架下，即使飛官完全清醒、
也無法穩定在所有情境下完成「感知→判斷→操作」循環。

ISAFU／AFDC 的存在，是把這段「**不可能交給人類**」的頻段交給機器。

### 09.2 主場極化優勢的動態過程

* 每一次 sortie：

  * 飛行軌跡與環境資料回流訓練 ISAFU／AFDC 模型；
* 每一季氣候循環：

  * TIAS 模型對亂流與風切分布更精確。

長期效果：

* 對我軍：

  * 同一段山後／下降走廊，越來越熟悉，
  * 空域難度感 **下降**。
* 對敵軍：

  * 難以合法長期在本島空域收集高品質資料，
  * 適應度 **停留在初期甚至惡化**。

---

## 10 — Glossary（Lexicon）

* **ISAFU（Island Semi/Auto Flight-Control Upgrade）**
  島嶼空域專用的半自排／自排飛控 OS，疊加於戰機飛控系統之上。

* **AFDC（Autonomous Flight Descent Controller）**
  極限下降 AI 控制模組，專注於最危險幾秒鐘的自動操控。

* **Island Air Denial Doctrine（IAD，空拒學說）**
  將防空重心從制空權轉為 **空存＋拖時間** 的小國防空戰略。

* **Conic Defense Geometry（CDG，錐形偏折幾何）**
  使用多向量錐幾何分散敵方打擊能量的防禦結構。

* **Terrain-Induced Attrition System（TIAS）**
  以地勢＋小氣候為核心，設計對外來飛行員造成長期損耗的空域結構。

* **Home-Field Polarity Advantage（主場極化優勢）**
  同一片空域對我軍與敵軍在物理難度與心理壓力上呈現長期正逆反差。

* **Auto-Descent / Hillside Mode**
  在特定走廊中啟用的 Auto-Mode，由系統全程負責下降與貼山姿態控制。

---

## 🔗 Related OS

* **Chaotic Airspace OS — 混沌空域作戰作業系統 總論**
* **Active Cross-section Inflation (ACI) — Anti-Stealth Geometric Denial Module**
* **Volumetric Stealth Cloud (VSC) — Airspace-level Fire-Control Denial Module**
* **Defense OS 2.0 — 戰略級軟硬一體防禦 OS**
* **Terrain-Induced Attrition System (TIAS) — 地形 × 小氣候損耗系統**
* **Autonomous Flight Descent Controller (AFDC) — 島嶼極限下降 AI 模組**

---

## 📚 How to Cite

K.K. (2026). *Island Semi/Auto Flight-Control Upgrade (ISAFU) — Terrain-synchronized Flight-Control OS for Mountainous Island Airspace*.
*KKAxiomWeaver Whitepaper Research Center.*
[https://github.com/KKAxiomWeaver/Whitepapers](https://github.com/KKAxiomWeaver/Whitepapers)

---

## 🛡 License

This work is licensed under **Creative Commons CC BY-NC-SA 4.0**.
© 2026 K.K. (Axiom Weaver)
