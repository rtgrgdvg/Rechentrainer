# 🧮 Rechentrainer

> Intelligenter Mathematik-Trainer für Schüler — Grundrechenarten interaktiv üben

---

## 🎯 Was kann Rechentrainer?

Rechentrainer ist ein browserbasiertes Lernprogramm für Schüler zum Üben der vier Grundrechenarten. Es läuft komplett im Browser — keine Installation, keine App, keine Anmeldung.

---

## ➕ Aufgabentypen

Rechentrainer unterstützt **12 Aufgabentypen** in vier Rechenarten. Bei jedem Typ wird eine andere Stelle durch `?` ersetzt — so wird nicht nur das Ergebnis, sondern auch das Umkehrdenken geübt:

| Rechenart | Typ 1 | Typ 2 | Typ 3 |
|---|---|---|---|
| **Addition** | `a + b = ?` | `a + ? = c` | `? + b = c` |
| **Subtraktion** | `a - b = ?` | `a - ? = c` | `? - b = c` |
| **Multiplikation** | `a × b = ?` | `a × ? = c` | `? × b = c` |
| **Division** | `a ÷ b = ?` | `a ÷ ? = c` | `? ÷ b = c` |

Alle Divisionsaufgaben liefern immer **natürliche Zahlen** als Ergebnis.

---

## ⚙️ Konfiguration

### Zahlenbereich
Pro Aufgabentyp kann eingestellt werden:
- **von/bis** — zufällige Zahlen im Bereich (z.B. 1–20)
- **Zahlen-Set** — nur bestimmte Zahlen verwenden (z.B. `1,2,5,10`)

### Zahlen-Sets nach Lernstrategie
Statt alle Zahlen gleichzeitig zu üben, können Sets schrittweise erweitert werden:

| Stufe | b-Set | Beschreibung |
|---|---|---|
| Stufe 1 | `1, 2, 5, 10` | Einfacher Einstieg |
| Stufe 2 | `1, 2, 3, 4, 5, 10` | Erweiterung |
| Stufe 3 | `1, 2, 3, 4, 5, 6, 7, 8, 9, 10` | Vollständig |

### Aufgabentypen aktivieren/deaktivieren
Jeder der 12 Aufgabentypen kann einzeln per Häkchen aktiviert oder deaktiviert werden.

### Einstellungen ausblenden
Ein Häkchen **„Einstellungen anzeigen"** blendet die gesamte Konfigurationstabelle aus — so sieht der Schüler nur die Aufgabe und das Eingabefeld.

---

## 🧠 Intelligentes Lernsystem

### 🔁 Spaced Repetition
- Aufgabentypen die der Schüler **falsch** beantwortet, kommen **öfter**
- Aufgabentypen die **richtig** beantwortet werden, kommen **seltener**
- Das Gewicht pro Aufgabentyp wird automatisch angepasst

### 📝 Fehlerkatalog
- Jede **konkret falsch gelöste Aufgabe** (z.B. `7 × 8 = ?`) wird gespeichert
- Nach 3–5 neuen Aufgaben kommt dieselbe Aufgabe mit `⟳` markiert wieder
- Erst nach **2× richtig in Folge** gilt die Aufgabe als gemeistert
- Die falsche Eingabe des Schülers wird ebenfalls gespeichert (z.B. `7 × 8 = ? / 54`)

Beide Lernoptionen können unabhängig voneinander ein- und ausgeschaltet werden.

---

## 📊 Dashboard

Das Dashboard gibt einen vollständigen Überblick über den Lernstand:

### Fortschrittsbalken
- Pro Aufgabentyp ein Balken
- Zeigt: Abdeckung (wie viele Kombinationen wurden geübt?) und Trefferquote (% richtig)
- Farbe: 🟢 >80% · 🟡 50–80% · 🔴 <50%
- Bei aktiviertem Spaced Repetition: aktuelles Gewicht sichtbar

### Aufgaben-Heatmap
- Jede mögliche Kombination (z.B. alle `a × b`) als farbiges Kästchen
- 🔲 Grau = noch nie gestellt
- 🟩 Grün = nur richtig beantwortet
- 🟥 Rot = nur falsch beantwortet
- 🟨 Gelb = gemischt (mal richtig, mal falsch)
- Hover über eine Zelle zeigt die genaue Statistik

### Fehlerkatalog-Liste
- Alle offenen Fehleraufgaben mit falscher Eingabe des Schülers
- Gemeisterte Aufgaben werden separat angezeigt

---

## 🗣️ Sprachsteuerung

*(Verfügbar in Chrome und Edge bei HTTPS)*

### 🔊 Aufgabe vorlesen (Text-to-Speech)
- Jede Aufgabe wird automatisch auf Deutsch vorgelesen
- Symbole werden natürlich gesprochen: `+` → „plus", `-` → „minus", `×` → „mal", `÷` → „geteilt durch"
- Nach der Auswertung hört der Schüler „Richtig!" oder die korrekte Antwort

### 🎤 Antwort sprechen (Speech-to-Text)
- Mikrofon-Button neben dem Eingabefeld
- Der Schüler spricht die Antwort — Zahlen und Zahlwörter werden erkannt
- Beispiel: „acht" → 8, „zwanzig" → 20

---

## 🔔 Akustisches Feedback

- **Falsche Antwort** → kurzer Piepton (zwei absteigende Töne)
- **Falsch** → nächste Aufgabe nach 800ms (schnell weiter)
- **Richtig** → nächste Aufgabe nach 1500ms (kurze Pause)

---

## 👤 Schülerverwaltung

### Schülername
Ein einfaches Namensfeld identifiziert den Schüler — keine Anmeldung nötig.

### Konfiguration speichern/laden
- 💾 **Speichern** → `RK-Conf-NAME.json` — enthält den kompletten Lernstand
- 📂 **Laden** → stellt alles wieder her: Einstellungen, Fehlerkatalog, Heatmap-Daten, SR-Gewichte

**Was wird gespeichert:**
| Inhalt | Beschreibung |
|---|---|
| Aufgabentypen | Welche aktiv sind |
| Zahlenbereiche & Sets | Alle Konfigurationen |
| Lernoptionen | Spaced Repetition, Fehlerkatalog |
| SR-Gewichte | Häufigkeit pro Aufgabentyp |
| Fehlerkatalog | Offene und gemeisterte Fehleraufgaben |
| Aufgaben-Statistik | Basis für Heatmap und Fortschrittsbalken |

### Protokoll (Log)
- 📋 **Log speichern** → `RK-Log-NAME.csv` — alle gelösten Aufgaben mit Datum und Uhrzeit
- Neue Sessions werden an die bestehende Datei **angehängt**
- Format: CSV (Semikolon-getrennt) — direkt in Excel öffenbar

**CSV-Spalten:**
`Datum · Uhrzeit · Schüler · Aufgabe · Erwartet · Eingabe · Richtig`

---

## 🖥️ Ergebnisanzeige

- Alle Aufgaben der aktuellen Session in einer Tabelle
- ✅ Richtige Antworten in heller Schrift
- ❌ Falsche Antworten in roter Schrift
- Zusammenfassung: Gesamt / Richtig / Falsch
- CSV-Download direkt aus dem Ergebnisfenster

---

## 🔒 Datenschutz

Alle Daten bleiben **lokal auf dem Gerät des Schülers**:
- Keine Anmeldung, kein Benutzerkonto
- Keine Daten werden an Server übertragen
- Konfiguration und Log-Dateien liegen beim Schüler
- *(Ausnahme: Spracherkennung nutzt Cloud-Dienste des Browsers)*

---

## 🌐 Technische Voraussetzungen

| Funktion | Anforderung |
|---|---|
| Grundfunktion | Jeder moderne Browser |
| Sprachausgabe | Chrome, Edge, Safari |
| Spracheingabe | Chrome oder Edge, HTTPS erforderlich |
| Offline-Betrieb | Vollständig möglich (ohne Spracheingabe) |

---

## 📁 Dateien

| Datei | Beschreibung |
|---|---|
| `index.html` | Die komplette Anwendung |
| `README.md` | Diese Dokumentation |
| `.nojekyll` | GitHub Pages Konfiguration |

---

## 🚀 Starten

**Online (GitHub Pages):**
👉 `https://DEIN-NAME.github.io/rechentrainer`

**Lokal:**
```bash
python3 -m http.server 8080
# dann: http://localhost:8080
```
