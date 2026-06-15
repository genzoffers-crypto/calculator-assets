# calculator-assets

Remote asset repository for the Liquid Glass Calculator app.
All assets are served via jsDelivr CDN: https://cdn.jsdelivr.net/gh/genzoffers-crypto/calculator-assets@main/

---

## themes/

Theme backgrounds for the calculator. Defined by 	hemes.json at root.

### Structure
- 	hemes.json — manifest at root
- 	hemes/<id>.webp — image files referenced by image field

### Adding a new theme
1. Drop a <id>.webp image in the 	hemes/ folder
2. Add an entry to 	hemes.json under 	hemes[]:
`json
{
  "id": "my-theme",
  "name": "My Theme",
  "image": "my-theme.webp",
  "bgColor": "#FFFFFF",
  "primaryColor": "#000000",
  "secondaryColor": "#333333",
  "tertiaryColor": "#666666",
  "category": "fun",
  "premium": false
}
`
3. Done. App picks it up within the cache TTL window (10 min in dev, 4h in production).

---

## formulas/

Formula images for the Formula Hub. Defined by ormulas.json at root.

### Structure
- ormulas.json — manifest at root (subjects, chapters, formulas)
- ormulas/<subject>/<chapter>/<formula>.webp — image files

### Adding a new formula
1. Drop a <formula>.webp image at the path matching its entry in ormulas.json:
   - e.g. ormulas/mathematics/calculus/derivatives.webp
2. Add an entry to ormulas.json under ormulas[]:
`json
{
  "id": "math-calculus-derivatives",
  "subjectId": "mathematics",
  "chapterId": "calculus",
  "title": "Derivative Formulas",
  "image": "mathematics/calculus/derivatives.webp",
  "tags": "LIMITS | RULES | DIFFERENTIATION",
  "order": 1,
  "premium": false
}
`
3. Done. No app code change needed.

### Adding a new subject or chapter
Add entries to the top-level subjects[] or chapters[] arrays. Use unique id values, link them with subjectId / chapterId in ormulas[].

---

## Image guidelines
- Format: .webp (preferred, smaller) or .png / .jpg
- Aspect ratio: matches the formula capsule holder (~1.55:1)
- Resolution: 1200×775 px or higher for crisp rendering
- File size: keep under 300 KB each