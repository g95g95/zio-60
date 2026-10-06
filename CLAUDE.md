# zio-60

Sito statico a file unico (`index.html`, nessuna build, nessuna richiesta esterna). Pubblicato con GitHub Pages dal branch `main`, root. URL: `https://g95g95.github.io/zio-60/`.

- Didascalia: "60 anni ziOooOooOooooOooOooooO" (`<h1 id="caption">`, `<title>`, meta OG, parole della pioggia `WORDS`).
- Data target: `TARGET` = `2026-10-13T00:00:00+02:00` (CEST). `?demo=N` sposta lo zero a N secondi da ora, solo per prova.
- Allo zero: `body.done` (pannello "AUGURI ZIO! 60") e `Rain.party()` (parole `PARTY`, oro, velocità ×1.8, flash).
- Pioggia: un canvas, 2 strati. Fondo katakana disegnato con trasformazione specchiata. Fronte a parole: 2 gocce per corsia a velocità condivisa, 65% frase in ordine, 35% 1–3 parole sciolte. `laneW` = parola più lunga di `WORDS`+`PARTY`.
- Dissolvenza e passi legati al tempo reale (`dt`), RAF fermo con tab nascosta, `prefers-reduced-motion` rispettato.
- QR: `#qr` SVG inline + `qr.svg` / `qr.png` (segno, error M). Moduli scuri su fondo chiaro, mai invertito.
- `og.png` 1200×630: screenshot della pagina senza `#clock` (le cifre sarebbero sbagliate nell'anteprima).
