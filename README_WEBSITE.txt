AGENDA 2030 – WEBSITE UND DEUTSCHLANDKARTE – VERSION 0.6

INHALT
- Aktualisierte HTML-Seiten mit Navigation „Deutschlandkarte“
- karte.html: interaktive, responsive Karte mit Leaflet
- projekte.geojson: Datenquelle für die Kartenpunkte (derzeit absichtlich leer)
- style.css: bestehendes Design plus Kartenlayout

WICHTIG: Es werden keine Beispiel- oder ungeprüften Projekte erfunden. Die Karte startet ohne Marker und zeigt einen Hinweis, bis geprüfte Standorte eingetragen sind.

SO GEHT ES AUF GITHUB WEITER
1. ZIP auf dem Mac herunterladen und per Doppelklick entpacken.
2. Im GitHub-Repository Agenda-2030 auf „Add file“ > „Upload files“ klicken.
3. Die enthaltenen Dateien direkt in den Hauptordner ziehen, nicht in einen Unterordner.
4. Gleichnamige Website-Dateien ersetzen. Die vorhandenen Markdown-Dateien (AGENDA.md, MITMACHEN.md, PROJEKTREGISTER.md, README.md, LICENSE.md) NICHT löschen oder ersetzen.
5. „Commit directly to main“ wählen und committen.
6. Nach einigen Minuten https://hgtroester-ai.github.io/Agenda-2030/karte.html öffnen.

WELCHE DATEIEN HOCHLADEN?
index.html, agenda.html, projekte.html, mitmachen.html, grundsaetze.html, karte.html, style.css, projekte.geojson.
README_WEBSITE.txt ist nur eine Anleitung und optional.

SO ERGÄNZEN WIR SPÄTER EINEN GEPRÜFTEN STANDORT
Öffne projekte.geojson über GitHub und klicke auf das Stiftsymbol (Edit). In das leere Feld „features“ fügen wir später je ein Feature ein. Schema-Beispiel – NICHT als realen Projekteinstieg verwenden, bis echte Daten geprüft sind:

{
  "type": "Feature",
  "geometry": {"type": "Point", "coordinates": [LONGITUDE, LATITUDE]},
  "properties": {
    "name": "Projektname",
    "city": "Ort",
    "category": "Themenbereich",
    "description": "Kurzbeschreibung",
    "url": "https://offizielle-projektseite.example/",
    "status": "BELEGT"
  }
}

GeoJSON verwendet die Reihenfolge [Längengrad, Breitengrad]. Koordinaten nur aus einer verlässlichen öffentlichen Projektadresse ableiten. Keine privaten Wohnadressen veröffentlichen. Status muss exakt BELEGT lauten, sonst erscheint der Punkt nicht.

TECHNIK UND DATENSCHUTZ
- Leaflet ist eine quelloffene Bibliothek; die Seite lädt Leaflet-Dateien vom CDN unpkg.com.
- Kartendarstellung lädt Kartenkacheln von tile.openstreetmap.org. Die OpenStreetMap-Quellenangabe ist sichtbar eingebaut.
- Beim Öffnen der Karte werden Anfragen an diese externen Dienste ausgelöst. Das sollte bei der späteren Datenschutzerklärung berücksichtigt werden.
- Die öffentlichen OpenStreetMap-Kachelserver unterliegen einer Nutzungsrichtlinie und bieten keine garantierte Verfügbarkeit. Für geringe, normale Website-Nutzung vorgesehen; bei starkem Verkehr ggf. anderen Kachelanbieter verwenden.
