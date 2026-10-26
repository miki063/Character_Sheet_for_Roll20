# D&D 5e Character Sheet for Roll20

> ☕ **Enjoying the sheet?** Any tip is greatly appreciated: **PayPal – mikulas.barna@seznam.cz**. Thank you! (It took a lot of time, but you certainly do not have to send anything. Just enjoy the sheet :))

A custom Dungeons & Dragons 5th Edition character sheet for [Roll20](https://roll20.net). It has a dark red-and-gold look, its own styled chat cards, and a lot of automation, so you spend less time doing bookkeeping and more time playing:

- features, items and feats turn into actions, limited uses or active effects with one click
- weapons know their properties (finesse, versatile, heavy, ammunition…) and spend ammunition by themselves
- rests restore what they should, effects count down, and encumbrance is calculated for you
- almost everything shows a description when you hover over it

It also includes an **NPC mode** with a classic stat block.

---

## Contents

1. [Installation](#installation)
2. [Repository layout](#repository-layout)
3. [The pages](#the-pages)
4. [How the automation works](#how-the-automation-works)
5. [Rolls and the chat](#rolls-and-the-chat)
6. [NPC mode](#npc-mode)
7. [Tips and troubleshooting](#tips-and-troubleshooting)

---

## Installation

You need to be the **GM** of the game. Custom character sheets require a Roll20 account that allows them.

1. Open your game and go to **Settings → Game Settings**.
2. Under **Character Sheet Template**, choose **Custom**.
3. Open [`sheet.html`](sheet.html), copy everything, and paste it into the **HTML Layout** tab.
4. Open [`sheet.css`](sheet.css), copy everything, and paste it into the **CSS Styling** tab.
5. Click **Save Changes**, then open (or create) a character.

**Updating to a newer version:** repeat steps 3–5. Existing characters keep their data; anything the sheet needs to convert is converted automatically the next time the character is opened.

The images are loaded directly from the [`Sheet_Art`](Sheet_Art) folder of this repository, so keep the folder and its file names as they are.

---

## The pages

### Header (always visible)

Name, player, class, subclass, background, race, size, height, weight, appearance, alignment, faith and **level**. The dragon crest shows the character's first name. The proficiency bonus and many other numbers follow the level automatically.

Below the header:

- **Initiative** – click the number to roll it (it is added to the turn tracker). The **≡** next to it opens a small pop-up for an extra initiative bonus.
- **Speed** and **Exhaustion** – hover over Exhaustion to see what your current level does.
- **Conditions** – active conditions are shown as red pills; **Edit** opens a pop-up with all conditions plus *Other* (with a short text). Hover over a condition to read its rules.
- **Kill Count** – the total of creatures slain. The arrow opens a list of all creature types with **–** / **+** buttons; the total can only be changed there.

Then the combat block: **Armor Class** (base, Dex modifier with an optional maximum, shield and any number of extra modifiers), **Resistances / Immunities / Vulnerabilities / Condition Immunities** (picked in a pop-up, hover the labels for what they mean), **Quest Log**, **hit points** (current, maximum, temporary, with Damage and Heal buttons), **hit dice** (the maximum equals your level) and **death saves**.

### Core

- **Abilities** – score, modifier and saving throw. Scores are not typed directly: click a score to open the **ability breakdown** (Score Base, Racial Bonus, Feat Bonus, ASIs from Classes, Magic Items, Magical Override). The override replaces the total only when it is higher. Hover over an ability for a short description.
- **Skills** – bonus, proficiency, expertise and a misc bonus. Hover over a skill to see what it covers.
- **Proficiency bonus**, **Inspiration**, **spell save DC / spell attack**, **passive Perception, Insight and Investigation**, senses.
- **Limited Features** – used / maximum, recovery (short rest, long rest, dawn, never) and a **+1** button. The **≡** opens editing (what a rest restores and the description), the triangle shows the description.
- **Active Effects** – see [Active effects](#active-effects).
- **Summary** – spell slots (hover a level to list its prepared spells), racial traits, background feature, class features, magical items, feats and acquired skills. Hover a name to read its description. Lists that are empty or hidden are not shown.
- **Weight** – total carried weight against your capacity, plus every container's load; it glows red when you are encumbered. Below it: **GP, SP, CP**.
- **Actions, Bonus Actions and Reactions** – your own entries plus everything added from other pages. The basic options (Attack, Dash, Dodge, Help, Grapple, Shove, Improvise…) are listed above each group; hover any of them for an explanation.

### Equipment

- Items carried **on your person** and in up to **8 containers** (backpack, pouches, bag of holding…), each with an optional weight limit. A container can count towards carried weight or not, and its limit can be added to your capacity. A container that still holds items cannot be removed; a re-added container starts empty.
- **Rations and waterskins** are managed in a small grid (how many in which container).
- **Coins** and their weight (optional), total wealth, carrying capacity and encumbrance (15 × Strength).
- Any item can be made into an action (e.g. a weapon with its attack and damage).

### Skills

Cards for **Racial Traits, Class Features, Magical Items, Feats** and **Acquired Skills**. Each card has a name, a source and a description, and its **≡** options let you:

- **Use as** an action, bonus action or reaction (as a simple skill or as an attack),
- make it a **Limited feature** (maximum uses, recovery, how much a rest restores),
- make it **become an active effect** when used,
- choose whether it is **shown on Core**.

Magical items also have charges, attunement, where they are carried, and up to three **spells** they grant.

### Spells

Cantrips and levels 1–9 with slots per level, the number of spells you can prepare and how many are prepared. Each spell has school, casting time, range, target, components, duration, concentration and ritual, and can be a plain **spellcard** or an **attack** (spell attack, saving throw, damage or healing). Upcasting asks for the slot level and adds the extra dice; cantrip damage scales at levels 5, 11 and 17. Spells granted by magical items are listed separately.

### Features

Personality traits, ideals, bonds, flaws, **background feature**, appearance, character history, allies, enemies and notes.

### Notes

Free notes for the campaign (sessions, NPCs, places…).

---

## How the automation works

### Linked copies

When a card on the Skills or Equipment page is set to *Use as* or *Limited feature*, a **copy** appears on Core (in Actions or Limited Features). The copy always follows the original: change the name, description, maximum uses or attack on the original and the copy updates. Copies are marked with their source and can only be removed on their original page – if you delete one on Core, it comes back.

### Weapons and attacks

An attack has an ability (Strength, Dexterity, spellcasting…), proficiency, hit bonus, damage, a second damage type and an optional saving throw. **Weapon properties** are picked as pills:

| Property | What the sheet does |
|---|---|
| Finesse | uses the better of Strength and Dexterity |
| Versatile | asks *one-handed or two-handed* when you roll and uses the right die |
| Heavy | rolls with disadvantage if your size is Small or Tiny |
| Range / Thrown | shows a range field; without them the attack is melee |
| Reach | marks the attack as reach 10 ft |
| Reinforced | rolls one extra damage die and drops the lowest |
| Rusted | rolls one extra damage die and drops the highest |
| Ammunition | see below |

**Ammunition:** either *Create new* (the weapon gets its own ammunition row in the container you choose) or *Connect to existing* (pick ammunition another weapon created – e.g. a longbow and a shortbow sharing the same arrows). Every attack spends one piece and the count is updated everywhere; at 0 the sheet posts *Out of …!* instead of rolling.

### Limited features and rests

- **Short Rest** restores short-rest features.
- **Long Rest** restores short- and long-rest features, hit points, half of your hit dice, spell slots, death saves and one level of exhaustion.
- **Dawn** restores dawn features.

Each feature can restore *all uses*, *a fixed number* or *a rolled number* (e.g. 1d6+1 – the roll is posted to chat). A magical item's limited uses are its charges.

### Active effects

Actions, Skills cards and spells can be set to **Become an active effect when used** (with a duration and concentration). They then get a **✦** button: pressing it adds the effect to *Active Effects* and posts a short line to chat. The eye button still only shows the description.

- **Next round** counts every timed effect down by one round (1 minute = 10 rounds); effects that run out disappear.
- A **short rest** counts as 1 hour and ends *until short rest* effects; a **long rest** counts as 8 hours and ends both rest types.
- Only one **concentration** effect can be active at a time.
- **Concentration** asks how much damage you took and rolls a Constitution save against DC 10 or half the damage (rounded down), whichever is higher. On a failure the concentration effect is removed.
- Effects can also be added by hand with **+Add**.

### Harvest

**Harvest** is always the first action. Choose the creature type and the sheet rolls a Dexterity check plus your proficiency in that type's skill (Arcana, Nature, Investigation or Medicine; expertise counts double). If you are not proficient, it asks whether someone helping you is – if yes, you add your proficiency bonus.

---

## Rolls and the chat

- The bar at the top switches **every d20 roll** between **Normal**, **Advantage** and **Disadvantage**. With advantage or disadvantage both dice are shown and the one that counts is highlighted.
- Chat cards show the roll, the bonus used, critical hits (with the extra damage), damage and its type, saving throw DCs and a button to show the description.
- Hover over a roll in chat to see how it was calculated.

---

## NPC mode

Switch **Sheet Type** (top right) to **NPC** for a classic stat block: AC, hit points (with a *Roll HP* button for the hit dice formula), speed, abilities, saving throws, skills, resistances, senses, languages, challenge rating (XP and proficiency bonus are filled in), traits, actions, bonus actions, reactions and legendary actions. NPC rolls can be sent publicly or only to the GM.

---

## Tips and troubleshooting

- **Images don't show** – make sure the `Sheet_Art` folder is still in this repository with the original file names.
- **A copy on Core keeps coming back** – remove it on its original page (Skills / Equipment) or switch off *Use as* / *Limited feature* there.
- **Something looks out of date** – close the character and open it again; the sheet re-checks all links when it opens, and again whenever you switch to the Core tab.
- **Rows with a red frame** – Roll20 marks rows it considers broken. The sheet hides that frame; if an empty or duplicated row is left behind, delete it with Roll20's *Modify* button.

---

If you find a bug or have an idea, feel free to open an issue. And once more – if the sheet makes your games easier, a tip on **PayPal (mikulas.barna@seznam.cz)** is very welcome. Happy adventuring! 🐉
