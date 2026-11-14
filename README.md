# Sailor Slippers Colour Planner

Color planner for Sailor Slippers by Annie Germain.

**Try out:** https://genvekt.github.io/sailor-slippers-colour-planner/

## About

An unofficial, free helper for knitters making the felted, striped **Sailor Slippers**. It helps you choose colours and work out how much yarn to buy:

- Preview your colour choices on a slipper drawing. Each pair has four colour parts: main, stripes, i-cord edge and sole.
- Choose a yarn brand from the dropdown. Each pair remembers its colours for each brand, so you can switch brands and come back without losing anything.
- Type the grams for each colour from your copy of the pattern.
- Plan as many pairs as you like. The shopping list adds up every colour across all pairs and rounds up to whole balls, so colours shared between pairs need fewer balls. It also shows how much of each colour is left over.

The page contains **no pattern information**: no sizes, stitch counts or yarn amounts.

Colour choices are saved in your own browser only. On-screen colours are approximations from shop photos.

## How to add a yarn

1. Create a JSON file in the `yarns/` folder, for example `yarns/my-yarn.json`:

   ```json
   {
     "name": "My Yarn",
     "url": "https://example.com/my-yarn",
     "ballWeightGrams": 50,
     "presets": [
       {"A": "01", "B": "08", "C": "08", "D": "26"}
     ],
     "groups": [
       {"type": "plain", "label": "Colours"}
     ],
     "colours": [
       {"number": "01", "name": "Ivory", "hex": "#efeadb", "type": "plain"},
       {"number": "08", "name": "Navy",  "hex": "#2f3a5e", "type": "plain"},
       {"number": "26", "name": "Charcoal", "hex": "#2e2e30", "type": "plain"}
     ]
   }
   ```

   | Field | Required | Meaning |
   |---|---|---|
   | `name` | yes | Shown in the yarn dropdown and shopping list. |
   | `url` | no | Link to the yarn's shop page, shown as "View … ↗" next to the dropdown. |
   | `ballWeightGrams` | yes | Weight of one ball, used to round up to whole balls. |
   | `presets` | no | Starting colours for new pairs, given as colour numbers for A, B, C and D. Pair 1 uses the first preset, pair 2 the second, and so on. If there are none, a spread of the yarn's colours is used. |
   | `groups` | yes | Headings in the colour picker. Each colour's `type` must match one group's `type`. |
   | `colours` | yes | Every colour: its shop `number`, `name`, an on-screen `hex` colour and its group `type`. Colours appear in the order listed, so order them roughly by hue. |

2. Add the file name to `yarns/index.json`:

   ```json
   {
     "files": [
       "drops-snow.json",
       "hobbii-snowstorm.json",
       "my-yarn.json"
     ]
   }
   ```

## Reference

This tool is an unofficial fan project and is not affiliated with the designer.

**Sailor Slippers** is a knitting pattern by Annie Germain (Annie Sews). Buy the pattern for sizes, yarn amounts and instructions:
https://www.anniesews.co.uk/sailor-slippers

Yarns currently included:
- [Drops Snow](https://www.garnstudio.com/yarn.php?show=drops-snow&cid=9)
- [Hobbii Snowstorm](https://hobbii.de/products/hp-1001867-snowstorm)
