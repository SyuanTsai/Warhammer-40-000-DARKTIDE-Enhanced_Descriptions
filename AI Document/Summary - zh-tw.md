# Translation Summary

## Progress

- [x] Main_Modules/TALENTS/TALENTS_Arbites.lua  (83/83 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Ogryn.lua    (88/88 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Psyker.lua   (79/79 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Zealot.lua   (78/78 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Scum.lua     (99/99 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Veteran.lua  (75/75 entries, git diff --check PASS)
- [x] Main_Modules/TALENTS/TALENTS_Zealot.lua   (78/78 entries, git diff --check PASS)

Total entries: Arbites 83, Ogryn 88, Psyker 79, Veteran 75, Zealot 78, Scum 99

## Current Position

- File: Main_Modules/TALENTS/TALENTS_Scum.lua
- Status: complete, 99/99 entries have zh-tw
- Last completed entry: loc_talent_buff_cooldown_on_ranged_kills
- Next entry: none
- Missing zh-tw entries remaining: 0

## Zealot File Structure

| Line | Key (short) | Section |
|---|---|---|
| 22 | loc_ability_shock_grenade_description | BLITZ 0 - Stun Grenade |
| 42 | loc_zealot_improved_stun_grenade_desc | BLITZ 1 - Stunstorm Grenade |
| 66 | loc_talent_ability_fire_grenade_desc | BLITZ 2 - Immolation Grenade |
| 85 | loc_ability_zealot_throwing_knifes_desc | BLITZ 3 - Blades of Faith |
| 123 | loc_talent_zealot_aura_toughness_damage_coherency_desc | AURA 0 - The Emperor's Will |
| 134 | loc_talent_zealot_toughness_aura_efficiency_desc | AURA 1 - Benediction |
| 148 | loc_talent_zealot_corruption_healing_coherency_improved_desc | AURA 2 - Beacon of Purity |
| 165 | loc_talent_zealot_stamina_cost_multiplier_delay_aura_description | AURA 3 - Zealous |
| 184 | loc_talent_zealot_2_combat_description_new | ABILITY 0 - Chastise the Wicked |
| 218 | loc_talent_zealot_attack_speed_after_dash_new_desc | ABILITY 1 - Fury of the Faithful |
| 270 | loc_talent_zealot_fotf_refund_cooldown_desc | ABILITY 1-1 - Unrelenting Fury |
| 281 | loc_talent_zealot_dash_has_more_charges_desc | ABILITY 1-2 - Redoubled Zeal |
| 286 | loc_talent_zealot_bolstering_prayer_variant_two_description | ABILITY 2 - Chorus |
| 357 | loc_talent_zealot_zealot_channel_grants_defensive_buff_desc | ABILITY 2-1 |
| 377 | loc_talent_zealot_zealot_channel_grants_offensive_buff_desc | ABILITY 2-2 |
| 396 | loc_ability_zealot_stealth_rending_description | ABILITY 3 - Shroudfield |
| 427 | loc_talent_zealot_stealth_duration_threat_damage_desc | ABILITY 3-1 |
| 442 | loc_talent_zealot_stealth_toughness_dr_desc | ABILITY 3-2 |
| 460 | loc_talent_zealot_stealth_cooldown_regeneration_desc | ABILITY 3-3 |
| 480 | loc_talent_zealot_fanatic_rage_crit_desc | KEYSTONE 1 - Blazing Piety |
| 498 | loc_talent_zealot_shared_fanatic_rage_new_desc | KEYSTONE 1-1 |
| 509 | loc_talent_zealot_fanatic_rage_improved_desc | KEYSTONE 1-2 |
| 516 | loc_talent_zealot_fanatic_rage_toughness_replenish_desc | KEYSTONE 1-3 - Stalwart |
| 537 | loc_talent_maniac_cooldown_on_melee_crits_buff_desc | KEYSTONE 1-4 - Invocation of Death |
| 542 | loc_talent_zealot_martyrdom_desc | KEYSTONE 2 - Martyrdom |
| 551 | loc_talent_zealot_martyrdom_grants_toughness_upd_desc | KEYSTONE 2-1 |
| 560 | loc_talent_zealot_corruption_resistance_stacking_desc | KEYSTONE 2-2 |
| 565 | loc_talent_zealot_attack_speed_per_martyrdom_upd_desc | KEYSTONE 2-3 |
| 573 | loc_talent_zealot_martyrdom_toughness_modifier_upd_desc | KEYSTONE 2-4 |
| 581 | loc_talent_zealot_damage_taken_restores_cd_new_description | KEYSTONE 2-5 |
| 586 | loc_talent_zealot_quickness_desc | KEYSTONE 3 - Inexorable Judgement |
| 612 | loc_talent_zealot_momentum_toughness_replenish_desc | KEYSTONE 3-1 |
| 619 | loc_talent_zealot_quickness_dodge_stacks_desc | KEYSTONE 3-2 |
| 626 | loc_talent_zealot_quickness_increased_duration_desc | KEYSTONE 3-3 |
| 633+ | Passive entries 1-42+ | PASSIVES |

## Zealot CKWord Keys (verified in COLORS_KWords_tw.lua)

- cls_zea → 狂信徒
- Holy_relic → 聖物
- fury_faithful → 有信者之怒
- Fury → 狂怒
- Momentum → 勢能
- Stealth → 隱身
- shroudf → 隱秘領域
- loner → 孤狼
- Doesnt_Stack_Zea_Aura / Doesnt_Stack_Zea_abil → CPhrs

## Manual Review Required

| File | Key | Issue | Suggested zh-tw | Reason |
|---|---|---|---|---|
| TALENTS_Ogryn.lua | loc_ability_ogryn_grenade_box_description | 一些敵人名稱無官方繁中 | 流氓狂戰士/疤甲劊子手 等 | 根據遊戲術語推測 |
| TALENTS_Scum.lua | loc_talent_broker_passive_stimm_increased_duration_desc | Cartel Special Stimm 在更新後 Translation prompt 無直接對應詞 | 卡特爾特製興奮劑 | 其他 Stimm 名稱已由更新後 Translation prompt 確認，Cartel Special 仍需人工確認 |

## Terminology Decisions

| EN | zh-tw | Source |
|---|---|---|
| Fury (Zealot) | 狂怒 | CKWord("Fury", "Fury_rgb_tw") |
| Momentum (Zealot) | 勢能 | CKWord("Momentum", "Momentum_rgb_tw") |
| Holy relic | 聖物 | CKWord("Holy_relic", "Holy_relic_rgb_tw") |
| Zealot class | 狂信徒 | CKWord("cls_zea", "cls_zea_rgb_tw") |
| Shroudfield | 隱秘領域 | CKWord("shroudf", "shroudf_rgb_tw") |

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
| Overkill Damage | 過量傷害 | TALENTS_Scum.lua context |

| Health | 生命 | COLORS_KWords_tw.lua |
| Burn | 燃燒 | COLORS_KWords_tw.lua |
| Suppression | 壓制 | (general) — needs confirmation if specific key exists |
| Warp Charge | 亞空間充能 | User instruction |
| Arbites Grenade | 仲裁手榴彈 | COLORS_KWords_tw.lua (Arbites_gren) |
| Cyber-Mastiff | 電子獒犬 | (inferred — needs confirmation) |

## Changed Files

- Main_Modules/TALENTS/TALENTS_Scum.lua
- AI Document/Summary - zh-tw.md

## Validation

- git diff --check: PASS
- luac -p: not available
- Notes: TALENTS_Scum.lua metadata scan PASS (99/99 zh-tw, 0 missing). Placeholder check PASS (0 mismatches). Structure count PASS (99 entry starts, 99 entry closes, 99 zh-tw lines). Fixed 4 pre-existing missing entry terminators.

## Final Result

- Completed files: Main_Modules/TALENTS/TALENTS_Scum.lua
- Entries updated: 37 missing zh-tw entries added; 4 pre-existing entry terminators repaired
- Entries skipped: 62 existing zh-tw entries retained
- Manual review count: 2 existing rows
- Validation result: PASS; git diff --check PASS, placeholder check PASS, structure count PASS
- Remaining risk: luac is not installed in this environment, so Lua parser validation could not be run

---
*Last updated: start of session*
