# Codex Pet Contract

## Sprite Atlas

- Format: PNG or WebP.
- Version 1 (or omitted `spriteVersionNumber`): `1536x1872`, 8 columns x 9 rows.
- Version 2 (`spriteVersionNumber: 2`): `1536x2288`, 8 columns x 11 rows.
- Cell: `192x208`.
- Background: transparent.
- Unused cells: fully transparent.

The webview animation uses CSS background positions from the fixed row and column counts. Do not add labels, gutters, borders, grid lines, shadows outside the cell, or extra frames.

V2 preserves the nine standard animation rows and adds sixteen clockwise look directions in rows 9–10, starting up at 0 degrees in 22.5-degree steps. The neutral/no-pointer pose remains the first idle cell.

## Local Custom Pet Package

Place files under:

```text
${CODEX_HOME:-$HOME/.codex}/pets/<pet-name>/
├── pet.json
└── spritesheet.webp
```

Manifest shape:

```json
{
  "id": "pet-name",
  "displayName": "Pet Name",
  "description": "One short sentence.",
  "spriteVersionNumber": 2,
  "spritesheetPath": "spritesheet.webp"
}
```

The app loads custom pets from the folder name under `${CODEX_HOME:-$HOME/.codex}/pets/`.

Set `spriteVersionNumber` to match the atlas. Omitted version numbers retain v1 compatibility; a v2 atlas requires version 2.
