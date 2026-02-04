# 💝 Valentine's Pong Gacha - 愛的博弈

## 🎮 遊戲簡介

這是一個融合了 **Pong遊戲** + **扭蛋抽卡** + **收藏系統** 的四層式情人節禮物體驗。你的男朋友需要通過打Pong遊戲賺取Token，然後用Token抽取你手繪的卡片，最終解鎖終極大獎 - 一個真實世界的寶藏線索！

---

## 🎯 四層體驗設計

### Layer 1: 🎁 神秘信封 (Landing)
- 打開網頁會看到一個神秘的挑戰宣言
- 點擊"解鎖"按鈕進入遊戲
- 營造儀式感和期待感

### Layer 2: 🎮 Token 賺取 (Game)
- 經典Pong遊戲 with 浪漫主題
- 贏一球 = +1 Token 💰
- 高速反彈（1.5x+速度）= +2 Tokens（Bonus！）
- Token永久保存（localStorage）
- 可隨時暫停/繼續/重新開始

### Layer 3: 🎰 扭蛋抽卡 (Gacha)
- 5 Tokens = 1次抽獎
- 4個稀有度等級：R / SR / SSR / UR
- 保底機制：5抽必出UR（如果之前沒抽到）
- 動畫效果：震動、翻牌、光芒
- 抽到的卡片自動保存

### Layer 4: 🏆 終極大獎 (Grand Prize)
- 抽到UR卡時觸發特殊全屏動畫
- 顯示你最浪漫的告白訊息
- 顯示真實世界寶藏的線索
- 他可以繼續玩遊戲收集其他卡片

---

## 📊 Gacha 機率系統

| 稀有度 | 機率 | 卡片數量 | 設計主題 |
|--------|------|----------|----------|
| **R** (普通) | 40% | 4張 | 日常小確幸 |
| **SR** (稀有) | 40% | 3張 | 浪漫特別時刻 |
| **SSR** (史詩) | 15% | 2張 | 永恆承諾 |
| **UR** (傳說) | 5% | 1張 | **終極獎勵（你的告白）** |

**保底機制：** 如果5次抽獎都沒抽到UR，第5次必定獲得UR！

---

## 💰 Token 系統

### 如何賺取 Tokens
1. **贏球：** 每贏AI一球 = +1 Token
2. **神鬼回擊：** 當球速 ≥ 1.5倍時成功反彈 = 額外 +1 Token（總共+2）
3. **持久戰：** 遊戲每10秒球速+10%，讓挑戰更刺激

### Token 花費
- 每次抽獎消耗 5 Tokens
- Tokens永久保存，即使關閉網頁也不會丟失

---

## 🎨 素材清單

### ✅ 已存在的素材
- `assets/heart.png` - 愛心球
- `assets/left_top.PNG` - 左上角裝飾
- `assets/right_top.PNG` - 右上角裝飾
- `assets/left_bottom.PNG` - 左下角裝飾
- `assets/right_bottom.PNG` - 右下角裝飾

### 📝 需要繪製的素材

#### 高優先級（必須）
- `assets/cards/UR1.png` - **UR卡：摯愛之心**（200x300px）
  - 這是最重要的！終極大獎卡片

#### 中優先級（強烈建議）
- `assets/cards/SSR1.png` - SSR卡：永恆誓言
- `assets/cards/SSR2.png` - SSR卡：星空之約
- `assets/cards/SR1.png` - SR卡：心動瞬間
- `assets/cards/SR2.png` - SR卡：浪漫約會
- `assets/cards/SR3.png` - SR卡：深情告白

#### 低優先級（推薦）
- `assets/cards/R1.png` - R卡：初次相遇
- `assets/cards/R2.png` - R卡：溫暖微笑
- `assets/cards/R3.png` - R卡：日常時光
- `assets/cards/R4.png` - R卡：甜蜜問候

#### 可選
- `assets/envelope.png` - 開場信封（400x300px）

**詳細繪製指南請查看：** [ARTWORK_GUIDE.md](ARTWORK_GUIDE.md)

---

## 🚀 如何運行

### 本地測試
```bash
cd /Volumes/T7/pong_val
python3 -m http.server 8080
```

然後在瀏覽器打開：`http://localhost:8080`

### 部署到 GitHub Pages
1. 創建 GitHub 倉庫
2. 上傳所有文件（包括 `assets` 文件夾）
3. 在倉庫設置中啟用 GitHub Pages
4. 分享鏈接給你的男朋友

---

## 🎮 遊戲操作說明

### 電腦端控制
- **單人模式：** W/S 鍵控制你的擋板
- **雙人模式：**
  - 玩家1：W/S 鍵
  - 玩家2：上下方向鍵

### 手機端控制
- 觸摸拖動擋板

### 遊戲按鈕
- **暫停/繼續：** 暫停遊戲不會影響Timer
- **重新開始：** 重置分數和速度，但Token保留
- **抽獎：** 打開扭蛋機介面（需要5個Token）
- **收藏：** 查看已解鎖的所有卡片

---

## 🔧 技術實現

### 核心功能
- ✅ 4層遊戲狀態系統（LANDING → GAME → GACHA → PRIZE）
- ✅ Token系統 with localStorage持久化
- ✅ Gacha機率系統（40/40/15/5 with 5抽保底）
- ✅ 卡片收藏系統（10張卡片，顯示收集進度）
- ✅ 動畫效果（震動、翻牌、光芒、心跳）
- ✅ 音效系統（擊球、得分、大獎）
- ✅ 響應式設計（支持手機和電腦）
- ✅ 佔位圖系統（即使沒有實際圖片也能正常運行）

### 數據持久化
所有進度都保存在瀏覽器的 localStorage：
- `loveTokens` - Token數量
- `unlockedCards` - 已解鎖的卡片列表
- `pityCounter` - 保底計數器
- `urUnlocked` - UR卡是否已解鎖

---

## 🎨 自定義內容

### 修改告白訊息
在 [index.html](index.html) 中找到 `showGrandPrize()` 函數：

```javascript
prizeMessage.innerHTML = `
    <span class="heart">💝</span><br>
    你贏得了我全部的愛！<br>  ← 修改這裡
    <span class="heart">💝</span>
`;

prizeClue.innerHTML = `
    <strong>🎁 真實世界的寶藏線索：</strong><br>
    「禮物就藏在...」<br>  ← 修改這裡
    <br>
    <small>情人節快樂，我的寶貝 ❤️</small>
`;
```

### 修改浪漫訊息
在 [index.html](index.html) 中找到 `messages` 陣列：

```javascript
const messages = [
    "Every point you score makes my heart skip a beat 💕",
    "You're doing amazing, sweetheart! 🌹",
    // 添加更多訊息...
];
```

---

## 📱 測試清單

### 基礎測試
- [ ] 打開網頁，看到Landing畫面
- [ ] 點擊"解鎖"按鈕，進入遊戲
- [ ] 看到Token顯示區域（右上角）
- [ ] 看到收藏按鈕（左上角）

### 遊戲測試
- [ ] 能用W/S鍵控制擋板
- [ ] 贏球後Token +1
- [ ] 高速球反彈後Token +2
- [ ] 暫停/繼續功能正常

### Gacha測試
- [ ] 累積5個Token後"抽獎"按鈕可點擊
- [ ] 點擊後進入扭蛋機畫面
- [ ] 點擊"抽一次"看到震動動畫
- [ ] 顯示抽到的卡片（有顏色的佔位圖）
- [ ] Token正確扣除（-5）

### 收藏測試
- [ ] 點擊"收藏"按鈕打開收藏冊
- [ ] 看到所有10張卡片（已解鎖的是彩色，未解鎖是灰色？）
- [ ] 顯示收集進度（例如：3/10, 30%）

### UR大獎測試
- [ ] 抽到UR卡後自動跳轉大獎畫面
- [ ] 顯示告白訊息和寶藏線索
- [ ] 點擊"繼續收集卡片"回到遊戲

### 持久化測試
- [ ] 關閉網頁，重新打開
- [ ] Token數量保留
- [ ] 已解鎖的卡片保留

---

## 🐛 疑難排解

### Q: 打開網頁沒有看到任何東西
A: 檢查瀏覽器控制台（F12）是否有錯誤訊息

### Q: 圖片沒有顯示
A:
1. 確認圖片文件在正確的位置（`assets/cards/`）
2. 確認文件名完全匹配（大小寫敏感！）
3. 清除瀏覽器緩存後重新加載
4. 如果沒有圖片，遊戲會顯示彩色佔位圖（正常現象）

### Q: Token沒有保存
A: 確認瀏覽器允許 localStorage（隱私模式可能會禁用）

### Q: 抽不到UR卡
A:
- 機率為5%，平均需要抽20次
- 保底機制：最多5抽必定獲得UR
- 可以在控制台運行 `game.pityCounter` 查看當前保底進度

---

## 💝 給你男朋友的訊息

親愛的，

這是我為你準備的情人節特別禮物。我花了很多時間設計這個遊戲，希望你能感受到我的心意。

每一張卡片都是我對你的愛意的表達。希望你在收集這些卡片的過程中，能回想起我們一起度過的美好時光。

當你抽到那張金色的UR卡時，那就是我想對你說的話。

Happy Valentine's Day, my love! ❤️

---

## 📚 文件索引

- [index.html](index.html) - 主遊戲文件
- [ARTWORK_GUIDE.md](ARTWORK_GUIDE.md) - 素材繪製指南
- [README.md](README.md) - 本文件（項目說明）

---

## 🎯 後續優化建議（可選）

如果你想進一步完善：

1. **音樂：** 添加背景音樂（可用 Audio API）
2. **特效：** 抽到UR時添加粒子特效
3. **動畫：** 信封打開動畫（CSS或SVG）
4. **多語言：** 中英文切換
5. **分享功能：** 讓他可以分享收藏進度
6. **成就系統：** 解鎖全部卡片後給予特別獎勵

---

**Created with ❤️ for a very special Valentine's Day**
