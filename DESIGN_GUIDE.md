# 🎨 Ultra Lab Motion Icons 素材庫使用指南（網頁開發 & 簡報設計）

本專案已成功 Fork 至您的個人 GitHub 倉庫：
🔗 **https://github.com/yesenwu-ctrl/ultralab-anim-icons**
本機路徑：`~/Projects/ultralab-anim-icons`

---

## 🚀 快速開始：本機即時檢索展示櫃

在終端機中執行以下指令，即可在本機瀏覽器打開離線展示櫃：

```bash
open ~/Projects/ultralab-anim-icons/index.html
```

在展示櫃中您可以：
- 🔍 **視覺化預覽** 全部 36 款動態圖示（訊號、形體、軌道、進程、書寫、器物 6 大分類）。
- 🎨 **自訂顏色**：即時預覽不同主題色在深色／淺色底上的效果。
- ⚡ **調速與控制**：自訂 0.5x ~ 2.0x 動態速度。
- 📋 **一鍵複製**：點擊任一圖示，直接一鍵複製 SVG 代碼或 CSS Class。

---

## 💻 網頁與前端設計使用指南

### 1. 直接貼入 SVG（零依賴、最推薦）
複製 `icons/<名稱>.svg` 內容貼入 HTML、React、Vue 或 Svelte 中：

```html
<button class="btn">
  <!-- 直接貼入 SVG -->
  <svg class="ul-i ul-loading-orbit" viewBox="0 0 24 24" ...>...</svg>
  處理中...
</button>
```
> **優勢**：不需要載入任何外部 CSS，顏色預設為 `currentColor`（自動繼承當前文字顏色）。

### 2. 載入 CSS 樣式表（頁面大量使用時最精簡）
引入 `css/ul-icons.css`（或使用您的個人 Fork CDN）：

```html
<!-- 使用 jsDelivr 引入您的 Fork CDN -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/yesenwu-ctrl/ultralab-anim-icons@main/css/ul-icons.css">

<!-- 套用 class -->
<svg class="ul-i ul-verify" viewBox="0 0 24 24">...</svg>
```

### 3. 微互動與 CSS 變數調校
這些圖示完全支援 CSS 變數控制：

```css
/* 自訂大小與播放速度 */
.my-icon {
  --ul-size: 32px;      /* 預設 24px */
  --ul-speed: 1.5;     /* 1.5 倍速，預設 1 */
  --ul-stroke: 2;      /* 線條粗細，預設 1.5 */
  color: #3B82F6;      /* 改變圖示顏色 */
}

/* 互動效果：滑鼠懸停 (Hover) 才開始動 */
.interactive-card .ul-i {
  --ul-play: paused;
}
.interactive-card:hover .ul-i {
  --ul-play: running;
}
```

---

## 📊 簡報設計使用指南（PowerPoint / Keynote / Google Slides / Notion）

### ⚠️ 簡報軟體痛點
目前 PowerPoint、Keynote 與 Google Slides 插入 `.svg` 檔時，**不會解析 SVG 內部的 CSS `@keyframes` 動畫**，插入後會變成**靜態圖片**。

### ✅ 簡報最佳解決方案：透明背景動態 GIF
在簡報中，使用 **透明背景的動態 GIF** 是最相容、支援度最好的方式：
- 直接**拖曳（Drag & Drop）**進 PowerPoint / Keynote / Google Slides 投影片。
- 在播放簡報時會**自動無限循環播放**。
- 不挑播放環境（Windows、Mac、iPad、Web 版 PPT 皆完美播放）。

### 🖼️ 簡報官方預覽動態圖
專案 `docs/` 資料夾中附有官方動態預覽：
- `docs/preview.gif`（36 款圖示合輯循環動畫）

---

## 🔄 未來同步官方更新指令

若原作者更新了新圖示，您可以隨時在本地執行以下指令同步到您的 Fork：

```bash
cd ~/Projects/ultralab-anim-icons
git fetch upstream
git checkout main
git merge upstream/main
git push origin main
```
