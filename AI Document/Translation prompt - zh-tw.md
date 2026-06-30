你現在要繼續維護 Warhammer 40K: Darktide Enhanced Descriptions 的繁體中文 zh-tw 翻譯。

這是中斷後續跑任務。前一次因為 Context 超過 1M 被中斷，所以這次必須嚴格避免讀取完整大型檔案。

請使用 Agent 模式執行，並在開始前一次性要求所有必要權限，避免我睡覺後因為權限確認而停止。

你需要的權限包含：

1. 讀取：

   * AI Document\Summary - zh-tw.md
   * AI Document\Translation Table - zh-tw.md
   * COLORS_KWords_Numbers\COLORS_KWords.lua
   * COLORS_KWords_Numbers\COLORS_KWords_ru.lua
   * COLORS_KWords_Numbers\COLORS_KWords_tw.lua
   * COLORS_KWords_Numbers\COLORS_Numbers.lua
   * Main_Modules\TALENTS*.lua

2. 修改：

   * COLORS_KWords_Numbers\COLORS_KWords_tw.lua
   * Main_Modules\TALENTS*.lua
   * AI Document\Summary - zh-tw.md

3. 執行必要檢查：

   * git status
   * git diff
   * git diff --check
   * rg / grep 搜尋
   * 產生 entry index 的 script
   * luac -p，如果環境有 luac
   * 如果沒有 luac，請至少執行 git diff --check，並檢查括號、字串串接、逗號與 placeholder

任務目標：

請依據英文 en 為主、俄文 ru 為輔，產生或更新繁體中文 ["zh-tw"] 翻譯。

如果原本已有 zh-tw，但內容過時，仍然要以 en 為主重新校正。
舊 zh-tw 只能作為輔助參考。
ru 只用於理解語意或補足 en 不清楚的地方，不可讓俄文語序影響繁中翻譯。

參考資料優先順序：

1. en 原文
2. AI Document\Translation Table - zh-tw.md
3. COLORS_KWords_Numbers\COLORS_KWords_tw.lua 既有繁中詞彙
4. 舊 zh-tw 翻譯
5. ru 翻譯

Translation Table 要求：

* 翻譯參考檔已改為：
  AI Document\Translation Table - zh-tw.md
* 不要再使用 References\Translation.md。
* Translation Table 中已有的專有名詞必須優先使用。
* 如果 Translation Table 沒有，但 COLORS_KWords_tw.lua 已有一致譯名，請沿用。
* 如果發現同一個英文詞在不同地方有多種 zh-tw 譯法，不要自行強行統一，請記錄到 AI Document\Summary - zh-tw.md 的 Manual Review Required。

中斷恢復要求：

開始後第一步只能先讀取：

AI Document\Summary - zh-tw.md

請從 Summary 中的 Current Position / Last completed entry / Next entry 繼續。
不要從檔案開頭重新處理。
不要重複處理已完成的 entry，除非該 entry 在 git diff 或 Summary 中被標記為需要修復。

如果 Summary 不存在或內容不足，才建立新的 entry index，從尚未完成的檔案開始。

嚴格 Context 限制：

禁止一次讀取完整檔案內容。
禁止把整個 TALENTS_*.lua 載入 context。
禁止把整個 COLORS_KWords_tw.lua 載入 context。
禁止使用「讀取大段文件後批量替換整個檔案」的方式。
禁止為了比對而一次讀取完整 en / ru / zh-tw 檔案。
禁止說「我會讀取更大的文件段落後批量處理」。

請改用 bounded chunk processing。

正確流程：

1. 先讀 AI Document\Summary - zh-tw.md。
2. 確認下一個要處理的檔案與 entry。
3. 建立或更新 entry index。
4. entry index 只能包含：

   * file path
   * localization key
   * start line
   * end line
   * 是否已有 zh-tw
   * 是否已完成
5. entry index 不可以包含完整 en / ru / zh-tw 內容。
6. 每批最多處理 5 個 localization entry。
7. 每次只讀取這 5 個 entry 的完整內容。
8. 逐一產生或更新 zh-tw。
9. 每完成 1 個 entry，就立刻更新 AI Document\Summary - zh-tw.md。
10. 每完成 5 個 entry，就執行 git diff --check。
11. 再處理下一批。

如果你認為需要讀更大的範圍，必須先限制在同一個 section，例如 BLITZ、AURA、ABILITY、KEYSTONE。
即使是 section，也不可讀取整個檔案。
每次最多仍只能載入 5 個 entry 的完整內容。

localization entry 定義：

一個 entry 的範圍類似：

["loc_xxx"] = {
en = "...",
ru = "...",
["zh-tw"] = "...",
},

請以完整 entry 為最小修改單位。
不可切斷 entry。
不可跨 entry 批量替換。

Lua 格式要求：

必須完整保留以下內容，不可翻譯、不可刪除、不可改名：

* localization key，例如 ["loc_talent_xxx"]
* en
* ru
* CKWord(...)
* CNumb(...)
* CPhrs(...)
* CNote(...)
* Dot_nc
* Dot_green
* Dot_red
* {damage:%s}
* {talent_name:%s}
* {cooldown:%s}
* 所有 {xxx:%s} placeholder
* "%s"
* \n
* {#color(...)}
* {#reset()}
* 註解中的日期與原始標記
* Lua 字串串接符號 ..

只新增或更新 ["zh-tw"]。
除非修復明顯語法錯誤，否則不要修改 en / ru。

placeholder 檢查：

每個 zh-tw 必須保留 en 中所有 placeholder。
例如：

* {damage:%s}
* {talent_name:%s}
* {cooldown:%s}
* {duration:%s}
* {chance:%s}

zh-tw 不可以新增不存在的 placeholder。
zh-tw 不可以刪除 en 既有 placeholder。
zh-tw 不可以改變 placeholder 名稱。

Lua 字串串接檢查：

請確認每個 zh-tw：

* 字串引號完整
* 每行串接 .. 正確
* 最後一行逗號正確
* \n 沒有被破壞
* CKWord / CNumb / CPhrs / CNote 括號完整
* 不要把中文插進 function name 或 color key 裡

繁中翻譯風格：

請使用台灣繁體中文。
語氣要像遊戲內技能說明，精簡、清楚、可讀。
避免中國用語。
避免過長句子。
避免直譯造成難讀。

常用詞方向：

* Damage：傷害
* Toughness：韌性
* Peril：危厄
* Stagger：踉蹌 / 使敵人踉蹌，依上下文使用
* Stun：擊暈
* Electrocute / Electrocuted / Electrocution：電擊 / 被電擊 / 電擊效果
* Soulblaze：靈魂烈焰，除非 Translation Table 指定其他譯名
* Warp Charge：亞空間充能，除非 Translation Table 指定其他譯名
* Combat Ability：戰鬥技能
* Blitz：閃擊技能
* Coherency：連結，除非 Translation Table 指定其他譯名
* Weakspot：弱點
* Critical Hit / Crit：暴擊
* Carapace：甲殼護甲
* Flak：防彈護甲
* Monstrosity：巨獸
* Elite：精英
* Specialist：專家

如果 AI Document\Translation Table - zh-tw.md 與上方詞彙不同，請以 Translation Table 為準。

UI 可讀性與換行要求：

這是遊戲內說明文字，不是文件翻譯。
請控制句子長度，避免一整段在遊戲 UI 中被自動斷成難讀的長行。

請優先使用語意斷行。
每個資訊點盡量一行。
每行中文盡量控制在約 18～28 個中文字以內。
長句請拆成多行。
段落之間保留空白行。

例如不要翻成：

釋放一道會在敵人之間跳躍並造成持續電擊傷害與高踉蹌值的鏈式生物閃電，充能後會造成更高傷害並更快跳躍。

應改成：

釋放一道鏈式生物閃電，
在敵人之間跳躍。

造成低量持續電擊傷害，
並造成高額踉蹌。

次要充能攻擊會提高傷害，
並更快跳躍至其他敵人。

短條件可以放同一行。
長條件必須拆行。

例如短條件：

..Dot_red.." 無法使巨獸踉蹌。"

例如長條件：

..Dot_red.." 無法使下列目標踉蹌：\n"
.."   "..Dot_red.." 突變者、歐格林、巨獸，\n"
.."   "..Dot_red.." 或啟用虛空盾的敵人。"

不要為了縮短而刪除重要遊戲機制。

Summary 要求：

請使用並持續更新：

AI Document\Summary - zh-tw.md

這個檔案是中斷恢復與人工確認用。
每處理完一個 entry，如果有任何需要紀錄的內容，立刻寫入 Summary。
不要等整批完成才寫，避免中斷後資訊遺失。

Summary 格式請維持或補齊為：

# Translation Summary - zh-tw

## Progress

* [ ] COLORS_KWords_Numbers/COLORS_KWords_tw.lua
* [ ] Main_Modules/TALENTS/TALENTS_Arbites.lua
* [ ] Main_Modules/TALENTS/TALENTS_Ogryn.lua
* [ ] Main_Modules/TALENTS/TALENTS_Psyker.lua
* [ ] Main_Modules/TALENTS/TALENTS_Scum.lua
* [ ] Main_Modules/TALENTS/TALENTS_Veteran.lua
* [ ] Main_Modules/TALENTS/TALENTS_Zealot.lua

如果實際資料夾中檔案數量不同，請以實際 Main_Modules/TALENTS/*.lua 為準，並在 Summary 中列出實際處理到的檔案。

## Current Position

* File:
* Last completed entry:
* Next entry:

## Manual Review Required

| File | Key | Issue | Suggested zh-tw | Reason |
| ---- | --- | ----- | --------------- | ------ |

## Terminology Decisions

| EN | zh-tw | Source |
| -- | ----- | ------ |

## Changed Files

*

## Validation

* git diff --check:
* luac -p:
* Notes:

需要寫入 Manual Review Required 的情況：

1. en 與 ru 意思明顯不一致。
2. 舊 zh-tw 與 en 差異很大，但不確定是否是設計性調整。
3. Translation Table 沒有對應詞，而且是 Warhammer / Darktide 專有名詞。
4. 英文原文可能有 bug、語法錯誤或前後矛盾。
5. UI 長度可能仍偏長，需要人工確認。
6. 不確定 Stagger / Stun / Suppression / Brittleness / Rending / Finesse 等詞要如何固定翻譯。
7. 任何你是「推測」的翻譯。

品質檢查要求：

每處理完一個 entry：

1. 更新 AI Document\Summary - zh-tw.md。
2. 確認 Current Position 已移動到下一個 entry。
3. 確認 Manual Review Required 是否需要新增。

每處理完 5 個 entry：

1. 執行 git diff --check。
2. 檢查該批 zh-tw 是否所有 placeholder 都完整保留。
3. 檢查 CKWord / CNumb / CPhrs / CNote 是否沒有被翻譯或破壞。
4. 檢查 Lua 字串串接是否沒有斷裂。
5. 如果有 luac，執行 luac -p。

每處理完一個檔案：

1. 執行 git diff --check。
2. 如果有 luac，執行 luac -p 該檔案。
3. 更新 Summary 的 Progress。
4. 更新 Changed Files。
5. 更新 Validation。

最後完成時，請在 Summary 最後新增：

## Final Result

* Completed files:
* Entries updated:
* Entries skipped:
* Manual review count:
* Validation result:
* Remaining risk:

不要自動 commit。
不要自動 push。
完成後只保留修改在 working tree，讓我醒來後 review git diff。

重要限制：

* 不要刪除 en / ru。
* 不要大量重排整個檔案。
* 不要改變 localization key。
* 不要改變 placeholder。
* 不要把簡體中文寫進 zh-tw。
* 不要把俄文譯名直接音譯成中文，除非 Warhammer 專有名詞確實需要。
* 不要為了縮短句子而刪除重要遊戲機制。
* 不確定就寫入 Summary，不要假裝確定。

開始前請先回報你將採用的流程，並明確確認：

1. 你會先讀 AI Document\Summary - zh-tw.md。
2. 你會使用 AI Document\Translation Table - zh-tw.md 作為翻譯表。
3. 你不會讀取完整大型檔案。
4. 你會使用 entry index + 每批最多 5 個 entry 的方式繼續。
5. 你會每完成一個 entry 就更新 Summary。
