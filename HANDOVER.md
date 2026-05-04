# Konzept v2 — Übergabe an Claude Code lokal

**Datei:** `index.html` · 1.408 Zeilen (vorher 867) · gewachsen um ~62 %

## ✅ Bereits umgesetzt

### Struktur & Navigation
- Nav um `#cluster`, `#eeat`, `#risk` erweitert
- Hero: Realistische Ranges statt Punktschätzung (2.100–4.500 € / 4–6 Mo. / 180–320 % / 60–80 %)
- Hero: Realismus-Badge „3 Szenarien · Annahmen transparent ausgewiesen"
- Hero-Subtitle erwähnt jetzt Cluster-Architektur, E-E-A-T und 11 Agenten
- Version: „v2 · Mai 2026"

### Workflow-Anpassungen
- **11. Agent (Faktencheck)** in Phase 3 nach dem Autor-Agent eingebaut — Claude Opus + Web, prüft Claims gegen Primärquellen, Confidence-Score
- Lektorat-Agent jetzt mit E-E-A-T-Score in der 80er-Schwelle
- Bild-Agent: ergänzt um „Beyonity LoRA" (Custom-Training)
- Risiko-Gate ersetzt klassischen Freigabe-Check (Standard 15 / Sensibel 30 / Kritisch 60 Min.)
- Eskalations-Note bei 3. Score-Fail an Editor-in-Chief
- Phase 4 erweitert: **Repurposing-Agent** (1 Artikel → 7 Assets) + LinkedIn vollautomatisch via API + A/B-Subject-Lines im Newsletter
- „Alle Phasen" Übersicht entsprechend aktualisiert

### ROI-Bereich
- 3-Szenarien-Tabelle nach dem Chart: Konservativ / Realistisch / Optimistisch
- Annahmen pro Szenario sichtbar (Stundensatz, Std./Mo., Tools)
- Vollkosten-Hinweis: 50 €/Std. unrealistisch, echte Vollkosten 75–100 € intern

### NEUE SEKTION: Topic Cluster (`#cluster`) — vollständig
- Vergleich Klassisches Content Marketing vs. Topic Cluster
- SVG-Hub-and-Spoke-Visualisierung (zentraler Pillar + 8 Spokes + Cross-Links)
- 3 konkret geplante Pillars für Beyonity:
  - **P1:** KI-CRM für Immobilien (Q2/2026, ~3.000 W., 8 Spokes, ~6.400 SV/Mo.)
  - **P2:** Vertriebsdigitalisierung (Q3/2026, ~2.500 W., 6 Spokes, ~4.100 SV/Mo.)
  - **P3:** PropTech in DACH (Q4/2026, ~2.800 W., 5 Spokes, ~3.200 SV/Mo.)
- 4 verbindliche Internal-Linking-Regeln
- Cluster-KPIs (3→5 Pillar, 25–35 Spokes, ≥85 % Coverage, +45 % Topical Authority)

### NEUE SEKTION: E-E-A-T (`#eeat`) — vollständig
- Risiko-Box: warum E-E-A-T nicht optional ist (Helpful-Content-Update)
- 4-Säulen-Modell mit je 4 konkreten Maßnahmen pro Säule:
  - **Experience** (Original-Daten, Mitarbeiter-Quotes, Beyonity-Index, echte Screenshots)
  - **Expertise** (Author-Pages, Reviewer-Zeile, Schema sameAs, KI-Disclaimer)
  - **Authoritativeness** (Linkable Assets, Outreach, HARO, Gastbeiträge)
  - **Trustworthiness** (Quellen, Last-reviewed, Halbjahres-Refresh, Meinung/Fakten getrennt)
- Author-Persona-System: 3 Beyonity-Köpfe (Paulo F. / Tech-Lead / Sales-Lead) mit Pillar-Zuordnung
- E-E-A-T Schema Markup Templates (Article + Person als JSON-LD)
- Workflow-Integration: welcher Agent welchen E-E-A-T-Aspekt prüft

## ⏳ Noch offen (für Claude Code lokal)

1. **GEO-Mediawert konservativer rechnen** — 15.600 € ist nicht haltbar (Impressionen ≠ Klicks). Realistisch 3–5 k €.
2. **Neue Sektion `#risk`** — DSGVO/Compliance + Risikoklassen-Matrix (Standard/Sensibel/Kritisch) + Halluzinations-Tracker + Crisis-Response-Plan + AVV-Status pro Tool als Tabelle
3. **Tools-Stack erweitern** — LinkedIn API, Otterly.ai/Brand24 (KI-Monitoring), Custom-LoRA-Training für fal.ai, AVV-Status-Spalte pro Tool
4. **Business-KPIs** ergänzen — Leads/MQLs pro Artikel, CAC, Time-to-Publish, Halluzinations-Rate, Cost-per-Article live
5. **Comments-Section** — Dropdown um „Topic Cluster", „E-E-A-T", „Risk & Compliance" erweitern
6. **TODOS-Liste im Script** — neue Tasks für Cluster-Setup, E-E-A-T-Implementierung, Risk-Workflow ergänzen

## 🛠 Prompt für Claude Code lokal

Nach `git pull` der überarbeiteten `index.html`:

```
Lies die aktuelle index.html. Sie enthält bereits Topic Cluster (#cluster) und E-E-A-T (#eeat) als
neue Hauptsektionen. Ergänze nun:

1. In der GEO-Sektion (#geo): Die Branding-Kalkulation (Bereich "Branding-Effekte durch
   GEO + SEO — Wertberechnung") konservativer rechnen. Aktuell wird mit 4,50 € CPC × 3.200
   Klicks = 14.400 € gerechnet, das mischt Impressionen mit Klicks. Korrigiere auf realistische
   Annahmen: 3.200 Impressionen × 3 % CTR = 96 Klicks × 4,50 € = ~430 € — × 4 Artikel = ~1.700 €.
   Plus GEO ~800 €. Gesamt: ~2.500 €/Mo. Mediawert. Verhältnis 1:10 statt 1:62.

2. Füge eine neue Sektion <section id="risk"> direkt NACH der GEO-Sektion ein. Inhalt:
   - Eyebrow: "Risk & Compliance"
   - Titel: "Risikoklassen, DSGVO und Quality Gates"
   - 3-Spalten-Risikoklassen-Matrix (Standard/Sensibel/Kritisch) mit jeweils:
     Beispiel-Content, Workflow-Tiefe, Human-Review-Zeit, Sign-off-Level
   - DSGVO-Tabelle: Tool · Datenfluss · Hosting-Region · AVV-Status · DPA-Link
     (Claude API, Gemini API, fal.ai, Perplexity, Helicone, LangSmith, Hubspot, n8n)
   - Halluzinations-Tracker-Box (KPI: <2 Halluzinationen pro 100 Artikel)
   - Crisis-Response-Plan (3 Eskalationsstufen)
   Design: Konsistent mit bestehenden Sektionen — nutze --bg1, --bd, --r2, .reveal Klassen,
   Bricolage Grotesque. Dark-Mode. Background: #0D1220 oder var(--bg).

3. Im Tool-Stack (#tools): Ergänze 4 neue Tool-Karten:
   - LinkedIn API (Distribution, ~0 € via Bestandskonto, AVV vorhanden)
   - Otterly.ai (KI-Monitoring, ~30 €/Mo., USA-Hosting)
   - Custom LoRA Training (einmalig ~150 €, Beyonity-Bildwelt)
   - n8n Hosting (Hetzner Cloud, ~5 €/Mo., DE-Hosting)
   Aktualisiere "Tool-Stack Total" auf realistischeren Wert (~290 €/Mo.).

4. In der Comments-Section: Erweitere das <select id="c-section"> um <option>Topic Cluster</option>,
   <option>E-E-A-T</option>, <option>Risk & Compliance</option>. Im JS-Block CMT_SEC_COL: passende
   Farben ergänzen ('Topic Cluster':'#93B9FF','E-E-A-T':'#C4B5FD','Risk & Compliance':'#FECACA').

5. TODO-Liste im Script (TODOS-Array): In Phase p2 (Strategie) ergänze:
   - "Topic-Cluster-Map in Confluence" (3 Pillars + Spokes definieren)
   - "Author-Profile aufsetzen" (3 Beyonity-Köpfe, LinkedIn-Sync)
   - "AVV mit allen LLM-Anbietern" (Anthropic, Google, fal.ai)
   In Phase p3: "Faktencheck-Agent (Claude Opus + Web)" + "Schema-Markup-Generator".

6. Footer aktualisieren: Version "v2 · Mai 2026" + Hinweis auf Cluster + E-E-A-T + Risk.

Mache die Änderungen direkt in index.html. Bewahre den bestehenden Design-Stil.
Nach jedem Schritt kurz commit-fähigen Diff zeigen.
```

## 📊 Datei-Größen

- Vor Überarbeitung: 867 Zeilen
- Nach aktueller Überarbeitung: 1.408 Zeilen
- Geschätzt nach finaler lokaler Überarbeitung: ~1.700–1.800 Zeilen
