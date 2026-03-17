# ScoreMyPack — Nutrition Label Scanner

A fully offline-capable PWA that scans nutrition labels and calculates the **Nutri-Score v2** grade (A–E).

## Key Change: No external APIs
This version uses **Tesseract.js** (open-source OCR engine, loaded from CDN) instead of the Anthropic API. All processing happens in the browser — no API key required, no data sent to any server.

## How it works
1. **Tesseract.js** performs OCR on the uploaded nutrition label image
2. A local parser extracts nutrition values (energy, fat, sugar, sodium, protein, fibre, etc.)
3. The **Nutri-Score v2** algorithm is applied entirely in JavaScript
4. Grade A–E is shown with full score breakdown

## Stack
- Single-file HTML/CSS/JS frontend
- Tesseract.js v4 (OCR engine, via CDN)
- Service Worker for offline/caching
- PWA manifest for installability

## Tips for best OCR results
- Photograph the nutrition table straight-on (not at an angle)
- Ensure good lighting — avoid shadows across the text
- Fill the frame with the nutrition table
- Avoid glare or reflections

## Nutri-Score v2 algorithm
Score = Negative points (energy, saturated fat, sugar, sodium) minus Positive points (fibre, protein, fruits/veg/nuts)
- A: ≤ −1
- B: 0 to 2
- C: 3 to 10
- D: 11 to 18
- E: ≥ 19

## Deployment
GitHub Pages + custom domain (HTTPS required for camera access)
