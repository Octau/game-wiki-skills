Enhancing

Make equipment more powerful.

Main Drop

Upgraded Equipment

Tool

Enhancer

**Enhancing** is a non-combat skill in Milky Way Idle. The player can gain Experience to level up this skill by enhancing equipment, including weapons, armor, charms, tools, and accessories. Enhanced equipment gains increased stats based on enhancement level. The player can reduce the time it takes to enhance by using Enhancers. Various pieces of equipment can boost Enhancing Speed, Experience gain, Success Rate, and Rare Find.

Enhanced equipment becomes more powerful with each enhancement level, up to +20. However, failed enhancement attempts reset the item to +0 unless protection items are used.

## Enhancing Mechanics

**Success or Failure:** Each enhancement attempt either succeeds (increasing the level by 1, or rarely by 2 with  Blessed Tea) or fails (resetting to +0).

**Protection:** Depending on the item, players can use copies of the base equipment,  Mirror Of Protection,  Philosophers Mirror, or crafting components to add protection to each attempt. Protected failures only decrease the enhancement level by 1 instead of resetting to +0.  Philosophers Mirror provides a unique mechanic: it guarantees enhancement success but changes the cost to a copy of the item at -1 enhancement level. For specific protections for each item be sure to check the appropriate wiki pages or click the protection slot while enhancing.

**Enhancement Bonuses:** Bonus stats scale as a percentage of base stats. The total bonus multiplier increases with each level:

Enhancement Bonus

| Enhancement Level | Bonus |
| --- | --- |
| +1 | 2.0% |
| +2 | 4.2% |
| +3 | 6.6% |
| +4 | 9.2% |
| +5 | 12.0% |
| +6 | 15.0% |
| +7 | 18.2% |
| +8 | 21.6% |
| +9 | 25.2% |
| +10 | 29.0% |
| +11 | 33.4% |
| +12 | 38.4% |
| +13 | 44.0% |
| +14 | 50.2% |
| +15 | 57.0% |
| +16 | 64.4% |
| +17 | 72.4% |
| +18 | 81.0% |
| +19 | 90.2% |
| +20 | 100% |

Enhancement Base Success Rate

| Enhancement Level | Success Rate |
| --- | --- |
| +1 | 50% |
| +2 | 45% |
| +3 | 45% |
| +4 | 40% |
| +5 | 40% |
| +6 | 40% |
| +7 | 35% |
| +8 | 35% |
| +9 | 35% |
| +10 | 35% |
| +11 | 30% |
| +12 | 30% |
| +13 | 30% |
| +14 | 30% |
| +15 | 30% |
| +16 | 30% |
| +17 | 30% |
| +18 | 30% |
| +19 | 30% |
| +20 | 30% |

**Slot Multipliers:** Accessories (necklaces, rings, earrings), back slot, trinkets, and charms receive 5× the normal enhancement bonus, while weapons, armor, and pouches receive 1× bonus.

## Teas

| Tea | Effect | Duration |
| --- | --- | --- |
| Enhancing Tea | +3 Enhancing Level, +2% Action Speed | 300s |
| Super Enhancing Tea | +6 Enhancing Level, +4% Action Speed | 300s |
| Ultra Enhancing Tea | +8 Enhancing Level, +6% Action Speed | 300s |
| Blessed Tea | +1% Chance to gain +2 levels instead of +1 on success | 300s |
| Wisdom Tea | +12% Experience (works for all skills) | 300s |

## Observatory

The Observatory is a House room that gives the player Enhancing buffs, as well as global buffs.

Each level provides:

* +1% Action Speed
* +0.05% Enhancing Success (multiplicative)
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Observatory

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 750  Swamp Essence | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 120,000  Bear Essence |
| 6  Cheese Enhancer | 1,500  Swamp Essence | 3,000  Aqua Essence | 6,000  Jungle Essence | 12,000  Gobo Essence | 24,000  Eyessence | 48,000  Sorcerer Essence | 60  Holy Enhancer |
| - | 1,500  Aqua Essence | 3,000  Jungle Essence | 6,000  Gobo Essence | 12,000  Eyessence | 24,000  Sorcerer Essence | 48,000  Bear Essence | 2,000  Super Enhancing Tea |
| - | 9  Cheese Enhancer | 12  Verdant Enhancer | 15  Azure Enhancer | 18  Burble Enhancer | 21  Crimson Enhancer | 24  Rainbow Enhancer | - |
| - | 9  Verdant Enhancer | 12  Azure Enhancer | 15  Burble Enhancer | 18  Crimson Enhancer | 21  Rainbow Enhancer | 24  Holy Enhancer | - |
| - | - | - | 1,000  Enhancing Tea | - | - | - | - |

## Formulas

### Action Time

The time required to make an enhancement attempt is 12 seconds base, reduced by Action Speed bonuses.

| Action Time Formula |
| --- |
| `Action Time = 12 / (1 + Total Speed Bonus / 100)` |

**Speed Sources:**

**Level Bonus (when Enhancing level > Item level):**

* +1% Action Speed per level above Item Level: `0.01 × max(Enhancing Level - Item Level, 0)`

**Observatory Bonus:**

* +1% per Observatory level (max +8% at level 8)

**Skill-Specific Equipment:**

| Item | Level | Speed Bonus |
| --- | --- | --- |
| Enhancer's Top | 90 | +10% base (+2.9% at +10 = 12.9% total) |
| Enhancer's Bottoms | 90 | +10% base (+2.9% at +10 = 12.9% total) |
| Enchanted Gloves | 60 | +10% base (+2.9% at +10 = 12.9% total) |
| Necklace Of Speed | 75 | +4% base Skilling Speed (+5.8% at +10 = 9.8% total) |
| Philosopher's Necklace | 90 | +4% base Skilling Speed (+5.8% at +10 = 9.8% total) |

**Teas:**

| Tea | Speed Bonus |
| --- | --- |
| Enhancing Tea | +2% |
| Super Enhancing Tea | +4% |
| Ultra Enhancing Tea | +6% |

**Community Buff (Enhancing Speed):** 20% base + 0.5% per level (max 29.5% at T20)

**Example:**

| Component | Value |
| --- | --- |
| Base Time | 12 seconds |
| Level Bonus (94 - 1, capped) | +25% |
| Observatory Level 2 | +2% |
| Enhancer's Top +10 | +29% |
| Enhancer's Bottoms +10 | +29% |
| Enchanted Gloves +10 | +24% |
| Enhancing Tea | +2% |
| Community Buff T15 | +27.5% |
| **Total Speed Bonus** | **+138.5%** |
| **Final Action Time** | **12 / (1 + 1.385) = 5.03 seconds** |

### Success Rate

Success rates depend on your Enhancing level relative to the Item Level, plus bonuses from Enhancing tools and achievements.

| Enhancement Success Rate Formula |
| --- |
| `Final Success Rate = Base Rate × (Level Modifier + Tool Bonus + Over-Level Bonus)` |

**Components:**

**Base Rate:** From enhancement level success table (shown above)

**Level Modifier:** Based on player Enhancing level vs Item Level:

* If Enhancing Level < Item Level: `(Enhancing Level ÷ Item Level + 1) ÷ 2`, capped at 1.0
* If Enhancing Level ≥ Item Level: `1.0` (no penalty)

**Tool Bonus:** Enhancing Success stat from equipment and achievements:

* Enhancing tools provide base bonus + enhancement scaling
* Champion Achievement tier: +0.2% permanent bonus (6th achievement tier)

**Over-Level Bonus:** Additional bonus when above item level:

* +0.05% per level above the item's level: `0.0005 × max(Enhancing Level - Item Level, 0)`

**Example (Below Item Level):**

* Enhancing Level: 10, Item Level: 50, Enhancement: +5
* Tool:  Cheese Enhancer +0 (0.6% success bonus)
* No Champion Achievement

| Component | Value |
| --- | --- |
| Base Rate | 40.0% (for +5 enhancement) |
| Level Modifier | (10 ÷ 50 + 1) ÷ 2 = 0.6 |
| Tool Bonus | 0.6% = 0.006 |
| Over-Level Bonus | 0% (level < item level) = 0 |
| **Final Success Rate** | **40.0% × (0.6 + 0.006 + 0) = 40.0% × 0.606 = 24.24%** |

**Example (At/Above Item Level):**

* Enhancing Level: 80, Item Level: 50, Enhancement: +10
* Tool:  Rainbow Enhancer +15 (4.71% success bonus)
* Champion Achievement: +0.2%

| Component | Value |
| --- | --- |
| Base Rate | 30.0% (for +10 enhancement) |
| Level Modifier | 1.0 (no penalty, level ≥ item level) |
| Tool Bonus | 4.71% + 0.2% = 4.91% = 0.0491 |
| Over-Level Bonus | 0.0005 × (80 - 50) = 1.5% = 0.015 |
| **Final Success Rate** | **30.0% × (1.0 + 0.0491 + 0.015) = 30.0% × 1.0641 = 31.92%** |

### Experience

Wisdom increases the experience you receive from skilling actions. All Wisdom sources are additive with each other, then multiply the base experience.

| Enhancing Experience Formula |
| --- |
| `Base XP = 1.4 × (1 + Enhancement Level) × (10 + Item Level)` |
| `Final XP = Base XP × (1 + Wisdom + Charm Experience)` |

**Enhancing-Specific Equipment:**

| Item | Level | Experience Bonus |
| --- | --- | --- |
| Enhancer's Bottoms | 90 | +4% base (+1.16% at +10 = 5.16% total) |
| Celestial Enhancer | 90 | +4% base (+1.16% at +10 = 5.16% total) |
| Enhancing Charm | 1-100 | +1% to +8% base (based on tier, scales with enhancement 5×) |

See the Wisdom page for all sources and detailed examples.

**Example:**

| Component | Value |
| --- | --- |
| Item Level | 50 |
| Current Enhancement | +5 |
| Base XP | 1.4 × (1 + 5) × (10 + 50) = 504 XP |
| Wisdom (30%) | +30% |
| Enhancer's Bottoms +10 (5.16%) | +5.16% |
| Master Enhancing Charm +10 (24.6%) | +24.6% |
| **Total Multiplier** | **1.5976** |
| **Final XP** | **504 × 1.5976 = 805 XP** |

Note: On failed attempts, you receive 10% of the experience you would have gained on success.

### Rare Find

Rare Find increases the drop rate of rare items while enhancing:

**Enhancing-Specific Equipment:**

| Item | Level | Rare Find Bonus |
| --- | --- | --- |
| Enhancer's Top | 90 | +15% base (+4.35% at +10 = 19.35% total) |
| Celestial Enhancer | 90 | +15% base (+4.35% at +10 = 19.35% total) |

**Essence Drops:**

All enhancement attempts have a chance to drop 1×  Enhancing Essence. The drop rate scales with item level:

| Essence Drop Rate Formula |
| --- |
| `Base Rate = 10% + (Item Level / 10)%` |
| `Final Rate = Base Rate × (1 + Rare Find)` |

**Examples:**

| Item Level | Base Drop Rate |
| --- | --- |
| 1 | 10.1% |
| 10 | 11% |
| 50 | 15% |
| 100 | 20% |

**Rare Drops:**

Enhancing actions can drop Artisan's Crates containing valuable items. Drop rates scale with item level and are affected by Rare Find bonuses.

| Item Level | Artisan's Crate | Approximate Rate |
| --- | --- | --- |
| 1 | Small Artisan's Crate | ~0.10% |
| 50 | Medium Artisan's Crate | ~0.25% |
| 100 | Large Artisan's Crate | ~0.50% |

See the Rare Find page for details on how this stat increases drop rates.