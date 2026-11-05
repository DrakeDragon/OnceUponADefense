# Once Upon a Defense

A fairytale tower defense game for your phone. Place storybook heroes along the paths, upgrade them down three different paths, and hold off waves of goblins, trolls, witches and giant bosses for 50, 75 or even 100 waves. When you win, keep going in endless **Free Play**.

This is a static, touch-first game built with HTML, CSS, JavaScript, and Canvas. The package includes all runtime artwork and runs without a build step, external libraries, or a backend.

## What's included

| File | Purpose |
|---|---|
| `index.html` | The game, including its interface, simulation, and Canvas renderer |
| `.nojekyll` | Lets GitHub Pages publish the static files directly |
| `README.md` | Deployment instructions and player guide |
| `art/atlas.webp` | Tower idle sprites, menu portraits, scenery, and enemy fallback art |
| `art/ground.webp` | Painted terrain texture |
| `art/enemy-motion.webp` | Four movement frames for each of the 22 enemies |
| `art/tower-motion.webp` | Three action frames for each of the 21 towers |

The illustrated combat build includes textured boards, animated enemies and towers, projectile trails, impact sparks, beams, chain lightning, and spell pulses.

## Deploy on GitHub Pages

1. Extract the ZIP. Keep the `art/` folder beside `index.html`.
2. For an existing site, copy the extracted contents into the folder your repository already publishes. Commit the update to its publishing branch. Keep any existing custom-domain configuration.
3. For a new site, commit the contents to the root of your repository on `main`. In **Settings → Pages**, choose **Deploy from a branch**, then select **main** and **/ (root)** and save. [GitHub Pages publishing documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
4. When the deployment succeeds, open the URL shown in **Settings → Pages**. On your phone, start a wave and check that enemies animate and towers show their attack effects. If the old graphics still appear, refresh the page and check that all four WebP files were committed under `art/`.

Existing progress carries over when you update the same site and open it in the same browser profile. The save is stored locally under `ouad_v1` and is scoped to the site's origin. Changing the domain, using a different browser or device, or clearing site data can make the game start fresh.

## Run locally

Open the extracted `index.html` in a modern browser for a quick preview. To test through HTTP, open a terminal in the extracted folder, run `python -m http.server 8000`, then visit `http://localhost:8000`. The local preview has its own save.

## How to play

- Pick a **board** and a **difficulty**, then choose up to **6 towers** for your loadout.
- Tap a tower in the bottom tray, then tap an empty grass tile to build it. You cannot build on the path or on decorations.
- Tap a placed tower to see its stats, change its **targeting mode** (First, Last, Strong, Weak, Close), sell it, or buy upgrades.
- Press **▶ Wave** to send the next wave. **Auto** starts waves for you, **x1/x2/x3** changes speed, **⏸** pauses.
- Enemies that reach the end cost you lives. Reach 0 lives and the run is over. Survive the final wave to win.
- Gold comes from defeating enemies and from a bonus at the end of every wave.

---

## Boards

| Board | Notes |
|---|---|
| Red's Forest | The starter board |
| Beanstalk Hill | A different route layout |
| Gingerbread Crossroads | A more winding route |

Each board has a fixed route layout. Flying enemies ignore the path and fly in a straight line from start to finish. Boards unlock in order as you clear earlier ones.

## Difficulties

| | Waves to win | Starting lives | Starting gold | Bean reward |
|---|---|---|---|---|
| Easy | 50 | 150 | 750 | 80 |
| Medium | 75 | 100 | 700 | 250 |
| Hard | 100 | 60 | 650 | 600 |

Bean rewards are multiplied by a per-board bonus (x1, x1.5, x2). Difficulty only ramps slowly: the first waves are a handful of weak enemies, new enemy types arrive gradually, and the first boss does not show up until wave 25.

Rewards:
- First clear pays full beans. Repeat clears pay 20%.
- A **flawless** first clear (no lives lost) pays +25%.
- Clearing **all three difficulties** on a board gives a +500 bean bonus.
- Losing still pays a little: wave reached divided by 3, times the board multiplier.

---

## Free Play

Win the final wave and a Victory screen lets you choose:
- **♾ Keep going: Free Play**: the run continues with no end. The wave counter shows ∞ and waves keep scaling. A boss comes **every 10 waves** after the finish (Troll King, Hydra, Dragon Queen, The Last Giant, then the cycle repeats with more bosses each time around).
- **Finish and leave**: your win still counts.
- **Bean Shop**: jump straight to spending.

Free Play gives XP for every extra wave and a few beans when the run ends (extra waves divided by 5, times the board multiplier). Win rewards are only paid the first time.

---

## Towers (21)

Every tower has **three upgrade paths of five tiers each**. You can use at most **two** paths on a tower, and only **one** of them can go past tier 2 (to tier 5). Choose what each tower becomes.

**Starters (6, always available)**

| Tower | Upgrade paths | Role |
|---|---|---|
| 🏹 Robin's Archer | Volley / Piercing / Merry Men | Fast homing arrows |
| 🪨 Giant's Slingshot | Boulders / Cluster / Stompers | Splash damage |
| ❄️ Snow Queen | Blizzard / Shatter / Frozen Heart | Pulses that slow and freeze |
| 🍎 Poison Apple | Potency / Contagion / Orchard | Poison that spreads |
| 🧚 Fairy Wand | Arc / Stun / Fairy Magic | Chain lightning |
| 🎯 Huntsman | Marksman / Hunter's Mark / Quick Draw | Long-range sniper, marks targets |

**Bean Shop towers (5)**

| Tower | Cost | Upgrade paths | Role |
|---|---|---|---|
| 🐱 Puss in Boots | 120 🫘 | Swift Claws / Cat Burglar / Seven League Boots | Cheap, fast fighter |
| 🪞 Mirror Mirror | 220 🫘 | Reflections / Radiance / Vanity | Chain magic, reaches camouflaged foes |
| 🪈 Pied Piper | 300 🫘 | Melody / Rat Choir / Tempo | Pushes enemies back along the path |
| 🌱 Beanstalk | 450 🫘 | Growth / Thorns / Reach | Pulse damage that grows over time |
| 💰 Rumpelstiltskin | 700 🫘 | Wealth / Haggle / Contract | Earns gold every wave |

**Level-unlock towers (10)**, unlocked by your player level:

| Level | Tower | Upgrade paths |
|---|---|---|
| 3 | 🏠 Gingerbread Cottage | Sticky Sweets / Sweet Bites / Little Bakers |
| 5 | 🧱 Brick House | Straw to Brick / Huff and Puff / Chimney |
| 7 | 🧵 Sleeping Spindle | Deep Sleep / Pricked Finger / Spinning Wheel |
| 9 | 🪓 Woodcutter | Axe Head / Timber / Woodsman |
| 11 | 🕛 Midnight Clock | Slow Time / Chimes / Gears |
| 14 | 🐉 Fire Drake | Dragonfire / Burn / Wings |
| 17 | 🧞 Genie of the Lamp | Wishes / Lamp Magic / Curse |
| 20 | 🗡️ Sword Knight | Steel / Valor / Chivalry |
| 23 | 🧙‍♀️ Fairy Godmother | Quick Magic / Might / Fairy Fortune (boosts nearby towers) |
| 26 | 🏰 Rapunzel's Tower | Golden Hair / Sky Watch / Lookout |

Shop and level towers are sidegrades: different, not simply stronger.

---

## Enemies (22)

Regular: 😈 Imp, 👺 Goblin, 😡 Hobgoblin, 🤬 Goblin Chief, 👿 Warlord, 🍪 Gingerbread Man, 🐺 Big Bad Wolf, 🐀 Rat, 🦅 Raven (flies), 🧌 Troll, 👻 Cloak Sprite (camouflaged, needs a tower that can detect it), 💚 Healing Nymph (heals others), 🔥 Fire Imp (immune to poison and fire), 🥶 Frost Wraith (immune to frost), 🧙 Witch (shields allies), 🗿 Stone Troll (immune to piercing unless armor-piercing), 🧔 Giant.

Many enemies are **layered**: when they die they split into smaller ones where they fell.

Bosses (they also split into smaller enemies, and resist freezing and stunning):
- 👹 **Ogre**: first boss, wave 25, bursts into trolls
- 👑 **Troll King**
- 🐍 **Hydra**: regenerates
- 🐲 **Dragon Queen**: flying and armored
- 🏔️ **The Last Giant**: the final boss of Hard, huge and armored

Matching your towers to enemy immunities, camouflage and fliers is a big part of the strategy.

---

## Progression

- **Player level and XP**: you earn XP every wave and a big bonus for winning. Levels unlock the 10 level-unlock towers above.
- **Beans** (currency) come from clearing boards and goals, and are spent in the **Bean Shop**:
  - Towers (5, see above)
  - **Talents** (12, up to 5 levels each): Fat Purse, Stout Hearts, Haggler, Green Thumb, Sharpened Steel, Quick Hands, Eagle Eye, Pocket Change, Wave Bounty, Good Trader, Heavy Boots, Healing Springs
  - **Themes** (6): Enchanted Forest (free), Candy Cottage, Frostwood, Autumn Harvest, Midnight Court, Golden Kingdom
- **Goals & Unlocks** screen: 26 goals with bean rewards, plus a list of what each level unlocks.
- **Balance Lab**: a bot plays each board and difficulty with 5 build strategies (Archer Hail, Frost + Poison, Sniper Squad, Balanced Six, Gold Rush) so you can see how beatable each one is.

---

## Tips

- Early waves are small, so build a few towers and spend on upgrades rather than filling every tile.
- Put towers where the path bends so they cover more of it.
- Mix damage types. Poison and frost fail against some enemies; a Stone Troll needs armor-piercing.
- Bring something that sees camouflage, and something that can hit fliers.
- Save gold for the boss waves.
- Slowing and freezing work less well on bosses; raw damage matters more there.

---

## Technical notes

- The Canvas renderer caches static terrain and scenery and caps its pixel ratio at 2×. The artwork ships as four WebP files.
- Touch-first controls using pointer events; works on desktop too.
- Everything is stored locally in the browser. Clearing site data resets progress.
- Waves are generated from a seeded budget formula, so each board plays the same way every time.

## Testing notes

- Easy is forgiving by design; Medium and Hard are tuned with a bot and have had less human testing.
- The level-unlock towers and Free Play scaling past wave 50 may still need balance tweaks after real play.
