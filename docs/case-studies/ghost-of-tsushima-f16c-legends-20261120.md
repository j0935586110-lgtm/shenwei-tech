# 實機案例：舊 Xeon 缺少 F16C，成功登入 PSN 並進入《對馬戰鬼》奇譚模式
**Verified case (partial) | Ghost of Tsushima DIRECTOR'S CUT | 2026-11-20**

> **重要：這不是萬用修復，也還不是「多人連線完整驗收」。** 實機已出現 PlayStation 登入歡迎通知，玩家親自回報成功進入奇譚模式。仍未驗證多人配對、完整合作關卡、長時間穩定性與 FPS。

## 為什麼這案例值得分享？
遊戲官方要求 CPU 支援 AVX 和 F16C。舊 CPU 缺少 F16C 時，單靠更新顯示卡無法補足指令集。有些玩家為了啟動單人遊戲而移除 PlayStation SDK，結果無法玩奇譚模式。本案例是在**保留官方 PlayStation PC SDK** 的情況下，透過 Intel SDE 模擬所缺的指令，實際登入並進入奇譚選單。

## 實機規格（單機案例，不代表其他機型也能成功）
| 項目 | 規格 |
|---|---|
| CPU | Intel Xeon E3-1240 v1（缺少原生 F16C） |
| 主機板 | ASUS B75M-A |
| GPU | NVIDIA GTX 1060 5 GB |
| RAM | DDR3 8 GB |
| OS | Windows 10 Pro 64-bit |
| Game | Steam 正版 Ghost of Tsushima DIRECTOR'S CUT，執行檔 v1053.9.0623.1807 |
| Intel SDE | 10.13.1（2026-07-28） |
| 結果 | 遊戲可執行、PSN 登入通知出現、玩家回報進入奇譚模式 |
| 未驗證 | 多人配對、完成合作任務、穩定效能 |

## 重現步驟（PowerShell，請修改路徑）
1. 使用**正版** Steam 遊戲、更新至適用版本，確認奇譚 DLC 已加入 Steam 帳號。保留官方 PlayStation PC SDK，準備本人合法的 PlayStation 帳號。
2. 從 [Intel 官方下載頁](https://www.intel.com/content/www/us/en/download/684897/intel-software-development-emulator.html) 取得 Intel SDE 10.13.1，依官方授權條款使用。**不要下載來源不明的補丁或改版遊戲執行檔。**
3. 確保遊戲已完全關閉，調整以下兩個路徑，執行：

```powershell
$Sde = 'C:\Tools\IntelSDE\sde.exe'
$Game = 'D:\Steam\steamapps\common\Ghost of Tsushima DIRECTOR''S CUT\GhostOfTsushima.exe'
if (!(Test-Path -LiteralPath $Sde)) { throw "SDE not found: $Sde" }
if (!(Test-Path -LiteralPath $Game)) { throw "Game not found: $Game" }
& $Sde -no-follow-child -hsw -f16c -- $Game
```

4. 確認 PSN 登入狀態，再進入奇譚模式。**不要移除 Sony SDK，也不要替換官方遊戲檔案**。如果登入、配對或進入關卡失敗，請分開回報在哪個階段發生。

`-hsw` 選擇 SDE 的 Haswell 模擬設定；`-f16c` 啟用 F16C 模擬；`-no-follow-child` 不追蹤新建子程序。這組參數確實在上述實機使用，但**尚未做控制變因測試**，不能聲稱其中任何單一參數已被證明是 PSN 成功的唯一原因。

## 限制與風險
測試時 8GB RAM 實機曾出現嚴重記憶體換頁，遊戲與 Sony SDK 在先前回合有 `0xC0000005` 崩潰紀錄。因此**這不是穩定流暢玩奇譚的證明**，也不建議把模擬器當成原生支援 F16C CPU 的長期替代品。不提供任何遊戲、Intel SDE、PlayStation SDK 二進位檔或破解器。

## 證據階段
- [x] 使用 SDE 啟動遊戲
- [x] 畫面出現 Sony PlayStation 登入歡迎通知（不公開帳號名稱）
- [x] 玩家回報已進入奇譚模式
- [ ] 成功配對另一位玩家並進入多人關卡
- [ ] 完成一場多人任務
- [ ] 記錄長時間 FPS、崩潰與記憶體用量
- [ ] 由其他玩家的不同電腦獨立重現

## 有相同問題嗎？
可以透過這個 GitHub 專案的 Issues 提交**非敏感**資訊：CPU、顯卡、RAM、Windows 與遊戲版本、卡住的階段、已嘗試的方法、錯誤碼。**不要公開 Steam/PSN ID、帳號密碼、序號、金鑰、IP 或未遮蔽的 Crash Dump。** 這是社群技術協助，不保證能修復任何裝置。

## 來源
- [Nixxes：AVX 與 F16C 需求](https://support.nixxes.com/hc/en-us/articles/49254543182227-This-game-requires-a-CPU-that-supports-F16C-instructions)
- [Nixxes Patch 4：SDK 2.5 支援缺少 AVX2 的 CPU](https://support.nixxes.com/hc/en-us/articles/49255497891603-Ghost-of-Tsushima-Director-s-Cut-PC-Patch-4-Release-Notes)
- [Intel SDE 官方文件](https://www.intel.com/content/www/us/en/developer/articles/tool/software-development-emulator.html)
- [PlayStation PC 支援與奇譚條件](https://www.playstation.com/en-us/support/games/ghost-of-tsushima-pc/)

*Independent community case study by 神瑋科技 SHENWEI TECH; not endorsed by Sony, Sucker Punch, Nixxes, Intel or Valve.*
