# Grundlagen zu Listen in Python

Dieses Skript vermittelt die wichtigsten Grundlagen zu Listen in Python.

------------------------------------------------------------------------

## 1. Was ist eine Liste?

Eine Liste ist eine geordnete Sammlung von Elementen.\
Sie kann verschiedene Datentypen enthalten und ist veränderbar
(mutable).

``` python
fruits = ["Apfel", "Banane", "Kirsche"]
```

------------------------------------------------------------------------

## 2. Elemente hinzufügen

Mit `append()` wird ein Element am Listenende hinzugefügt.

``` python
fruits.append("Orange")
```

Mit `insert()` kann an einer bestimmten Position eingefügt werden:

``` python
fruits.insert(1, "Mango")
```

------------------------------------------------------------------------

## 3. Elemente entfernen

Ein bestimmtes Element löschen:

``` python
fruits.remove("Banane")
```

Das letzte Element löschen:

``` python
fruits.pop()
```

Ein Element an einer Position löschen:

``` python
fruits.pop(1)
```

------------------------------------------------------------------------

## 4. Länge einer Liste

Die Anzahl der Elemente:

``` python
len(fruits)
```

------------------------------------------------------------------------

## 5. Zugriff auf Elemente

Indexierung startet bei 0:

``` python
fruits[0]   # Erstes Element
fruits[-1]  # Letztes Element
```

------------------------------------------------------------------------

## 6. Listen durchlaufen

Die Elemente einer Liste lassen sich mit einer Schleife durchlaufen:

``` python
for fruit in fruits:
    print(fruit)
```

------------------------------------------------------------------------

## 7. Suchen in Listen

Mit dem Operator `in` prüfen, ob ein Element enthalten ist:

``` python
if "Apfel" in fruits:
    print("Apfel ist dabei!")
```

------------------------------------------------------------------------

## 8. Sortieren von Listen

Alphabetische Sortierung:

``` python
fruits.sort()
```

Umgekehrte Reihenfolge:

``` python
fruits.reverse()
```

------------------------------------------------------------------------

## 9. Liste kopieren

Eine echte Kopie erstellen:

``` python
copy_list = fruits.copy()
```

------------------------------------------------------------------------

## 10. Weitere nützliche Methoden

-   `count(x)` -- Anzahl eines Elements\
-   `index(x)` -- erste Position eines Elements\
-   `extend(list)` -- eine Liste erweitern

Beispiel:

``` python
numbers = [1, 2, 3]
numbers.extend([4, 5])
```

------------------------------------------------------------------------

## Zusammenfassung

Listen sind eines der wichtigsten und flexibelsten Datentypen in
Python.\
Sie erlauben:

-   Speichern mehrerer Werte\
-   Dynamische Veränderungen (hinzufügen, löschen)\
-   Sortieren und Durchsuchen\
-   Verwaltung beliebiger Datentypen


