# Bilder

Kundenbilder in diesen Ordner legen. Eingetragen werden sie in
`src/site.config.json` — nicht in einer `.astro`-Datei.

## Vor dem Ablegen

Ein unbearbeitetes Handyfoto ist schnell 5 MB und macht die Seite langsam.
Deshalb jedes Bild einmal durch diese drei Schritte:

1. **Verkleinern** auf 1600 px Breite (Galerie: 1200 px reichen)
2. **Als WebP speichern**, Qualität 80
3. **Sprechend benennen**, klein, ohne Leerzeichen und Umlaute:
   `dach-sanierung-erding.webp`, nicht `IMG_4471.webp`

Unter Windows genügt dafür [Squoosh](https://squoosh.app) im Browser — nichts zu
installieren, die Bilder verlassen den Rechner nicht.

**Faustregel:** Über 300 KB pro Bild ist zu viel. Ein Hero-Bild in 1600 px WebP
landet typisch bei 120–250 KB.

## Eintragen

In `src/site.config.json`:

```json
"logo": "/bilder/logo.webp",
"hero": {
  "src": "/bilder/hero.webp",
  "alt": "Zwei Dachdecker beim Eindecken eines Steildachs"
},
"gallery": [
  { "src": "/bilder/arbeit-1.webp", "alt": "Neu eingedecktes Satteldach", "caption": "Steildach, Erding" },
  { "src": "/bilder/arbeit-2.webp", "alt": "Abgedichtetes Flachdach mit Kiesschüttung" }
]
```

Der Pfad beginnt mit `/bilder/` — ohne `public`. Was hier im Ordner liegt, ist
später unter dieser Adresse erreichbar.

**Weglassen ist erlaubt.** `"logo": ""`, `"src": ""` oder `"gallery": []` heißt:
Der Abschnitt fällt weg und die Seite bleibt vollständig. Lieber kein Bild als
ein schlechtes.

## Formate

| Wo | Seitenverhältnis | Breite |
|---|---|---|
| Logo | frei | Höhe wird auf 38 px gerechnet, also mind. 80 px hoch liefern |
| Hero | 16:9 (wird zugeschnitten) | 1600 px |
| Galerie | 4:3 (wird zugeschnitten) | 1200 px |

Zugeschnitten wird mittig. Bei einem Motiv am Bildrand vorher selbst
zuschneiden.

## alt-Texte

Jedes Bild braucht einen. Er beschreibt, **was zu sehen ist** — für blinde
Besucher und für Google:

- Gut: `Handwerker verlegt Tonziegel auf einem Steildach`
- Schlecht: `Dachdeckerei Huber GmbH`, `Bild1`, `dach.webp`

## Rechte

Nur Bilder verwenden, an denen der Kunde die Rechte hat: eigene Fotos oder
gekaufte Lizenzen. **Keine Bilder von der alten Website übernehmen, ohne zu
klären, woher sie stammen** — bei Agentur-Seiten liegen die Rechte oft bei der
Agentur, nicht beim Betrieb. Sind Personen erkennbar, braucht es deren
Einverständnis.
