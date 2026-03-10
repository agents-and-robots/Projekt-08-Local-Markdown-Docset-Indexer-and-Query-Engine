# Local Markdown Docset Indexer & Query Engine (Offline, CPU-only)

Dieses Projekt indexiert lokale Markdown-Dateien und ermöglicht einfache Abfragen über den Inhalt.
Es arbeitet vollständig offline, benötigt keine GPU und verwendet keine KI-Modelle.

Funktionen:
- Markdown-Dateien einlesen
- Überschriften und Abschnitte extrahieren
- einfachen Index aufbauen
- Queries ausführen (z. B. nach Begriffen suchen)
- Ergebnisse mit Kontext zurückgeben

Das Projekt demonstriert:
- deterministische Textanalyse
- einfache Indexstrukturen
- Query-Handling
- Prompt-Driven Development (PDD)

## Projektstruktur

/src  
    loader.py  
    indexer.py  
    query_engine.py  
    agent.py  

/docs  
    architecture.md  

/tests  
    test_loader.md  
    test_indexer.md  
    test_query_engine.md  
    test_agent.md  

hardware-requirements.md  
instructions.md  
README.md  
credits.md

## Hardware Requirements

Dieses Projekt ist vollständig lokal ausführbar und benötigt keine spezielle Hardware.
Siehe `hardware-requirements.md`.

## Lizenz

MIT License.

## Credits

Siehe `credits.md`.
