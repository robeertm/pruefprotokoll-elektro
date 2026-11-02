# Prüfprotokoll Elektroprüfung – Kundenversion

Fertiges Programm zum Erstellen von **Prüfprotokollen für die Elektroprüfung**.
Eine einzige HTML-Datei – **Doppelklick**, läuft im Browser (Edge/Chrome), **auch ohne Internet**,
keine Installation. Die Kundendatenbank startet **leer**.

> ### ⚠️ Bitte vor dem Einsatz lesen
>
> **Dieses Programm ist weitgehend KI-generiert.** Quelltext und Dokumentation
> sind von einer KI geschrieben und von einem Menschen durchgesehen — nicht
> umgekehrt. Es wird **ohne Gewähr und ohne jede Haftung** bereitgestellt: für
> Fehler, für falsche oder unvollständige Ausgaben, für verlorene Eingaben oder
> für Folgen aus der Nutzung. **Die Verwendung erfolgt auf eigenes Risiko.**
>
> Drei Punkte, die hier besonders zählen:
>
> - **Das Programm prüft nichts — es dokumentiert.** Es nimmt entgegen, was
>   eingegeben wird, und formt daraus ein Protokoll. Ob gemessen, bewertet und
>   dokumentiert wurde, was die geltenden Vorschriften und Normen verlangen,
>   verantwortet allein die prüfende Fachkraft.
> - **Es ersetzt weder Fachkunde noch Messgerät noch Normenwerk.** Eine
>   Plausibilitäts- oder Vollständigkeitsprüfung der Eingaben findet nicht
>   statt; Rechenergebnisse und Bewertungen können falsch sein.
> - **Über die rechtliche Verwendbarkeit eines erzeugten Protokolls** — gegenüber
>   Auftraggebern, Versicherern oder Behörden — entscheidet nicht dieses
>   Programm. Das ist vor dem produktiven Einsatz zu klären.

## Was das Programm kann
- **Ortsveränderliche Betriebsmittel** (DGUV V3 · VDE 0701-0702): Geräte mit Messwerten,
  Sicht-/Funktionsprüfung und automatischer Bewertung, kompaktes PDF auch bei vielen Geräten.
- **Ortsfeste Anlagen** (DIN VDE 0100-600 / 0105-100): zweiseitiges Prüfprotokoll mit
  Besichtigung, Erprobung, Messung, Potentialausgleich und Unterschriften, dazu der
  **Anhang zum Übergabebericht** im Querformat mit allen Stromkreisen – Schleifenimpedanz und
  Kurzschlussstrom, R_PE, RCD mit Auslöseprüfung der positiven und negativen Halbwelle je
  L1/L2/L3, R_ISO, Differenzstrom und Spannung. R_ISO-Werte über dem Messbereich des gewählten
  Prüfgeräts erscheinen als „≥ Messbereichsende"; 3~-Stromkreise haben ein Häkchen „Rechtsdrehfeld".
- **Ortsfeste Ex-Anlagen**: Zustandsprüfung nach DIN EN 60079-17.
- Kundenstamm, Anlagen-Stamm und Geräte-Katalog (Import per CSV/Excel), Komplett-Backup.

## Herunterladen
- Neueste **Windows-Version (ZIP)**: siehe **[Releases](../../releases/latest)**.
- Oder die Datei `Prüfprotokoll Elektroprüfung.html` hier direkt speichern und öffnen.

## Lizenz
Ohne Lizenzschlüssel läuft das Programm als **Testversion** (Ansehen/Eingeben; Drucken,
Speichern und Export gesperrt). Den Schlüssel bekommst du vom Anbieter. Oben im Programm
unter **„🔑 Lizenz & Updates"** Namen + Schlüssel eintragen → alle Funktionen frei.

## Updates
Im Programm auf **„🔑 Lizenz & Updates" → „Auf Updates prüfen"**. Ist eine neue Version da,
erscheint oben ein grünes Band **„⬇️ Update-Paket laden"** – es lädt das komplette ZIP.
Danach entpacken und die Dateien in den bisherigen Programm-Ordner kopieren/ersetzen
(gleicher Ordner → gespeicherte Eingaben bleiben erhalten).

© 2026 Robert Manuwald · Version 1.33.0

---
*Automatisch veröffentlichte Kundenversion. Dieses Repo enthält bewusst nur die
Kundendateien – keine Kundendaten und keine Entwickler-Werkzeuge.*
