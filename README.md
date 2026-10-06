# 60 anni ziOooOooOooooOooOooooO

Conto alla rovescia a **martedì 13 ottobre 2026, ore 00:00** (ora italiana) su sfondo a pioggia Matrix.

Online: <https://g95g95.github.io/zio-60/>

## Cosa fa

- Pannello centrale con didascalia e conto alla rovescia (giorni, ore, minuti, secondi). Le cifre si "decifrano" a ogni cambio.
- Pioggia su 2 strati: dietro i katakana specchiati come nel film, davanti le parole della didascalia.
- Allo zero: stato festa. Il pannello mostra **AUGURI ZIO! 60**, la pioggia accelera e diventa anche dorata.
- QR code del sito in basso a destra.
- Animazione in pausa con la tab nascosta. Con `prefers-reduced-motion` la pioggia è lenta e niente lampeggia.
- Anteprima del link (WhatsApp, Telegram, …) con `og.png`.

## Uso

Un solo `index.html` senza dipendenze: aprilo nel browser oppure pubblicalo su GitHub Pages.

Per vedere la festa prima del 13 ottobre aggiungi `?demo=SECONDI` all'URL, per esempio
<https://g95g95.github.io/zio-60/?demo=5>.

## QR code

SVG inline nella pagina, più le copie stand-alone `qr.svg` e `qr.png`. Moduli scuri su fondo chiaro: la
versione invertita (verde su nero) molti scanner non la leggono. Per rigenerarli:

```bash
pip install segno
python -c "import segno; q=segno.make('https://g95g95.github.io/zio-60/', error='m'); \
q.save('qr.svg', scale=10, border=4, dark='#04140a', light='#d9ffe3'); \
q.save('qr.png', scale=12, border=4, dark='#04140a', light='#d9ffe3')"
```

Il QR inline in `index.html` va rigenerato a parte (path SVG dei moduli scuri, `viewBox` con bordo di 4).
