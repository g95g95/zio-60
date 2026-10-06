# zio-60 — piano

Obiettivo: sito statico con conto alla rovescia a **martedì 13 ottobre 2026, ore 00:00 (Europe/Rome)**,
didascalia **"60 anni ziOooOooOooooOooOooooO"**, sfondo a pioggia Matrix, QR code del sito.
Base: `g95g95/countdown-biomeccanica`, migliorato. Repo nuovo pubblico `g95g95/zio-60` + GitHub Pages.
URL finale: `https://g95g95.github.io/zio-60/`.

## Scelte tecniche
- Un solo `index.html` (HTML + CSS + JS inline). Nessuna build, nessuna dipendenza, nessuna richiesta esterna.
- `TARGET = 2026-10-13T00:00:00+02:00`: il 13 ottobre è ancora ora legale (CEST, fino al 25 ottobre).
- Pioggia su 2 strati in un canvas:
  - fondo: glifi katakana a mezza larghezza specchiati + cifre (come nel film), più piccoli e tenui → profondità;
  - fronte: parole della didascalia ("60", "anni", "ziOooO…"), 65% in ordine, 35% sciolte, come l'originale.
- `laneW` calcolato sulla parola più lunga di `WORDS` (nell'originale era una stringa fissa).

## Task
- [x] 1. `index.html`
  - [x] countdown giorni/ore/min/sec; a ogni cambio la cifra si "decifra" passando per glifi casuali
  - [x] didascalia con effetto decrypt all'apertura
  - [x] pannello centrale 50vw × 50vh, responsive (mobile in verticale)
  - [x] pioggia a 2 strati, testa luminosa, scia indipendente dal frame rate
  - [x] stato "Festa" allo zero: pannello "AUGURI ZIO!" + "60", pioggia più veloce con lampi dorati di "AUGURI" / "60"
  - [x] pausa dell'animazione con tab nascosta (`visibilitychange`)
  - [x] `prefers-reduced-motion`: pioggia lenta, nessun lampeggio
  - [x] parametro di prova `?demo=SECONDI` per vedere il passaggio allo zero prima del 13 ottobre
  - [x] favicon SVG inline + meta Open Graph (anteprima del link su WhatsApp con `og.png`)
- [x] 2. QR code verso l'URL Pages: SVG inline in basso a destra + `qr.svg` / `qr.png` (segno, moduli scuri su fondo chiaro)
- [x] 3. `og.png` 1200×630 da screenshot headless della pagina
- [x] 4. Verifica locale con Edge headless: desktop, mobile, stato festa (`?demo=3`), decodifica del QR dallo screenshot
- [x] 5. `README.md` + `CLAUDE.md` minimale
- [x] 6. `git init` → repo GitHub pubblico `zio-60` → push → GitHub Pages (main, root) → verifica HTTP 200

## Note
- Repo pubblico: necessario per GitHub Pages su account free. Il sito e il QR sono visibili a chiunque abbia il link.
- I glifi katakana usano i font di sistema (Windows, Android, iOS li hanno). Nessun webfont da scaricare.

## Esito (6 ottobre 2026)
- Verifica con Playwright + Edge: desktop 1920×1080, mobile 390×844 @3x, festa con `?demo=1`. Nessun errore JS.
- Conteggio corretto (6 g 11 h 42 m alle 12:17 del 6/10). QR decodificato dagli screenshot → `https://g95g95.github.io/zio-60/`.
