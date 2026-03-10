# LLM Instructions – Local Markdown Docset Indexer & Query Engine (Offline)

Diese Datei definiert alles, was ein LLM benötigt, um dieses Projekt vollständig selbständig umzusetzen:
- Input/Output-Protokoll
- Modul- und Agenten-Logik
- Regelwerk
- Hardware-Constraints
- How-To-Use

---

## 1. Ziel

Erstelle ein System, das einen Satz von Markdown-Dateien einliest, einen einfachen Index aufbaut
und Queries über diesen Index beantwortet — vollständig offline.

---

## 2. Hardware Constraints

Dieses Projekt muss vollständig auf normaler Consumer-Hardware lauffähig sein:

- CPU-only
- keine GPU-Abhängigkeiten
- keine Modelle > 1 GB
- keine externen APIs oder Cloud-Dienste
- alles offline
- Python-Standardbibliothek

---

## 3. Modul-Spezifikationen

### 3.1 Loader (/src/loader.py)

Signatur: load(files: list[str]) -> list[dict]

Aufgabe:
- Markdown-Dateien von Pfaden einlesen

Rückgabeformat:
- docs: Liste von Objekten:
  - path: string
  - content: string

---

### 3.2 Indexer (/src/indexer.py)

Signatur: build_index(docs: list[dict]) -> dict

Aufgabe:
- einfachen Index aufbauen
- z. B.:
  - pro Dokument:
    - Überschriften
    - Abschnitte
    - Vorkommen von Begriffen

Rückgabeformat:
- index: dict (strukturierte, aber einfache Form)

---

### 3.3 Query Engine (/src/query_engine.py)

Signatur: query(index: dict, term: str) -> list[dict]

Aufgabe:
- nach einem Begriff suchen
- Ergebnisse mit Kontext zurückgeben

Rückgabeformat:
- results: Liste von Objekten:
  - path: string
  - heading: string | null
  - snippet: string

---

### 3.4 Agent (/src/agent.py)

Signatur: run(files: list[str], term: str) -> dict

Aufgabe:
- orchestriert loader, indexer, query_engine

Rückgabeformat:
- index: dict
- results: list[dict]
- steps: list[str]

---

## 4. Orchestrator-Logik

1. docs = load(files)
2. index = build_index(docs)
3. results = query(index, term)
4. Ergebnis zurückgeben

---

## 5. Regelwerk / Constraints

### Loader
- liest Dateien als UTF-8
- ignoriert nicht vorhandene Dateien (oder meldet sie separat)

### Indexer
- erkennt Markdown-Überschriften (#, ##, ###)
- ordnet Textblöcke Überschriften zu
- speichert pro Abschnitt:
  - heading
  - body

### Query Engine
- einfache substring-Suche
- snippet ist ein kurzer Ausschnitt um den Treffer herum

---

## 6. Aufgaben an das LLM

Das LLM soll:

1. loader.py implementieren  
2. indexer.py implementieren  
3. query_engine.py implementieren  
4. agent.py implementieren  
5. architecture.md ergänzen  
6. Tests in /tests aktualisieren  

---

## 7. How-To-Use (für Code-Assistenten)

1. Öffne das Repository.  
2. Öffne `instructions.md`.  
3. Markiere den gesamten Inhalt.  
4. Sende ihn an deinen Code-Assistenten mit:

„Lies diese instructions.md vollständig. Implementiere dann alle beschriebenen Module und Dateien. Halte dich strikt an das Input/Output-Protokoll, das Regelwerk und die Hardware-Constraints. Beginne mit loader.py.“

Damit kann ein LLM das Projekt vollständig autonom umsetzen.
