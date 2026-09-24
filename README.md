# MacroLane data

Menu, nutrition, price, deal and ordering-tweak data for the MacroLane Android app. This repo holds data only;
the app's code lives elsewhere.

The app checks this repo once a day (and from **Me → Menus & prices → Check for updates**) and switches to these
files when they change, with no app update needed.

| File | What it holds |
| --- | --- |
| `menus.json` | Chains, menu items, nutrition and typical prices. Its `version` must be at least the one built into the app, or the app ignores the download. |
| `deals.json` | Standing offers, value menus and rewards programs. |
| `item_pictures.json` | Which illustration each item shows (from pictures already in the app). |
| `tweaks.json` | Ordering tweaks ("No mayo") and the nutrition each one takes off. |

Before switching, the app checks that every file parses and that the menu isn't missing more than half its chains
or items; if not, it keeps the menus it has. To publish a change, update all four files together and bump
`version` in `menus.json`.
