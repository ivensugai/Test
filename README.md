# 🐉 Dragon Quest Lite — A Quick Pokémon Adventure

A tiny, self-contained overworld RPG in the spirit of *Dragon Warrior*.
Walk a map, run into monsters in the tall grass, level up, and defeat the
Dragon Lord. No build step, no dependencies — just one HTML file.

## Play

- **Hosted:** https://ivensugai.github.io/Test/
- **Local:** open `index.html` in any modern browser. That's it.

## The quest

The **Dragon Lord** 🐉 has seized the castle to the east. Cross the wilds,
grow stronger by battling monsters, and reach the castle to defeat him.
If you faint, the quest is over.

## How to play

1. **Pick a partner** — Flamepup (Fire), Aquafin (Water), or Leaflet (Grass).
2. **Explore the map** with the **arrow keys / WASD** or the on-screen D-pad.
3. **Tall grass 🟩** hides random monster encounters; **roads 🟫** are safe.
4. **Battle** wild monsters to level up and gain max HP. Your HP carries
   over between fights — return **home 🏠** any time to heal to full.
5. **Reach the castle 🏰** and defeat the **Dragon Lord** to win. (You can't
   flee the final battle!)

## Mechanics

- **Type matchups** — Fire > Grass > Water > Fire, plus Electric > Water.
  Super-effective hits do 2×, resisted hits ½.
- **STAB** — a move matching your type gets a 1.5× bonus.
- **Persistent HP** — damage carries across the overworld; heal at home.
- **Random encounters** — ~18% chance per step in tall grass.
- **Sound** — retro 8-bit-style effects (steps, hits, heals, victory
  fanfare) synthesized live with the Web Audio API — no audio files.
  Toggle with the 🔊 button in the top-right.

Have fun, hero! 🦊🐢🦎⚔️🐉
