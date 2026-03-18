# Hikvision Access Card

Lovelace Custom Card für [Hikvision Face Terminals](https://github.com/yourusername/hikvision-ha).

Zeigt Türstatus, Aktivität, letzte Person, Zugangsstatus, Live-Snapshot und Zugangssperre in einem kompakten Mushroom-Style Card.

## Installation via HACS

1. HACS → Dashboards → **Eigene Repositories**
2. URL: `https://github.com/yourusername/hikvision-access-card` · Kategorie: **Lovelace**
3. Installieren → HA neu laden

## Manuelle Installation

Datei `hikvision-access-card.js` nach `/config/www/` kopieren und als Ressource eintragen:

- URL: `/local/hikvision-access-card.js`
- Typ: **JavaScript-Modul**

## Konfiguration

```yaml
type: custom:hikvision-access-card
device: hintereingang_halle   # Entity-Prefix (Gerätename, Leerzeichen → _)
title: Hintereingang Halle    # optional — wird sonst aus device abgeleitet
```

## Voraussetzungen

- [Hikvision Access Control Integration](https://github.com/yourusername/hikvision-ha)
- Home Assistant 2023.1+
- Empfohlen: [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom) (für Theme-Variablen)
