# Änderungsverlauf — Prüfprotokoll Elektroprüfung

Alle nennenswerten Änderungen am Programm werden hier festgehalten.
Neueste Version oben. Das Format orientiert sich an
[Keep a Changelog](https://keepachangelog.com/de/), die Versionsnummern folgen
[Semantischer Versionierung](https://semver.org/lang/de/) (`MAJOR.MINOR.PATCH`).

Die aktuelle Version steuert den Auto-Updater: Ist im Programm unter
**„🔑 Lizenz & Updates → Auf Updates prüfen"** eine neuere Version verfügbar, erscheint
oben ein grünes Update-Band. Bei jeder sichtbaren Änderung wird die Versionsnummer erhöht
und hier ein Eintrag ergänzt.

---

## [1.31.0] — 2026-07-20
### Geändert
- **Update-Hinweis deutlicher.** Findet das Programm beim Start (und danach alle 5 Minuten)
  eine neuere Version, erscheint oben ein **großes, sanft pulsierendes grünes Band**
  („✨ Neue Version vX verfügbar — 👉 Hier tippen, um zu aktualisieren 🔄"). **Das ganze
  Band ist klickbar** und startet den vorhandenen Update-Vorgang (ZIP-Paket laden). Es wird
  **nichts automatisch aktualisiert oder neu geladen** — der Kunde entscheidet per Klick.
  Das Band bleibt sichtbar, bis es weggeklickt (`✕`) oder aktualisiert wird; bei einer noch
  neueren Version taucht es wieder auf. Zusätzlich weiterhin ein kleiner „manuell laden"-Link.

## [1.30.0] — 2026-07-20
### Geändert
- **Reiter-Reihenfolge umsortiert.** Die drei Verwaltungs-Reiter stehen jetzt in der
  Reihenfolge **👥 Kundenstamm · 📇 Anlagen-Stamm · 🧰 Geräte-Katalog** (vorher stand der
  Geräte-Katalog vor dem Anlagen-Stamm). Die drei Prüfprotokoll-Reiter davor bleiben
  unverändert.

## [1.29.0] — 2026-07-20
### Geändert
- **Geräte-Katalog füttert jetzt alle drei Prüfprotokolle.** Bisher gab es nur die Zuordnung
  „ortsveränderlich" und „ortsfest (Anlage)". Neu ist eine dritte Zuordnung
  **„🏭 ortsfest EX (Zustand)"** – Geräte lassen sich damit direkt in das Protokoll
  **„Ortsfeste EX"** (Zustandsprüfung DIN EN 60079-17) übernehmen (Haken setzen → Gerät
  erscheint sofort im richtigen Tab). Auch der Anzeige-Filter im Katalog und der CSV-Import
  („ortsfest EX" / „Zustand") kennen die neue Zuordnung.

## [1.25.0] — 2026-07-20
### Geändert
- **Anlagen-Stamm hat jetzt einen eigenen Reiter in der oberen Leiste** – direkt neben
  „🧰 Geräte-Katalog". Das Verwalten der Standorte (Anlagen mit Koordinaten, NIS-Nr.,
  Kostenstelle) war bisher aufklappbar im Reiter „🏭 Anlagenprüfung" versteckt. Jetzt ist es
  eine eigene Ansicht **„📇 Anlagen-Stamm"** mit Zähler, gleichberechtigt neben Kundenstamm
  und Geräte-Katalog. Anlegen, Bearbeiten, CSV-/Excel-Import und -Export bleiben unverändert;
  „➜ ins Protokoll" übernimmt eine Anlage weiterhin in die Anlagenprüfung.

## [1.24.0] — 2026-07-20
### Geändert
- **Rückmeldung per E-Mail statt GitHub-Konto.** Der Rückmeldung-Knopf öffnet jetzt eine
  vorausgefüllte E-Mail an den Anbieter – kein GitHub-Konto mehr nötig.

## [1.23.0] — 2026-07-20
### Neu
- **Rückmeldung-Knopf** unter „🔑 Lizenz & Updates" für Wünsche/Fehlermeldungen.

## [1.22.0] — 2026-07-19
### Geändert
- **Geräte-Code übersteht jetzt das Löschen des Browser-Speichers.** Bisher war der
  Geräte-Code (an den die Lizenz gebunden ist) eine zufällige ID im Browser-Speicher –
  wurde dieser gelöscht, änderte sich der Code und man brauchte einen neuen Schlüssel.
  Jetzt wird der Code aus **festen Merkmalen des Rechners** berechnet
  (Betriebssystem, CPU-Kerne, Arbeitsspeicher, Grafikkarte/Treiber, Farbtiefe, Sprache).
  Er bleibt dadurch **stabil**, auch wenn der Browser-Speicher geleert wird. Bewusst
  **nicht** einbezogen: Bildschirmauflösung und Browser-Version (ändern sich zu oft) –
  so bleibt der Code auch mit externem Monitor oder nach einem Browser-Update gleich.
### Kompatibilität
- **Bestehende Lizenzen gelten weiter.** Schlüssel, die vor v1.22.0 ausgestellt wurden,
  werden weiterhin akzeptiert, solange die alte (zufällige) ID noch im Browser liegt.
  Wird der Speicher gelöscht, ist **einmalig** ein neuer Schlüssel nötig – dieser übersteht
  danach jedes weitere Löschen dauerhaft.

## [1.21.0] — 2026-07-18
### Geändert
- **Aufräumen: nichts Betriebssystem-Spezifisches mehr.** Das Programm ist und bleibt
  **eine einzige HTML-Datei**, die auf **Windows, macOS und Linux** per Doppelklick im
  Browser läuft.
  - Der **Windows-Starter** (`Start (Doppelklick).cmd`) wurde aus dem Update-/Download-Paket
    **entfernt** – man öffnet einfach die HTML-Datei direkt.
  - Die **Kurzanleitung (LIESMICH.txt)** gilt jetzt ausdrücklich für **alle Systeme**.
  - In der App und in der Doku heißt das Update-Paket neutral **„Update-Paket (ZIP)"**
    statt „Windows-ZIP".
- **Repo verschlankt:** alte Werkstatt-Uploads (`werkstatt-uploads/`) und eine veraltete
  Workflow-Vorlage (`werkzeuge/`) wurden entfernt – sie wurden nicht mehr gebraucht.
- *Hinweis:* Der interne ZIP-Dateiname enthält aus Kompatibilitätsgründen (Veröffentlichungs-
  Workflow + ältere ausgelieferte Programme) noch „Windows"; der Inhalt ist voll systemunabhängig.

## [1.20.0] — 2026-07-18
### Geändert
- **Geräte kommen jetzt ausschließlich aus dem Geräte-Katalog.** In beiden Protokollen
  (**Ortsveränderlich** und **Anlagenprüfung**) wurden die Möglichkeiten entfernt, ein Gerät
  direkt im Protokoll anzulegen:
  - Der Knopf **„➕ Gerät hinzufügen" / „➕ Leeres Gerät"** ist weg (kein leeres Gerät mehr).
  - Die **zweite Katalog-Auswahl** ist weg: weder das Auswahlfeld „🧰 Gerät aus Katalog
    hinzufügen …" über der Liste (Anlagenprüfung) noch das Feld „🧰 Gerät aus Ex-Katalog"
    in jeder Gerätekarte.
- **Ein einziger Weg:** Geräte werden im Tab **„🧰 Geräte-Katalog"** per Haken hinzugefügt und
  landen – je nach Zuordnung (ortsveränderlich / ortsfest) – automatisch im richtigen Protokoll.
  Ein Hinweistext in beiden Protokollen weist darauf hin.

## [1.19.0] — 2026-07-18
### Neu
- **Filter im Geräte-Katalog.** Über der Katalogliste gibt es jetzt drei Knöpfe
  **„Alle" · „📋 ortsveränderlich" · „🏭 ortsfest (Anlage)"**. Damit lässt sich die Liste auf eine
  Prüfart eingrenzen – praktisch bei vielen Geräten. Der Filter wirkt zusammen mit der Suche und mit
  „➜ Alle sichtbaren in Prüfliste" (es werden nur die aktuell angezeigten Geräte übernommen).

---

## [1.18.0] — 2026-07-18
### Neu
- **Geräte-Katalog speist jetzt beide Prüfarten.** Jedes Katalog-Gerät hat eine **Zuordnung**
  (**📋 ortsveränderlich** oder **🏭 ortsfest (Anlage)**). Beim Setzen des Hakens erscheint das Gerät
  **sofort im richtigen Tab** – ortsveränderlich im Tab „Ortsveränderlich", ortsfest in der
  „Anlagenprüfung". So werden beide Tabs zentral und ausschließlich aus dem Gerätekatalog gefüttert.
- **Zuordnung direkt umstellbar** – in jeder Katalogzeile per Auswahl; ist das Gerät bereits in einer
  Prüfliste, wandert es automatisch in den anderen Tab.
- **Import/Export** kennt jetzt die Spalte **„Zuordnung"** (Werte „ortsfest" bzw. „ortsveränderlich";
  ohne Angabe → ortsveränderlich). Die Katalog-Sicherung (CSV) enthält die Zuordnung mit.

## [1.17.4] — 2026-07-17
### Geändert
- **Update lädt jetzt das komplette Paket (Windows-ZIP)** statt nur der HTML-Datei. Der grüne Band-Button
  heißt jetzt **„⬇️ Update-Paket laden"** und lädt das vollständige Release-ZIP
  (`Pruefprotokoll-Elektro-Windows.zip`: Programm-HTML + Starter + LIESMICH + version.json + CHANGELOG +
  LICENSE) in den Download-Ordner. Anleitung im Programm: **1.** entpacken, **2.** Dateien in den
  bisherigen Programm-Ordner kopieren und ersetzen (gleicher Ordner/Pfad → gespeicherte Eingaben/Kunden
  bleiben erhalten), **3.** `Prüfprotokoll Elektroprüfung.html` neu öffnen.
- ZIP-Download-Link wird direkt aus dem GitHub-Release gezogen (Asset `…-Windows.zip`), mit konstruierter
  Fallback-URL. Hinweistexte (Lizenz-Dialog, LIESMICH.txt, öffentliches README) entsprechend angepasst.

---

## [1.17.3] — 2026-07-17
### Geändert
- **„➜ ins Protokoll" gilt jetzt für beide Messarten:** Wenn du im Kundenstamm einen Kunden mit
  **„➜ ins Protokoll"** übernimmst, werden seine Daten (Firma/Name, Adresse, Kontakt, Anlage) sowohl
  ins **ortsveränderliche** Protokoll als auch in die **ortsfeste Anlage** übernommen – nicht mehr nur
  in die ortsveränderliche Seite. Hinweistext im Kundenstamm entsprechend angepasst.

---

## [1.17.2] — 2026-07-17
### Geändert
- **Anlagen-Tab (ortsfest):** Der Button **„➕ Leeres Gerät"** sitzt jetzt **unter** der Geräteliste
  (statt darüber) – genau wie auf der ortsveränderlichen Seite. Der Katalog-Auswahl-Dropdown bleibt
  oben. Reine Anordnungsänderung, keine Auswirkung auf gespeicherte Daten.

---

## [1.17.1] — 2026-07-17
### Behoben
- **Update-Loop behoben** („installiert, findet aber immer wieder dieselbe neue Version"). Ursache: der
  In-App-Updater lud die neue Datei über `raw.githubusercontent.com`, dessen CDN **~5 Minuten veraltet**
  ist und Cache-Buster ignoriert – so wurde bei schnell aufeinanderfolgenden Versionen teils die **alte**
  Datei erneut installiert, während die Update-Prüfung (frische Releases-API) weiter die neue Version fand.
  - Der Updater lädt jetzt über die **GitHub-Contents-API** (immer aktueller Stand), nur als Fallback noch
    über das CDN.
  - **Sicherung gegen Endlos-Update:** Vor dem Ersetzen wird geprüft, dass die geladene Datei **wirklich
    neuer** ist als die laufende. Ist sie es (noch) nicht, bricht das Update mit klarem Hinweis ab
    („Server-Verzögerung – in 1–2 Minuten erneut") statt dieselbe Version wieder einzuspielen.
  - Ein evtl. hängengebliebenes Update-Band verschwindet, sobald die Version aktuell ist.

## [1.17.0] — 2026-07-17
### Geändert
- **Anlagenprüfung (ortsfest) vereinheitlicht.** Der Abschnitt **„Auftrag & Beteiligte" ist jetzt
  identisch** zur ortsveränderlichen Prüfung (gleiche Felder + Reihenfolge, inkl. Kundenstamm-Auswahl
  und Prüfnorm). Die anlagenspezifischen Objektdaten (Art, NIS-Nr., Kostenstelle, Standort, Koordinaten)
  stehen in einem eigenen Block **„Anlagen-Objekt"**.
- **Geräte der Anlage wie bei ortsveränderlich.** Statt fest vorbelegter Pumpen/Messtechnik/Betriebsmittel
  gibt es jetzt eine **generische Geräte-Liste** – **nichts ist mehr vorausgefüllt**. Geräte werden aus dem
  **Geräte-Katalog** ausgewählt (gilt jetzt für **beide** Protokolltypen) oder leer hinzugefügt; jedes Gerät
  wird einzeln geprüft (R_PE · R_ISO · I_PE · Sicht/Funktion · Mess-Schritte). **Bestehende Anlagen-Daten
  (Pumpen etc.) werden beim Update automatisch in die neue Geräte-Liste übernommen.**
- **RISO auf den Geräte-Messbereich begrenzt.** Wird ein Wert **über** dem Messbereich des Prüfgeräts
  eingegeben, zeigt das Protokoll **„≥ <Messbereich>"** (z. B. „≥ 300"), statt einen Wert, den das Gerät
  gar nicht messen kann. Beim Verlassen des Feldes wird der Eingabewert entsprechend gekappt.

## [1.16.0] — 2026-07-17
### Neu
- **Prüfgerät-Auswahl als Dropdown mit Favoriten.** Statt Freitext gibt es jetzt eine Auswahlliste
  gängiger Gerätetester/Prüfgeräte (Gossen Metrawatt SECUTEST/PROFITEST, Benning ST 7xx / IT,
  Fluke 6200/6500/166x, Megger PAT/MFT, Bender, Kyoritsu, Beha-Amprobe, Chauvin Arnoux, HT).
  Über **„🔧 Prüfgeräte verwalten"** lassen sich mit ⭐ **Favoriten** setzen (nur diese erscheinen im
  Dropdown) und **eigene Geräte** ergänzen. Gilt für ortsveränderliche **und** Anlagen-Prüfung.
### Geändert
- **RISO „≥" jetzt geräteabhängig:** Jedes Prüfgerät hat einen hinterlegten **RISO-Messbereich (MΩ)**.
  Das „≥" wird nur noch gesetzt, wenn der Messwert **den Messbereich erreicht/übersteigt** (z. B.
  SECUTEST bis 300 → „≥ 300"; Megger PAT420 bis 2000 → erst ab 2000). Darunter erscheint der **echte
  Messwert** ohne ≥. Ist kein Prüfgerät gewählt, gilt 500 MΩ als Schwelle.
- Die Prüfgeräte-/Favoritenliste wird im **Komplett-Backup** mitgesichert (Rechnerwechsel).

## [1.15.1] — 2026-07-17
### Geändert
- **Isolationswiderstand (R_ISO):** Bei Feldern mit „größer-gleich"-Grenzwert (R_ISO bei
  Geräten und bei Pumpen/Aggregaten der Anlagenprüfung) wird jetzt automatisch das Zeichen
  **„≥"** vor den eingetragenen Wert gestellt — sowohl im Eingabefeld (sobald ein Wert
  eingetragen ist) als auch im gedruckten Protokoll (z. B. „≥ 300 MΩ"). Leere Felder bleiben
  unverändert. Der gespeicherte Zahlenwert und die automatische Grenzwert-Bewertung (Ampel)
  bleiben davon unberührt.

## [1.15.0] — 2026-07-17
### Neu
- **Ortsfeste Anlagenprüfung nach DIN VDE 0105** als eigener Bereich. Oben gibt es jetzt zwei
  getrennte Protokoll-Tabs: **„📋 Ortsveränderlich"** (wie bisher: DGUV V3 · VDE 0701-0702) und
  **„🏭 Anlagenprüfung"** (DIN VDE 0105-100). Beide werden **komplett getrennt** gespeichert und
  gedruckt.
- Die Anlagenprüfung bildet die übliche Prüf-Vorlage ab: **Checklisten** (Dokumentation/Kennzeichnung,
  EVU-Zählung, Erdung/Blitzschutz, Schaltschrank), **Pumpen/Aggregate flexibel** – jedes Gerät
  einzeln, mit Motorschutz, Isolationswert (Riso), Pumpenschaltung und Temperaturüberwachung –
  sowie **Messtechnik** und **Steckdosen/Beleuchtung/sonstige Betriebsmittel**. Alle Bereiche sind
  frei erweiterbar (Positionen/Geräte hinzufügen und entfernen).
- **Anlagen-Stamm mit Standort-Koordinaten:** Standorte (Name, Art, Kostenstelle, NIS-Nr.,
  Koordinaten) lassen sich verwalten und **per CSV/Excel importieren**. Im Protokoll wählt man die
  Anlage aus – Name und Koordinaten werden automatisch übernommen.
- **Mini-Karte** aus den Koordinaten (DMS oder Dezimal): Koordinaten-Anzeige, Links zu
  OpenStreetMap/Google Maps und eine einblendbare Kartenvorschau.
### Geändert
- Bei den **ortsveränderlichen** Betriebsmitteln ist **ZLPE** (Kurzschlussstrom) aus den
  Mess-Schritten entfernt – es gehört zur ortsfesten Anlagenprüfung. Vorhandene RISO-Messungen
  bleiben unverändert.

## [1.14.0] — 2026-07-16
### Neu
- **Zeitlich begrenzte Lizenzen (Miete/Abo möglich).** Im Lizenz-Werkzeug lässt sich jetzt beim
  Erzeugen eines Schlüssels die **Gültigkeitsdauer** wählen: **dauerhaft**, **7 / 30 / 365 Tage**
  oder **frei** (beliebige Anzahl Tage bzw. ein festes Enddatum). Die Dauer steckt fälschungssicher
  im signierten Schlüssel.
- Im Programm zeigt der Bereich **„🔑 Lizenz & Updates → ① Lizenzschlüssel“** jetzt an, bis wann die
  Lizenz gilt (z. B. „gültig bis 31.12.2026“). Läuft die Frist in **21 Tagen oder weniger** ab,
  erscheint ein deutlicher Hinweis mit den verbleibenden Tagen.
- **Nach Ablauf** schaltet die App automatisch wieder in den **Testmodus** und zeigt oben ein
  rotes Band „Lizenz abgelaufen“. Für eine Verlängerung stellt der Anbieter einfach einen neuen
  Schlüssel mit neuem Ablauf aus.
- Bereits ausgegebene, dauerhafte Schlüssel (bisheriges Format) bleiben **unverändert gültig**.

## [1.13.0] — 2026-07-16
### Neu
- **Handy- & Kleinbildschirm-tauglich (responsiv).** Das Programm passt sich jetzt an
  Smartphones und kleine Monitore an: auf schmalen Displays werden die Formulare **einspaltig**
  mit großen Tippfeldern, Kopf- und Kartenränder sind kompakter, und die Werkzeugleiste oben
  **klebt nicht mehr** am Rand (sie scrollt mit), damit sie umgebrochen nicht den halben
  Bildschirm verdeckt. Gespeichert wird ohnehin automatisch. Die Dialoge (Hilfe, Backup,
  Lizenz) passen jetzt sauber auf schmale Bildschirme. Der Druck/PDF bleibt unverändert.

## [1.12.0] — 2026-07-15
### Neu
- **Kompaktes PDF / Druck als Tabelle.** Die geprüften Betriebsmittel werden beim Drucken
  jetzt als **schlanke Tabelle** ausgegeben (eine Zeile pro Gerät) statt als große Karten.
  Damit passen **viele Geräte auf eine Seite** — bei hunderten Geräten wird das Protokoll
  nicht mehr riesig. Mess-Schritte (RISO/ZLPE) erscheinen als kompakte Zusatzzeile unter dem
  jeweiligen Gerät, damit nichts verloren geht. Die Tabellen-Kopfzeile wird auf jeder Seite
  wiederholt; Zeilen brechen nicht mitten über den Seitenrand.
- Am Bildschirm bleibt alles wie gewohnt (bearbeitbare Geräte-Karten) — die kompakte Tabelle
  erscheint **nur** im Druck/PDF.

## [1.11.2] — 2026-07-15
### Behoben
- **PDF robust bei langen Namen/Anschriften.** Lange Kundennamen, Anschriften und
  Bezeichnungen wurden im Druck abgeschnitten; leere Felder zeigten ihren Platzhalter. Jetzt
  werden alle Feldwerte als umbrechender Text gedruckt (leer → „—"), und es druckt nur der
  Protokoll-Tab (Kundenstamm/Katalog bleiben außen vor).

## [1.11.1] — 2026-07-15
### Behoben
- Obere Leiste wieder **einreihig** — Knopf-Label „Hilfe / Rechtliches" auf „Hilfe" gekürzt,
  damit die Leiste bei ~1240 px nicht umbricht.

## [1.11.0] — 2026-07-15
### Neu
- **Ein-Klick-Update in-place** — der Update-Knopf ersetzt die laufende Datei direkt und lädt
  neu; Kundendaten und Gerätebindung bleiben erhalten. Fallback auf Download, falls der
  Browser das direkte Ersetzen nicht kann.
- **Auto-Update-Prüfung alle 5 Minuten** (statt 1×/Tag) plus Sofort-Prüfung, wenn der Rechner
  wieder online geht oder das Tab wieder aktiv wird.
- **Leiser Offline-Hinweis** in der oberen Leiste, verschwindet automatisch bei Verbindung.

## [1.10.0] — 2026-07-15
### Geändert
- **Lizenz v3 — Geräte-Bindung (Node-Lock).** Ein Lizenzschlüssel gilt nur noch auf **dem
  Gerät**, dessen Geräte-Code beim Signieren verwendet wurde. Die App zeigt einen Geräte-Code;
  Kunde schickt Name + Code, erhält einen passenden Schlüssel. Alte v2-Schlüssel (nur Name)
  sind damit ungültig.

## [1.9.1] — 2026-07-15
### Geändert
- **Lizenz nicht mehr im Backup.** Beim Rechnerwechsel muss die Lizenz neu eingegeben werden
  (Vorstufe zum Schutz gegen Doppelnutzung).

## [1.9.0] — 2026-07-15
### Neu
- **Tab-Navigation** statt langer Scroll-Seite: **📋 Protokoll**, **👥 Kundenstamm**,
  **🧰 Geräte-Katalog** — jeweils mit Live-Zähler. Der Druck betrifft weiterhin nur das
  Protokoll.

## [1.8.5] — 2026-07-15
### Geändert
- **Komplett-Backup** wandert in die obere Leiste (Knopf **🗄️ Backup** mit Erklär-Dialog).

## [1.8.4] — 2026-07-15
### Behoben
- Prüffirma war mit einem echten Firmennamen vorbelegt → jetzt leerer Default mit generischem
  Platzhalter (keine Fremd-Daten in der Kundenversion).

## [1.8.3] — 2026-07-15
### Neu
- **Datensicherung (Rechnerwechsel & Backup).** Ein Knopf sichert **alle** Daten (Protokoll,
  Kundenstamm, Katalog) in **eine** Datei und spielt sie auf einem neuen Gerät wieder ein.

## [1.8.2] — 2026-07-15
### Behoben
- **Editions-spezifische Speicher-Schlüssel.** Die Kundenversion nutzt eigene Speicher-Namen
  (`*_kunde_v1`) und startet garantiert leer, statt versehentlich Autor-Altdaten aus dem
  Browser anzuzeigen.

## [1.8.1] — 2026-07-15
### Behoben
- **Geräte-Katalog der Kundenversion startet leer.** Der Autor-Seed (Ex-Beispieltabellen)
  wird beim Bauen der Kundenversion vollständig entfernt; der Kunde füllt seinen Katalog per
  CSV/Excel-Import selbst.

## [1.8.0] — 2026-07-15
### Geändert (Sicherheit) ⚠️
- **Fälschungssichere Lizenz v2 (ECDSA P-256 / Signatur).** Die Kundendatei enthält nur noch
  den **öffentlichen** Schlüssel und kann Lizenzen nur **prüfen**, nicht mehr erzeugen.
  Schlüssel entstehen ausschließlich im separaten Autor-Werkzeug mit dem privaten Schlüssel.
  Die ausgelieferte Kundendatei kann Lizenzen nur **prüfen**, niemals erzeugen.

---

_Ältere interne Stände (< 1.8.0) sind aus Sicherheitsgründen nicht mehr im Umlauf und werden
hier nicht weitergeführt._
