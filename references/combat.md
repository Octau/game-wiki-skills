# Combat Stats & Styles


================================================================
## Combat
================================================================

Combat

Fight monsters.

Main Drop

XP, Loot

Tool

Weapons

Combat is the act of fighting monsters for experience, coins and drops.

Combat styles are determined by your equipped weapon. Physical styles include Stab (Spear), Slash (Sword), and Smash (Mace/Bulwark). Ranged styles use Bow or Crossbow. Magic styles use staves for Fire, Water, or Nature damage.

You engage in combat with Monsters, Zones (groups of monsters with a boss) and Dungeons (multiple waves of enemies plus a final, tough boss).

## Skills

There are seven subskills within Combat, each contributing to your total Combat Level, and each providing you with different bonuses. The experience you gain from combat is applied after each wave is cleared.

Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally (14% each) among  Stamina,  Intelligence,  Attack,  Defense, and the Primary Training skill (giving it 44% total)

**Note:** Experience gained is further modified by Wisdom and skill-specific Charm Experience bonuses. See Wisdom for the complete formula.

 Stamina: Increases max HP by 10 per level.

 Intelligence: Increases max MP by 10 per level.

 Attack: Increases your accuracy, attack speed, and cast speed.

 Defense: Increases your evasion, armor, and elemental resistances. When wielding a Bulwark, your damage scales with Defense instead of Melee.

 Melee: Increases your melee damage.

 Ranged: Increases your ranged damage.

 Magic: Increases your magic damage.

## Combat Styles

Combat style is determined by the kind of weapon you're using. Different styles may be more or less effective against different types of Monster.

Attacks fall into four different damage types: Physical, Water, Nature, or Fire.

| Weapon Type | Style |
| --- | --- |
| Sword | Slash |
| Spear | Stab |
| Mace | Smash |
| Bulwark | Smash |
| Crossbow | Ranged |
| Bow | Ranged |
| Water Staff | Magic (Water) |
| Nature Staff | Magic (Nature) |
| Fire Staff | Magic (Fire) |

## Combat Mechanics

### Damage Mitigation

Incoming damage in combat is reduced through two layers of defense:

#### Evasion Layer

Evasion provides a chance to avoid attacks entirely. The hit chance is determined by comparing the attacker's Accuracy against your Evasion rating:

| Formula |
| --- |
| `Hit Chance = accuracy^1.4 / (accuracy^1.4 + evasion^1.4)` |

Each Combat Style (Stab, Slash, Smash, Ranged, Magic) has its own Accuracy and Evasion ratings.

#### Armor/Resistance Layer

If an attack successfully hits, the damage is then mitigated by your defensive stats based on the attack's Damage Type:

* Armor reduces physical damage (used by Stab, Slash, Smash, and Ranged styles)
* Elemental Resistance reduces magical damage (Fire, Water, and Nature)

The attacker's Penetration stat reduces your effective defense:

| Penetration Calculation |
| --- |
| `Penetrated Defense = Armor (or Resistance) - Penetration` |

The final damage multiplier is calculated as:

| Damage Formula |
| --- |
| `Damage Taken = 100 / (100 + Penetrated Defense)` |

If penetration exceeds defense (negative Penetrated Defense), damage is amplified:

| Amplified Damage Formula |
| --- |
| `Damage Taken = (100 - Penetrated Defense) / 100` |

**Note:** Physical combat styles (Stab, Slash, Smash) each have separate Evasion ratings but share a single Armor stat. Magic has one Evasion rating but uses three separate elemental Resistances (Fire, Water, Nature). Ranged uses physical Armor but has its own Evasion rating.

### Crowd Control (CC)

Crowd control effects temporarily disable combat actions:

| Effect | Description |
| --- | --- |
| **Stun** | Prevents all actions (auto attacks and abilities) |
| **Blind** | Prevents auto attacks only (abilities still work) |
| **Silence** | Prevents abilities only (auto attacks still work) |

**Tenacity** reduces the chance of being affected by crowd control:

| Formula |
| --- |
| `CC Chance = Base CC Chance × 100 / (100 + Tenacity)` |

### Special Attack Modifiers

| Category | Modifier | Description |
| --- | --- | --- |
| **Offensive** | **Pierce** | Attack continues to the next target after hitting (some abilities have 100% pierce chance) |
| **Mayhem** | When an attack misses, it hits a different random target instead |
| **Blaze/Bloom/Ripple** | Proc-based effects that trigger after casting abilities (see detailed section below) |
| **Defensive** | **Parry** | Chance to negate damage and counter-attack (see detailed section below) |
| **Thorns** | Reflects a percentage of damage back to the attacker (Physical or Elemental) |
| **Retaliation** | Counter-attack using Smash combat style when hit |
| **Sustain** | **Life Steal** | Drains a percentage of damage dealt as HP |
| **Mana Leech** | Drains a percentage of damage dealt as MP |

### Elemental Procs (Blaze/Bloom/Ripple)

These equipment stats provide a chance to trigger bonus effects after casting any ability.

| Stat | Proc Effect |
| --- | --- |
| **Blaze** | Casts a bonus AoE fire attack dealing 30% of max damage to all enemies |
| **Bloom** | Heals the lowest HP ally for 10 + 15% of max damage |
| **Ripple** | Restores 10 mana and reduces all ability cooldowns by 2 seconds |

**How They Work:**

* After you cast any ability, each elemental proc stat rolls independently
* If the roll succeeds, the bonus effect triggers immediately
* Multiple procs can trigger from a single ability cast (e.g., both Blaze and Ripple)
* Proc chances are additive from equipment
* No mana cost or cooldown for proc effects

**Equipment:** Blaze is found on Fire staves, Bloom on Nature staves, and Ripple on Water staves. These stats make elemental weapons particularly valuable for their versatility—dealing damage while also providing utility effects.

### Damage Amplification

Several stats amplify your damage output beyond base weapon damage:

| Stat | Effect |
| --- | --- |
| **Amplify (Fire/Water/Nature)** | Multiplicative bonus to that damage type: `Damage × (1 + Amplify)` |
| **Task Damage** | Multiplicative bonus to ALL damage: `Damage × (1 + Task Damage)` |
| **Auto Attack Damage** | Additive bonus for auto attacks only: `Damage × (1 + Auto Attack Damage)` |
| **Ability Damage** | Multiplicative bonus for abilities only: `Damage × (1 + Ability Damage)` |
| **Defensive Damage** | Increases damage when wielding Bulwarks—scales with Defense level instead of Melee |

**Order of Application:**
1. Base damage calculated (weapon damage + accuracy/evasion)
2. Amplify applies (elemental or physical)
3. Crit multiplier (if crit)
4. Task Damage applies
5. Auto Attack Damage OR Ability Damage applies (depending on attack type)

**Bulwark Mechanic:** When wielding a Bulwark, Defensive Damage adds bonus damage based on Defense level rather than Melee level, allowing tank builds to deal competitive damage.

### Speed and Haste

Combat speed is affected by three different stats:

| Stat | Effect |
| --- | --- |
| **Attack Speed** | Reduces auto attack interval: `Interval = Base / (1 + Attack Speed)` Also affected by Attack level |
| **Cast Speed** | Reduces ability cast time Also scales with Attack level: `+Attack Level / 2000` |
| **Ability Haste** | Reduces ability cooldowns: `Cooldown = Base × 100 / (100 + Ability Haste)` |

**Example:** With 100% Ability Haste, a 60-second cooldown becomes 30 seconds.

### Stacking Effects

Several buffs and debuffs stack multiple times:

| Type | Effect | Max Stacks | Description |
| --- | --- | --- | --- |
| **Debuffs** | **Curse** | 5 | Increases damage taken |
| **Weaken** | 5 | Reduces damage dealt |
| **Buff** | **Fury** | 5 | Increases accuracy and damage • Gains a stack on successful hit • Loses all stacks on miss |

### Threat

Threat controls which party member monsters target in multi-player combat.

* Every player has 100 base threat, plus any bonuses from equipment
* When a monster attacks, each player's chance of being targeted is proportional to their threat
* Higher threat = higher chance to be hit (allowing "tank" builds to protect allies)
* Only matters in party play (ignored when soloing)

| Threat Source | Multiplier |
| --- | --- |
| Base | 100 |
| Equipment | Various flat bonuses |
| Taunt (Ability) | 2.5× base + 2.5% per level |
| Provoke (Ability) | 5× base + 5% per level |

**Example:**

| Player | Threat | Targeting Chance |
| --- | --- | --- |
| Player 1 | 100 | 100/700 = 14.3% |
| Player 2 (with Provoke) | 600 | 600/700 = 85.7% |
| **Total** | **700** | **100%** |

### Parry

Parry provides a chance to intercept enemy attacks and counter-attack.

| Property | Value |
| --- | --- |
| Base Chance | 8% (Regal Sword), 8.4% (Regal Sword Refined) |
| Trigger | Once per enemy ability cast |
| Effect | Counter-attack + negates damage to entire party (AoE) or target (single-target) |

**Mechanic:**

* When an enemy casts an ability (single-target or AoE), one parry check occurs
* One party member with parry > 0 is randomly selected to make the check
* That selected member rolls their parry chance (8% for Regal Sword)
* If successful, the parrying unit immediately counter-attacks the enemy
* **For single-target attacks:** The original target completely avoids damage
* **For AoE attacks:** The ENTIRE PARTY avoids all damage from the ability

Parry is exceptionally powerful against AoE abilities, as a successful 8% roll completely negates damage to all party members.

**Multiple Parry Users:**
If multiple party members have parry, one is randomly selected to roll. Parry chances do NOT stack—having two players with 8% parry gives 50% chance of selecting each player, then that player rolls 8%, not a combined 16% chance.

### Critical Hits

Critical hits deal maximum damage with no variation, making them highly valuable for burst damage.

| Property | Mechanic |
| --- | --- |
| Base Crit Chance | Ranged: 30% of hit chance Other styles: 0% |
| Bonus Crit Chance | Equipment bonuses (additive) |
| Crit Damage Effect | Deals maximum possible damage (min = max × (1 + crit damage bonus)) |

**Formula:**

| Critical Chance Calculation |
| --- |
| `Crit Chance = Base Crit Chance + Equipment Crit Rate Bonus` |

**Damage on Critical Hit:**

| Critical Damage Calculation |
| --- |
| `Min Damage = Max Damage × (1 + Critical Damage Bonus)` |
| `Max Damage = Max Damage × (1 + Critical Damage Bonus)` |

This means critical hits always deal the maximum possible damage (no damage roll variation), further increased by any Critical Damage bonuses from equipment.

**Equipment:** Critical Rate is found primarily on Ranged gear (Beast/Centaur/Acrobatic sets, Chimerical Quiver). Critical Damage bonuses are rarer.

### Enrage

Monsters gain stacking Enrage buffs during extended combat encounters.

| Property | Value |
| --- | --- |
| Stack Interval | Every 60 seconds |
| Maximum Stacks | 10 |
| Per Stack Bonus | +10% Accuracy and +10% Damage |
| Max Stack Bonus | +100% Accuracy and +100% Damage (at 10 stacks) |

### Level Malus

Party members who are at least 20% below the highest combat level will receive an experience and drop debuff.

| Level Malus Formula |
| --- |
| `Penalty = min(90%, 3 × (Level Ratio - 1.2))` |

* Penalty increases by 3% for each 1% level difference beyond the 20% threshold (ratio of 1.2)
* Maximum penalty is 90% (reduced to 10% of normal rewards)
* Applies to BOTH experience gained and drop quantities (including dungeon chests)
* The penalty is based on the **highest** combat level in the party, not your own level
* Level ratio = Highest Combat Level / Your Combat Level
* Level percentage is floored to 2 decimal places before calculating penalty

**Example 1 (Moderate Penalty):**

| Component | Value |
| --- | --- |
| Highest party member | Level 100 |
| Your level | Level 75 |
| Level ratio | 100 / 75 = 1.333 (33.3% below) |
| Level difference beyond threshold | 1.333 - 1.2 = 0.13 (13%) |
| **Penalty** | **min(90%, 3 × 13%) = 39% malus to XP and drops** |

**Example 2 (Maximum Penalty):**

| Component | Value |
| --- | --- |
| Highest party member | Level 100 |
| Your level | Level 50 |
| Level ratio | 100 / 50 = 2.0 (50% below) |
| Level difference beyond threshold | 2.0 - 1.2 = 0.80 (80%) |
| **Calculated penalty** | 3 × 80% = 240% |
| **Actual penalty** | **min(90%, 240%) = 90% malus (receive 10% of rewards)** |

## Formulas

Your total combat level can be calculated by:

| Combat Level Formula |
| --- |
| `Combat Level = 0.1 × (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 × MAX(Attack, Defense, Melee, Ranged, Magic)` |
| where MAX is the maximum function (the highest number in the range) |

## Combat Houses

Dining RoomLibraryDojoGymArmoryArchery RangeMystical Study

### Dining Room

The Dining Room is a House room that provides Stamina buffs and global bonuses.

Each level provides:

* +1 Stamina level
* +0.03% HP regeneration
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Dining Room

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 125  Donut | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 20,000  Spaceberry Donut |
| 125  Cupcake | 250  Donut | 500  Blueberry Donut | 1,000  Blackberry Donut | 2,000  Strawberry Donut | 4,000  Mooberry Donut | 8,000  Marsberry Donut | 20,000  Spaceberry Cake |
| 1  Small Pouch | 250  Blueberry Donut | 500  Blackberry Donut | 1,000  Strawberry Donut | 2,000  Mooberry Donut | 4,000  Marsberry Donut | 8,000  Spaceberry Donut | 3  Giant Pouch |
| - | 250  Cupcake | 500  Blueberry Cake | 1,000  Blackberry Cake | 2,000  Strawberry Cake | 4,000  Mooberry Cake | 8,000  Marsberry Cake | 2,000  Super Stamina Coffee |
| - | 250  Blueberry Cake | 500  Blackberry Cake | 1,000  Strawberry Cake | 2,000  Mooberry Cake | 4,000  Marsberry Cake | 8,000  Spaceberry Cake | - |
| - | 3  Small Pouch | 1  Medium Pouch | 3  Medium Pouch | 1  Large Pouch | 3  Large Pouch | 1  Giant Pouch | - |
| - | - | - | 1,000  Stamina Coffee | - | - | - | - |

### Library

The Library is a House room that provides Intelligence buffs and global bonuses.

Each level provides:

* +1 Intelligence level
* +0.03% MP regeneration
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Library

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 250  Gummy | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 20,000  Star Fruit Gummy |
| 250  Yogurt | 500  Gummy | 500  Apple Gummy | 1,000  Orange Gummy | 2,000  Plum Gummy | 4,000  Peach Gummy | 8,000  Dragon Fruit Gummy | 20,000  Star Fruit Yogurt |
| 2  Poke | 250  Apple Gummy | 500  Orange Gummy | 1,000  Plum Gummy | 2,000  Peach Gummy | 4,000  Dragon Fruit Gummy | 8,000  Star Fruit Gummy | 2  Silencing Shot |
| 2  Scratch | 500  Yogurt | 500  Apple Yogurt | 1,000  Orange Yogurt | 2,000  Plum Yogurt | 4,000  Peach Yogurt | 8,000  Dragon Fruit Yogurt | 2  Frost Surge |
| 2  Smack | 250  Apple Yogurt | 500  Orange Yogurt | 1,000  Plum Yogurt | 2,000  Peach Yogurt | 4,000  Dragon Fruit Yogurt | 8,000  Star Fruit Yogurt | 2  Nature's Veil |
| - | 2  Quick Shot | 2  Toughness | 2  Impale | 2  Rain Of Arrows | 2  Berserk | 2  Puncture | 2  Firestorm |
| - | 2  Water Strike | 2  Precision | 2  Cleave | 2  Ice Spear | 2  Frenzy | 2  Maim | 2,000  Super Intelligence Coffee |
| - | 2  Entangle | - | 2  Sweep | 2  Flame Blast | 2  Elemental Affinity | 2  Stunning Blow | - |
| - | 2  Fireball | - | 1,000  Intelligence Coffee | 2  Toxic Pollen | - | - | - |

### Dojo

The Dojo is a House room that provides Attack buffs and global bonuses.

Each level provides:

* +1 Attack level
* +0.5% attack speed
* +0.5% cast speed
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Dojo

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 16  Cheese Spear | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 160  Holy Spear |
| 8  Cheese Sword | 24  Cheese Spear | 32  Verdant Spear | 40  Azure Spear | 48  Burble Spear | 56  Crimson Spear | 64  Rainbow Spear | 80  Holy Sword |
| - | 24  Verdant Spear | 32  Azure Spear | 40  Burble Spear | 48  Crimson Spear | 56  Rainbow Spear | 64  Holy Spear | 2,000  Super Attack Coffee |
| - | 12  Cheese Sword | 16  Verdant Sword | 20  Azure Sword | 24  Burble Sword | 28  Crimson Sword | 32  Rainbow Sword | - |
| - | 12  Verdant Sword | 16  Azure Sword | 20  Burble Sword | 24  Crimson Sword | 28  Rainbow Sword | 32  Holy Sword | - |
| - | - | - | 1,000  Attack Coffee | - | - | - | - |

### Gym

The Gym is a House room that provides Melee buffs and global bonuses.

Each level provides:

* +1 Melee level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Gym

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 16  Cheese Mace | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 160  Holy Mace |
| 8  Cheese Sword | 24  Cheese Mace | 32  Verdant Mace | 40  Azure Mace | 48  Burble Mace | 56  Crimson Mace | 64  Rainbow Mace | 80  Holy Sword |
| - | 24  Verdant Mace | 32  Azure Mace | 40  Burble Mace | 48  Crimson Mace | 56  Rainbow Mace | 64  Holy Mace | 2,000  Super Melee Coffee |
| - | 12  Cheese Sword | 16  Verdant Sword | 20  Azure Sword | 24  Burble Sword | 28  Crimson Sword | 32  Rainbow Sword | - |
| - | 12  Verdant Sword | 16  Azure Sword | 20  Burble Sword | 24  Crimson Sword | 28  Rainbow Sword | 32  Holy Sword | - |
| - | - | - | 1,000  Melee Coffee | - | - | - | - |

### Armory

The Armory is a House room that provides Defense buffs and global bonuses.

Each level provides:

* +1 Defense level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Armory

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 8  Cheese Helmet | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 80  Holy Helmet |
| 8  Cheese Plate Body | 12  Cheese Helmet | 16  Verdant Helmet | 20  Azure Helmet | 24  Burble Helmet | 28  Crimson Helmet | 32  Rainbow Helmet | 80  Holy Plate Body |
| 8  Cheese Plate Legs | 12  Verdant Helmet | 16  Azure Helmet | 20  Burble Helmet | 24  Crimson Helmet | 28  Rainbow Helmet | 32  Holy Helmet | 80  Holy Plate Legs |
| 8  Cheese Gauntlets | 12  Cheese Plate Body | 16  Verdant Plate Body | 20  Azure Plate Body | 24  Burble Plate Body | 28  Crimson Plate Body | 32  Rainbow Plate Body | 80  Holy Gauntlets |
| 8  Cheese Boots | 12  Verdant Plate Body | 16  Azure Plate Body | 20  Burble Plate Body | 24  Crimson Plate Body | 28  Rainbow Plate Body | 32  Holy Plate Body | 80  Holy Boots |
| - | 12  Cheese Plate Legs | 16  Verdant Plate Legs | 20  Azure Plate Legs | 24  Burble Plate Legs | 28  Crimson Plate Legs | 32  Rainbow Plate Legs | 2,000  Super Defense Coffee |
| - | 12  Verdant Plate Legs | 16  Azure Plate Legs | 20  Burble Plate Legs | 24  Crimson Plate Legs | 28  Rainbow Plate Legs | 32  Holy Plate Legs | - |
| - | 12  Cheese Gauntlets | 16  Verdant Gauntlets | 20  Azure Gauntlets | 24  Burble Gauntlets | 28  Crimson Gauntlets | 32  Rainbow Gauntlets | - |
| - | 12  Verdant Gauntlets | 16  Azure Gauntlets | 20  Burble Gauntlets | 24  Crimson Gauntlets | 28  Rainbow Gauntlets | 32  Holy Gauntlets | - |
| - | 12  Cheese Boots | 16  Verdant Boots | 20  Azure Boots | 24  Burble Boots | 28  Crimson Boots | 32  Rainbow Boots | - |
| - | 12  Verdant Boots | 16  Azure Boots | 20  Burble Boots | 24  Crimson Boots | 28  Rainbow Boots | 32  Holy Boots | - |
| - | - | - | 1,000  Defense Coffee | - | - | - | - |

### Archery Range

The Archery Range is a House room that provides Ranged buffs and global bonuses.

Each level provides:

* +1 Ranged level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Archery Range

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 6  Wooden Crossbow | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 60  Arcane Crossbow |
| 4  Wooden Bow | 9  Wooden Crossbow | 12  Birch Crossbow | 15  Cedar Crossbow | 18  Purpleheart Crossbow | 21  Ginkgo Crossbow | 24  Redwood Crossbow | 40  Arcane Bow |
| 4  Rough Hood | 9  Birch Crossbow | 12  Cedar Crossbow | 15  Purpleheart Crossbow | 18  Ginkgo Crossbow | 21  Redwood Crossbow | 24  Arcane Crossbow | 40  Umbral Hood |
| 4  Rough Tunic | 6  Wooden Bow | 8  Birch Bow | 10  Cedar Bow | 12  Purpleheart Bow | 14  Ginkgo Bow | 16  Redwood Bow | 40  Umbral Tunic |
| 4  Rough Chaps | 6  Birch Bow | 8  Cedar Bow | 10  Purpleheart Bow | 12  Ginkgo Bow | 14  Redwood Bow | 16  Arcane Bow | 40  Umbral Chaps |
| 4  Rough Bracers | 8  Reptile Hood | 16  Reptile Hood | 16  Gobo Hood | 32  Gobo Hood | 24  Beast Hood | 48  Beast Hood | 40  Umbral Bracers |
| 4  Rough Boots | 8  Reptile Tunic | 16  Reptile Tunic | 16  Gobo Tunic | 32  Gobo Tunic | 24  Beast Tunic | 48  Beast Tunic | 40  Umbral Boots |
| - | 8  Reptile Chaps | 16  Reptile Chaps | 16  Gobo Chaps | 32  Gobo Chaps | 24  Beast Chaps | 48  Beast Chaps | 2,000  Super Ranged Coffee |
| - | 8  Reptile Bracers | 16  Reptile Bracers | 16  Gobo Bracers | 32  Gobo Bracers | 24  Beast Bracers | 48  Beast Bracers | - |
| - | 8  Reptile Boots | 16  Reptile Boots | 16  Gobo Boots | 32  Gobo Boots | 24  Beast Boots | 48  Beast Boots | - |
| - | - | - | 1,000  Ranged Coffee | - | - | - | - |

### Mystical Study

The Mystical Study is a House room that provides Magic buffs and global bonuses.

Each level provides:

* +1 Magic level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Mystical Study

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 4  Wooden Water Staff | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 40  Arcane Water Staff |
| 4  Wooden Nature Staff | 6  Wooden Water Staff | 8  Birch Water Staff | 10  Cedar Water Staff | 12  Purpleheart Water Staff | 14  Ginkgo Water Staff | 16  Redwood Water Staff | 40  Arcane Nature Staff |
| 4  Wooden Fire Staff | 6  Birch Water Staff | 8  Cedar Water Staff | 10  Purpleheart Water Staff | 12  Ginkgo Water Staff | 14  Redwood Water Staff | 16  Arcane Water Staff | 40  Arcane Fire Staff |
| 4  Cotton Hat | 6  Wooden Nature Staff | 8  Birch Nature Staff | 10  Cedar Nature Staff | 12  Purpleheart Nature Staff | 14  Ginkgo Nature Staff | 16  Redwood Nature Staff | 40  Radiant Hat |
| 4  Cotton Robe Top | 6  Birch Nature Staff | 8  Cedar Nature Staff | 10  Purpleheart Nature Staff | 12  Ginkgo Nature Staff | 14  Redwood Nature Staff | 16  Arcane Nature Staff | 40  Radiant Robe Top |
| 4  Cotton Robe Bottoms | 6  Wooden Fire Staff | 8  Birch Fire Staff | 10  Cedar Fire Staff | 12  Purpleheart Fire Staff | 14  Ginkgo Fire Staff | 16  Redwood Fire Staff | 40  Radiant Robe Bottoms |
| 4  Cotton Gloves | 6  Birch Fire Staff | 8  Cedar Fire Staff | 10  Purpleheart Fire Staff | 12  Ginkgo Fire Staff | 14  Redwood Fire Staff | 16  Arcane Fire Staff | 40  Radiant Gloves |
| 4  Cotton Boots | 8  Linen Hat | 16  Linen Hat | 16  Bamboo Hat | 32  Bamboo Hat | 24  Silk Hat | 48  Silk Hat | 40  Radiant Boots |
| - | 8  Linen Robe Top | 16  Linen Robe Top | 16  Bamboo Robe Top | 32  Bamboo Robe Top | 24  Silk Robe Top | 48  Silk Robe Top | 2,000  Super Magic Coffee |
| - | 8  Linen Robe Bottoms | 16  Linen Robe Bottoms | 16  Bamboo Robe Bottoms | 32  Bamboo Robe Bottoms | 24  Silk Robe Bottoms | 48  Silk Robe Bottoms | - |
| - | 8  Linen Gloves | 16  Linen Gloves | 16  Bamboo Gloves | 32  Bamboo Gloves | 24  Silk Gloves | 48  Silk Gloves | - |
| - | 8  Linen Boots | 16  Linen Boots | 16  Bamboo Boots | 32  Bamboo Boots | 24  Silk Boots | 48  Silk Boots | - |
| - | - | - | 1,000  Magic Coffee | - | - | - | - |

================================================================
## Stamina
================================================================

Stamina

Increase your maximum HP to survive longer in combat.

Main Drop

Combat experience

Tool

None

**Stamina** is a combat skill that determines your maximum HP, allowing you to survive longer in battle. Each level provides 10 HP in the base calculation, with additional bonuses from equipment, house rooms, and consumables.

## Maximum HP Formula

| Maximum HP Formula |
| --- |
| `Maximum HP = floor(10 × (10 + Effective Stamina Level) + Equipment HP)` |

**Components:**

* \*\*Base HP\*\*: 100 (10 × 10)
* \*\*Stamina Contribution\*\*: 10 HP per effective Stamina level
* \*\*Effective Stamina Level\*\*: Base Stamina + buffs from Dining Room and Stamina Coffee
* \*\*Equipment HP\*\*: Flat HP bonuses from equipped items
* \*\*Floor function\*\*: Final result is rounded down

### Stamina Level Buffs

Stamina level can be increased by several sources before the HP calculation:

**Dining Room:**

* +1 Stamina level per room level (permanent)
* Maximum: +8 Stamina at level 8

**Stamina Coffee:**

* +3 flat Stamina level
* +8% ratio Stamina level
* Both bonuses scale with Drink Concentration
* Duration: 5 minutes

## Examples

**Level 50 Stamina, no buffs:**

* Maximum HP = floor(10 × (10 + 50) + 0) = floor(600) = 600 HP

**Level 125 Stamina with buffs:**

* Dining Room Level 5: +5 Stamina
* Stamina Coffee with 11.5% Drink Concentration:

```
 * Flat: +3 × 1.115 = +3.345
 * Ratio: +125 × 8% × 1.115 = +11.15
```

* Effective Stamina: 125 + 5 + 3.345 + 11.15 = 144.495
* Base HP: floor(10 × (10 + 144.495)) = floor(1544.95) = 1544 HP
* Plus equipment HP for final total

## Combat Level Formula

| Combat Level Formula |
| --- |
| `Combat Level = 0.1 × (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 × MAX(Attack, Defense, Melee, Ranged, Magic)` |

## Experience Distribution

Stamina experience is gained by defeating enemies in combat. Experience distribution follows the Focus Training system:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Remaining 70%:** Split equally among Stamina, Intelligence, Attack, Defense, and Primary Training skill (14% each)

All combat styles (Stab, Slash, Smash, Ranged, Magic) can train Stamina.

## House Rooms

The Dining Room is a House room that provides Stamina buffs and global bonuses.

Each level provides:

* +1 Stamina level
* +0.03% HP regeneration
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Dining Room

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 125  Donut | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 20,000  Spaceberry Donut |
| 125  Cupcake | 250  Donut | 500  Blueberry Donut | 1,000  Blackberry Donut | 2,000  Strawberry Donut | 4,000  Mooberry Donut | 8,000  Marsberry Donut | 20,000  Spaceberry Cake |
| 1  Small Pouch | 250  Blueberry Donut | 500  Blackberry Donut | 1,000  Strawberry Donut | 2,000  Mooberry Donut | 4,000  Marsberry Donut | 8,000  Spaceberry Donut | 3  Giant Pouch |
| - | 250  Cupcake | 500  Blueberry Cake | 1,000  Blackberry Cake | 2,000  Strawberry Cake | 4,000  Mooberry Cake | 8,000  Marsberry Cake | 2,000  Super Stamina Coffee |
| - | 250  Blueberry Cake | 500  Blackberry Cake | 1,000  Strawberry Cake | 2,000  Mooberry Cake | 4,000  Marsberry Cake | 8,000  Spaceberry Cake | - |
| - | 3  Small Pouch | 1  Medium Pouch | 3  Medium Pouch | 1  Large Pouch | 3  Large Pouch | 1  Giant Pouch | - |
| - | - | - | 1,000  Stamina Coffee | - | - | - | - |

## See Also

* HP - Hit points and healing mechanics
* Coffee - Stamina Coffee and other stat-boosting consumables
* Houses - Dining Room and other house upgrades
* Focus Training - Combat experience distribution
* Combat Level - Overall combat effectiveness calculation

================================================================
## Intelligence
================================================================

Intelligence

 Intelligence Intelligence is a skill included in the Combat section of Milky Way Idle. It increases your maximum MP, allowing you to cast more Abilities in battle. Each level of Intelligence increases your maximum MP by 10 (base MP is 100 at level 1).

Intelligence also determines how many abilities you can equip at once:

| Intelligence Level | Ability Slots | Special Ability Slot |
| --- | --- | --- |
| 1-19 | 1 | 1 |
| 20-49 | 2 | 1 |
| 50-89 | 3 | 1 |
| 90+ | 4 | 1 |

**Special Abilities** have a dedicated slot separate from regular abilities. Special abilities include the five Aura abilities (Critical Aura, Fierce Aura, Guardian Aura, Mystic Aura, Speed Aura) and utility abilities (Insanity, Invincible, Revive).

### Formulas

Here are some calculations for Intelligence-related stats:

For combat level:
Combat Level = 0.1 \* (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 \* MAX(Attack, Defense, Melee, Ranged, Magic), where MAX is the maximum function (the highest number in the range).

For maximum MP:
Max MP = 100 + (Intelligence Level × 10)

### Library

The Library is a House room that provides Intelligence buffs and global bonuses.

Each level provides:

* +1 Intelligence level
* +0.03% MP regeneration
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Library

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 250  Gummy | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 20,000  Star Fruit Gummy |
| 250  Yogurt | 500  Gummy | 500  Apple Gummy | 1,000  Orange Gummy | 2,000  Plum Gummy | 4,000  Peach Gummy | 8,000  Dragon Fruit Gummy | 20,000  Star Fruit Yogurt |
| 2  Poke | 250  Apple Gummy | 500  Orange Gummy | 1,000  Plum Gummy | 2,000  Peach Gummy | 4,000  Dragon Fruit Gummy | 8,000  Star Fruit Gummy | 2  Silencing Shot |
| 2  Scratch | 500  Yogurt | 500  Apple Yogurt | 1,000  Orange Yogurt | 2,000  Plum Yogurt | 4,000  Peach Yogurt | 8,000  Dragon Fruit Yogurt | 2  Frost Surge |
| 2  Smack | 250  Apple Yogurt | 500  Orange Yogurt | 1,000  Plum Yogurt | 2,000  Peach Yogurt | 4,000  Dragon Fruit Yogurt | 8,000  Star Fruit Yogurt | 2  Nature's Veil |
| - | 2  Quick Shot | 2  Toughness | 2  Impale | 2  Rain Of Arrows | 2  Berserk | 2  Puncture | 2  Firestorm |
| - | 2  Water Strike | 2  Precision | 2  Cleave | 2  Ice Spear | 2  Frenzy | 2  Maim | 2,000  Super Intelligence Coffee |
| - | 2  Entangle | - | 2  Sweep | 2  Flame Blast | 2  Elemental Affinity | 2  Stunning Blow | - |
| - | 2  Fireball | - | 1,000  Intelligence Coffee | 2  Toxic Pollen | - | - | - |

## Experience Calculation

Intelligence experience is gained by defeating enemies in combat. Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally among all eligible skills for your combat style

All combat styles (Stab, Slash, Smash, Ranged, Magic) can train Intelligence.

**Note:** Experience gained is further modified by Wisdom and skill-specific Charm Experience bonuses. See Wisdom for the complete formula.

================================================================
## Attack
================================================================

Attack

 Attack is a Combat skill that increases your auto-attack speed, ability cast speed, and accuracy rating for all combat styles. Attack can be primary trained with the Stab combat style which uses spears as the weapon.

### Effects

Attack Speed is improved by 0.05% per Attack level.
Attack Interval=Base Interval(1 + Attack/2000)×(1+Attack Speed Bonus)

Cast Speed is improved by 0.05% per Attack level.
Cast Time=Base Cast Time(1 + Attack/2000)×Cast Speed Bonus

Accuracy increases by 1 per Attack level before any other modifiers.
Accuracy=(10+Attack)×(1+Bonus%)

Combat Level = 0.1 × (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 × MAX(Attack, Defense, Melee, Ranged, Magic)
The MAX function takes the largest number in the range.

### Dojo

The Dojo is a House room that provides Attack buffs and global bonuses.

Each level provides:

* +1 Attack level
* +0.5% attack speed
* +0.5% cast speed
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Dojo

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 16  Cheese Spear | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 160  Holy Spear |
| 8  Cheese Sword | 24  Cheese Spear | 32  Verdant Spear | 40  Azure Spear | 48  Burble Spear | 56  Crimson Spear | 64  Rainbow Spear | 80  Holy Sword |
| - | 24  Verdant Spear | 32  Azure Spear | 40  Burble Spear | 48  Crimson Spear | 56  Rainbow Spear | 64  Holy Spear | 2,000  Super Attack Coffee |
| - | 12  Cheese Sword | 16  Verdant Sword | 20  Azure Sword | 24  Burble Sword | 28  Crimson Sword | 32  Rainbow Sword | - |
| - | 12  Verdant Sword | 16  Azure Sword | 20  Burble Sword | 24  Crimson Sword | 28  Rainbow Sword | 32  Holy Sword | - |
| - | - | - | 1,000  Attack Coffee | - | - | - | - |

## Experience Calculation

Attack experience is gained by defeating enemies in combat. Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally between the Stamina, Intelligence, Attack and Defense skills

**Note:** Experience gained is further modified by Wisdom and skill-specific Charm Experience bonuses. See Wisdom for the complete formula.

================================================================
## Melee
================================================================

Melee

 Melee Melee is a skill included in the Combat section of Milky Way Idle. It increases your damage when using melee weapons in battle. Melee is the Primary Training skill for both the Slash and Smash combat styles, which use swords and maces respectively.

### Formulas

Here are some calculations for Melee-related stats:

For combat level:
Combat Level = 0.1 \* (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 \* MAX(Attack, Defense, Melee, Ranged, Magic), where MAX is the maximum function (the highest number in the range).

For melee damage:
Melee Damage = (10 + Melee) \* (1 + Bonus%)

### Gym

The Gym is a House room that provides Melee buffs and global bonuses.

Each level provides:

* +1 Melee level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Gym

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 16  Cheese Mace | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 160  Holy Mace |
| 8  Cheese Sword | 24  Cheese Mace | 32  Verdant Mace | 40  Azure Mace | 48  Burble Mace | 56  Crimson Mace | 64  Rainbow Mace | 80  Holy Sword |
| - | 24  Verdant Mace | 32  Azure Mace | 40  Burble Mace | 48  Crimson Mace | 56  Rainbow Mace | 64  Holy Mace | 2,000  Super Melee Coffee |
| - | 12  Cheese Sword | 16  Verdant Sword | 20  Azure Sword | 24  Burble Sword | 28  Crimson Sword | 32  Rainbow Sword | - |
| - | 12  Verdant Sword | 16  Azure Sword | 20  Burble Sword | 24  Crimson Sword | 28  Rainbow Sword | 32  Holy Sword | - |
| - | - | - | 1,000  Melee Coffee | - | - | - | - |

## Experience Calculation

Melee experience is gained by defeating enemies in combat. Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally among all eligible skills for your combat style

The Slash and Smash combat styles can train Melee.

================================================================
## Defense
================================================================

Defense

 Defense Defense is a skill included in the Combat section of Milky Way Idle. It increases your Evasion rating for all combat styles, allowing you to dodge enemy attacks more effectively.

### Formulas

Here are some calculations for Defense-related stats:

For combat level:
Combat Level = 0.1 \* (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 \* MAX(Attack, Defense, Melee, Ranged, Magic), where MAX is the maximum function (the highest number in the range).

For evasion rating (all combat styles):
Evasion Rating = (10 + Defense) \* (1 + Bonus%)

For defensive damage (when wielding Bulwark):
Defensive Damage = (10 + Defense) \* (1 + Bonus%)

When wielding a Bulwark, your damage scales with Defense level instead of Melee level, allowing tank builds to deal competitive damage.

### Armory

The Armory is a House room that provides Defense buffs and global bonuses.

Each level provides:

* +1 Defense level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Armory

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 8  Cheese Helmet | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 80  Holy Helmet |
| 8  Cheese Plate Body | 12  Cheese Helmet | 16  Verdant Helmet | 20  Azure Helmet | 24  Burble Helmet | 28  Crimson Helmet | 32  Rainbow Helmet | 80  Holy Plate Body |
| 8  Cheese Plate Legs | 12  Verdant Helmet | 16  Azure Helmet | 20  Burble Helmet | 24  Crimson Helmet | 28  Rainbow Helmet | 32  Holy Helmet | 80  Holy Plate Legs |
| 8  Cheese Gauntlets | 12  Cheese Plate Body | 16  Verdant Plate Body | 20  Azure Plate Body | 24  Burble Plate Body | 28  Crimson Plate Body | 32  Rainbow Plate Body | 80  Holy Gauntlets |
| 8  Cheese Boots | 12  Verdant Plate Body | 16  Azure Plate Body | 20  Burble Plate Body | 24  Crimson Plate Body | 28  Rainbow Plate Body | 32  Holy Plate Body | 80  Holy Boots |
| - | 12  Cheese Plate Legs | 16  Verdant Plate Legs | 20  Azure Plate Legs | 24  Burble Plate Legs | 28  Crimson Plate Legs | 32  Rainbow Plate Legs | 2,000  Super Defense Coffee |
| - | 12  Verdant Plate Legs | 16  Azure Plate Legs | 20  Burble Plate Legs | 24  Crimson Plate Legs | 28  Rainbow Plate Legs | 32  Holy Plate Legs | - |
| - | 12  Cheese Gauntlets | 16  Verdant Gauntlets | 20  Azure Gauntlets | 24  Burble Gauntlets | 28  Crimson Gauntlets | 32  Rainbow Gauntlets | - |
| - | 12  Verdant Gauntlets | 16  Azure Gauntlets | 20  Burble Gauntlets | 24  Crimson Gauntlets | 28  Rainbow Gauntlets | 32  Holy Gauntlets | - |
| - | 12  Cheese Boots | 16  Verdant Boots | 20  Azure Boots | 24  Burble Boots | 28  Crimson Boots | 32  Rainbow Boots | - |
| - | 12  Verdant Boots | 16  Azure Boots | 20  Burble Boots | 24  Crimson Boots | 28  Rainbow Boots | 32  Holy Boots | - |
| - | - | - | 1,000  Defense Coffee | - | - | - | - |

## Experience Calculation

Defense experience is gained by defeating enemies in combat. Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally among all eligible skills for your combat style

Defense is not a Primary Training skill for any weapon type. Defense can receive experience through Focus Training (by equipping a Defense charm) or through the default split distribution when no charm is equipped.

All combat styles (Stab, Slash, Smash, Ranged, Magic) can train Defense.

**Note:** Experience gained is further modified by Wisdom and skill-specific Charm Experience bonuses. See Wisdom for the complete formula.

================================================================
## Magic
================================================================

Magic

 Magic is a skill included in the Combat section of Milky Way Idle. It increases your damage when using magic weapons in battle. Magic is the Primary Training skill for the Magic combat style, which uses staves and wands to cast elemental spells (Fire, Water, Nature).

### Formulas

Here are some calculations for Magic-related stats:

For combat level:
Combat Level = 0.1 \* (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 \* MAX(Attack, Defense, Melee, Ranged, Magic), where MAX is the maximum function (the highest number in the range).

For magic damage:
Magic Damage = (10 + Magic) \* (1 + Bonus%)

### Elemental Procs

Magic staves provide unique proc-based effects that trigger after casting abilities:

* **Fire Staves (Blaze):** Chance to cast bonus AoE fire attack dealing 30% of max damage to all enemies
* **Nature Staves (Bloom):** Chance to heal the lowest HP ally for 10 + 15% of max damage
* **Water Staves (Ripple):** Chance to restore 10 mana and reduce all ability cooldowns by 2 seconds

See Combat Mechanics for full details.

### Mystical Study

The Mystical Study is a House room that provides Magic buffs and global bonuses.

Each level provides:

* +1 Magic level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Mystical Study

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 4  Wooden Water Staff | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 40  Arcane Water Staff |
| 4  Wooden Nature Staff | 6  Wooden Water Staff | 8  Birch Water Staff | 10  Cedar Water Staff | 12  Purpleheart Water Staff | 14  Ginkgo Water Staff | 16  Redwood Water Staff | 40  Arcane Nature Staff |
| 4  Wooden Fire Staff | 6  Birch Water Staff | 8  Cedar Water Staff | 10  Purpleheart Water Staff | 12  Ginkgo Water Staff | 14  Redwood Water Staff | 16  Arcane Water Staff | 40  Arcane Fire Staff |
| 4  Cotton Hat | 6  Wooden Nature Staff | 8  Birch Nature Staff | 10  Cedar Nature Staff | 12  Purpleheart Nature Staff | 14  Ginkgo Nature Staff | 16  Redwood Nature Staff | 40  Radiant Hat |
| 4  Cotton Robe Top | 6  Birch Nature Staff | 8  Cedar Nature Staff | 10  Purpleheart Nature Staff | 12  Ginkgo Nature Staff | 14  Redwood Nature Staff | 16  Arcane Nature Staff | 40  Radiant Robe Top |
| 4  Cotton Robe Bottoms | 6  Wooden Fire Staff | 8  Birch Fire Staff | 10  Cedar Fire Staff | 12  Purpleheart Fire Staff | 14  Ginkgo Fire Staff | 16  Redwood Fire Staff | 40  Radiant Robe Bottoms |
| 4  Cotton Gloves | 6  Birch Fire Staff | 8  Cedar Fire Staff | 10  Purpleheart Fire Staff | 12  Ginkgo Fire Staff | 14  Redwood Fire Staff | 16  Arcane Fire Staff | 40  Radiant Gloves |
| 4  Cotton Boots | 8  Linen Hat | 16  Linen Hat | 16  Bamboo Hat | 32  Bamboo Hat | 24  Silk Hat | 48  Silk Hat | 40  Radiant Boots |
| - | 8  Linen Robe Top | 16  Linen Robe Top | 16  Bamboo Robe Top | 32  Bamboo Robe Top | 24  Silk Robe Top | 48  Silk Robe Top | 2,000  Super Magic Coffee |
| - | 8  Linen Robe Bottoms | 16  Linen Robe Bottoms | 16  Bamboo Robe Bottoms | 32  Bamboo Robe Bottoms | 24  Silk Robe Bottoms | 48  Silk Robe Bottoms | - |
| - | 8  Linen Gloves | 16  Linen Gloves | 16  Bamboo Gloves | 32  Bamboo Gloves | 24  Silk Gloves | 48  Silk Gloves | - |
| - | 8  Linen Boots | 16  Linen Boots | 16  Bamboo Boots | 32  Bamboo Boots | 24  Silk Boots | 48  Silk Boots | - |
| - | - | - | 1,000  Magic Coffee | - | - | - | - |

## Experience Calculation

Magic experience is gained by defeating enemies in combat. Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally among all eligible skills for your combat style

The Magic combat style can train Magic.

**Note:** Experience gained is further modified by Wisdom and skill-specific Charm Experience bonuses. See Wisdom for the complete formula.

================================================================
## Ranged
================================================================

Ranged

 Ranged Ranged is a skill included in the Combat section of Milky Way Idle. It increases your damage when using ranged weapons in battle. Ranged is the Primary Training skill for the Ranged combat style, which uses bows and has a unique 30% base critical hit chance.

### Formulas

Here are some calculations for Ranged-related stats:

For combat level:
Combat Level = 0.1 \* (Stamina + Intelligence + Attack + Defense + MAX(Melee, Ranged, Magic)) + 0.5 \* MAX(Attack, Defense, Melee, Ranged, Magic), where MAX is the maximum function (the highest number in the range).

For ranged damage:
Ranged Damage = (10 + Ranged) \* (1 + Bonus%)

### Archery Range

The Archery Range is a House room that provides Ranged buffs and global bonuses.

Each level provides:

* +1 Ranged level
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Archery Range

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 6  Wooden Crossbow | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 60  Arcane Crossbow |
| 4  Wooden Bow | 9  Wooden Crossbow | 12  Birch Crossbow | 15  Cedar Crossbow | 18  Purpleheart Crossbow | 21  Ginkgo Crossbow | 24  Redwood Crossbow | 40  Arcane Bow |
| 4  Rough Hood | 9  Birch Crossbow | 12  Cedar Crossbow | 15  Purpleheart Crossbow | 18  Ginkgo Crossbow | 21  Redwood Crossbow | 24  Arcane Crossbow | 40  Umbral Hood |
| 4  Rough Tunic | 6  Wooden Bow | 8  Birch Bow | 10  Cedar Bow | 12  Purpleheart Bow | 14  Ginkgo Bow | 16  Redwood Bow | 40  Umbral Tunic |
| 4  Rough Chaps | 6  Birch Bow | 8  Cedar Bow | 10  Purpleheart Bow | 12  Ginkgo Bow | 14  Redwood Bow | 16  Arcane Bow | 40  Umbral Chaps |
| 4  Rough Bracers | 8  Reptile Hood | 16  Reptile Hood | 16  Gobo Hood | 32  Gobo Hood | 24  Beast Hood | 48  Beast Hood | 40  Umbral Bracers |
| 4  Rough Boots | 8  Reptile Tunic | 16  Reptile Tunic | 16  Gobo Tunic | 32  Gobo Tunic | 24  Beast Tunic | 48  Beast Tunic | 40  Umbral Boots |
| - | 8  Reptile Chaps | 16  Reptile Chaps | 16  Gobo Chaps | 32  Gobo Chaps | 24  Beast Chaps | 48  Beast Chaps | 2,000  Super Ranged Coffee |
| - | 8  Reptile Bracers | 16  Reptile Bracers | 16  Gobo Bracers | 32  Gobo Bracers | 24  Beast Bracers | 48  Beast Bracers | - |
| - | 8  Reptile Boots | 16  Reptile Boots | 16  Gobo Boots | 32  Gobo Boots | 24  Beast Boots | 48  Beast Boots | - |
| - | - | - | 1,000  Ranged Coffee | - | - | - | - |

## Experience Calculation

Ranged experience is gained by defeating enemies in combat. Experience distribution depends on your equipment:

* **Primary Training:** 30% of monster experience goes to the skill determined by your weapon
* **Focus Training:** 70% of monster experience goes to the skill determined by your charm (if equipped)
* **Without Focus Training:** The 70% is split equally among all eligible skills for your combat style

The Ranged combat style can train Ranged.

================================================================
## HP (Hit Points)
================================================================

A tab displaying a character's name, along with two bars displaying their HP (in green) and their **MP** (in blue)

**Hit Points**, commonly abbreviated as **HP**, is one of your main stats in Milky Way Idle's combat system. It determines how much damage a character can take before being defeated.

## Maximum HP

Your maximum HP is determined by your Stamina level plus bonuses from equipment and house rooms.

| Maximum HP Formula |
| --- |
| `Maximum HP = floor(10 × (10 + Effective Stamina Level) + Equipment HP Bonuses)` |

### Equipment with HP Bonuses

| Item | Level | HP Bonus |
| --- | --- | --- |
| Small Pouch | 1 | +50 |
| Medium Pouch | 10 | +100 |
| Large Pouch | 20 | +150 |
| Giant Pouch | 35 | +200 |
| Gluttonous Pouch | 50 | +250 |
| Guzzling Pouch | 65 | +250 |
| Shoebill Shoes | 80 | +50 |
| Colossus Plate Legs | 85 | +100 |
| Colossus Plate Body | 85 | +120 |
| Knight's Aegis | 95 | +100 (108 refined) |
| Corsair Helmet | 75 | +100 (108 refined) |
| Anchorbound Plate Legs | 95 | +200 (216 refined) |
| Anchorbound Plate Body | 95 | +250 (270 refined) |

### House Room Bonuses

The Dining Room is a House room that provides Stamina buffs and global bonuses.

Each level provides:

* +1 Stamina level
* +0.03% HP regeneration
* +0.05% Wisdom
* +0.2% Rare Find (increases drop rate for all rare items)

Upgrade Costs for Dining Room

| Level 1 | Level 2 | Level 3 | Level 4 | Level 5 | Level 6 | Level 7 | Level 8 |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 500,000  Coin | 2,000,000  Coin | 5,000,000  Coin | 12,000,000  Coin | 25,000,000  Coin | 50,000,000  Coin | 90,000,000  Coin | 160,000,000  Coin |
| 75  Lumber | 150  Lumber | 300  Birch Lumber | 600  Cedar Lumber | 1,200  Purpleheart Lumber | 2,400  Ginkgo Lumber | 4,800  Redwood Lumber | 12,000  Arcane Lumber |
| 125  Donut | 150  Birch Lumber | 300  Cedar Lumber | 600  Purpleheart Lumber | 1,200  Ginkgo Lumber | 2,400  Redwood Lumber | 4,800  Arcane Lumber | 20,000  Spaceberry Donut |
| 125  Cupcake | 250  Donut | 500  Blueberry Donut | 1,000  Blackberry Donut | 2,000  Strawberry Donut | 4,000  Mooberry Donut | 8,000  Marsberry Donut | 20,000  Spaceberry Cake |
| 1  Small Pouch | 250  Blueberry Donut | 500  Blackberry Donut | 1,000  Strawberry Donut | 2,000  Mooberry Donut | 4,000  Marsberry Donut | 8,000  Spaceberry Donut | 3  Giant Pouch |
| - | 250  Cupcake | 500  Blueberry Cake | 1,000  Blackberry Cake | 2,000  Strawberry Cake | 4,000  Mooberry Cake | 8,000  Marsberry Cake | 2,000  Super Stamina Coffee |
| - | 250  Blueberry Cake | 500  Blackberry Cake | 1,000  Strawberry Cake | 2,000  Mooberry Cake | 4,000  Marsberry Cake | 8,000  Spaceberry Cake | - |
| - | 3  Small Pouch | 1  Medium Pouch | 3  Medium Pouch | 1  Large Pouch | 3  Large Pouch | 1  Giant Pouch | - |
| - | - | - | 1,000  Stamina Coffee | - | - | - | - |

## HP Recovery

HP recovers through natural regeneration, consumables, and healing abilities.

| HP Regeneration Formula |
| --- |
| `HP per 10 seconds = Base Regeneration + House Room Bonuses` |

### Base Regeneration

All players regenerate HP at a base rate during combat.

| Base HP Regeneration | Rate |
| --- | --- |
| Per 10 seconds | 1.0% of Maximum HP |

### Healing Abilities

Several abilities can restore HP during combat:

| Ability | Effect | Target | Mana Cost |
| --- | --- | --- | --- |
| Minor Heal | 20 + 30% Magic damage | Self | 30 |
| Heal | 30 + 45% Magic damage | Self | 60 |
| Quick Aid | 40 + 30% Magic damage | Lowest HP ally | 60 |
| Rejuvenate | 30 + 20% Magic damage | All allies | 90 |

### Food Recovery

Food items crafted through Cooking provide HP restoration:

* **Donuts**: Instant HP recovery
* **Cakes**: 25% more healing than donuts, split over 30 seconds

Players cannot equip two food items of the same type simultaneously.

## Example Calculations

**Example 1**

| Component | Value |
| --- | --- |
| Stamina Level | 25 |
| Base HP | floor(10 × (10 + 25)) = 350 HP |
| Medium Pouch | +100 HP |
| **Total Maximum HP** | **450 HP** |
| Base Regen per 10s | 1.0% of 450 = 4.5 HP |
| Dining Room Level 2 | +0.06% of 450 = 0.27 HP |
| **Total HP Regen per 10s** | **4.77 HP** |

**Example 2**

| Component | Value |
| --- | --- |
| Stamina Level | 80 |
| Base HP | floor(10 × (10 + 80)) = 900 HP |
| Guzzling Pouch | +250 HP |
| Anchorbound Plate Body | +250 HP |
| Anchorbound Plate Legs | +200 HP |
| **Total Maximum HP** | **1,600 HP** |
| Base Regen per 10s | 1.0% of 1,600 = 16.0 HP |
| Dining Room Level 8 | +0.48% of 1,600 = 7.68 HP |
| **Total HP Regen per 10s** | **23.68 HP** |

## Death and Respawn

When a player's HP reaches zero, they are defeated and automatically respawn after 150 seconds (2.5 minutes) with full HP and MP restored, except in Dungeons where no respawn occurs, only failure.

## See Also

* MP - The other primary combat resource
* Stamina - The skill that determines maximum HP
* Regeneration - Stat that affects HP regeneration rate
* Abilities - Actions that consume HP or provide healing
* Food - Consumables that can restore HP
