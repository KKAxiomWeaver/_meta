# K.K. Whitengineering • Multi-domain OS • Axiom Weaver 

This repository contains all whitepapers authored by **K.K. (Axiom Weaver)**.  
No folders are used; papers are organized through **naming conventions + Master Index**.

### Repository Structure Strategy
- All files stored at root (`/`)
- Naming: `YYYY-MMDD - <WorldCode> - <OS> - <Title>.md`
- `MASTER_INDEX.md` provides cross-domain cross-references
- `_meta/` stores templates, index, version map, badges

---

# Liquidity Window OS · 長假 / 繳稅 / ETF 壓力的流動性窗口模型  
Version `0.9` — `2026-01-11`

**Author:** K.K. (Axiom Weaver)  
**Affiliation:** *KKAxiomWeaver Whitepaper Research Center*  
**License:** CC BY-NC-SA 4.0  
© 2026 K.K.

---

## 📝 Abstract

Liquidity Window OS 形式化了一種在實務盤感中極為關鍵、卻常被忽略的結構現象：  
**市場並非持續均質運作，而是被一個個「流動性窗口」切割──長假、ETF 剃除、繳稅期、季底結帳、指數調整，都會暫時改變「誰在場、誰缺席、誰有主導權」。**

本白皮書將：  

- 定義長假、繳稅期、ETF 被動賣壓等事件如何創造「小朋友 vs 大人」的控盤窗口；  
- 說明為何 **ETF 機械賣壓 + 流動性變薄**，經常催生主升段的起手式，而不是終點；  
- 建構一套「Window-State Model」，描述資金在不同窗口狀態下的行為轉換；  
- 將流動性窗口與 Capital Chessboard OS 串接，說明外資控制權與本地主力定價之間的節奏切換。  

Liquidity Window OS 不預測價格，而是給出一個 **時序與流動性為核心的 MK 子系統**，幫助讀盤者判斷：  
「現在是誰的盤？」「這個漲跌是趨勢本身，還是窗口效應？」  
並作為 Market OS 與 Civilization OS 之間的微結構橋接層。

---

## 01 — Problem Statement

傳統市場分析有幾個盲點：

1. **假設市場流動性是連續且均質的**  
   - 僅用「成交量」一個指標粗略衡量  
   - 忽略市場在長假、繳稅、ETF 調整時，參與者構成的劇烈變化  

2. **忽略「誰在場」比「價格怎麼走」更重要**  
   - 外資休假、本地主力當家；  
   - ETF 被動賣壓 vs 主動資金吸貨；  
   - 繳稅期導致散戶、本地大戶現金吃緊。  

3. **將 ETF 賣壓誤認為「趨勢反轉」**  
   - 實際上多數 ETF 賣壓是「制度性、機械性」而非價值判斷；  
   - 結果：**錯把吸貨窗口當成崩盤起點。**

4. **缺乏一個可以整合「日曆事件 + 資金節奏」的 OS**  
   - 無法回答：「聖誕長假前外資的買超代表什麼？」「5 月綜所稅對島嶼股市的結構意義是什麼？」  

Liquidity Window OS 針對上述缺口，  
提出一個以「時間窗口 + 參與者構成 + 機械賣壓」為主的框架，  
將實務盤感中的「今天是小朋友的盤 / 家長的盤」變成可描述、可重複的系統語言。

---

## 02 — Concept Model

### 2.1 What is a Liquidity Window?

**Liquidity Window（流動性窗口）** 是指在特定時間區段內，由於制度、日曆事件或資金約束，  
導致市場參與者組成與流動性狀態發生顯著變化的「時間片」。  

例子：

- 聖誕長假前後（外資休息、本地主力當家）  
- 農曆年封關前後（島嶼資金避險、假期後重啟）  
- ETF 剃除成分股的賣壓集中期  
- 5 月綜所稅、9 月營所稅等繳稅窗口  

在這些窗口中：

- **誰不能動（外資、長線基金）**  
- **誰被迫動（ETF、被動型資金、需要現金繳稅者）**  
- **誰最自由（本地主力、短線資金、系統交易）**

的組合被改寫。

### 2.2 Little Kids vs Parents Model

直覺化比喻：

- **Parents（家長）**：外資、長線機構、保守風控下的資金  
- **Kids（小朋友）**：本地主力、短線資金、高風險承擔者  
- 當家長缺席（長假、事件風險前避險），  
  → 小朋友主導盤面，  
  → 容易出現獨立行情與誇張波動。  

Liquidity Window OS 用這個比喻來刻畫：

> **誰在當主控？是家長在控局，還是小朋友在玩？**

### 2.3 Window-State Machine

定義市場存在多種 Window State：

- `W0` — Normal Flow（常態流動）  
- `W1` — Holiday Mode（長假模式）  
- `W2` — Tax Squeeze（繳稅擠壓）  
- `W3` — ETF Pressure（ETF 機械賣壓）  
- `W4` — Quarter/Year-End Dressing（季底／年底作帳）  

每一種狀態都有特定的：

- 參與者構成  
- 必然行為  
- 主導權轉移模式  

Liquidity Window OS 定義這個「狀態機」，並描述不同狀態之間的轉換條件。

---

## 03 — Mechanics（How It Works）

### 3.1 Participant Composition Dynamics（參與者構成動力學）

在任一時間 `t`，市場參與者可簡化為：

- `F(t)` 外資與長線機構  
- `D(t)` 被動型資金（ETF、指數基金）  
- `L(t)` 本地主力（local strong hands）  
- `R(t)` 零售散戶（retail）  
- `H(t)` 高頻與量化策略（HFT / Quant）

流動性窗口使某些項目暫時「弱化」或「強化」：

- 長假 → `F(t)` 有效縮水，`L(t)` 控制權上升  
- 繳稅期 → `R(t)`、`部分 L(t)` 被迫賣出，`F(t)` / `D(t)` 承接  
- ETF 剃除 → `D(t)` 機械拋售，`L(t)` / `F(t)` 成為吸納者  

### 3.2 ETF Pressure Mechanics

在 `W3 = ETF Pressure` 狀態下：

- 賣壓來自被動規則，而非價值判斷；  
- 賣出節奏是「固定公式」，不是人為隨意決策；  
- 若標的基本面強、文明敘事對位正確，  
  → 強手會把這段視為 **折價配發**。  

典型波形：

1. 剃除訊息出現 → 價格先行下殺（恐慌＋套利）  
2. 機械賣壓實際執行週期 → 價格不再創新低，甚至逐步墊高  
3. 賣壓尾端 → 主力與外資已吸滿／建位完成  
4. 壓力終止後 → 第一根主升段起手長紅 K  

Liquidity Window OS 強調：

> **ETF 壓力是「流動性事件」，不是「價值否定」。**

### 3.3 Holiday Mode Mechanics

在 `W1 = Holiday Mode`：

- 外資 Desk 人力縮減／風控限縮 → `F(t)` 縮水  
- 模型改為低槓桿、低交易頻率  
- 本地主力 `L(t)` 在薄量環境中擁有 **定價優勢**  

結果表現為：

- 大盤量縮、方向模糊  
- 強勢個股在薄量中被主力「抬階」  
- 偶爾出現與大盤完全脫鉤的獨立漲停／崩跌  

在 Capital Chessboard OS 視角下，  
這往往是本地主力「幫外資預先抬價到新棋盤高度」的時間。

### 3.4 Tax Squeeze Mechanics

在 `W2 = Tax Squeeze`（繳稅窗口）：

- 散戶 `R(t)` 與部分本地大戶 `部分 L(t)` 被現金需求驅動  
- 強制性賣壓、非價值型賣壓增加  
- 若文明敘事與基本面支持趨勢，  
  → 長線資金與外資會在這段「無奈賣壓」中逐步佈局  

常見表現：

- 指數悶、量縮、情緒保守  
- 強勢股「悶悶漲」，弱勢股無人理  
- 結束後若無重大利空 → 常是主升段啟動點之一  

### 3.5 State Transition Logic

- 正常 → ETF 調整期 → `W3`  
- 正常／`W3` → 接到長假 → `W1`  
- 正常 → 繳稅月份 → `W2`  
- 季末／年末 → `W4`  

流動性窗口會疊加：  
例如 `W3 + W1` = **ETF 壓力尾段 + 長假薄量**  
→ 這時本地主力的定價權極大，  
→ 也常是主升段「第一階抬價」的最佳時刻。

---

## 04 — Architecture

### 4.1 System Layers

1. **Calendar Layer（日曆層）**  
   - 長假、節慶、繳稅期、結算日、指數調整日  

2. **Participant Layer（參與者層）**  
   - 外資、被動資金、本地主力、散戶、量化  

3. **Window State Layer（狀態層）**  
   - W0 ~ W4 的 Window State Machine  

4. **Market Microstructure Layer（微結構層）**  
   - 價量變化、單量型態、漲跌節奏  

5. **Narrative & Capital Chessboard Layer**  
   - 上層敘事與資本棋盤（由其他 OS 提供）  

Liquidity Window OS 位於 Calendar + Participant + Window State 之間，  
將上層的文明敘事、下層的價格行為串成一條可解釋的鏈。

### 4.2 Modules

- **Calendar Parser Module**  
  - 解析日曆事件並標記潛在窗口期。  

- **Participant Impact Estimator**  
  - 評估某事件對 `F/D/L/R/H` 的約束與自由度。  

- **Window Classifier**  
  - 將當前時段分類為 W0~W4。  

- **Pattern Mapper**  
  - 對應不同窗口狀態下常見的價量／行為型態。  

- **Integration Bridge**  
  - 將窗口狀態資訊提供給：  
    - Capital Chessboard OS（幫助詮釋外資控盤行為）  
    - Hi-D Trend Engine（避免把短期窗口誤判為長期趨勢反轉）。  

### 4.3 Dependencies

- 依賴上層：  
  - **Civ-OS**（文明級趨勢，不被短期窗口誤導）  
  - **Capital Chessboard OS**（外資控制權需求）  

- 提供資訊給：  
  - **MK-OS**（島嶼市場與其他市場連動）  
  - **Local Strategy OS**（本地主力行為模型）  

---

## 05 — Use Cases

1. **解釋「大盤平、個股飆」的情況**  
   - 長假前後、外資縮手，  
     本地主力在 `W1` 狀態下抬升特定文明對位標的。  

2. **辨識 ETF 賣壓是「吸貨期」還是「崩潰期」**  
   - 若文明敘事、基本面強，  
     `W3` 更可能是強手悄悄吸貨的窗口。  

3. **利用繳稅期辨識強弱股**  
   - 繳稅期中仍能逆勢墊高的標的，  
     通常是被長線資金與本地主力共同鎖定。  

4. **解讀外資長假前買超行為**  
   - 在 `W1` 前夕仍大買，  
     → 更像是「預先卡位」，避免假期後在更高價追回曝險。  

5. **風控與槓桿管理**  
   - 在 `W1` / `W2` / `W3` 狀態下調整槓桿與持股集中度，  
     避免把短期流動性錯覺當成基本面變化。  

---

## 06 — Risks & Limitations

1. **過度依賴「事件標記」的風險**  
   - 僅因為有長假並不代表一定會發生主升段；  
   - 流動性窗口是條件，不是保證。  

2. **忽略個別公司基本面**  
   - 若忽略企業本身已失去文明對位，  
     即使窗口存在，也可能只是下跌加速期。  

3. **模型複雜度過高**  
   - 自動化實作時，過多狀態與參數會降低可用性。  

4. **被解讀為「時機預言機」的誤用風險**  
   - 本 OS 不是用來「猜明天漲跌」，  
     而是用來分類市場的流動性環境。  

5. **政策與黑天鵝事件**  
   - 突發性戰爭、制裁、金融事故，  
     可能瞬間打斷原先規律窗口。  

---

## 07 — Comparative Analysis

### 與純技術分析比較

- 技術分析：  
  - 聚焦於價量歷史，忽略誰在場、誰缺席。  
- Liquidity Window OS：  
  - 聚焦「參與者組成 + 日曆事件 + 機械賣壓」。  

### 與基本面分析比較

- 基本面：  
  - 解釋企業價值變化的長期原因。  
- 本 OS：  
  - 解釋短中期「資金路徑與節奏」，  
    為何好企業會在一段時間被「壓抑」或「異常加速」。  

### 與傳統「季節性效應」比較

- 季節效應研究：  
  - 波段統計（如 1 月效應、5 月賣股…）  
- Liquidity Window OS：  
  - 提供結構性原因（稅制、假期、指數與 ETF 規則）  
  - 並將之整合進參與者行為模型。  

---

## 08 — Implementation Path

### Stage I — Manual Mapping

- 以歷史數據手工標註：  
  - 聖誕／復活節／農曆年  
  - 繳稅期  
  - ETF 調整  
- 建立 Window State 日曆，對照指數與個股表現。  

### Stage II — Semi-automatic Classification

- 為每一天標記：  
  - 流動性強弱  
  - 外資參與度  
  - ETF 交易量異常與否  
- 以規則判定進入 W0~W4 的條件。  

### Stage III — OS Integration

- 將 Window 狀態輸入：  
  - Capital Chessboard OS（輔助判斷外資買超意義）  
  - Hi-D Trend Engine（避免短期噪音干擾長期趨勢判讀）  

### Stage IV — Strategy Sandbox

- 建立「情境回測」：  
  - 同一文明敘事下，  
    在不同 Window 狀態中進場／出場的表現差異。  

---

## 09 — Appendix

- A1. Window State Machine 示意圖  
- A2. 範例：某 AI/儲存主題股在 `W3 + W1` 條件下的走勢切片  
- A3. 島嶼市場繳稅期 vs 外資買超的歷史統計方向（概念級）  
- A4. 長假期間主力控盤常見行為列表（抽象化，不指具體標的）  

---

## 10 — Glossary（Lexicon）

- **Liquidity Window（流動性窗口）**  
  由日曆事件與制度性因素造成的特定時段，市場參與者結構與流動性狀態與常態明顯不同。  

- **Holiday Mode（長假模式）**  
  外資縮手、流動性變薄、本地主力定價權增加的市場狀態。  

- **Tax Squeeze（繳稅擠壓）**  
  因現金需求逼迫散戶與本地大戶賣出部位所形成的賣壓窗口。  

- **ETF Pressure（ETF 壓力）**  
  因成分調整、規則變更導致的被動機械賣壓，不直接代表價值判斷。  

- **Capital Gravity（資本重力）**  
  文明敘事與長線趨勢對資本配置的結構性吸引力，導致資金在某些節點長期聚集。  

- **Little Kids vs Parents Model（小朋友 / 家長模型）**  
  用以比喻本地主力與外資在不同窗口時期的控盤關係。  

- **Window State Machine（窗口狀態機）**  
  將市場分為 W0~W4 各種狀態，描述隨時間與事件的切換邏輯。  

---

## 🔗 Related OS

- Capital Chessboard OS · 外資控制權棋盤模型  
- MK-OS（Market OS · Island & Global）  
- Civ-OS（Civilization OS）  
- Hi-D Trend Engine OS（高維趨勢引擎）  
- Island Strategy OS（島嶼資本與戰略安全 OS）  

---

## 📚 How to Cite

K.K. (2026). *Liquidity Window OS · 長假 / 繳稅 / ETF 壓力的流動性窗口模型*.  
*KKAxiomWeaver Whitepaper Research Center.*  
https://github.com/KKAxiomWeaver/Whitepapers  

---

## 🛡 License

This work is licensed under **Creative Commons CC BY-NC-SA 4.0**.  
© 2026 K.K. (Axiom Weaver)
