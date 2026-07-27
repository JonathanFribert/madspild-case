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

Nøgletal og git-historik i casen er fra 27. juli 2026:
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
