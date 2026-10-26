# D&D 5e Character Sheet for Roll20

A custom Dungeons & Dragons 5th Edition character sheet for [Roll20](https://roll20.net), with a dark red-and-gold look, styled chat rolls and a lot of automation: linked features, ammunition, limited uses, active effects and more. It also has an NPC stat block mode.

## Installation

You need to be the GM of the game, with a Roll20 account that allows custom sheets.

1. Open the game's **Settings → Game Settings**.
2. Under **Character Sheet Template**, choose **Custom**.
3. Paste the contents of [`sheet.html`](sheet.html) into the **HTML Layout** tab.
4. Paste the contents of [`sheet.css`](sheet.css) into the **CSS Styling** tab.
5. Click **Save Changes**, then open a character.

The images are loaded straight from the [`Sheet_Art`](Sheet_Art) folder of this repository, so keep that folder (and its file names) where it is.

## Repository layout

```
Character_Sheet_for_Roll20/
├── README.md     - this file
├── sheet.html    - Roll20 "HTML Layout" (layout + sheet workers + roll template)
├── sheet.css     - Roll20 "CSS Styling"
└── Sheet_Art/    - all images used by the sheet (PNG)
```

## Pages

**Core**
- Header with name, class, race and level; the dragon crest shows the first name.
- Initiative (with a pop-up bonus), speed, exhaustion (hover for its effects), conditions (pills with rules on hover) and a **Kill Count** by creature type.
- Armor Class, resistances / immunities / vulnerabilities / condition immunities, hit points, hit dice (maximum follows your level), death saves and a **Quest Log**.
- Abilities and saving throws (scores are set in a pop-up breakdown: base, racial, feat, ASI, magic items, magical override), skills with hover descriptions.
- Proficiency bonus, inspiration, spell save DC and attack, passive senses.
- **Limited Features** with short rest / long rest / dawn recovery (all uses, a fixed number or a rolled number).
- **Active Effects** with durations in rounds, minutes or hours, *Next round*, and a *Concentration* save button.
- Summary of spell slots (hover a level for its prepared spells), racial traits, background feature, class features, magical items, feats and acquired skills (hover for descriptions).
- Weight carried, each container's load, and money.
- **Actions, Bonus Actions and Reactions**: attacks with weapon properties (finesse, versatile, heavy, reinforced, rusted…), saves, damage, and the built-in **Harvest** check.

**Equipment**: items on your person and in up to 8 containers with weight limits, encumbrance, rations and waterskins, coins.

**Skills**: racial traits, class features, magical items, feats and acquired skills. Any of them can become an action, a limited feature or an active effect, and magical items can be carried in a container and grant spells.

**Spells**: cantrips to 9th level with slots, preparation, attack / save / damage rolls, upcasting and cantrip scaling.

**Features**: personality, ideals, bonds, flaws, background feature, appearance and history.

**Notes**: free notes for the campaign.

## Roll modes

The bar at the top switches every d20 roll between **Normal**, **Advantage** and **Disadvantage**; with advantage or disadvantage both dice are shown in chat and the one that counts is highlighted.
