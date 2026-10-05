# Madspild-case

Portfolio-case for madspild-appen, hostet med GitHub Pages fra dette repo
(branch `main`, rod). Selve appens kildekode ligger i det PRIVATE repo
`JonathanFribert/madspild-app` og forbliver privat; casen er selvstændig
HTML uden build-trin, ligesom `nyhedsmonitor-case`.

## Filer

- `index.html` — dansk udgave
- `en.html` — engelsk udgave (1:1-spejl af index.html)
- `skaerm-*.png` — skærmbilleder taget direkte fra produktionssitet
  (https://madspild-app.vercel.app) med Puppeteer/headless Chrome
- `sitemap.xml`, `robots.txt`

## Redigering

Ved indholdsændring: hold `index.html` og `en.html` i sync (samme struktur,
oversat tekst). Sandfærdighedsprincip som på nyhedsmonitor-casen: kun tal fra
rigtige kørsler/logs/API-svar, aldrig opfundne.

Casen blev bygget om den 5. oktober 2026 på samme skabelon som
`blazeitupradio-case` i forside-repoet: samme CSS for figurer og effekter
(reveal ved scroll, tællende nøgletal, LIVE-stempel, læsefremdrift, crossfade
til forsiden), grøn farvepalet i fem kategorifarver valideret for farveblindhed
og kontrast i begge temaer, trelagsfigur, fallback-kæde for opskrifter og
forklaringstabel over værktøjerne.

Tallene i afsnit 04 er hentet den 5. oktober 2026 gennem appens egen søgerute
(`/api/food-waste?lat=&lng=&radius=`), som returnerer højst 1.000 varer:
1.000 varer fra 44 butikker (733 Netto, 267 føtex); kategorier 452/342/135/71;
rabatter 473/158/163/124/80 i intervallerne 20–29/30–39/40–49/50–59/60+;
udløb 336/297/367 for under 24 t/24–48 t/over 48 t; normalpris 25.844 kr.,
tilbudspris 16.580 kr., 7.934 enheder på lager. Genkør med
`curl "https://madspild-app.vercel.app/api/food-waste?lat=55.69&lng=12.55&radius=12"`
og tæl i Python, hvis tallene skal opdateres.

Nøgletal og git-historik fra første udgave (27. juli 2026):
- 6 postnumre, ~1.000 aktuelle tilbud, 30+ butikker (live-tal, ændrer sig)
- 4.637 linjer kode, 25 filer
- 19 commits fordelt på 5 unikke udviklingsdage: 6/6, 7/6, 14/6, 15/7, 20/7 (og 27/7 for selve casen)

Genoptag `git log --format='%cd' --date=short -- ~/Desktop/madspild-app | sort -u`
og de øvrige kommandoer i madspild-app's egen `AI_CONTEXT.md`, hvis tallene
skal opdateres senere.

## Publicering

```bash
git add . && git commit -m "..." && git push
```

GitHub Pages bygger automatisk fra `main`. Aktivér Pages under
Settings → Pages → Source: Deploy from a branch → main / (root), hvis det
ikke allerede er sat op.
