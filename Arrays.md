# Arrays

Aneinanderreihung von mehreren Werten im Speicher. Indexierbar durch ganzzahligen, null-basierten Index.

## Darstellung im Speicher

```java
int[] intArray = new int[4];
```

> Arraystellen 0 bis 3 werden mit dem Standardwert für `int` initialisert (0).

| Index | [0] | [1] | [2] | [3] |
|-------|-----|-----|-----|-----|
| Werte | 0   | 0   | 0   | 0   |

### Übung

Wie sehen die Werte nach der folgenden Transformation aus?

```java
intArray[1] = 7;
intArray[3] = 4;
intArray[0] = 1;
```

| Index | [0] | [1] | [2] | [3] |
|-------|-----|-----|-----|-----|
| Werte | ?   | ?   | ?   | ?   |

## Arrays sind Referenzparameter

### Übung

Folgende Überlegung, gegeben sind zwei Funktionen `main` und `g`. Bestimme das Ergebnis der Ausgabe am Ende von `main`.

> Falls du dir unsicher bist, recherchiere zuerst den Unterschied zwischen "Pass by value" und "Pass by reference".

```java
public static void main(String[] args) {
    int i = 0;
    boolean[] bools = new boolean[3];
    
    g(bools, i);
    g(bools, i);
    g(bools, i);
    
    System.out.println(bools[0]);
    System.out.println(bools[1]);
    System.out.println(bools[2]);
    System.out.println(i);
}

void g(boolean[] b, int index) {
    b[index] = true;
    index++;
}
```

## Mehrdimensionale Arrays

Arrays in Java haben immer einen Datentyp. Bekannte Datentypen sind zum Beispiel `int`, `boolean` oder `double`. Doch
mit der Einführung von Arrays haben wir auch einen neuen Datentyp `Array(Datentyp)` eingeführt.
Im rekursiven Sinne dieser Definition können wir also Arrays von Arrays erstellen.

> Es kann nie ein mehrdimensionales Array geben welches nur mit Arrays konstruiert wird. Das innerste Array muss daher
> immer ein Array von einem primitiven Datentyp oder von einem Objekt sein.<br/>
> `Array(Array(Array))` geht nicht.<br/>
> `Array(Array(int))` geht.<br/>
> `Array(Array(String))` geht.

Um ein mehrdimensionales Array zu erstellen, nutzen wir folgende Schreibweise:

```java
// Wichtig: Es müssen bereits Größen für alle Dimensionen angegeben werden!
int[][] array = new int[2][3];

// Zugriff auf Array:
array[0][1] = 4;
```

### Übung

TicTacToe!

1. Welche Dimension sollte unser TicTacToe Spielfeld haben?
2. Welcher Datentyp ergibt für ein TicTacToe Spielfeld Sinn?
3. Schreibe den Javacode um das Array für das Spielfeld zu erstellen und sinnvoll zu befüllen.
4. Schreibe den Code um ein `X` in die Mitte des Spielfelds zu setzen.
5. Schreibe den Code um ein `O` unten rechts auf das Spielfeld zu setzen.

