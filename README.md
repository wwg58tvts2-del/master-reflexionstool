# KI-DMS Reflexionstool

## Zweck des Tools

Dieses Tool dient der strukturierten Reflexion und strategischen Einordnung von KI-Funktionalitäten im Dokumentenmanagementsystem (DMS) für Hochschulen (HS). 

Es unterstützt Entscheidungs- und Digitalisierungsverantwortliche dabei,

- eigene Prioritäten bei der KI-Einführung festzulegen,
- diese mit empirisch erhobenen Vergleichswerten abzugleichen,
- strategische Betriebsmodelle (On-Premises vs. Cloud) einzuordnen,
- und die eigene Position bewusst zu reflektieren.

Das Tool ersetzt keine formalen Entscheidungsprozesse, sondern dient als vorgelagerte, strukturierte Reflexionshilfe.

---

## Funktionsumfang

### 1. Bewertung von KI-Funktionalitäten
Nutzer:innen bewerten den erwarteten Nutzen einzelner KI-Funktionen für ihre Hochschule auf einer Skala.  
Die Bewertung erfolgt zunächst ohne Anzeige der Vergleichswerte, um kognitive Verzerrungen (z. B. Ankereffekt) zu vermeiden.

### 2. Drag & Drop Priorisierung
Funktionen, Chancen und Hemmnisse können per Drag & Drop in eine individuelle Wunschreihenfolge gebracht werden.  
Die Rangfolge ergibt sich somit aus der tatsächlichen Einschätzung der Nutzer:innen.

### 3. Benchmark-Vergleich
Nach Abschluss der eigenen Bewertung können die Eingaben mit folgenden Vergleichswerten abgeglichen werden:

- Median der Gesamtstichprobe  
- Median differenziert nach Rollenprofil (Technik / Organisation)

Abweichungen werden nicht als Defizit interpretiert, sondern als mögliche strategische Schwerpunktsetzung.

### 4. Info-Tooltips
Zu jeder Funktion existiert ein Info-Icon (ⓘ), das beim Hover oder Klick:

- eine kurze fachliche Beschreibung
- ein praxisnahes Beispiel

anzeigt.  
Dies dient der begrifflichen Präzisierung und Vergleichbarkeit der Bewertungen.

### 5. Weitere KI-Wünsche
Anzeige zusätzlicher Freitextnennungen aus der Befragung, um Innovationspotenziale sichtbar zu machen.

### 6. Reset- und Vergleichsfunktionen
- „Vergleichen“-Button zur Anzeige der Benchmark-Daten
- „Alles zurücksetzen“-Button zur vollständigen Löschung aller Eingaben

---

## Technische Umsetzung

- HTML5
- CSS (Bootstrap 5)
- JavaScript (jQuery)
- Bootstrap-Tooltips
- Drag & Drop (SortableJS oder native Implementierung)

### Architekturprinzip

- Reine Client-Side-Anwendung
- Keine Backend-Anbindung
- Keine Datenspeicherung
- Keine Serverkommunikation
- Keine externen APIs

Alle Daten (Funktionen, Benchmarks, Beschreibungen, Beispiele) sind statisch als JavaScript-Objekte im Code hinterlegt.

---

## Datenmodell

Die zentralen Datenstrukturen befinden sich im JavaScript-Code:

- `funktionItems`
- `chancenItems`
- `hemmnisseItems`
- `benchmarkData`

Jedes Funktionsobjekt enthält:

- id
- label
- description
- example
- medianGesamt
- medianTechnik
- medianOrganisation

---

## Aufbau der Benutzeroberfläche

### Tabs
1. Funktionalitäten
2. Betrieb (On-Premises vs. Cloud)
3. Weitere KI-Funktionen

### Interaktionselemente
- Radio-Buttons (Skalenbewertung)
- Drag & Drop Listen
- Vergleichsgruppen-Auswahl
- Tooltips
- Reset-Button

### Responsives Design
Das Layout basiert auf Bootstrap 5 und ist für Desktop- und Tablet-Nutzung optimiert.

---

## Methodische Einordnung

Das Tool basiert auf einer empirischen Expertenbefragung.  
Die dargestellten Medianwerte sind deskriptive Vergleichswerte und stellen keine normativen Empfehlungen dar.

Zur Minimierung kognitiver Verzerrungen gilt:

- Eigene Bewertung erfolgt vor Anzeige der Benchmarks
- Vergleichsdaten erscheinen erst nach aktiver Auswahl
- Rangfolgen werden nicht vorgegeben, sondern aus Eingaben berechnet

---

## Nutzung

1. Datei lokal im Browser öffnen.
2. Eigene Einschätzungen abgeben.
3. Funktionen priorisieren.
4. Vergleichsgruppe auswählen.
5. „Vergleichen“ klicken.
6. Ergebnisse reflektieren.

Es ist keine Installation erforderlich.

---

## Anpassung und Erweiterung

Neue Funktionen oder Benchmarks können ergänzt werden, indem im JavaScript-Array:

- neue Objekte hinzugefügt werden
- description- und example-Felder ergänzt werden
- Medianwerte erweitert oder angepasst werden

Das visuelle Design kann im `<style>`-Block im `<head>` angepasst werden.

---

## Limitationen

- Keine persistente Speicherung
- Keine Exportfunktion
- Keine Mehrbenutzerfähigkeit
- Keine automatische Aktualisierung der Benchmark-Daten

Das Tool ist als Reflexionsinstrument konzipiert, nicht als operative Entscheidungssoftware.

---

## Lizenz / Nutzungshinweis

Das Tool wurde im Rahmen einer wissenschaftlichen Masterarbeit entwickelt und dient ausschließlich Forschungs- und Reflexionszwecken.

Eine produktive Nutzung sollte vorab rechtlich und organisatorisch geprüft werden.
