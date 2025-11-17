# Grundlagen für OOP in Python

Dieses Skript fasst alle wichtigen Grundlagen für OOP zusammen.

------------------------------------------------------------------------

## 1. Klassen und Objekte

In Python werden Klassen mit dem Schlüsselwort `class` definiert.\
Ein Objekt ist eine Instanz dieser Klasse.
Eine Klasse ist eine Schablone, Bauplan oder Vorlage für Objekte. Eine Instanz (auch: Objekt) ist ein konkretes Exemplar der Klasse.
Sie entsteht, wenn die Klasse aufgerufen wird.

``` python
class Person:
    pass

p = Person()  # Objektinstanz
```

------------------------------------------------------------------------

## 2. Konstruktor (`__init__`)

Der Konstruktor wird automatisch ausgeführt, wenn ein Objekt erzeugt
wird.

``` python
class Person:
    def __init__(self, name, age):
        self.name = name      # Instanzattribute
        self.age = age
```

Was ist self?
- self ist ein Verweis auf das aktuelle Objekt (die Instanz), auf dem eine Methode aufgerufen wird.

- Jede Instanzmethode muss self als ersten Parameter haben.

- Es erlaubt der Methode, auf die Attribute und andere Methoden derselben Instanz zuzugreifen.

------------------------------------------------------------------------

## 3. Instanzattribute

Attribute, die zu einem bestimmten Objekt gehören.\
Man greift über `self.attribut` darauf zu.

``` python
self.name = name
```

------------------------------------------------------------------------

## 4. Methoden

Methoden sind Funktionen innerhalb einer Klasse.\
Sie haben immer mindestens einen Parameter: `self`.

``` python
class Person:
    def greet(self):
        print("Hallo!")
```

------------------------------------------------------------------------

## 5. Standardwerte im Konstruktor

Konstruktoren können Default-Werte enthalten.

``` python
class Animal:
    def __init__(self, species="unknown"):
        self.species = species
```

------------------------------------------------------------------------

## 6. Vererbung

Eine Klasse kann Eigenschaften einer anderen Klasse übernehmen.

``` python
class Vehicle:
    def describe(self):
        print("Ich bin ein Fahrzeug.")

class Car(Vehicle):   # erbt von Vehicle
    pass
```

------------------------------------------------------------------------

## 7. Methoden überschreiben

Eine erbende Klasse kann Methoden neu definieren.

``` python
class Car(Vehicle):
    def describe(self):
        print("Ich bin ein Auto.")
```

------------------------------------------------------------------------

## 8. Private Attribute

Private Attribute beginnen mit `__` und können nur über Methoden
verändert werden.

``` python
class BankAccount:
    def __init__(self):
        self.__balance = 0

    def deposit(self, amount):
        self.__balance += amount
```

------------------------------------------------------------------------

## 9. Klassenattribute

Für alle Instanzen gleich.

``` python
class Robot:
    robot_count = 0   # Klassenattribut

    def __init__(self):
        Robot.robot_count += 1
```

------------------------------------------------------------------------

## 10. Statische Methoden

Methoden ohne Zugriff auf die Instanz (`self`).

``` python
class MathTools:
    @staticmethod
    def add(a, b):
        return a + b
```

------------------------------------------------------------------------

## 11. Arbeiten mit Listen voller Objekte

Objekte können wie andere Daten in Listen gespeichert werden.

``` python
students = [Student("Anna"), Student("Ben")]
for s in students:
    print(s.name)
```

------------------------------------------------------------------------

## 12. Zusammenfassung

Diese Grundlagen decken alles ab, was für die Übungen nötig ist:

-   Klassen definieren\
-   Objekte erzeugen\
-   Konstruktoren\
-   Attribute und Methoden\
-   Vererbung und Überschreiben\
-   Klassenattribute\
-   Statische Methoden\
-   Zugriffskontrolle (private Attribute)


