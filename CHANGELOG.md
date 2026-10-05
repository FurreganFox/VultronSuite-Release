# Changelog

All notable changes to Vultron Acquire and Vultron Visualize.
/ Alle nennenswerten Änderungen an Vultron Acquire und Vultron Visualize.

## [Acquire 1.0.8] - [Visualize 1.0.8] - Unreleased

### Changed / Geändert
- Notifications are now shown only as a Windows notification card
  (bottom right); the extra pop-up windows were removed. Acquire: a
  notification for each queue step can be switched on/off per step in the
  step editor ("Show a notification when this step finishes", default on;
  replaces "Also show a pop-up ..."). The end of the whole queue and
  queue errors always show a notification.
  / Benachrichtigungen erscheinen jetzt nur noch als Windows-Karte (unten
  rechts); die zusätzlichen Pop-up-Fenster entfallen. Acquire: Die
  Benachrichtigung für jeden Queue-Schritt lässt sich pro Schritt im
  Schritt-Editor ein-/ausschalten ("Show a notification when this step
  finishes", Standard: an; ersetzt "Also show a pop-up ..."). Ende der
  gesamten Queue und Queue-Fehler zeigen immer eine Benachrichtigung.

### Fixed / Behoben
- Saving a new license key in the license pop-up now takes effect
  immediately (Acquire and Visualize) - no more "server unreachable"
  messages until a restart. A rejected key no longer stays saved and no
  longer closes Acquire.
  / Ein neuer Lizenzschlüssel im Lizenz-Pop-up wirkt jetzt sofort
  (Acquire und Visualize) - keine "Server nicht erreichbar"-Meldungen mehr
  bis zum Neustart. Ein abgelehnter Schlüssel bleibt nicht gespeichert und
  schließt Acquire nicht mehr.
- If the license server no longer knows a running session (e.g. after
  standby), the program now claims it again automatically instead of
  counting down an outage.
  / Kennt der Lizenzserver eine laufende Sitzung nicht mehr (z. B. nach
  Standby), beansprucht das Programm sie automatisch neu, statt einen
  Ausfall herunterzuzählen.
- "Update available" is never shown twice at the same time (Acquire and
  Visualize).
  / "Update available" erscheint nie mehr doppelt gleichzeitig (Acquire
  und Visualize).
- Acquire: when a Current-Voltage monitoring recording stops, the Ivium
  driver connection is now restarted automatically (device disconnect,
  driver reopen, reconnect - what stopping and restarting with the power
  button does by hand). Logging pauses for a few seconds and resumes on its
  own (mitigation for #1).
  / Acquire: Wenn eine Current-Voltage-Aufnahme endet, wird die
  Ivium-Treiberverbindung automatisch neu gestartet (Gerät trennen, Treiber
  neu öffnen, neu verbinden - das, was das Aus- und Einschalten per
  Power-Button von Hand bewirkt). Das Logging pausiert einige Sekunden und
  läuft von selbst weiter (Abmilderung für #1).

## [Acquire 1.0.7] - [Visualize 1.0.7] - 2026-10-05

### Added / Neu
- Windows notifications (Action Center toast) when a Method Queue step
  finishes, when the whole queue finishes/aborts/fails, and when a
  Visualize analysis completes or fails (#11). License problems also
  trigger a toast.
  / Windows-Benachrichtigungen (Toast im Action Center), wenn ein
  Method-Queue-Schritt fertig ist, wenn die ganze Queue endet/abgebrochen
  wird/fehlschlägt und wenn eine Visualize-Analyse abgeschlossen wird oder
  fehlschlägt (#11). Auch Lizenzprobleme lösen einen Toast aus.
- Acquire: new per-step option "Also show a pop-up when this step
  finishes" in the step editor (#12). When the whole queue ends, a pop-up
  is always shown in addition to the toast.
  / Acquire: neue Option pro Schritt "Also show a pop-up when this step
  finishes" im Schritt-Editor (#12). Wenn die ganze Queue endet, erscheint
  zusätzlich zum Toast immer ein Pop-up.

### Fixed / Behoben
- Acquire: the Results Panel title for an impedance spectrum no longer
  shows a raw database file name after a GUI-driven run (#17).
  / Acquire: Der Titel im Results Panel zeigt für ein Impedanzspektrum nach
  einem GUI-gesteuerten Lauf keinen rohen Datenbank-Dateinamen mehr (#17).
- Acquire: removed a harmless but confusing "invalid command name
  ..._tick_greeting" message in the console after clicking Start.
  / Acquire: Eine harmlose, aber irritierende Konsolenmeldung "invalid
  command name ..._tick_greeting" nach dem Klick auf Start ist behoben.

## [Acquire 1.0.6] - [Visualize 1.0.6] - 2026-10-02

### Added / Neu
- Acquire: zoom support in the Results Panel preview (#14).
  / Acquire: Zoom-Unterstützung in der Vorschau des Results Panels (#14).
- Admin-free installer with component selection (Acquire only /
  Visualize only / both), German and English.
  / Installer ohne Administratorrechte mit Komponentenauswahl (nur
  Acquire / nur Visualize / beides), Deutsch und Englisch.

### Fixed / Behoben
- Only one pop-up (license, version, graph options) can be open at a
  time (#13).
  / Es kann nur noch ein Pop-up (Lizenz, Version, Graph-Optionen)
  gleichzeitig geöffnet sein (#13).
- Pop-ups show their status message above the close hint (#16).
  / Pop-ups zeigen ihre Statusmeldung über dem Schließen-Hinweis (#16).
- Acquire: after a longer Current-Voltage monitoring run, the device
  connection is reset automatically when monitoring stops, so the
  completion detection of a later i-V curve no longer lags behind
  IviumSoft (mitigation for #1).
  / Acquire: Nach einer längeren Current-Voltage-Überwachung wird die
  Geräteverbindung beim Stoppen automatisch zurückgesetzt, damit die
  Fertig-Erkennung einer späteren i-V-Kurve nicht mehr hinter IviumSoft
  herhinkt (Abmilderung für #1).
- Updates retry a failed file download up to three times with increasing
  waiting time.
  / Updates wiederholen einen fehlgeschlagenen Datei-Download bis zu
  dreimal mit wachsender Wartezeit.
- Removed a "SyntaxWarning: invalid escape sequence" shown at startup.
  / Eine beim Start angezeigte "SyntaxWarning: invalid escape sequence"
  wurde entfernt.

## [Acquire 1.0.5] - [Visualize 1.0.5] - 2026-09-30

### Changed / Geändert
- Acquire: saved .idf files are renamed automatically to their real name
  (e.g. "700 °C.idf" instead of "700 degC.idf"). Files saved earlier are
  not renamed retroactively.
  / Acquire: Gespeicherte .idf-Dateien werden automatisch auf ihren
  echten Namen umbenannt (z. B. "700 °C.idf" statt "700 degC.idf"). Früher
  gespeicherte Dateien werden nicht rückwirkend umbenannt.
- License and version pop-ups: white border at startup fixed, "Registered
  to:" label, status line only shown when it has content, save and
  install-now buttons as icons next to the text.
  / Lizenz- und Versions-Pop-ups: weißer Rahmen beim Start behoben,
  Beschriftung "Registered to:", Statuszeile nur bei Inhalt sichtbar,
  Speichern- und Install-now-Button als Icons neben dem Text.
- Acquire: the last remaining "Copy data to clipboard" text button is now
  an icon button like the others.
  / Acquire: Der letzte verbliebene Text-Button "Copy data to clipboard"
  ist jetzt wie die anderen ein Icon-Button.

## [Acquire 1.0.4] - [Visualize 1.0.4] - 2026-09-28

### Fixed / Behoben
- Fixed incomplete/corrupted download during updates (atomic file
  replacement with SHA256 verification).
  / Unvollständiger/korrupter Download beim Update behoben (atomarer
  Dateiaustausch mit SHA256-Prüfung).
- The UI now correctly locks while an update is being applied.
  / UI-Sperre während eines laufenden Updates funktioniert jetzt korrekt.
- Line breaks in update notes now render reliably.
  / Zeilenumbrüche in den Update-Notizen werden zuverlässig dargestellt.

### Added / Neu
- The updater can now update itself when needed.
  / Der Updater kann sich jetzt bei Bedarf selbst aktualisieren.

<!--
Always add new entries at the TOP, format:
Neue Einträge immer OBEN einfügen, Format:

## [App version] - YYYY-MM-DD
### Added / Changed / Fixed / Removed
- English line.
  / Deutsche Zeile.
-->
