# CWS AI Cockpit — Konzept-Prototyp

Interaktives Dashboard zur Bewerbung **Teamlead AI (m/w/d), CWS Workwear, Ref. JR1013216**.
Zeigt, wie ich ein AI Center of Excellence bei CWS steuern würde — jeder View beantwortet
wörtlich einen Aufgaben-Bullet aus der Stellenanzeige (Zitatblock oben in jedem Tab).

**Ricardo Serrano · Juli 2026**

## Live-Demo

**https://ai-cockpit-konzept.vercel.app**

(Vercel-Projekt `ai-cockpit-konzept`, Production-Deployment. Nach dem Deploy
verifiziert: HTTP 200, ausgelieferte Datei byte-identisch mit diesem Repo,
kompletter Klick-Durchlauf aller Views und Features grün.)

Lokal: `index.html` direkt im Browser öffnen — keine Abhängigkeiten, kein Build.

## Bedienung (Screenshare)

| Taste | Funktion |
|---|---|
| `1`–`5` | View wechseln |
| `P` | Präsentationsmodus (Sidebar + Demo-Hinweis aus, Content zentriert) |
| `E` | Lesehilfe ein-/ausblenden (gelbe Erklär-Boxen, standardmäßig an) |
| `Strg+P` | Tab 01 als sauberes A4-Querformat drucken/als PDF sichern |

Interaktiv: Tabellenzeilen aufklappen (Klick/Enter), Status-Filter über der
Portfolio-Tabelle, Tooltips auf den Matrix-Punkten.

## Aufbau

Eine einzige HTML-Datei (`index.html`), kein Framework, kein Backend, kein
localStorage. Einzige externe Ressource: Google Fonts (asynchron geladen,
Fallback sans-serif — funktioniert offline).

| View | Aufgaben-Bullet aus der Anzeige |
|---|---|
| 01 Strategie & Portfolio | Use Cases identifizieren, bewerten, nach Business-Mehrwert und ROI priorisieren |
| 02 AI-Lifecycle | Gesamter Lifecycle von Idee bis produktiver Einsatz (Stage-Gate) |
| 03 Roadmap & Team | Aufbau des AI Center of Excellence, fachliche + disziplinarische Führung |
| 04 Integration | AI-Lösungen mit Fachbereichen und IT in CRM/ERP/Datenplattformen integrieren |
| 05 Governance & Enablement | EU AI Act, Compliance, Qualität; Trainings, Wissenstransfer, Change |

CWS-CI: Rot `#E2001A` als einzige Akzent-/Funktionsfarbe, CWS-Gelb `#FFD500`
ausschließlich im Logo-Lockup (CWS · WORKWEAR wie im Web-Auftritt),
Archivo/Inter/IBM Plex Mono, kantige Flächen. Alle Kennzahlen und Use Cases sind **illustrative Annahmen**,
keine realen CWS-Daten (Hinweisblock im Footer).

## Gesprächsvorbereitung

`GESPRAECH.md` enthält den Minutenplan für die 7–10-Minuten-Demo im
Erstgespräch: Route 1 → 2 → 5 → 3 (Tab 4 als Q&A-Reserve), Mic-Drop-Choreografie
um UC-08, Pre-Flight-Ritual und Fallbacks. Nach dem Gespräch taugt die URL
als Leave-Behind: Der Lesehilfe-Modus (Taste `E`, standardmäßig an) erklärt
jeden View selbst und kennzeichnet die Demo-Daten — der Präsentationsmodus
(`P`) blendet ihn automatisch aus.

## Qualitätssicherung

Automatisiert per Playwright vor jedem Deploy:

- alle 5 Tabs, alle Tabellenzeilen auf/zu, Matrix-Tooltips, Filter, Tastatur
- Viewports 1920 / 1440 / 1280 / 1180 / 1024 px ohne horizontales Scrollen
- keine Konsolen-Fehler
- Lighthouse (Desktop): **Performance 100 · Accessibility 100 · Best Practices 96**
- Druck-Emulation: Tab 01 auf einer A4-Querformat-Seite

## Änderungslog

| Iteration | Inhalt |
|---|---|
| 1 | Grundstruktur: Sidebar, KPI-Leiste, 5 Views (Portfolio-Tabelle + Matrix, Stage-Gate-Kanban, Roadmap/Team, Systemlandschaft, Governance/Enablement) |
| 2 | Features A–F: Presenter-Mode (P), BPM-Prozess-Baselines, Filter-Chips, Tasten 1–5, KPI-Count-up (800 ms, respektiert `prefers-reduced-motion`), Druck-Stylesheet A4 quer |
| 3 | Feinschliff: Fonts nicht-blockierend, 25px-Touchtargets Matrix, Kontrast-Fix — Lighthouse 100/100/96 |
| 4 | Corporate Design nachgeschärft: Logo-Lockup Rot+Gelb wie cws.com, Headlines fetter — bewusst ohne runde Buttons (Cockpit ≠ Marketing-Site) |
| 5 | Alle 7 Aufgaben-Bullets der Anzeige wörtlich zitiert (Strategie-Bullet ergänzt, Tab-05-Zitate wortgetreu) |
| 6 | Audit-Fixes: Zahlen konsistent (Pipeline 3,1 Mio €, KPI „14/14 klassifiziert" statt „100 % konform"), Business Case mit Invest/Payback (UC-01, UC-03), AI Board + Betriebsvereinbarung (§ 87 BetrVG), Betriebsmodell CoE/IT/Fachbereich, Lenkungskreis Geschäftsführung, AI-Radar, Europa-Skalierung + Zielbild 2028+, Sunset-Kriterium im Betrieb — plus `GESPRAECH.md` (Minutenplan fürs Erstgespräch) |
| 7 | Lesehilfe-Modus: selbsterklärende gelbe Hinweis-Boxen je View + globaler Demo-Daten-Hinweis (Taste `E`/Sidebar-Button, standardmäßig an, in Presenter-Mode und Druck automatisch aus) · `noindex` + Link-Vorschau-Meta für den Leave-Behind-Versand |
| 8 | CWS-Perspektive: Nachhaltigkeits-Signale (CO₂ Flotte, Textil-Kreislauf, Energie-Idee) + Business Case der Einheit selbst (Vollausbau ≈ 1,0 Mio € vs. 3,1 Mio € Pipeline — eigene Gate-2-Regel erfüllt) · Q&A-Erweiterung in GESPRAECH.md |
