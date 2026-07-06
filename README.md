# Untangle

Ein minimalistisches Untangle-Puzzlespiel für Browser und Touch-Geräte – von mindmatters.

Ziel des Spiels ist es, ein Netz aus Knoten und Kanten so zu entwirren, dass sich keine zwei Linien mehr kreuzen. Sich überschneidende Kanten sind rot, überschneidungsfreie grün.

## Spielen

Es gibt keinen Build-Schritt und keine Abhängigkeiten. Die `index.html` einfach im Browser öffnen:

```bash
open index.html
```

Alternativ über einen lokalen Server, z. B.:

```bash
python3 -m http.server
```

und dann `http://localhost:8000` aufrufen.

## Steuerung

- **Knoten ziehen** – Knoten anklicken bzw. antippen und verschieben.
- **Mehrfachauswahl** – am Desktop mit gedrückter `Shift`-Taste mehrere Knoten wählen, auf Touch-Geräten per langem Druck (Long Press) in den Auswahlmodus wechseln. Ausgewählte Knoten lassen sich gemeinsam verschieben.
- **Zoomen und Verschieben** – am Desktop `Strg` + Mausrad zum Zoomen, Mausrad/Trackpad zum Verschieben; auf Touch-Geräten Pinch-Geste mit zwei Fingern.
- **Zahlen** – die Zahl in jedem Knoten zeigt seinen Grad (Anzahl der Kanten).

## Menü

Über das Menü oben rechts:

- **Schwierigkeit** – von Leicht (8 Knoten) bis Apokalypse (100 Knoten).
- **Neues Spiel** – erzeugt ein neues Rätsel.
- **Auflösen** – animiert die Lösung.

### Schwierigkeitsstufen

| Stufe        | Knoten |
| ------------ | ------ |
| Leicht       | 8      |
| Schwer       | 14     |
| Experte      | 20     |
| Meister      | 28     |
| Großmeister  | 38     |
| Legende      | 50     |
| Wahnsinn     | 70     |
| Apokalypse   | 100    |

## Technik

Reines HTML, CSS und JavaScript in einer einzigen Datei, gerendert auf einem `<canvas>`. Jedes Rätsel wird als planarer Graph erzeugt: Knoten werden zufällig platziert, kreuzungsfrei verbunden und anschließend verwürfelt – so ist stets eine überschneidungsfreie Lösung garantiert.
