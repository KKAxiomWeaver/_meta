# Zero-Visibility Air Safety System  
Version `1.0` — `2026-01-09`

**Author:** K.K. (Axiom Weaver)  
**Affiliation:** *KKAxiomWeaver Whitepaper Research Center*  
**License:** CC BY-NC-SA 4.0  
© 2026 K.K.

---

## 📝 Abstract

This whitepaper proposes the **Zero-Visibility Air Safety System (ZVASS)**:  
an OS module specifically designed for **“white wall” conditions** in mountainous island airspace—when clouds, fog or precipitation erase all external visual references and heavily degrade onboard sensing.

On a high-relief island like Taiwan, rapid cloud-bottom drops, valley fog and orographic precipitation can turn a previously manageable flight into a **near-instant zero-visibility scenario**, especially during descent, valley transit or hillside maneuvers. In such conditions, traditional “pilot skill + partial instruments” is not a robust safety model; the system must assume that **human visual cues go to zero** and that **some sensors may be degraded or lying** (GNSS spoofing, multipath, clutter).

ZVASS defines:

- a **sensor-trust hierarchy** and graceful-degradation logic under zero-visibility,  
- a set of **emergency auto-profiles** for climb / stabilisation / safe-hold / auto-descent,  
- integration points with **I-ADSCO / AFDC / ISAFU / TIAS / NDZ**,  
- and procedures for both **peacetime safety** and **wartime degraded operations**.

The goal is to ensure that, when the island “switches off the outside world” by dropping a cloud curtain, aircraft operating in this environment have a dedicated OS layer that **takes over, stabilises, and buys time**, rather than relying on human improvisation under sensory collapse.

---

## 01 — Problem Statement

### 1.1 「白牆」事件：外界全部消失的瞬間

在高山島嶼空域，飛行員經常描述：

- 穿越山谷時，前方突然出現白牆；  
- 原本看得見的山脊與地平線在數秒內完全消失；  
- 機體進入雲中後，  
  **內耳、視覺、地標感全部失效**；  
- 短時間內必須同時處理姿態、下降率、地形避障。  

這種「white-out / white wall」情境在：

- 山區直升機任務、  
- 島嶼戰機進出基地、  
- 搜救與補給任務中極為常見。

### 1.2 現行解法的不足

目前對零能見度的應對多半是：

- 仰賴 IFR 技術與儀表飛行規程；  
- 仰賴個人經驗與訓練；  
- 飛行員被要求在極端壓力下「冷靜、專注、照程序」。  

問題在於：

- 島嶼空域的 **雲層常貼著山體與山谷**，  
  IFR 程序本身是在較大空域與較緩地形假設下設計；  
- 在谷地或山側遭遇白牆時，  
  可用高度與反應時間極為有限；  
- 戰時還可能疊加：電磁干擾、設備損傷、疲勞與心理壓力。  

### 1.3 問題定義

ZVASS 要處理的是：

- 在 **外界視覺 = 0、部分感測器不可靠** 甚至遭干擾時，  
  如何提供一個 **專門的「零視界模式」**，  
  讓系統接手核心穩定與避障任務？  
- 如何定義「感測器信任階層」，  
  並在資料互相矛盾時，  
  做出 **最不可能導致 catastrophic failure** 的決策？  
- 如何讓這套系統，在 **平時飛安 + 戰時生存**  
  都能發揮功能？

---

## 02 — Concept Model

### 2.1 Zero-Visibility Air Safety System（ZVASS）

**ZVASS**：

> 一套在「外界視覺完全喪失、儀表部分不可靠」條件下，  
> 專門負責 **姿態穩定、防失速、防撞地** 與  
> **爭取時間** 的飛安 OS 模組。  

它不是完整自動駕駛系統的替代品，  
而是：

- 當某些 trigger 被觸發時（白牆、感測異常、地形風險升高），  
- 強制將系統進入一種 **保命優先模式**，  
- 將所有多餘的「任務意圖」暫時關閉，  
- 集中資源在「先不要撞山／地／海」。

### 2.2 Safe Envelope First（包絡優先）

ZVASS 的設計哲學：

> **先確保機體仍然在一個可恢復的飛行包絡內，  
> 任務與戰果一律排在後面。**

具體來說：

- 防止失速／超 G／極端姿態；  
- 保持足夠的高度與能量緩衝；  
- 避免誤入已知高風險 TIAS／NDZ 深處（若不必要）；  
- 在盤整情況之前，不再嘗試複雜戰術動作。  

### 2.3 Sensor Trust Hierarchy（感測器信任階層）

在零能見度下，  
不同感測器的可靠度並不相同：

- GNSS 可能遭遇：遮蔽、反射、干擾或欺騙；  
- 雷達高度計在陡峭山谷中仍有一定可靠度，但也可能被地形形狀影響；  
- INS 長期會飄移，但短時間內穩定；  
- EO/IR 在白牆中效用接近零。  

ZVASS 的核心之一是定義一個：

> **Sensor Trust Stack（感測信任堆疊）**，  
> 在白牆情境下，  
> 為不同數據源分配信任權重與 fallback 邏輯。

---

## 03 — Mechanics（How It Works）

### 3.1 Trigger：怎樣的情境會啟動 ZVASS？

ZVASS 以多種 trigger 組合判斷：

- 外界光學參考突然掉到近乎 0；  
- 雲霧濃度（或雷達反射）達到設定閾值；  
- 飛行員主動切入「Zero-Vis Mode」；  
- 感測器輸出開始出現互相矛盾：  
  - GNSS vs INS vs 雷達高度 vs 地形預估。  

一旦進入 Zero-Vis Mode：

- 非必要任務系統被降級或暫停；  
- Flight-OS 切換到 **ZVASS 主導的控制 profile**。  

### 3.2 Sensor Trust Stack（簡化示意）

在 Zero-Vis 模式下，信任階層可能為：

1. **短期 INS + IMU + 空速**（作為姿態與動力主軸）  
2. **雷達高度計**（短距離地形距離）  
3. **事先載入的 DEM + 飛行路徑預估**  
4. **GNSS / 外部導航訊號**（經異常檢測過濾）  
5. **其他輔助感測器**

若偵測到：

- GNSS 與 INS 差異超出閾值，  
  則暫時降低 GNSS 權重；  

- 雷達高度與 DEM 推算高度嚴重不一致，  
  則標記該方向為高不確定性，  
  適度增加高度餘裕。

### 3.3 Emergency Profiles（緊急剖面）

ZVASS 應提供最少三類預設剖面：

1. **Climb & Stabilise Profile**  
   - 適用於懷疑前方有地形／未知風險；  
   - 指令機體：  
     - 緩和但明確爬升、  
     - 穩定姿態、  
     - 增加高度緩衝。  

2. **Hold & Assess Profile**  
   - 在已知安全空域上方作小範圍 holding；  
   - 給系統與飛官時間檢查感測器、  
     等待雲層或狀況改善。  

3. **Guided Auto-Descent Profile**  
   - 結合 I-ADSCO／AFDC 接管；  
   - 尋找預先定義的「安全下降走廊」，  
     有系統引導飛機安全降落或離開危險區。  

所有剖面之共同點：

> **以 survivability 為唯一優先目標。**

---

## 04 — Architecture

### 4.1 ZVASS 在 Flight-OS 的位置

- **Perception Layer**  
  - 接收各感測器輸出，並產生「可信度標籤」。  

- **Assessment Layer**  
  - 檢測是否進入 Zero-Vis 情境；  
  - 判斷是否需要切換 ZVASS 模式。  

- **Envelope Protection Layer**  
  - 監控姿態、G 值、空速、高度等是否超出安全包絡；  
  - 在必要時強制介入。  

- **Profile Selection Layer**  
  - 根據當前任務與環境，  
    選擇 Climb / Hold / Auto-Descent 等剖面。  

- **Execution & HMI Layer**  
  - 實際調控控制面與推力；  
  - 呈現簡化資訊給飛官：  
    - 「我們正在做什麼」  
    - 「還剩多少高度／燃油／時間餘裕」。  

### 4.2 Integration with Other OS

- **與 I-ADSCO / AFDC / ISAFU**  
  - 在紅區段下降時，  
    ZVASS 負責對感測器與環境不確定性做風險管理，  
    I-ADSCO／AFDC 則負責精細控制。  

- **與 TIAS / NDZ**  
  - 當進入高 TIAS／NDZ 區域且能見度又低時，  
    ZVASS 會將風險等級提升，  
    優先考慮爬升或離開該區。  

- **與 IAND / IPUW**  
  - 戰術層（是否出場、是否 Pop-up）由 Doctrine 決定；  
  - 一旦戰術在 Zero-Vis 下導致狀況惡化，  
    ZVASS 負責保命收尾。  

---

## 05 — Use Cases

### 5.1 山區運補直升機任務

- 直升機在山谷中執行運補，  
  突然雲霧加重、能見度快速下降；  
- 飛官啟動 ZVASS：  
  - 系統先進入 Climb & Stabilise，  
    將機體拉離谷底；  
  - 然後切換到 Hold & Assess，  
    評估是否返回基地或改往替代降落點。  

### 5.2 戰機進出島嶼基地

- 戰機返場時，  
  入場航線上雲底高度突然低於預期；  
- ZVASS 感測到 GNSS／氣壓高度／雷達高度資訊不一致，  
  同時飛官外界視覺趨近 0；  
- 系統自動將模式升級：  
  - 防止過度下降；  
  - 建議改用替代進場；  
  - 或由 I-ADSCO 導向安全 holding 區。  

### 5.3 戰時：電磁干擾 + 白牆

- 敵方對 GNSS 與通訊施以干擾／欺騙；  
- 同時，島嶼本地天氣造成海岸與山區白牆；  
- 在此組合情境下：  
  - ZVASS 將 GNSS 信任權重降低；  
  - 強化 INS＋雷達高度＋DEM 的比對；  
  - 以最保守的姿態維持可存活狀態，  
    避免機體因錯誤導航訊號飛向山體。  

---

## 06 — Risks & Limitations

- **過度複雜性**  
  - 若設計過於複雜，  
    可能引入難以檢驗的新故障模式；  
  - 必須保持「核心功能簡潔可證明」。  

- **訓練與信任問題**  
  - 飛官必須經過訓練，  
    知道何時相信 ZVASS、何時撤銷指令；  
  - 避免在系統異常時依然盲信。  

- **誤判 Zero-Vis 情境**  
  - 若 ZVASS 錯誤判定情境，  
    可能在並不需要時大量介入，  
    違反任務需求；  
  - 需謹慎設計觸發條件與 hysteresis。  

- **系統受損或欺騙時的降級模式**  
  - 必須明確定義：  
    在哪些感測器全部失效情境下，  
    系統將如何「盡可能保命」，  
    而不是做出高風險動作。  

---

## 07 — Comparative Analysis

### 7.1 vs 一般 IFR / TAWS

- 一般 IFR 程序與 TAWS：  
  - 假設空域較大、有較多迴旋空間；  
  - 假設導航訊號可靠；  
  - 假設主要風險來自「飛太低」。  

- ZVASS：  
  - 假設空域窄、地形凶、天氣劇變；  
  - 假設部分導航訊號不可靠甚至敵對；  
  - 假設飛行員已處在高壓戰場環境。  

### 7.2 vs 純 AI 自駕構想

- ZVASS 不是全 AI 自駕，  
  是 **Flight-OS 的一個「白牆防護模組」**；  
- 保留飛官決策權，  
  但在已知人類判斷會嚴重失準的條件下，  
  提供「優先保命」的自動反應。  

---

## 08 — Implementation Path

### Stage I — Concept & Safety Case

- 定義清楚：  
  - ZVASS 的觸發條件、  
  - 任務目標、  
  - 非目標（不負責什麼）。  

- 建立初步安全案例（Safety Case）：  
  - 哪些情境下 ZVASS 明顯降低事故率。  

### Stage II — 模擬與人機測試

- 在高擬真模擬器中重現：  
  - 山區白牆、  
  - 海岸白牆、  
  - 雙重白牆（雲＋雨）；  

- 測試：  
  - 飛官單靠自己 vs 啟用 ZVASS 的差異；  
  - 認知負荷、錯誤率與姿態偏離。  

### Stage III — 限制實飛與資料回收

- 選定少數高風險航線，  
  在良好監控條件下進行 ZVASS 實飛測試；  
- 收集數據反饋模型，  
  微調 Sensor Trust Stack 與 Emergency Profiles。  

### Stage IV — 戰備整合

- 將 ZVASS 納入：  
  - 島嶼空軍戰備程序；  
  - IPUW／IAND 對應 SOP；  
  - Civil–Military 整合（民用機也可受益）。  

---

## 09 — Appendix

未來可加：

- 白牆事故案例與 HFPIA 的關聯整理；  
- 具體 Zero-Vis 測試環境設計（風洞＋氣象實驗）；  
- ZVASS 與地面管制中心（ATC / 戰管）之協同流程。  

---

## 10 — Glossary（Lexicon）

- **ZVASS**  
  Zero-Visibility Air Safety System，  
  專責「白牆」情境的飛安 OS 模組。  

- **White Wall / White-out**  
  因雲、霧、雪或降水導致外界視覺完全消失的狀態。  

- **Sensor Trust Stack**  
  在感測器資訊互相矛盾時，  
  依可靠度排序與決策的信任堆疊。  

- **Climb & Stabilise / Hold & Assess / Guided Auto-Descent**  
  ZVASS 的三大緊急操作剖面。  

---

## 🔗 Related OS

- Island Auto-Descent & Stability Control OS（I-ADSCO）  
- Auto-Flight Downward Control OS（AFDC）  
- Island Semi/Auto Flight-Control Upgrade OS（ISAFU）  
- Terrain-Induced Attrition System OS（TIAS）  
- Natural Deception Zones OS（NDZ）  
- Island Air Non-Entry Doctrine OS（IAND）  
- Island Pop-up Warfare OS（IPUW）  
- Defense OS 2.0  

---

## 📚 How to Cite

K.K. (2026). *Zero-Visibility Air Safety System*.  
*KKAxiomWeaver Whitepaper Research Center.*  
https://github.com/KKAxiomWeaver/Whitepapers  

---

## 🛡 License

This work is licensed under **Creative Commons CC BY-NC-SA 4.0**.  
© 2026 K.K. (Axiom Weaver)
