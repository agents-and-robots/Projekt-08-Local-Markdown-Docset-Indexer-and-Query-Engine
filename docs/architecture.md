# Architektur – Local Markdown Docset Indexer & Query Engine

## Module

- loader.py – lädt Markdown-Dateien
- indexer.py – baut Index aus Überschriften und Abschnitten
- query_engine.py – führt Suchanfragen aus
- agent.py – orchestriert den Prozess

## Datenfluss

1. Loader liest Dateien ein
2. Indexer baut Index
3. Query Engine beantwortet Queries
4. Agent orchestriert alles
