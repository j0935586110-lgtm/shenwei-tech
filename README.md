# 神瑋科技 SHENWEI TECH 官方網站

> **核心標語**：「讓每個人都擁有自己的 AI 代理」  
> **創辦人**：傅建瑋（Chien-Wei Fu）  
> **線上發布網址 (GitHub Pages)**：[https://j0935586110-lgtm.github.io/shenwei-tech/](https://j0935586110-lgtm.github.io/shenwei-tech/)

---

## 關於神瑋科技

神瑋科技（SHENWEI TECHNOLOGY）由 AI 系統架構師**傅建瑋**創立，專注於引領個人與企業跨越簡單對話式 AI 的限制，建構具備思考規劃、工具調用（Model Context Protocol / MCP）、人機協同審批護欄與自主持有的 **自主 AI 代理（Autonomous Agent）** 與高效自動化工作流。

### 四大業務核心基石

1. **AI 代理開發（Autonomous AI Agent Development）**
   - 多代理協同工作流（Multi-Agent Swarms）
   - MCP 伺服器與專屬工具鏈接（API / Database / Webhook）
   - Ed25519 數位簽章與 Human-in-the-Loop 安全審批佇列
   - 100% 原始碼與部署設定完全移交客戶

2. **企業 AI 化（Enterprise AI Transformation）**
   - 企業工作流審計與 AI 導入可行性診斷
   - 企業私有化向量知識庫（GraphRAG / 混合檢索）
   - 地端大型語言模型部署（Local LLM / Ollama / vLLM）
   - 商業隱私保護與敏感資料脫敏隔離

3. **智慧網站（Intelligent Web Solutions）**
   - 現代化 AI 原生自適應互動界面
   - 零依賴極速載入（JAMstack / Edge Deployment）
   - 無障礙設計（WCAG AA）與完整 SEO 結構化資料
   - 動態內容引擎與個人化導流轉換漏斗

4. **AI 實戰教育（Hands-on AI Education）**
   - 高階決策者「AI 戰略與商業決策」研討班
   - 工程團隊「Agentic AI 與工作流自動化」實戰工作坊
   - 以客戶真實業務題目為實作教案，完訓即交付上線可運行程式碼

---

## 網站架構與互動特色

- **高科技深色 / 瑞士編輯風明亮 雙主題自由切換**：支援系統偏好偵測與 `localStorage` 記憶。
- **神瑋 AI 代理即時終端模擬器（Interactive Agent Simulator）**：展示 Agent 接收指令、意圖拆解、MCP 工具調用、安全護欄校驗到成果輸出的完整毫秒級執行過程。
- **企業 AI 導入效益與可行性評估器（Interactive Readiness Calculator）**：透過 3-Step 互動問答，即時生成客製化導入方案與預期工時釋放試算。
- **嚴謹四大導入閉環流程**：清楚呈現「需求盤點 → PoC 雛形 → 敏捷整合 → 驗收賦能」之時程與交付標準。
- **透明常見問答（FAQ）手風琴**：針對原始碼歸屬、資料隱私、維運門檻等實務關切問題提供詳盡解答。
- **官方 LINE 即時諮詢通道與預約表單**：支援一鍵複製洽詢摘要、複製官方信箱，無縫引導商務對接。

---

## 本機預覽方式

本專案為高效純靜態網頁架構，免安裝龐大 Node.js 依賴：

### 方法一：Python 內建 HTTP 伺服器
```bash
python3 -m http.server 8080
```
開啟瀏覽器訪問 `http://localhost:8080`。

### 方法二：直接瀏覽器開啟
直接以雙擊或瀏覽器開啟 `index.html` 即可完整體驗所有功能。

---

## 自動化部署與 CI/CD

本專案透過 `.github/workflows/deploy.yml` 實現 GitHub Actions 自動化持續部署至 GitHub Pages：
- 每次推送（Push）至 `main` 分支即自動觸發 Pages 構建與部署。
- 無需外部伺服器維護，全球 CDN 高速分發。

---

## 版權與聯絡資訊

- **公司名稱**：神瑋科技 SHENWEI TECH
- **創辦人**：傅建瑋
- **官方信箱**：[contact@shenwei.tech](mailto:contact@shenwei.tech)
- **官方網址**：[https://j0935586110-lgtm.github.io/shenwei-tech/](https://j0935586110-lgtm.github.io/shenwei-tech/)
