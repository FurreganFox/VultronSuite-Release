# Vultron Suite – User Guide / Benutzerhandbuch

Valid for version **1.0.7** / Gültig für Version **1.0.7**

- [English](#english)
- [Deutsch](#deutsch)

---

## English

**Vultron Acquire** logs voltage/current from an Ivium potentiostat on the measurement
computer (via IviumSoft), runs method queues and shows the results.
**Vultron Visualize** processes the measurement data of a test rig into Excel/TXT files and,
for raw-data rigs, an interactive HTML dashboard. Both need a personal **license key** from
whoever manages the licenses.

### Installation and updates

1. Download `Vultron_Suite_Setup_<version>.exe` from [Releases](../../../releases) and run it.
   No administrator rights are needed. Choose Acquire, Visualize or both.
2. On first start the program asks for your license key (once).
3. Both programs check for new versions at startup and regularly in the background. When one is
   available, a notice appears; **Install now** downloads it and restarts the program. The UI is
   locked while updating, so do not update in the middle of a measurement.
4. Click the version text in the footer to see the version pop-up (close with a second click or `Esc`).

### Vultron Acquire

**Requirements:** IviumSoft is running and the device is connected. While Acquire is connected
(power button), IviumSoft itself has no normal device access.

**Setup page**

| Field | Meaning |
|---|---|
| Current_Voltage folder | Required. Logs are written as `Current_Voltage-YYYY-MM-DD.csv` (Timestamp, Voltage[mV], Current[mA], Event). |
| DataServer root folder (optional) | IviumSoft's DataServer folder. Needed for batch/impedance results in the Results Panel. |
| Methods root folder (optional) | Default folder for the Method Queue's file picker. |
| License key / Licensed to | Enter and save the key; shows who the license is issued to. |
| Log rate | Sampling rate in Hz (2–50, default 10). |

Click **Start**. If the license check fails you stay on the Setup page and can fix the key.

**Main window**

- **Power button** – checks IviumSoft and starts logging; click again to stop.
- **Record button** – starts/stops a separate *Current-Voltage Monitoring* recording (only active
  while logging runs); the result appears in the Results Panel.
- **Method Queue...** – opens the queue window. The **play button** next to it runs/aborts the saved queue.
- The indicator on the right shows what is running (e.g. "Queue active – Step X/Y").
- Chart: drag to zoom, right-click to reset. **Window** sets the time window, **Auto-scroll** follows
  new data, **Jump to** goes to an earlier queue step, the gear opens **Graph options**.
- **Results Panel** shows impedance spectra and polarization curves; the **Step** menu reaches earlier results.

**Method Queue**

- Add `.imf` method files with **Add step...** or drag them from Explorer into the window.
- **Edit step...**, **Remove step**, **Move up/down**, **Save queue...**, **Load queue...**,
  **Set auto-save folder for all...**.
- The play button runs/aborts the queue, the skip button skips the current step.
- Toggle **Skip the settle wait between steps** to remove the pause (about 20 s) between steps.

Step editor options: method file, label (used in file names and result titles), OCP equilibration (s),
timeout (s), *Skip the settle wait before this step*, *Also show a pop-up when this step finishes*,
and *Enable auto-save for this step* (saves `.idf`/`.csv`; new `.idf` files carry their real name, e.g. `700 °C.idf`).

### Vultron Visualize

1. Choose a **Test Rig**.
2. Click **Run Checks** (configuration check). File selection and start unlock afterwards.
3. **Browse…**: select the experiment folder (raw-data rigs) or the report file `.txt` (other rigs).
4. Set **Output Formats**: *Generate Excel File*, *Export as Text File*, and for raw-data rigs
   *Visualize Data in Chart* (interactive HTML). At least Excel or TXT stays enabled.
5. Click **Confirm & Start**. The processing window shows progress and ends with **Done** or **Failed**
   (errors are listed in the *Errors* section). **Restart** begins a new run, **Exit** closes the program.

The two icon buttons on the start page open the **Config Builder** (most important `config.txt` values)
and the **Test Rig Editor** (edit/create test rig entries). In the HTML dashboard, automatically
detected events can be renamed, removed or added; every change is recorded in a tamper-evident log.

### Notifications (since 1.0.7)

A Windows notification card appears (bottom right) when:

| Event | Notification | Extra pop-up |
|---|---|---|
| Acquire: queue step finished | yes | only if enabled for that step |
| Acquire: whole queue finished / aborted | yes | always |
| Acquire: queue ends with an error | yes | yes |
| Visualize: analysis finished (or with errors) | yes | no |
| License problems | yes | existing license notices only |

If no card appears, check Windows notification settings (including Focus/Do not disturb).

### Troubleshooting

| Problem | What to do |
|---|---|
| License check fails at start | Check internet connection and key, click **Start** again. |
| "License Server Unreachable" during a measurement | Logging keeps running and the program retries automatically; use **Retry Now** once the connection is back. |
| IviumSoft crash notice | Restart IviumSoft, then click the power button again. |
| No result in the Results Panel | Is the DataServer folder set? Aborted or skipped steps produce no result. |
| Visualize start is locked | Run **Run Checks** and select a test rig first. |

Logs: `%LOCALAPPDATA%\Vultron\Acquire\Logs` and `%LOCALAPPDATA%\Vultron\Visualize\Logs`.
Please report bugs via [Issues](../../../issues) and attach the relevant log lines.

---

## Deutsch

**Vultron Acquire** loggt am Messrechner Spannung/Strom eines Ivium-Potentiostaten (über IviumSoft),
fährt Method-Queues und zeigt die Ergebnisse. **Vultron Visualize** verarbeitet die Messdaten eines
Test Rigs zu Excel/TXT-Dateien und bei Raw-Data-Rigs zu einem interaktiven HTML-Dashboard. Beide
benötigen einen persönlichen **Lizenzschlüssel** von der Person, die die Lizenzen verwaltet.

### Installation und Updates

1. `Vultron_Suite_Setup_<Version>.exe` aus den [Releases](../../../releases) laden und starten.
   Administratorrechte sind nicht nötig. Acquire, Visualize oder beides auswählen.
2. Beim ersten Start wird einmalig der Lizenzschlüssel abgefragt.
3. Beide Programme prüfen beim Start und regelmäßig im Hintergrund auf neue Versionen. Ist eine
   verfügbar, erscheint ein Hinweis; **Install now** lädt sie und startet neu. Die Oberfläche ist
   während des Updates gesperrt – nicht mitten in einer Messung aktualisieren.
4. Klick auf die Versionsangabe in der Fußzeile öffnet das Versions-Pop-up (Schließen: erneuter
   Klick oder `Esc`).

### Vultron Acquire

**Voraussetzung:** IviumSoft läuft und das Gerät ist verbunden. Solange Acquire per Power-Button
verbunden ist, hat IviumSoft selbst keinen normalen Gerätezugriff.

**Setup-Seite**

| Feld | Bedeutung |
|---|---|
| Current_Voltage folder | Pflicht. Logs entstehen als `Current_Voltage-JJJJ-MM-TT.csv` (Timestamp, Voltage[mV], Current[mA], Event). |
| DataServer root folder (optional) | IviumSoft-DataServer-Ordner. Nötig für Batch-/Impedanz-Ergebnisse im Results Panel. |
| Methods root folder (optional) | Standardordner für die Dateiauswahl der Method Queue. |
| License key / Licensed to | Schlüssel eintragen und speichern; zeigt, auf wen die Lizenz ausgestellt ist. |
| Log rate | Abtastrate in Hz (2–50, Standard 10). |

Mit **Start** geht es weiter. Schlägt die Lizenzprüfung fehl, bleibst du auf der Setup-Seite und
kannst den Schlüssel korrigieren.

**Hauptfenster**

- **Power-Button** – prüft IviumSoft und startet das Logging; erneuter Klick stoppt.
- **Aufnahme-Button** – startet/stoppt eine separate *Current-Voltage Monitoring*-Aufnahme (nur
  aktiv, solange das Logging läuft); das Ergebnis erscheint im Results Panel.
- **Method Queue...** – öffnet das Queue-Fenster. Der **Play-Button** daneben startet/bricht die
  gespeicherte Queue ab.
- Der Indikator rechts zeigt, was gerade läuft (z. B. „Queue active – Step X/Y“).
- Diagramm: Aufziehen zoomt, Rechtsklick setzt zurück. **Window** wählt das Zeitfenster,
  **Auto-scroll** folgt neuen Daten, **Jump to** springt zu einem früheren Queue-Schritt, das
  Zahnrad öffnet die **Graph options**.
- **Results Panel** zeigt Impedanzspektren und Polarisationskurven; über das **Step**-Menü sind
  frühere Ergebnisse erreichbar.

**Method Queue**

- `.imf`-Methoden mit **Add step...** hinzufügen oder aus dem Explorer ins Fenster ziehen.
- **Edit step...**, **Remove step**, **Move up/down**, **Save queue...**, **Load queue...**,
  **Set auto-save folder for all...**.
- Der Play-Button startet/bricht die Queue ab, der Skip-Button überspringt den laufenden Schritt.
- Schalter **Skip the settle wait between steps** entfernt die Pause (ca. 20 s) zwischen den Schritten.

Optionen im Schritt-Editor: Methodendatei, Label (für Dateinamen und Ergebnistitel), OCP
equilibration (s), Timeout (s), *Skip the settle wait before this step*, *Also show a pop-up when
this step finishes* und *Enable auto-save for this step* (speichert `.idf`/`.csv`; neue
`.idf`-Dateien tragen den echten Namen, z. B. `700 °C.idf`).

### Vultron Visualize

1. **Test Rig** wählen.
2. **Run Checks** klicken (Konfigurationsprüfung). Danach werden Dateiauswahl und Start freigeschaltet.
3. **Browse…**: Experiment-Ordner (Raw-Data-Rigs) oder Report-Datei `.txt` (übrige Rigs) auswählen.
4. **Output Formats** festlegen: *Generate Excel File*, *Export as Text File* und bei Raw-Data-Rigs
   *Visualize Data in Chart* (interaktives HTML). Mindestens Excel oder TXT bleibt aktiv.
5. **Confirm & Start** klicken. Das Verarbeitungsfenster zeigt den Fortschritt und endet mit **Done**
   oder **Failed** (Fehler stehen im Bereich *Errors*). **Restart** startet neu, **Exit** beendet.

Die zwei Icon-Buttons auf der Startseite öffnen den **Config Builder** (wichtigste `config.txt`-Werte)
und den **Test Rig Editor** (Rig-Einträge bearbeiten/anlegen). Im HTML-Dashboard lassen sich
automatisch erkannte Ereignisse umbenennen, entfernen oder ergänzen; jede Änderung wird
manipulationssicher protokolliert.

### Benachrichtigungen (seit 1.0.7)

Unten rechts erscheint eine Windows-Benachrichtigungskarte bei:

| Ereignis | Benachrichtigung | Zusätzliches Pop-up |
|---|---|---|
| Acquire: Queue-Schritt fertig | ja | nur wenn für den Schritt aktiviert |
| Acquire: ganze Queue fertig / abgebrochen | ja | immer |
| Acquire: Queue endet mit Fehler | ja | ja |
| Visualize: Analyse fertig (oder mit Fehlern) | ja | nein |
| Lizenzprobleme | ja | nur die bereits vorhandenen Lizenzhinweise |

Erscheint keine Karte, die Windows-Benachrichtigungseinstellungen prüfen (auch Fokus/Nicht stören).

### Häufige Probleme

| Problem | Lösung |
|---|---|
| Lizenzprüfung scheitert beim Start | Internetverbindung und Schlüssel prüfen, erneut **Start** klicken. |
| „License Server Unreachable“ während der Messung | Das Logging läuft weiter und das Programm versucht es automatisch erneut; nach Wiederherstellung der Verbindung **Retry Now**. |
| IviumSoft-Absturzhinweis | IviumSoft neu starten, dann den Power-Button erneut klicken. |
| Kein Ergebnis im Results Panel | DataServer-Ordner gesetzt? Abgebrochene oder übersprungene Schritte erzeugen kein Ergebnis. |
| Visualize-Start gesperrt | Zuerst **Run Checks** ausführen und ein Test Rig wählen. |

Logs: `%LOCALAPPDATA%\Vultron\Acquire\Logs` und `%LOCALAPPDATA%\Vultron\Visualize\Logs`.
Bugs bitte über [Issues](../../../issues) melden und die relevanten Logzeilen anhängen.
