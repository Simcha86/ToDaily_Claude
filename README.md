# TRS – lokale PWA (MVP)

## Start

1. Python 3 installieren.
2. Im Projektordner ein Terminal öffnen.
3. `python -m http.server 8000` ausführen.
4. Am Notebook `http://localhost:8000` öffnen.

Die App speichert Daten lokal im Browser (localStorage). Sie unterstützt Aufgaben, tägliche/wochentägliche/wöchentliche/monatliche/einmalige Wiederholungen, Erledigungshistorie, Kalender, Statistiken, JSON-Backup und CSV-Export. Offline-Verfügbarkeit nach erstem Aufruf über Service Worker.

## Android

Für eine installierbare PWA die Dateien über einen HTTPS-Webserver bereitstellen und die URL in Chrome auf Android öffnen; dann im Browsermenü „App installieren“ wählen. `localhost` auf dem Notebook ist vom Smartphone aus nicht dasselbe Gerät. Ein lokaler HTTP-Server über das Netzwerk reicht für die PWA-Installation auf Android normalerweise nicht aus.

## Bekannte Einschränkungen

- Keine Synchronisierung zwischen Geräten oder Cloud-Datenbank.
- Erinnerungen werden nur geprüft, solange die App aktiv ist; keine garantierten Android-Hintergrundalarme.
- Browserdaten können beim Löschen von Websitedaten verloren gehen; regelmäßig JSON-Backups exportieren.
- Änderungen an Wiederholungsregeln können historische Soll-Werte rückwirkend verändern.
- Monatsregeln unterstützen feste Kalendertage, nicht „erster Sonntag“.
- Kein vollständiges Test- oder Produktions-Release; reale Geräte- und Browsertests stehen aus.

Für geräteübergreifende Synchronisierung wäre ein abgesicherter Backend-Dienst (z. B. Supabase) mit Authentifizierung, Offline-Queue und Konfliktbehandlung erforderlich. Für native Android-Hintergrunderinnerungen wäre z. B. Capacitor mit Local Notifications zu ergänzen.
