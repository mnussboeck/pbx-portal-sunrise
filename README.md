# Sunrise Business · CloudPBX Admin (Prototyp)

Single-File-HTML-Prototyp für das **Sunrise Business CloudPBX Admin-Portal** — inkl. Mandanten-Admin, Super-Admin, Service Management und **Benutzerportal** mit interaktiven Tutorials.

## Schnellstart

```bash
# Repository klonen (falls noch nicht lokal)
git clone https://github.com/mnussboeck/pbx-portal-sunrise.git
cd pbx-portal-sunrise

# Prototyp im Browser öffnen (macOS)
open index.html
```

Alternativ: `index.html` per Doppelklick oder Drag & Drop in den Browser ziehen.

> Kein Build-Schritt, kein Server und keine Abhängigkeiten nötig.

## Demo online (GitHub Pages)

**URL nach Aktivierung:** `https://mnussboeck.github.io/pbx-portal-sunrise/`

Nach jedem `git push` auf `main` aktualisiert sich die Demo automatisch (meist innerhalb von 1–2 Minuten).

### Ersteinrichtung (einmalig)

1. Repository auf GitHub öffnen → **Settings** → **Pages**
2. **Build and deployment** → Source: **Deploy from a branch**
3. Branch: `main`, Ordner: `/ (root)` → **Save**
4. Nach 1–2 Minuten ist die URL oben erreichbar

**Voraussetzung:** GitHub Pages auf **privaten** Repositories erfordert [GitHub Pro](https://github.com/pricing) (oder Team/Enterprise). Auf dem kostenlosen Plan funktioniert Pages nur bei **öffentlichen** Repositories — für diesen UI-Prototyp ohne echte Daten oft vertretbar.

### Demo wieder offline nehmen

**Settings** → **Pages** → neben der Live-URL **⋯** → **Unpublish site**

Alternativ: Source auf **None** setzen. Das Repository bleibt unverändert; die Site lässt sich jederzeit erneut aktivieren.

> **Hinweis:** Die Pages-URL ist öffentlich erreichbar, auch wenn das Repository privat ist. Kein Passwortschutz — Link nur intern teilen. Enthält nur UI-Mockups ohne echte Daten.

## Rollen im Prototyp

Über die **Role Bar** oben wechseln:

| Rolle | Beschreibung |
|-------|----------------|
| **Tenant-Admin** | Benutzer, Routing, Warteschlangen, Anruffilter, … |
| **Super-Admin** | Mandanten, Billing, Teams Direct Routing, … |
| **Benutzerportal** | Self-Service: Status, Anrufe, Weiterleitung, Voicemail, Einstellungen |
| **Service Management** | Carrier-/Trunk-Verwaltung (SM) |
| **UCC** | Unified-Communications-Cockpit (Demo) |

## Benutzerportal — Highlights

- **Mehrsprachig:** DE, FR, IT, EN (Sprachumschalter)
- **Responsive:** Mobile Bottom-Navigation (≤ 768 px)
- **Hilfe & Tutorials:** 6 interaktive Anleitungen mit Spotlight-Führung
- **Onboarding:** Willkommensdialog beim ersten Besuch (localStorage)
- **Kontext-Hilfe:** «Hilfe zu dieser Seite» auf jeder UP-Seite

### Tutorials

| Tutorial | Seite |
|----------|--------|
| Portal kennenlernen | Übersicht |
| Anrufprotokoll | Gesprächsübersicht |
| Rufweiterleitungen | Weiterleitung |
| Voicemail nutzen | Voicemail |
| Persönliche Anruffilter | Einstellungen |
| Ansage aufnehmen | Aufnahme |

## Projektstruktur

```
pbx-portal-sunrise/
├── index.html      # Gesamter Prototyp (HTML, CSS, JS, i18n)
├── .gitignore
└── README.md
```

Der Prototyp ist bewusst **monolithisch** — alles in einer Datei für einfache Demo und Weitergabe.

## Entwicklung

Änderungen am Prototyp:

```bash
# Datei bearbeiten (z. B. in Cursor)
# …

git add index.html
git commit -m "Kurze Beschreibung der Änderung"
git push
```

### Onboarding zurücksetzen (Demo)

Im Browser (DevTools → Konsole):

```javascript
localStorage.removeItem('pbx_up_onboarding_seen');
```

Danach Rolle «Benutzerportal» erneut wählen.

## Hinweise

- **Demo-Daten:** Alle Inhalte sind Mockups; Aktionen wie «Abmelden» zeigen Toasts.
- **Kein Backend:** Keine echte API-Anbindung.
- **Grösse:** `index.html` enthält eingebettete Assets (Base64) — für Produktion Aufteilung in Module empfohlen.

## Nächste Schritte (Roadmap)

- [ ] HTML in `css/`, `js/`, `i18n/` aufteilen
- [ ] Build-Setup (z. B. Vite)
- [ ] API-Anbindung für Kernflows (Profil, Weiterleitung, Voicemail)

## Lizenz

Interner Prototyp — Nutzung nach Absprache.
