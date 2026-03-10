# Test: Indexer

## Natürliche Sprache
Der Indexer soll Überschriften erkennen und Abschnitte zuordnen.

## Maschinenlesbare Struktur
input:
  docs:
    - path: "docs/example.md"
      content: "# Title\nSome text."

expected:
  has_heading: "Title"
