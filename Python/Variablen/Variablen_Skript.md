# Grundlagen zu Variablen in Python

Variablen gehören zu den grundlegendsten Konzepten jeder Programmiersprache. Sie dienen dazu, **Werte zu speichern**, auf die man im Verlauf eines Programms zugreifen, sie verändern oder weiterverarbeiten kann. In Python sind Variablen besonders leicht zu verwenden, da das Zuweisen von Werten sehr einfach ist und keine vorherige Typdefinition notwendig ist.

---

## Was ist eine Variable?

Eine Variable kann man sich als **benannten Speicherplatz** im Arbeitsspeicher vorstellen. Dieser Speicherplatz enthält einen Wert, auf den man über den **Variablennamen** zugreifen kann.  
Wenn man beispielsweise schreibt:

```python
name = "Anna"
```

dann bedeutet das: In der Variable `name` wird der Text (eine Zeichenkette, also ein *String*) `"Anna"` gespeichert.  
Über den Variablennamen `name` kann man diesen Wert jederzeit abrufen oder verändern.

---

## Variablennamen und Zuweisung

In Python werden Variablen **durch eine einfache Zuweisung** erstellt:

```python
x = 5
text = "Hallo Welt"
```

Der Operator `=` weist den Wert auf der rechten Seite der Variable auf der linken Seite zu.  
Dabei gilt: **Eine Variable entsteht automatisch, sobald ihr ein Wert zugewiesen wird.**  
Man spricht also nicht von einer „Deklaration“ wie in anderen Programmiersprachen (z. B. Java oder C), sondern von einer **dynamischen Zuweisung**.

Bei der Wahl von Variablennamen gelten bestimmte Regeln:

- Der Name darf **keine Leerzeichen** enthalten.  
- Er darf nur aus **Buchstaben, Zahlen und Unterstrichen (`_`)** bestehen.  
- Er darf **nicht mit einer Zahl beginnen**.  
- Groß- und Kleinschreibung wird unterschieden (`Name` ≠ `name`).  
- Python-Reservierte Wörter (z. B. `if`, `for`, `class`) dürfen nicht als Variablennamen verwendet werden.

Empfohlen ist die Schreibweise **snake_case**, also kleine Buchstaben mit Unterstrichen zwischen Wörtern, z. B. `benutzer_name` oder `alter_in_jahren`.

---

## Datentypen und dynamische Typisierung

Python ist **dynamisch typisiert**. Das bedeutet, dass man beim Erstellen einer Variable **nicht angeben muss**, welchen Datentyp sie hat – Python erkennt den Typ automatisch anhand des zugewiesenen Wertes:

```python
zahl = 10          # int (Ganzzahl)
preis = 19.99      # float (Kommazahl)
name = "Maria"     # str (Text)
ist_aktiv = True   # bool (Wahrheitswert)
```

Möchte man wissen, welchen Typ eine Variable aktuell hat, kann man die Funktion `type()` verwenden:

```python
print(type(name))     # <class 'str'>
print(type(preis))    # <class 'float'>
```

Eine Variable kann im Laufe des Programms sogar einen anderen Typ annehmen, da Python dies zur Laufzeit dynamisch verwaltet:

```python
x = 5
x = "jetzt ein Text"
```

Das ist bequem, erfordert aber auch **Sorgfalt**, um unerwartete Fehler zu vermeiden.

---

## Rechnen mit Variablen

Variablen können auch in Berechnungen verwendet werden. Python unterstützt die Grundrechenarten:

| Operator | Bedeutung         | Beispiel |
|-----------|------------------|-----------|
| `+`       | Addition          | `a + b` |
| `-`       | Subtraktion       | `a - b` |
| `*`       | Multiplikation    | `a * b` |
| `/`       | Division (float)  | `a / b` |
| `//`      | Ganzzahldivision  | `a // b` |
| `%`       | Rest (Modulo)     | `a % b` |
| `**`      | Potenzierung      | `a ** b` |

Beispiel:

```python
a = 10
b = 3
ergebnis = a % b
print(ergebnis)  # Ausgabe: 1
```

Man kann Variablen auch **schrittweise verändern**:

```python
punkte = 0
punkte += 10   # entspricht: punkte = punkte + 10
```

---

## Variablen in Ausgaben verwenden

Variablen können direkt in Ausgaben integriert werden.  
Der klassische Weg ist die Verwendung von `print()`:

```python
name = "Lukas"
alter = 25
print("Ich heiße", name, "und bin", alter, "Jahre alt.")
```

Noch eleganter ist die **f-String-Syntax**, die seit Python 3.6 verfügbar ist:

```python
print(f"Ich heiße {name} und bin {alter} Jahre alt.")
```

Python fügt hier automatisch den Inhalt der Variablen an den richtigen Platz im Text ein.

---

## Variablen und Benutzereingaben

Mit der Funktion `input()` kann der Benutzer zur Laufzeit Eingaben machen.  
Diese Eingaben werden immer als **Text (String)** gespeichert:

```python
name = input("Wie heißt du? ")
print(f"Hallo {name}!")
```

Wenn man Zahlen einlesen möchte, muss man den Datentyp umwandeln, z. B. mit `int()` oder `float()`:

```python
alter = int(input("Wie alt bist du? "))
print(f"In fünf Jahren bist du {alter + 5} Jahre alt.")
```

---

## Fazit

Variablen bilden das Fundament jedes Python-Programms.  
Sie ermöglichen es, Werte zu speichern, zu verändern und wiederzuverwenden.  
Das Verständnis für **Datentypen**, **Zuweisungen**, **Namenskonventionen** und **Eingaben** ist die Voraussetzung für das Arbeiten mit komplexeren Strukturen wie Listen, Funktionen oder Klassen.

Wer Variablen sicher beherrscht, hat den ersten wichtigen Schritt in der Python-Programmierung geschafft.
