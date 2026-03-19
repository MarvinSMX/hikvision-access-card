# Hikvision Access Card

Lovelace Custom Card für **ein** [Hikvision Face Terminal](https://github.com/yourusername/hikvision-ha): Tür, Aktivität, Person, Zugang, optional Kamera, Zugangssperre.

**Mehrere Terminals auf einer Karte?** → separates Repository  
[Hikvision Access Overview Card](https://github.com/yourusername/hikvision-access-overview-card) (`custom:hikvision-access-overview-card`).

## Installation via HACS

1. HACS → **Frontend** → **Eigene Repositories**
2. URL dieses Repos · Kategorie: **Lovelace**
3. Installieren → **HA neu laden**

## Manuelle Installation

Datei `hikvision-access-card.js` nach `/config/www/` kopieren und als Ressource eintragen:

- URL: `/local/hikvision-access-card.js`
- Typ: **JavaScript-Modul**

## Konfiguration

```yaml
type: custom:hikvision-access-card
device: hintereingang_halle   # Entity-Prefix (Gerätename, Leerzeichen → _)
title: Hintereingang Halle    # optional
show_camera: true             # optional, default true
```

## Voraussetzungen

- [Hikvision Access Control Integration](https://github.com/yourusername/hikvision-ha)
- Home Assistant 2023.1+
- Empfohlen: [Mushroom Cards](https://github.com/piitaya/lovelace-mushroom) (Theme-Variablen)
