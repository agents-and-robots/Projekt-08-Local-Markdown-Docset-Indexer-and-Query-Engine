# Test: Agent

## Natürliche Sprache
Der Agent soll Index und Ergebnisse zurückgeben (Baseline: leer).

## Maschinenlesbare Struktur
input:
  files:
    - "docs/example.md"
  term: "test"

expected:
  index: {}
  results: []
