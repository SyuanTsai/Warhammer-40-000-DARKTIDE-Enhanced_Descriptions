# Translation Summary

## Progress

- [x] Main_Modules/TALENTS/TALENTS_Arbites.lua  (83/83 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Ogryn.lua    (88/88 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Psyker.lua   (79/79 entries, git diff --check PASS)
- [ ] Main_Modules/TALENTS/TALENTS_Scum.lua     (entries TBD)
- [ ] Main_Modules/TALENTS/TALENTS_Veteran.lua  (entries TBD)
- [ ] Main_Modules/TALENTS/TALENTS_Zealot.lua   (entries TBD)

Total entries across all files: ~503

## Current Position

- File: Main_Modules/TALENTS/TALENTS_Ogryn.lua
- Last completed entry: loc_talent_ogryn_carapace_armor_any_damage_desc (KEYSTONE 2, entry 30/88)
- Ogryn Batches 1-6: DONE (30 entries), all git diff --check PASS

## Manual Review Required

| File | Key | Issue | Suggested zh-tw | Reason |
|---|---|---|---|---|
| TALENTS_Arbites.lua | loc_talent_ability_adamant_grenade_description | Cyber-Mastiff 無固定譯名 | 電子獒犬 | 遊戲官方未確認 |
| TALENTS_Ogryn.lua | loc_ability_ogryn_grenade_box_description | 一些敵人名稱無官方繁中 | 流氓狂戰士/疤甲劊子手 等 | 根據遊戲術語推測 |

## Terminology Decisions

| EN | zh-tw | Source |
|---|---|---|
| Damage | 傷害 | COLORS_KWords_tw.lua |
| Toughness | 韌性 | Translation.md / COLORS_KWords_tw.lua |
| Peril | 反噬 | Translation.md / COLORS_KWords_tw.lua |
| Stagger | 踉蹌 | Translation.md / COLORS_KWords_tw.lua |
| Stun | 眩暈 | COLORS_KWords_tw.lua (Stun) |
| Electrocute/Electrocution | 電擊 | COLORS_KWords_tw.lua |
| Soulblaze | 靈火 | COLORS_KWords_tw.lua |
| Combat Ability | 戰鬥技能 | COLORS_KWords_tw.lua (Cmbt_abil) |
| Coherency | 協同 | COLORS_KWords_tw.lua |
| Weakspot | 弱點 | Translation.md / COLORS_KWords_tw.lua |
| Critical Hit / Crit | 暴擊 | Translation.md / COLORS_KWords_tw.lua |
| Carapace | 甲殼護甲 | Translation.md |
| Flak | 防彈護甲 | Translation.md |
| Elite | 精英 | General usage |
| Specialist | 特殊敵人 | General usage |
| Monstrosity / Monster | 怪物 | General usage |
| Rending | 撕裂 | COLORS_KWords_tw.lua |
| Brittleness | 脆弱 | Translation.md / COLORS_KWords_tw.lua |
| Bleed | 流血 | COLORS_KWords_tw.lua |
| Corruption | 腐敗 | Translation.md / COLORS_KWords_tw.lua |
| Focus Target | 鎖定目標 | Translation.md |
| Blitz | 閃擊技能 | User instruction |
| Feel No Pain | 麻木 | Translation.md / COLORS_KWords_tw.lua |
| Finesse | 靈巧 | Translation.md / COLORS_KWords_tw.lua |
| Hit Mass | 順劈目標 | Translation.md / COLORS_KWords_tw.lua |
| Cleave | 順劈攻擊 | COLORS_KWords_tw.lua |
| Stamina | 耐力 | COLORS_KWords_tw.lua |
| Power | 威力 | COLORS_KWords_tw.lua |
| Health | 生命 | COLORS_KWords_tw.lua |
| Burn | 燃燒 | COLORS_KWords_tw.lua |
| Suppression | 壓制 | (general) — needs confirmation if specific key exists |
| Warp Charge | 亞空間充能 | User instruction |
| Arbites Grenade | 仲裁手榴彈 | COLORS_KWords_tw.lua (Arbites_gren) |
| Cyber-Mastiff | 電子獒犬 | (inferred — needs confirmation) |

## Changed Files

- (none yet)

## Validation

- git diff --check: (pending)
- luac -p: (not available — using structure check as fallback)
- Notes: All existing zh-tw entries in Ogryn.lua and Zealot.lua are commented out.

---
*Last updated: start of session*
