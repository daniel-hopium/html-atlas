# HTML-Atlas – HTML zum Anfassen

110 HTML-Elemente und Attribute mit Live-Vorschau: Variante anklicken, Wirkung sehen, darunter
das HTML der Vorschau mit hervorgehobenem Attribut – und bei vielen Einträgen, was im
Accessibility Tree ankommt, also was ein Screenreader vorliest. Auf Deutsch und Englisch.

Online: https://daniel-hopium.github.io/html-atlas/

## Starten

`index.html` im Browser öffnen, per Doppelklick. Kein Build, kein Server, keine
Abhängigkeiten. Internet braucht es nur für die Google-Schriften.

## Inhalt

Zehn Kapitel:

| Kapitel | Beispiele |
|---|---|
| Text & Inline-Semantik | `<strong>`/`<b>`, Überschriften-Ebenen, `<abbr>`, `<time>`, `<code>`/`<kbd>`, `<del>`/`<ins>` |
| Struktur & Landmarks | Landmarks, `<section>` vs. `<div>`, Listen, `<dl>`, `<figure>`, `<search>` |
| Links & Navigation | `href`-Arten, `target`/`rel`, `download`, Link vs. Button, Skip-Link, Linktext |
| Formularfelder | `type`, `<label>`, `inputmode`, `enterkeyhint`, `autocomplete`, `<datalist>`, `<fieldset>` |
| Validierung & Absenden | `required`, `pattern`, `min`/`max`/`step`, `readonly` vs. `disabled`, `<button type>`, `form="…"` |
| Eingebautes Verhalten | `<details name>`, `<dialog>`, `closedby`, `popover`, `command`/`commandfor`, `inert`, `hidden="until-found"` |
| Bilder & Medien | `alt`, `loading`, `srcset`/`sizes`, `<picture>`, `<video>`, `<track>`, `<iframe>` |
| Tabellen | `<caption>`, `scope`, `colspan`/`rowspan`, `headers`, Scroll-Container |
| Globale Attribute | `lang`, `dir`/`<bdi>`, `translate`, `data-*`, `title`, `tabindex`, `contenteditable` |
| Dokument & Laden | Doctype, `charset`, Viewport, `<title>`, `async`/`defer`, `preload`, `<base>` |

Jeder Eintrag hat eine eigene Adresse (`#forms/autocomplete`), die Kurzform `#autocomplete`
springt ins richtige Kapitel. Der Überblick hat eine durchsuchbare Tabelle aller Einträge.

## Bedienung

- **Sprache:** Der Link oben rechts wechselt zwischen Deutsch und Englisch. Die Wahl steht als
  `?lang=en` in der Adresse (teilbar) und wird im `localStorage` gemerkt.
- `Strg+K` (Mac: `Cmd+K`) springt in die Suche der Seitenleiste.
- Hell und dunkel folgen der Systemeinstellung.

## Aufbau

Alles steckt in einer Datei:

- **`HA_CATS`**: die zehn Kapitel.
- **`HTMLA`**: ein Objekt pro Eintrag – Vorschau-HTML (`stage`), Zielelement (`t`),
  Varianten (`vals`: Attributwert, `null` zum Entfernen, `true` für boolesche Attribute oder
  ganzes Markup im Modus `html`), optional `measure()` für Messwerte, `init()` für Verhalten
  und `ax` für die Accessibility-Zeile.
- **`haApply()`** setzt die Variante, **`haSerialize()`** macht aus dem Live-DOM der Vorschau
  lesbares HTML und hebt die geänderten Attribute hervor.
- **ARIA-Engine** (`implicitRole`, `accName`, `inspect`) aus dem ARIA-Kompass, ergänzt um die
  Text-Rollen aus HTML-AAM (`strong`, `code`, `time`, `deletion` …). Vereinfacht – genau genug
  zum Lernen, kein Ersatz für die Devtools.
- **Zweisprachig:** `tx('Deutsch','English')` steht direkt neben jedem Text; der
  Sprachumschalter lädt die Seite neu.

## Die Schwester-Apps

- [Daumenregel](https://daniel-hopium.github.io/pattern-library/) – UI-Regeln mit
  Live-Beispielen, WCAG-Kompass und Quiz
- [CSS-Atlas](https://daniel-hopium.github.io/css-atlas/) – CSS-Eigenschaften mit
  Live-Vorschau
- [ARIA-Kompass](https://daniel-hopium.github.io/aria-compass/) – WAI-ARIA mit Inspektor und
  Screenreader-Trainer
- [Angular-Patterns](https://daniel-hopium.github.io/angular-patterns/) – modernes Angular mit
  Live-Simulationen
