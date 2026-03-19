# Hikvision Access Card

Lovelace Custom Cards für [Hikvision Face Terminals](https://github.com/yourusername/hikvision-ha).

Dieses Repository enthält **zwei eigenständige Karten** (jeweils eigene `.js`-Datei):

| Datei | Typ in YAML | Zweck |
|-------|-------------|--------|
| `hikvision-access-card.js` | `custom:hikvision-access-card` | Ein Terminal: Tür, Aktivität, Person, Zugang, optional Kamera, Sperre |
| `hikvision-access-overview-card.js` | `custom:hikvision-access-overview-card` | **Mehrere** Terminals kompakt — ideal pro Gebäude-Tab im Dashboard „Sicherheit / Zugriff“ |

## Installation via HACS

1. HACS → **Frontend** → **Eigene Repositories**
2. URL deines Card-Repos · Kategorie: **Lovelace**
3. Installieren → **HA neu laden**

### Wichtig: zweite Lovelace-Ressource

HACS trägt standardmäßig nur die in `hacs.json` hinterlegte Hauptdatei ein (`hikvision-access-card.js`).  
Für die Übersichtskarte zusätzlich:

1. **Einstellungen → Dashboards → ⋮ → Ressourcen**
2. **Ressource hinzufügen**
3. URL (Pfade können je nach HACS-Ordner leicht abweichen):

   - ` /hacsfiles/hikvision-access-card/hikvision-access-overview-card.js `

4. **Typ:** JavaScript-Modul → Speichern → Browser einmal hart neu laden (Strg+Shift+R)

## Manuelle Installation

Beide Dateien nach `/config/www/` kopieren und **beide** als Ressource eintragen (Typ: **JavaScript-Modul**):

- `/local/hikvision-access-card.js`
- `/local/hikvision-access-overview-card.js`

## Konfiguration — Einzelkarte

```yaml
type: custom:hikvision-access-card
device: hintereingang_halle   # Entity-Prefix (Gerätename, Leerzeichen → _)
title: Hintereingang Halle    # optional
show_camera: true             # optional, default true
```

## Konfiguration — Übersicht (mehrere Geräte)

```yaml
type: custom:hikvision-access-overview-card
title: Gebäude 441 — Zugang   # optional
devices:
  - device: hintereingang_halle
    title: Hintereingang Halle
  - device: nebeneingang
    title: Nebeneingang
```

Oder kurz nur Prefixe:

```yaml
type: custom:hikvision-access-overview-card
devices:
  - hintereingang_halle
  - nebeneingang
```

**Interaktion Übersicht:**

- Klick auf Zeile (links) → More-Info **Gerätestatus**
- Doppelklick auf Zeile → Verlauf (History) der wichtigsten Entitäten
- Schloss-Button → Zugangssperre ein/aus

## Dashboard „Sicherheit / Zugriff“

Beispiel mit **einem Tab pro Gebäude** und je einer Übersichtskarte: siehe  
[`examples/lovelace-sicherheit-zugriff.yaml`](examples/lovelace-sicherheit-zugriff.yaml).

## Voraussetzungen

- [Hikvision Access Control Integration](https://github.com/yourusername/hikvision-ha)
- Home Assistant 2023.1+
- Empfohlen: [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom) (Theme-Variablen)
