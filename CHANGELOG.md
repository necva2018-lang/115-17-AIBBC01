# 開發紀錄 — AI BBC Landing Page

**專案名稱：** AI轉型不能等，3小時帶你無痛上手  
**主辦單位：** AI BBC  
**開發工具：** Claude Code（claude.ai/code）  
**版本：** v1.0.0  
**完成日期：** 2026-04-23

---

## 專案說明

為 AI BBC 推廣課程建立單頁式 Landing Page，目標讓中高齡潛在學員在 60 秒內看完核心訊息後完成報名，或透過 LINE 分享給親友。

**報名連結：** https://www.surveycake.com/s/l78MP

---

## 開發歷程

### v1.0.0（2026-04-23）首次發布

#### 技術架構
- 純 HTML + CSS 單一檔案（`index.html`）
- 不依賴任何外部框架或 JS 函式庫
- Mobile-First 響應式設計
- 斷點：576px / 768px / 1200px

#### 設計風格
- **主題：** 手繪素描風格（Hand-drawn / Sketchy）
- **字體：** Caveat（標題）、Patrick Hand（內文）
- **背景：** 素描本橫線紋理 + SVG 噪點紙張感
- **特效：** 不完美圓角卡片、微旋轉、手繪波浪 SVG 分隔線、feTurbulence 濾鏡

#### 色彩系統
| 用途 | 色碼 |
|------|------|
| 主墨色 | `#1E140A` |
| 強調紅（CTA） | `#C94830` |
| 草綠 | `#4A7240` |
| 琥珀黃 | `#E8B820` |
| 紙張底色 | `#FDFBF4` |

#### 頁面結構（8 區塊）
| # | ID | 功能 |
|---|----|------|
| 01 | `#section-hero` | 主視覺：標語、標題、CTA 按鈕、右側情境照 |
| 02 | `#section-urgency` | 急迫性警示：4 痛點 + 翻轉語 + 氛圍三格圖 |
| 03 | `#section-benefits` | 課程好處：6 張卡片 + 寬幅照 + 長期好處欄 |
| 04 | `#section-outline` | 課程大綱：6 單元手風琴（手機全展開） |
| 05 | `#section-info` | 開課資訊：日期、費用、場地、繳費方式 |
| 06 | `#section-who` | 適合誰：兩欄對比 |
| 07 | `#section-guarantee` | 三重保障：可回訓、LINE 群、講義 |
| 08 | `#section-cta` | 報名 CTA：見證照、3 步驟、QR Code、按鈕 |

#### 圖片系統
- 全部圖片框統一 `aspect-ratio: 1/1`，`object-fit: cover` 自動填滿
- 共 10 張圖片位置（Hero、氛圍×3、寬幅、場地、教材、學員見證×3）
- 手繪素描邊框 + 黃底貼紙標籤

#### 實際填入資料
| 項目 | 內容 |
|------|------|
| 銀行帳號 | 玉山銀行 808 — 0700-717-106441 |
| 戶名 | 群澄資訊有限公司 |
| LINE 聯絡 | https://lin.ee/5i7hCx0 |
| 聯絡電話 | 049-2903412 |
| Google 地圖 | https://maps.app.goo.gl/ocUj4dEH7Jk6svnD6 |
| QR Code | LINE 官方 QR（連結至報名表） |

#### 行動版專屬功能
- Sticky 底欄：固定橘色報名按鈕（`position: fixed; bottom: 0`）
- 點擊電話號碼自動撥打（`tel:` 協議）
- 點擊 LINE 直接開啟 LINE App（`lin.ee` 短網址）
- QR Code 區段在手機版隱藏，改以直接連結按鈕取代
- 課程大綱手機版全部展開（JS 偵測 viewport 寬度）

---

## 檔案結構

```
115-17-AIBBC01/
├── index.html                    # 主頁面（HTML + CSS 全部內嵌）
├── CLAUDE.md                     # Claude Code 開發說明
├── CHANGELOG.md                  # 本開發紀錄
└── LandingPage_完整開發說明書.docx  # 原始需求規格書
```

---

## 待辦事項（未來版本）

- [ ] 替換 OG 預覽圖（`og-image.jpg`，1200×630px）
- [ ] 加入 Google Analytics 追蹤碼
- [ ] 加入 LINE Tag 廣告再行銷像素
- [ ] 確認 LINE 內建瀏覽器相容性測試
- [ ] Lighthouse 效能測試（目標 LCP ≤ 2.5s）

---

*本頁面由 Claude Code 輔助生成，版權所有 © 2026 AI BBC*
