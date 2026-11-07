# 心之群島：高年級心理學探索

給高年級（五、六年級）學生的 3D 心理學素養網站。6 座課程島＋1 座中央島，包含教材、島民概念、每課 4 題練習、總複習、學習進度與紀念證書。

- 正式網站：https://hw568.github.io/mind-islands/
- 專案首頁：https://github.com/hw568/mind-islands

## 網站內容

| 順序 | 課程島 | 主題 |
| --- | --- | --- |
| 01 | 情緒氣象島 | 情緒覺察、情緒調節、壓力反應 |
| 02 | 自我探索島 | 自我概念、標籤、成長型思維、同化與調適 |
| 03 | 人我橋樑島 | 事實與詮釋、我訊息、同理心、界線 |
| 04 | 記憶迴廊島 | 注意力、工作記憶、提取練習、間隔複習 |
| 05 | 思考實驗島 | 捷思、確認偏誤、從眾、說服與慢思考 |
| 06 | 心靈守護島 | 心理健康光譜、復原力、支持網絡、求助 |

中央島設有原創 Q 版嚮導「皮亞傑」、總複習與學習證書。皮亞傑以心理學家的研究概念為靈感，不是本人，也不代表任何機構。

## 教材與編輯

教材以 Markdown 為唯一來源：

- 課名、正文、測驗、島民：`site/islands/<島名>/教材.md`
- 課程順序：`site/islands/manifest.json`
- 首頁文案與控制列：`site/index.html`、`site/js/app.mjs`
- 配色與主題：`site/js/appearance.mjs`
- 裝飾與角色：`site/js/decorations.mjs`、`site/js/anime-character.mjs`
- 版面：`site/styles.css`
- 教材來源與改寫界線：`materials/教材來源.md`

修改 Markdown 後執行同步：

```powershell
python scripts/sync_content.py .
python scripts/check_content.py . --release
```

`site/data/content.json` 與 `site/content.html` 是同步產物，不要手動反向覆寫 Markdown。

## 本機預覽

```powershell
cd mind-islands
node scripts/serve.cjs
```

預設 http://127.0.0.1:8765/；可用 `$env:PORT=8799` 改用其他連接埠。伺服器會監看 Markdown。

## 發布

`main` 保存專案原始碼與教材；`gh-pages` 保存實際部署的 `site/` 內容，GitHub Pages 從 `gh-pages` 根目錄發布。

本次驗收與未測限制見 `驗收報告.md`。

## 授權與聲明

- 本站為自編素養教材，沒有引用外部教材原文。
- 內容供教學使用，不能替代心理諮商或醫療建議。
- 網站引擎與角色為原創；Three.js 0.160.0 依 MIT 授權隨附，授權文字見 `site/vendor/THREE-LICENSE.txt`。
