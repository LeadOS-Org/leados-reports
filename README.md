# leados-reports

Öffentliches Berichte-Repository für LeadOS. Enthält **ausschließlich**
strukturierte Berichte (Protokolle, Tagesberichte, Monatsberichte) im
JSON-Format — keinen Produktcode. Wird von der LeadOS-Arbeitsstand-Seite
zur Laufzeit per `fetch()` eingelesen (siehe `integration-module.html`
im Übergabepaket).

## Struktur

```
index.json              — Liste aller Berichte (id, typ, datum, titel, pfad)
schema/
  index.schema.json      — JSON-Schema für index.json
  report.schema.json      — JSON-Schema für einzelne Berichte
reports/
  <id>.json               — ein Bericht pro Datei
```

## Neuen Bericht hinzufügen

1. Neue Datei `reports/<typ>-<datum>.json` nach `schema/report.schema.json` anlegen.
2. Eintrag in `index.json` ergänzen (id, typ, datum, titel, pfad).
3. Commit + Push (bzw. PR, falls Branch-Protection aktiv).

## Governance

Dieses Repo ist bewusst von `leados-design-foundation` (Produktcode,
privat) getrennt, damit Berichte ohne Rücksicht auf die Sichtbarkeit
des Produktrepos veröffentlicht werden können. Git bleibt Single
Source of Truth — jeder Bericht ist eine versionierte, diff-fähige Datei.
