# Zusammenfassung: Grundlagen zu Bedingungen in Python

Bedingungen ermöglichen es, Programme logisch zu steuern und auf unterschiedliche Situationen zu reagieren.  
In Python werden sie mit `if`, `elif` und `else` umgesetzt.

---

## Wichtige Konzepte

### 1. if-Anweisung
Eine `if`-Anweisung prüft, ob eine Bedingung **wahr (True)** ist.  
Wenn ja, wird der eingerückte Codeblock ausgeführt.

```python
x = 10
if x > 5:
    print("x ist größer als 5")
```

---

### 2. if – else
Mit `else` kann man eine Alternative angeben, wenn die Bedingung **nicht erfüllt** ist.

```python
x = 3
if x > 5:
    print("x ist größer als 5")
else:
    print("x ist kleiner oder gleich 5")
```

---

### 3. if – elif – else
Mehrere Bedingungen können mit `elif` kombiniert werden.

```python
temperatur = 20

if temperatur < 10:
    print("Es ist kalt.")
elif temperatur < 25:
    print("Es ist warm.")
else:
    print("Es ist heiß.")
```

---

### 4. Vergleichsoperatoren

| Operator | Bedeutung           | Beispiel | Ergebnis |
|-----------|--------------------|-----------|-----------|
| `==` | gleich | `5 == 5` | True |
| `!=` | ungleich | `5 != 3` | True |
| `>` | größer als | `7 > 4` | True |
| `<` | kleiner als | `2 < 8` | True |
| `>=` | größer oder gleich | `5 >= 5` | True |
| `<=` | kleiner oder gleich | `3 <= 7` | True |

---

### 5. Logische Operatoren

| Operator | Bedeutung | Beispiel | Ergebnis |
|-----------|------------|-----------|-----------|
| `and` | beide Bedingungen müssen wahr sein | `x > 0 and x < 10` | True |
| `or` | eine Bedingung reicht | `x < 0 or x > 100` | True |
| `not` | kehrt das Ergebnis um | `not(x > 5)` | True, wenn x ≤ 5 |

---

### 6. Bedingungen mit Texten

Strings können ebenfalls verglichen werden.

```python
name = input("Wie heißt du? ")
if name == "Anna":
    print("Willkommen zurück!")
else:
    print("Hallo,", name)
```

Groß- und Kleinschreibung lässt sich mit `.lower()` vereinheitlichen:

```python
farbe = input("Farbe: ").lower()
if farbe == "rot":
    print("Stopp!")
```

---

### 7. Typische Anwendungen

- Prüfen, ob eine Zahl positiv, negativ oder null ist  
- Vergleichen von Benutzereingaben (z. B. Passwörter)  
- Bewertung von Zahlen oder Texten  
- Kombination mehrerer Bedingungen mit `and`, `or`, `not`  
- Ausführung verschiedener Aktionen in Abhängigkeit vom Zustand

---

## Fazit

Bedingungen sind das Herzstück jeder Programm-Logik.  
Sie ermöglichen es, Programme dynamisch zu gestalten, Entscheidungen zu treffen und Abläufe zu steuern.

Wer die Verwendung von `if`, `elif`, `else` und logischen Operatoren beherrscht, kann interaktive und flexible Python-Programme schreiben.

---
