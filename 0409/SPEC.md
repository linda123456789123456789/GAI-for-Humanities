# 有聲單字卡 Demo - 專案規格書

## 專案概述
建立一個互動式有聲單字卡網頁應用程式，幫助學習英文單字，包含翻牌效果、分類切換和三種語速的發音功能。

## 功能需求

### 1. 單字卡內容
**正面**: 英文單字
**背面**: 中文翻譯 + 英文例句

#### 分類與內容 (共15個單字)

##### 日常問候 (Daily Greetings)
1. Hello - 你好 | "Hello, how are you today?"
2. Good morning - 早安 | "Good morning, have a great day!"
3. Thank you - 謝謝 | "Thank you for your help."
4. Goodbye - 再見 | "Goodbye, see you tomorrow!"
5. Nice to meet you - 很高興認識你 | "Nice to meet you, I'm John."

##### 交通情境 (Transportation)
1. Airport - 機場 | "Where is the airport?"
2. Bus stop - 公車站 | "The bus stop is near the park."
3. Taxi - 計程車 | "Can you call a taxi for me?"
4. Ticket - 票券 | "I need to buy a ticket."
5. Platform - 月台 | "Which platform does the train leave from?"

##### 住宿情境 (Accommodation)
1. Hotel - 飯店 | "I have a reservation at the hotel."
2. Room - 房間 | "Can I see the room first?"
3. Check-in - 辦理入住 | "What time is check-in?"
4. Breakfast - 早餐 | "Is breakfast included?"
5. Key card - 房卡 | "Here is your key card."

### 2. 互動功能

#### 翻牌功能
- 點擊單字卡即可翻轉
- 正面顯示英文單字
- 背面顯示中文翻譯和英文例句
- 使用 CSS 3D transform 實現流暢翻轉動畫

#### 分類切換
- 三個分類按鈕：日常問候、交通情境、住宿情境
- 點擊按鈕切換顯示對應分類的單字
- 當前選中的分類按鈕需有視覺反饋（高亮）

#### 發音功能（三種語速）
- 慢速 (0.7x)：適合初學者，清楚聽見每個音節
- 正常速度 (1.0x)：標準語速
- 快速 (1.3x)：模擬真實對話速度
- 使用 Web Speech API 實現
- 提供三個發音按鈕，分別對應不同語速

#### 卡片導航
- 上一張/下一張按鈕
- 顯示當前卡片編號 (如: 1/5)
- 到達首/尾卡片時按鈕置灰或循環

### 3. 使用者介面設計

#### 版面配置
```
+------------------------------------------+
|           有聲單字卡學習系統              |
+------------------------------------------+
|  [日常問候] [交通情境] [住宿情境]         |
+------------------------------------------+
|                                          |
|           +------------------+           |
|           |                  |           |
|           |   單字卡區域      |           |
|           |                  |           |
|           +------------------+           |
|                                          |
+------------------------------------------+
| [慢速🐢] [正常🔊] [快速⚡]                |
+------------------------------------------+
|      [◀上一張]  (1/5)  [下一張▶]        |
+------------------------------------------+
```

#### 設計風格
- **風格**: 現代卡片式設計搭配流暢動畫
- **配色**: 
  - 主色調：藍色系 (#4A90E2)
  - 次要色：白色背景，深灰文字
  - 強調色：橙色 (#F5A623) 用於按鈕 hover
- **動畫效果**:
  - 卡片翻轉：3D flip animation (0.6s)
  - 按鈕 hover：scale + shadow
  - 分類切換：fade in/out
- **響應式**: 在桌面和平板上都能良好顯示

### 4. 技術規格

#### 實作方式
- **單一 HTML 檔案** (language_card.html)
- HTML5 + CSS3 + Vanilla JavaScript
- 不依賴外部框架或函式庫

#### 核心技術
1. **Web Speech API** (`speechSynthesis`)
   - 語言設定: 'en-US'
   - 可調整語速: rate 參數 (0.7, 1.0, 1.3)
   
2. **CSS 3D Transforms**
   - `transform: rotateY(180deg)` 實現翻牌
   - `backface-visibility: hidden` 處理背面
   - `transition` 控制動畫時間

3. **JavaScript 事件處理**
   - Click events: 翻牌、切換分類、導航
   - 狀態管理: 當前分類、當前卡片索引

#### 資料結構
```javascript
const flashcards = {
  greetings: [
    { english: "Hello", chinese: "你好", example: "Hello, how are you today?" },
    // ...
  ],
  transportation: [ /* ... */ ],
  accommodation: [ /* ... */ ]
};
```

### 5. 瀏覽器支援
- Chrome/Edge: 完整支援
- Firefox: 完整支援
- Safari: 完整支援
- 需要現代瀏覽器支援 Web Speech API

### 6. 使用者體驗
- 首次載入顯示第一個分類的第一張卡片
- 所有互動都有即時視覺反饋
- 語音播放時顯示載入狀態（可選）
- 簡潔直觀，無需說明即可上手

## 交付成果
1. ✅ SPEC.md - 專案規格文件（本文件）
2. 📝 language_card.html - 完整可運行的單字卡應用程式

## 成功標準
- [x] 可以在瀏覽器中直接開啟 HTML 檔案運行
- [x] 所有15個單字正確顯示
- [x] 翻牌動畫流暢自然
- [x] 三個分類可以正確切換
- [x] 三種語速的發音功能正常運作
- [x] 上一張/下一張導航功能正常
- [x] 介面美觀、響應迅速
