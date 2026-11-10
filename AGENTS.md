# AGENTS.md - Julie 的閱讀書櫃 (Julie's Reading Bookshelf) 專案協同開發規範

## 1. 專案概述與目標
本專案為個人閱讀知識庫與心得展示網站「Julie 的閱讀書櫃 (Julie's Reading Bookshelf)」。旨在透過分類目錄整理書籍，展示書籍封面圖、元資料、重點摘要、閱讀筆記與個人真實心得。全站所有頁面皆採用純 HTML 搭配 CSS 構建。

## 2. 視覺與 UI 風格規範
- **風格定位**：明亮、溫暖、文青手寫手帳風（Hand-drawn & Notebook Style）。
- **字型規範**：
  - 中文主字型：Google Fonts 文青手寫字體「LXGW WenKai TC」（霞鶩文楷）。
  - 英文手寫字型：Google Fonts「Caveat」。
  - 預設後備字型：`'LXGW WenKai TC', 'Caveat', cursive, system-ui, -apple-system, sans-serif`。
- **色彩與背景計畫**：
  - 背景：暖米色手帳紙張（#F7F4EE），透過 CSS `linear-gradient` 疊加微弱的淡灰色手帳方格/橫線紋理（Grid / Notebook Paper Pattern），消除畫面過於死白或太空的生硬感。
  - 背景插圖與浮水印：背景加入微透正版吉伊卡哇（Chiikawa）可愛卡通角色插圖（吉伊卡哇、小八貓、兔兔）以及蝴蝶結（Bows）、櫻桃（Cherries）等手帳浮水印元素（半透明 opacity: 0.10 ~ 0.13、pointer-events: none，與暖米色方格紙紋理完美融合，營造溫馨手帳氛圍且不干擾文字閱讀與滑鼠操作）。
  - 卡片底色：米白手帳紙張色（#FFFDF9）。
  - 主文字與線條：深棕色（#3D352E）、手繪感灰黑，避免過於強烈的高對比純黑。
  - 強調色：柔和莫蘭迪色系（暖橘 #E07A5F、手繪螢光黃劃線效果 #FFF3B0、莫蘭迪綠 #81B29A）。
- **字型與元件**：
  - 區塊採用圓角手繪邊框、和紙膠帶（Washi Tape）、貼紙標籤、拍立得造型書籍封面卡片。
  - **標題下方金句樣式**：若書籍頁面或卡片包含精選金句，必須置於主標題正下方，採用比主標題較小的字體與斜體/次要顏色（例如：`font-size: 0.9em; opacity: 0.85; font-style: italic;`）呈現。不得單獨設立額外的金句區塊。
- **卡片必備標籤元件**：
  - 1-5 星評分（如：★★★★☆）

## 3. 目錄與檔案結構
專案依據 11 大書籍分類建立資料夾結構，所有單頁皆為純 HTML（`.html`）：

```text
my-reading-bookshelf/
├── AGENTS.md                 # Agent 協同開發與內容擴充規範
├── index.html                # 網站首頁（Julie 的閱讀書櫃首頁總覽與最新心得）
├── assets/
│   ├── css/
│   │   └── style.css         # 手繪風主 CSS 樣式表（含 Google Fonts 與方格紙紋理）
│   ├── js/                   # 互動腳本
│   └── images/               # 靜態圖片資源（如書籍封面）
└── content/                  # 書籍類別資料夾
    ├── lit-fiction/          # 文學小說（Lit/Fiction、輕小說、漫畫）
    ├── bus-finance/          # 商業理財（Bus/Finance）
    ├── psych-selfhelp/       # 心理勵志（Psych/Self-Help）
    ├── hum-socsci/           # 人文社會（Hum/SocSci）
    ├── nat-sci/              # 自然科普（NatSci）
    ├── art-design/           # 藝術設計（Art/Design）
    ├── lifestyle/            # 生活風格（Lifestyle、飲食、旅遊）
    ├── parenting-kids/       # 親子教養 / 兒童與青少年（Parenting、Kids/YA）
    ├── language-exams/       # 語言學習與考試（Lang Learn、Exams）
    ├── comp-info/            # 電腦資訊（Comp/Info）
    └── religion-divination/  # 宗教命理（Rel/Divination）
```
