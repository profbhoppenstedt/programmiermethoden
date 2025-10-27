# Funktionen in Python – Begleitskript zu den 20 Übungen

Dieses Skript erklärt die notwendigen Grundlagen zu **Funktionen in Python** und ergänzt die 20 Übungen.  
Es ist praxisnah aufgebaut und enthält kurze, testbare Codebeispiele.

---

## 1. Was ist eine Funktion?  _(zu Übung 1–4)_

Eine Funktion ist ein benannter, wiederverwendbarer Codeblock. Man definiert sie mit `def` und ruft sie über ihren Namen auf.

```python
def begruessung():
    print("Hallo, Welt!")

begruessung()
```

**Parameter** sind Platzhalter für Eingaben. **Argumente** sind die konkreten Werte beim Aufruf.

```python
def quadrat(x):
    return x * x

wert = quadrat(5)  # 25
```

---

## 2. Funktionen definieren und aufrufen  _(zu Übung 1–5)_

Grundform:
```python
def funktionsname(parameter1, parameter2):
    # Rumpf
    return ergebnis  # optional
```

- `return` gibt einen Wert zurück (ansonsten gibt die Funktion `None` zurück).
- Ohne `return` eignet sich eine Funktion für Ausgaben oder Nebenwirkungen (z. B. `print`, Dateizugriffe).

Beispiele zu den Übungen:
```python
def begruessung():
    print("Hallo, Welt!")            # Ü1

def begruesse(name):
    print(f"Hallo, {name}!")         # Ü2

def addiere(a, b):
    return a + b                      # Ü3

def quadrat(x):
    return x * x                      # Ü4

def ist_gerade(x):
    return x % 2 == 0                 # Ü5
```

---

## 3. Mehrere Parameter und einfache Logik  _(zu Übung 6–7, 11)_

```python
def maximum(a, b):                    # Ü6
    if a >= b:
        return a
    return b

def minimum(a, b, c):                 # Ü7
    m = a
    if b < m:
        m = b
    if c < m:
        m = c
    return m

def zeichen(x):                       # Ü11
    if x > 0:
        return "positiv"
    elif x < 0:
        return "negativ"
    else:
        return "null"
```

---

## 4. Rückgabewerte vs. Ausgaben  _(zu allen Übungen)_

- **Ausgabe** mit `print()` ist nur sichtbar auf der Konsole.
- **Rückgabewert** mit `return` kann weiterverarbeitet, getestet oder erneut verwendet werden.

Richtlinie: Für berechnende Funktionen bevorzugt **`return`** verwenden, für UI/Debug **`print`**.

---

## 5. Schleifen in Funktionen  _(zu Übung 8–10, 15, 17–20)_

Viele Aufgaben benötigen Schleifen innerhalb der Funktionen.

```python
def fakultaet(n):                     # Ü8
    ergebnis = 1
    for i in range(1, n + 1):
        ergebnis *= i
    return ergebnis

def summe_bis(n):                     # Ü9
    s = 0
    for i in range(1, n + 1):
        s += i
    return s

def potenz(basis, exponent):          # Ü10
    ergebnis = 1
    for _ in range(exponent):
        ergebnis *= basis
    return ergebnis

def reihe(n):                         # Ü15
    for i in range(1, n + 1):
        print(i)

def anzahl_gerade(n):                 # Ü17
    zaehler = 0
    for i in range(1, n + 1):
        if i % 2 == 0:
            zaehler += 1
    return zaehler

def anzahl_teiler(n):                 # Ü18
    count = 0
    for d in range(1, n + 1):
        if n % d == 0:
            count += 1
    return count

def ist_primzahl(n):                  # Ü19
    if n < 2:
        return False
    d = 2
    while d * d <= n:
        if n % d == 0:
            return False
        d += 1
    return True
```

---

## 6. Bedingungen in Funktionen  _(Querbezug zu mehreren Übungen)_

Kombiniere `if`/`elif`/`else` mit `return`, um klaren, **frühen Ausstieg** zu ermöglichen:

```python
def temperatur_kategorie(t):
    if t < 0:
        return "frostig"
    if t < 20:
        return "kuehl"
    return "warm"
```

---

## 7. Standardargumente und optionale Parameter

Mit Standardwerten lassen sich Funktionen flexibler gestalten:

```python
def potenz(basis, exponent=2):  # Standard: Quadrat
    ergebnis = 1
    for _ in range(exponent):
        ergebnis *= basis
    return ergebnis

# Aufrufe
potenz(5)      # 25
potenz(2, 10)  # 1024
```

**Hinweis:** Änderbare Datentypen (z. B. Listen) sollten **nicht** als Default verwendet werden. Für diese Aufgaben arbeiten wir nur mit Zahlen/Strings, daher unkritisch, aber die Regel ist gut zu kennen.

---

## 8. Mehrere Rückgabewerte (Tuple)

Eine Funktion kann mehrere Werte zurückgeben (als Tuple). Für die aktuellen Übungen selten nötig, aber nützlich zu wissen:

```python
def extremwerte(a, b, c):
    # Minimum und Maximum zurückgeben
    return minimum(a, b, c), maximum(a, b)

mn, mx = extremwerte(3, 7, 2)
```

---

## 9. Geltungsbereich (Scope) von Variablen

- **Lokal:** Variablen innerhalb einer Funktion gelten nur dort.
- **Global:** Variablen außerhalb sind global sichtbar, sollten aber **nicht** in Funktionen überschrieben werden, außer mit `global` (in der Praxis vermeiden).

```python
x = 10  # global

def foo():
    x = 5  # lokal (verdeckt das globale x)
    return x
```

---

## 10. Dokumentation und Typannotationen

### Docstrings

Beschreibe kurz Zweck, Parameter und Rückgabewert:

```python
def ist_gerade(x):
    """Gibt True zurück, wenn x gerade ist, sonst False.
    Parameter: x (int)
    Rückgabewert: bool
    """
    return x % 2 == 0
```

### Typannotationen (optional, aber hilfreich)

```python
def addiere(a: int, b: int) -> int:
    return a + b
```

Tools wie Linters/IDE können so Fehler früher erkennen.

---

## 11. Rekursion (optional)  _(Alternative zu Ü8/19)_

Manche Probleme lassen sich rekursiv lösen – eine Funktion ruft sich selbst auf.

```python
def fakultaet_rekursiv(n):
    if n <= 1:
        return 1
    return n * fakultaet_rekursiv(n - 1)
```

Für Primzahlen ist Iteration meist effizienter, aber Rekursion ist ein wichtiges Konzept.

---

## 12. Funktionen kombinieren  _(zu Ü16 und Ü20)_

Funktionen sind Bausteine, die man zusammensetzen kann.

```python
def addiere(a, b):
    return a + b

def doppelte_summe(a, b):  # Ü16
    return 2 * addiere(a, b)

def hauptprogramm():       # Ü20
    print("Beispiele:")
    print("Summe:", addiere(2, 3))
    print("Doppelte Summe:", doppelte_summe(2, 3))
    print("Fakultät 5:", fakultaet(5))
    print("Prim 29:", ist_primzahl(29))

# Optionaler Startpunkt:
if __name__ == "__main__":
    hauptprogramm()
```

---

## 13. Testen und Fehlersuche (kurz)

- Teste Funktionen mit **typischen**, **Rand-** und **Fehleingaben**.
- Nutze `assert` für einfache Tests:

```python
assert addiere(2, 3) == 5
assert ist_gerade(4) is True
assert ist_primzahl(1) is False
```

---

## 14. Checkliste zur Umsetzung der 20 Übungen

- [ ] Funktionen mit sinnvollen Namen definieren (`snake_case`).
- [ ] Parameter klar benennen, nur nötige Daten übergeben.
- [ ] Rückgabewerte statt reiner `print`-Ausgaben, wo Berechnungen gefordert sind.
- [ ] Schleifen, Bedingungen und Rückgaben klar strukturieren.
- [ ] Kurze Tests/Beispiele ergänzen.

---

### Mini-Referenz

- Definition: `def name(params): ...`
- Rückgabe: `return wert`
- Standardwerte: `def f(x=0): ...`
- Typen: `def f(x: int) -> bool: ...`
- Hilfe/Docstring: dreifache Anführungszeichen direkt unter `def`

---


