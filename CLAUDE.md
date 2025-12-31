# Family Tree Project

## Goal
Create a simple family tree diagram for dinner guests based on a group photo.

## Files
- `relationships.md` - Source of truth for names and photo positions
- `family_tree.json` - Generated from relationships.md, used for diagram rendering
- `sample_reference.png` - Visual design reference
- `photos/` - Cropped photos (b1.png-b12.png, m1.png-m14.png, f1.png-f7.png)
- `originals/` - Source photos including full.jpg
- `doodles/` - Doodle versions of each person

## Photo Position Codes
- B1-B12: Back row, left to right
- M1-M14: Middle row, left to right
- F1-F7: Front row, left to right
- X-prefix: Connector people not in photo (Popo, Gooma3, Gooma2's eldest son)

## family_tree.json Schema
```json
{
  "people": [{"id", "name", "gender", "aka?", "inPhoto?"}],
  "families": [{"partners": [ids], "children": [ids], "note"}],
  "hidden": [ids]
}
```

## Diagram Style
- Circular photos with colored borders (blue=male, pink=female)
- Names only, no dates
- Older generations above, younger below
- Lines connecting parents to children
- See sample_reference.png for layout inspiration

## Hidden People
Currently no hidden people. All relationships resolved.

Previously hidden (now shown):
- M9 (Michelle) - Peter & Cora's daughter
- M12 (Dai-sou) - Gooma2's eldest DIL (eldest son name unknown, shown as X7)
- M13 (Yee-sou) - Gooma2's 2nd DIL, AhFat's wife

## Workflow
1. Update relationships.md with new info
2. Regenerate family_tree.json to match
3. Generate diagram from family_tree.json
