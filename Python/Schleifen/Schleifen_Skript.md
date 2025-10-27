# Grundlagen zu Schleifen in Python

Schleifen sind ein zentrales Konzept in der Programmierung.  
Sie ermöglichen es, Anweisungen **mehrfach automatisch auszuführen**, ohne den Code zu wiederholen.  
In Python gibt es zwei Haupttypen von Schleifen: **for-Schleifen** und **while-Schleifen**.

---

## 1. for-Schleifen

Eine `for`-Schleife wird verwendet, wenn man **eine bestimmte Anzahl von Durchläufen** kennt oder eine Folge von Werten durchlaufen möchte.

Beispiel:

```python
for i in range(5):
    print(i)
```
**Ausgabe:**
```
0
1
2
3
4
```

### Erklärung:

- `range(5)` erzeugt die Zahlen 0, 1, 2, 3 und 4.  
- `i` ist die Laufvariable, die nacheinander jeden dieser Werte annimmt.  
- Der eingerückte Code unter `for` wird bei jedem Durchlauf ausgeführt.

---

### Wichtige Varianten von range()

| Ausdruck | Beschreibung | Erzeugte Werte |
|-----------|---------------|----------------|
| `range(5)` | von 0 bis 4 | 0, 1, 2, 3, 4 |
| `range(1, 6)` | von 1 bis 5 | 1, 2, 3, 4, 5 |
| `range(0, 10, 2)` | mit Schrittweite 2 | 0, 2, 4, 6, 8 |
| `range(10, 0, -1)` | rückwärts | 10, 9, 8, 7, 6, 5, 4, 3, 2, 1 |

---

### Beispiel: Summe berechnen

```python
summe = 0
for i in range(1, 11):
    summe += i
print("Summe:", summe)
```
**Ergebnis:** `Summe: 55`

---

### Beispiel: Quadratzahlen

```python
for i in range(1, 6):
    print(i, "hoch 2 =", i ** 2)
```

---

## 2. while-Schleifen

Eine `while`-Schleife wird verwendet, wenn man **nicht genau weiß, wie oft** ein Codeblock wiederholt werden soll.  
Sie läuft so lange, wie eine Bedingung **wahr (True)** ist.

Beispiel:

```python
i = 1
while i <= 5:
    print(i)
    i += 1
```
**Ausgabe:**
```
1
2
3
4
5
```

### Erklärung:

- Die Schleife prüft vor jedem Durchlauf die Bedingung `i <= 5`.  
- Wenn die Bedingung nicht mehr erfüllt ist, wird die Schleife beendet.  
- Wichtig: Die Variable `i` muss innerhalb der Schleife verändert werden, sonst entsteht eine **Endlosschleife**.

---

## 3. Steuerung von Schleifen

Python bietet zwei Schlüsselwörter, um Schleifen gezielt zu steuern:

### a) `break` – Schleife abbrechen

```python
for i in range(1, 10):
    if i == 5:
        break
    print(i)
```
**Ergebnis:** Die Schleife stoppt bei 5.

---

### b) `continue` – Durchlauf überspringen

```python
for i in range(1, 10):
    if i == 5:
        continue
    print(i)
```
**Ergebnis:** Die Zahl 5 wird ausgelassen.

---

## 4. Verschachtelte Schleifen

Man kann Schleifen ineinander verschachteln, um z. B. Tabellen oder Muster zu erzeugen.

Beispiel:

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(i, j)
```
**Ausgabe:**
```
1 1
1 2
1 3
2 1
2 2
2 3
3 1
3 2
3 3
```

---

## 5. Mathematische Anwendungen

Schleifen eignen sich besonders für mathematische Aufgaben wie:

### Summe:
```python
summe = 0
for i in range(1, 11):
    summe += i
print(summe)
```

### Produkt (Fakultät):
```python
fakultaet = 1
for i in range(1, 6):
    fakultaet *= i
print(fakultaet)
```

### Potenzen:
```python
basis = 2
for exp in range(1, 6):
    print(basis, "hoch", exp, "=", basis ** exp)
```

---

## 6. while vs. for

| Merkmal | for-Schleife        | while-Schleife                     |
|----------|---------------------|------------------------------------|
| Anzahl der Durchläufe bekannt | ja                  | nein                               |
| Endbedingung flexibel | (break)             | ja                                 |
| Gefahr von Endlosschleifen | gering              | hoch                               |
| Typische Anwendung | Zählen, Iterationen | Benutzereingaben, unklare Abbrüche |

---

## 7. Typische Fehler

1. **Endlosschleife:** Bedingung wird nie falsch.  
2. **Variable nicht verändert:** Kein Fortschritt in der Schleife.  
3. **Einrückungsfehler:** Codeblock nicht korrekt eingerückt.  
4. **range() falsch verwendet:** Grenzen oder Schritte vertauscht.

---

## 8. Zusammenfassung

- `for`-Schleifen: Wiederholungen mit bekannter Durchlaufzahl  
- `while`-Schleifen: Wiederholungen mit Bedingung  
- `break`: Schleife beenden  
- `continue`: aktuellen Durchlauf überspringen  
- Schleifen sind die Basis für viele Programmieraufgaben wie Zählen, Rechnen und Strukturieren von Ausgaben.

---
