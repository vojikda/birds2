# Ptačí kvíz (česky)

Jednoduchý ptačí kvíz na 15 kol (webová stránka).

## Formát dat

Kvíz načítá `data/birds.csv` (bez databáze, bez build kroku).

CSV columns:

1. `imageSrc` - URL to the bird picture **or** a relative path like `images/sparrow.jpg`
2. `czechName` - correct bird name in Czech
3. `info` - short interesting text shown after the player answers

Header example:

```csv
imageSrc,czechName,info
"images/sparrow.jpg","vrabec domácí","Zajímavost o vrabci..."
```

## Current data (from your XLSX)

I extracted the embedded bird pictures from `ptaci_tabulka.xlsx` and generated:

- `images/` (JPEG files with the bird pictures)
- `data/birds.csv` (pairs `images/<file>` with the correct Czech name)

## Bodování

- Start at `0` points.
- Správná odpověď: `+1`
- Špatná odpověď: `-1`
- Po 15 kolech uvidíš konečné skóre a můžeš restartovat.

## Spuštění lokálně

Because the page uses `fetch()` to load the CSV, open it via a local web server (not `file://`).

Example (from this folder):

```bash
python3 -m http.server 8000
```

Then open: `http://localhost:8000/`

## Nasazení na GitHub Pages

1. Create a new GitHub repository (any name), then push this folder contents to it.
2. Go to your repository settings -> **Pages**.
3. Set **Source** to `main` branch and `/ (root)` folder.
4. After a minute, open the “Your site is live at …” link.

