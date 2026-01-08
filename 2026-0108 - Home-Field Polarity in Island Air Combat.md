# Home-Field Polarity in Island Air Combat  
Version `1.0` — `2026-01-08`

**Author:** K.K. (Axiom Weaver)  
**Affiliation:** *KKAxiomWeaver Whitepaper Research Center*  
**License:** CC BY-NC-SA 4.0  
© 2026 K.K.

---

## 📝 Abstract

This whitepaper introduces **Home-Field Polarity in Island Air Combat (HFPIA)**:  
a model describing how mountainous island terrain and micro-climate create a **systematic, asymmetric difficulty gradient** between *local* and *external* pilots.

On a high-density mountain island such as Taiwan, the same airspace is:

- progressively easier and safer for **local pilots** who train there for years,  
- and increasingly hostile for **external pilots** who lack embodied terrain & micro-climate memory.

HFPIA formalizes this gap as **home-field polarity** rather than generic “familiarity”. It integrates with the **Terrain-Induced Attrition System (TIAS)** and **Island Air Denial Doctrine (IAD)** to show that, even before any shot is fired, external air forces already face elevated accident risk, degraded mission effectiveness, and long-term psychological penalties when operating inside the island airspace.

The paper defines:

- metrics for polarity (risk ratio, cognitive load index, data asymmetry),  
- the feedback loop that strengthens local advantage over time,  
- and implementation paths for turning this natural polarity into a deliberate **Air Denial OS component**.

---

## 01 — Problem Statement

### 1.1 「同一片天空，為什麼難度完全不同？」

在多數空戰理論中，  
飛行環境被視為「中立」：  

- 空域難度主要由天氣、敵我火力決定；  
- 飛行員素質被假定為可互相比較；  
- 「熟不熟悉空域」被當作一個軟性因素，而非系統變量。  

然而，以台灣為代表的高山島嶼空域中，  
我們觀察到一個更根本的現象：

> **同一空域，對本地飛行員與外來飛行員的「實際難度」並不相同，  
> 甚至差異可以達到多倍。**

### 1.2 傳統分析的盲點

既有研究通常把這種差異歸因於：

- 個人經驗多寡、  
- 訓練時數、  
- 機種熟悉度。  

但這些說法忽略了關鍵：

- 島嶼的 **山脈結構 + 峽谷風場 + 貼地雲層**  
  本身會與「身體記憶」綁定；  
- 本地飛行員透過數百 sortie，在無數小事件中微調直覺；  
- 外來飛行員即便訓練再好，也不可能在短時間取得同等體驗數據。  

也就是說：

> **差異不只是「誰練比較久」，  
> 而是「誰擁有整套島嶼物理資料庫」。**

### 1.3 問題定義

本白皮書要處理的問題是：

- 如何從 **系統角度** 描述「本地 vs 外來」在島嶼空域的難度差？  
- 如何把這種差異，從模糊印象 → 變成可被 OS 利用的 **Home-Field Polarity**？  
- 如何讓這個效應，成為 Island Air Denial OS 的一個「可設計模組」，而非單純運氣？

---

## 02 — Concept Model

### 2.1 Home-Field Polarity（主場物理優勢）

**Home-Field Polarity** 定義為：

> 在特定高山島嶼空域中，  
> 由於地形 + 小氣候 + 長期訓練數據的疊加，  
> 導致 **本地飛行員與外來飛行員** 在  
> 「事故風險、任務負荷、心理壓力」上  
> 出現 **持續且可放大的非對稱差距**。

這不只是「熟不熟悉」，  
而是一種 **物理與認知的雙向偏壓（polarity）**。

### 2.2 三個核心向量

HFPIA 由三個向量構成：

1. **Risk Gradient（風險梯度）**  
   - 在同樣任務、同樣路徑下，  
     外來飛行員的事故機率 > 本地飛行員。  

2. **Cognitive Load Gradient（認知負荷梯度）**  
   - 外來飛行員在處理地標、氣象、亂流時的「腦內帶寬消耗」遠高於本地。  

3. **Data Asymmetry Gradient（資料非對稱梯度）**  
   - 本地擁有長期 sortie 產生的黑盒數據、飛行紀錄、事故檔案、口述經驗；  
   - 外來在戰時不可能取得同等級資料。  

三者疊加，  
形成 **單向性的主場優勢**。

### 2.3 Model Abstraction（抽象形式）

我們可以將某一空域的「實際難度」表示為：

> **D = f(Terrain, Micro-Climate, Traffic, Threat, Data, Training)**  

其中：

- 對本地飛行員：  
  `Data_local` 與 `Training_local` 可長期成長；  
- 對外來飛行員：  
  `Data_foreign` 幾乎固定在低水平，  
  `Training_foreign` 受限於模擬與短期部署。

HFPIA 主張：

> 在高山島嶼中，  
> `∂D/∂Data` 與 `∂D/∂Training` 的權重遠高於平原空域。  

也就是說：  
**越是山區越「吃熟悉度」**，  
而熟悉度又天然偏向本地。

---

## 03 — Mechanics（How It Works）

### 3.1 微事件累積成「身體地圖」

本地飛行員在數百 sortie 中，會不斷經歷：

- 某條谷地每到冬季就特別亂；  
- 某座山的背風面常有下沉氣流；  
- 某區域雲牆形成前的視覺徵兆；  
- 某些雷達回波與實際地形的偏差模式。  

這些事件大多不會進入正式文件，  
但會在飛行員腦中形成 **身體地圖（embodied map）**：

- 對某些區域有「不舒服的直覺」；  
- 對某些高度有「莫名的不信任」。  

外來飛行員：

- 即便看過圖資與簡報，  
- 也不可能在幾十小時訓練內重現同等微事件頻率。  

於是，在同一條航路上：

> 本地的「本能反應」  
> = 外來的「意識計算 + 遲來的操作」。

### 3.2 TIAS 與 HFPIA 的互動

**TIAS（Terrain-Induced Attrition System）** 描述的是：

- 在高山島嶼空域，  
  地形與小氣候對任何飛機都會提高事故風險。

HFPIA 則進一步指出：

- 在 TIAS 固定的前提下，  
  本地 vs 外來 的風險曲線並非平移，  
  而是 **斜率不同**。  

也就是說：

- 同樣增加 sortie 數，  
  本地的事故率累積較慢，  
  外來的事故率累積較快。  

### 3.3 時間維度的極化

隨時間推進：

- **本地**：  
  - 不斷更新 TIAS 模型與 AFDC／ISAFU 系統；  
  - 飛行員的身體地圖愈來愈完整；  
  - 出現「這裡大家都覺得險，但我們習慣了」的現象。  

- **外來**：  
  - 很難長期留在島上累積經驗；  
  - 即便偶爾侵入，也難以帶走足夠真實數據；  
  - 每次入侵幾乎都是「硬闖未知迷宮」。  

結果就是：

> **同一片空域，  
> 對本地來說越飛越順，  
> 對外來而言永遠是困難場。**

---

## 04 — Architecture

### 4.1 HFPIA 在整體 OS 中的位置

- **Environment Layer**：  
  - HFPIA 與 TIAS 一起描述島嶼空域的「物理難度空間」。  

- **Training OS Layer**：  
  - 定義本地飛官訓練目標：  
    將主場優勢最大化，而非追求抽象飛行時數。  

- **Doctrine Layer**：  
  - 為 IAND / IAD 提供理論支撐：  
    為何「不鼓勵敵人長期留在本島空域」本身就是戰略。  

- **Alliance Layer**：  
  - 向盟軍解釋：  
    為何「讓島嶼空軍負責本地高難度空域」，  
    而「盟軍負責外圍與高空制空」是合理分工。  

### 4.2 模組

1. **Risk Ratio Module**  
   - 計算本地 vs 外來在特定空域的預期事故比值。  

2. **Cognitive Load Index Module**  
   - 透過模擬與實飛數據，  
     評估不同背景飛官在同任務下的負荷。  

3. **Data Asymmetry Module**  
   - 管理「本地累積資料 vs 外來可獲得資料」落差。  

4. **Training Prioritization Module**  
   - 建議哪一些「主場難點」應優先納入例行訓練。  

---

## 05 — Use Cases

1. **戰術決策：是否誘使敵機深入本島空域？**  
   - HFPIA 可告訴指揮官：  
     在某些地區，敵機進來的實際風險非常高；  
     因此「誘入」的策略是可行的。  

2. **訓練規劃：本地飛官要特別熟悉哪些區域？**  
   - 使用 HFPIA 地圖，挑出「主場優勢可放大區」；  
   - 讓訓練重點不只是一般飛行科目，而是「主場物理學」。  

3. **對盟軍的戰場簡報**  
   - 清楚說明：  
     為何部分低空／山谷任務應由本地飛官主責，  
     盟軍則專注於中高空或遠距支援。  

4. **心理戰與嚇阻**  
   - 透過公開或半公開方式，  
     讓對手理解「這片空域對你們飛官非常不友善」，  
     形成 **心理層面的 TIAS**。  

---

## 06 — Risks & Limitations

- **資料偏誤風險**  
  - 若本地事故資料不完整或被低估，  
    會錯判 HFPIA 強度。  

- **過度自信風險**  
  - 本地飛官可能因「主場優勢」敘事而低估風險；  
  - 必須強調：HFPIA 是相對優勢，不是絕對安全。  

- **敵方適應風險**  
  - 外來空軍可能透過長期演訓部分降低差距；  
  - 或使用全自動／無人機減少人類認知負荷。  

- **政治誤讀**  
  - 外界可能誤解：  
    強調 HFPIA 等於小看敵方飛行員專業；  
  - 實際上這是物理條件與資料分布造成的。  

---

## 07 — Comparative Analysis

### 7.1 vs General “Familiarity” Arguments

傳統說法：「熟能生巧」。  
HFPIA 的差異在於：

- 不是心理層面，而是 **地形＋小氣候＋資料非對稱** 的結構性結果；  
- 強調 **時間維度與數據累積**；  
- 明確指出：「外來飛官在戰時無法補齊這個缺口」。  

### 7.2 vs Generic “Pilot Quality” Narratives

- 「飛官素質高低」是一種容易政治化的敘事；  
- HFPIA 刻意避開這個框架，  
  把焦點放在 **系統條件與物理現實**。  

---

## 08 — Implementation Path

### Stage I — HFPIA Baseline Mapping

- 整合：  
  - 過去事故報告（軍民）、  
  - 氣象資料、  
  - 地形 DEM、  
  - sortie 航跡紀錄；  
- 為本島主要空域建立初步 HFPIA 地圖：  
  - 對本地 vs 外來的難度差異做質性標註。  

### Stage II — Training OS Integration

- 將 HFPIA 高差區納入飛官訓練計畫；  
- 使用模擬器重現「外來視角」與「本地視角」難度差；  
- 讓本地飛官理解自己真正的優勢來源。  

### Stage III — Doctrine & Alliance Integration

- 在 Island Air Denial Doctrine 中，  
  明示 HFPIA 的存在與戰術運用方式；  
- 在與盟軍的聯合作戰簡報中，  
  使用 HFPIA 做任務分工依據。  

### Stage IV — Long-term Data Strategy

- 將 HFPIA 納入  
  「島嶼空域數位孿生（Digital Twin）」 的長期維運；  
- 持續收集 sortie 航跡與氣象實測，  
  讓主場優勢成為 **越飛越強的 OS 模組**。  

---

## 09 — Appendix

可能的延伸內容：

- 使用簡化統計模型估算「本地 vs 外來事故率倍數區間」；  
- 建立示意圖：  
  - 為何某些谷地對外來飛機是「天然陷阱」，  
    對本地只是「高難訓練場」。  
- 與陸上作戰中「山地步兵 vs 外來部隊」的對比。  

---

## 10 — Glossary（Lexicon）

- **HFPIA（Home-Field Polarity in Island Air Combat）**  
  島嶼空戰主場物理優勢模型。  

- **Risk Gradient**  
  同一空域下，本地 vs 外來在事故機率上的梯度差。  

- **Cognitive Load Gradient**  
  同一任務下，兩者在認知負荷與決策壓力上的差異。  

- **Data Asymmetry**  
  本地與外來在真實飛行數據、事故紀錄與氣象體驗上的非對稱。  

- **Embodied Map（身體地圖）**  
  飛行員藉由微事件累積出來的非語言化空域直覺。  

- **Digital Twin of Island Airspace**  
  島嶼空域數位孿生，用以支援 TIAS 與 HFPIA 的建模。  

---

## 🔗 Related OS

- Terrain-Induced Attrition System OS（TIAS）  
- Island Air Denial Doctrine OS（IAD / IAND）  
- Auto-Flight Downward Control OS（AFDC）  
- Island Semi/Auto Flight-Control Upgrade OS（ISAFU）  
- Conic Defense Geometry OS（CDG）  
- Defense OS 2.0  

---

## 📚 How to Cite

K.K. (2026). *Home-Field Polarity in Island Air Combat*.  
*KKAxiomWeaver Whitepaper Research Center.*  
https://github.com/KKAxiomWeaver/Whitepapers  

---

## 🛡 License

This work is licensed under **Creative Commons CC BY-NC-SA 4.0**.  
© 2026 K.K. (Axiom Weaver)
