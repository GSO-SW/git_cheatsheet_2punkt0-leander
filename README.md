# gitStarted Zusammenfassung
In diesem Repo soll zusammengefasst werden, was man für die Arbeit mit git und gitHub kennen sollte.
- In [diesem cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) finden Sie Hinweise, wie man .md-Dateien formatiert.
- Mit diesen [Generator](https://www.tablesgenerator.com/markdown_tables) können Sie Tabellen für Markdown erzeugen

:dart: Ziele:
1. Die Arbeit soll nicht im Browser stattfinden. Clonen Sie das Repo und arbeiten Sie lokal.
1. Hier gehts um Teamwork: Ich erwarte häufige Commits (+ häufiges pushen/pullen )

## TODO
- Begriffe definieren und erklären (z.B. repository, branch etc.)
- git Befehle für die Arbeit mit lokalen Repositories (inkl. Erläuterungen)
- git Befehle für die Arbeit mit entfernten Repositories (inkl. Erläuterungen)

## TODO2
- Fachbegriffe OOP erklären (mit Beispielen)
  - abstract (Klassen)
  - abstract (Methoden)
  - virtual
  - override
  - Polymorphie
- Wie überschreibt man die Methode `virtual string ToString()`?


## Was ist eine Repository?
 - Eine `Repository` ist ein Haufen von Dateien, sozusagen ein Projekt

## Was ist ein Branch?
 - Ein `Branch` ist ein Arbeitsbereich. Mit branches kann man verschiedene Aufgabenbereiche einteilen, wie zum Beispiel
   Verwaltung von Daten, Überarbeitung von Skripten oder Design

## Was ist die Staging area/der Index?
 - Die `Staging area` oder der `Index` ist der Bereich, in dem Geänderte Dateien liegen, bevor sie zum Origin gepusht werden.
   Dateien gelangen dort hin, indem man sie committed

## Was ist der Origin?
 - Der `Origin` (eng. Herkunft) ist das Gesamtergebnis, das aus allen Branches der Repository entsteht.
   Der Branch `master` hat immer den Zugriff auf den `Origin`

## Was ist der Working Tree?
 - Der `Working Tree` ist der Bereich, in dem gearbeitet wird. Wenn man dateien ändert, kann man sie mit dem `git add`-Befehl
   aus dem `Working Tree` zur `Staging area` hinzufügen

## Git Befehle für die Arbeit mit lokalen Repositorys
 - `git commit`: Dieser Befehl wird auch für entfernte Repos verwendet. Damit fasst man alle Änderungen zusammen, und fügt sie zur `staging area` hinzu
 - `git init`: Mit diesem Befehl initialisiert man eine neue Repository im aktuellen Verzeichnis
 - `git branch`: Ruft alle branches ab, die in der aktuellen Repo enthalten sind
 - `git add`: Mit diesem Befehl fügt man geänderte dateien aus dem Working-Tree zum Index hinzu
 - `git log`: Zeigt alle vergangenen commits im aktuellen branch an
 - `git checkout`: Verlässt den aktuellen branch

## Git Befehle für die Arbeit mit entfernten Repositorys
 - `git fetch`: Sucht nach allen Änderungen im Origin und zeigt diese an. Aktualisiert also alle Informationen zum Origin
 - `git push`: Fügt alle commits vom aktuellen branch zur Repo des aktuellen branches hinzu
 - `git pull`: Nimmt alle Änderungen im Origin und schreibt diese in die Repo im aktuellen branch

## Was macht der `abstract`-Modifizierer für Klassen in C#?
 - Der `abstract`-Modifizierer verbietet Instanziierungen der Klasse, erlaubt im Gegenzug aber andere member der Klasse mit `abstract` zu modifizieren
 - Ab .NET 7 und C# 11 ist der `abstract`-Modifizierer auch mit dem `static`-Modifizierer vereinbar
 - Der `abstract`-Modifizierer ist nicht in versiegelten Klassen zulässig

   Beispiel: Klasse Mensch ist abtrakt. Es gibt viele arten von Menschen, daher sollte die Art von Mensch als Kinder-Klasse genauer
             definiert sein. Member, welche Informationen über den jeweiligen Menschen zurückgeben, sollte abstrakt sein, da diese Infos
             von Mensch zu Mensch unterschiedlich sein können.

## Was macht der `abtstract`-Modifizierer für Klassen-Member in C#?
 - Ein member, welches als `abstract` markiert ist, darf keine Implementierung enthalten.
   Diese member müssen jedoch bei jeder Vererbung ersten Grades eine Implementierung via `override` erhalten

## Was macht der `virtual`-Modifizierer in C#?
 - Der `virtual`-Modifizierer erlaubt neue Implementierung via `override` in Vererbungen aus alles Graden
 - Der `virtual`-Modifizierer ist nicht in versiegelten Klassen zulässig

## Was macht der `override`-Modifizierer in C#?
 - Der `override`-Modifizierer erstellt einen Member als neue Implementierung eines Member der Übergeordneten Klasse mit dem selben Namen
 - Falls der neu zu Implementierende Member nicht über die Modifizierer `virtual` oder `abstract` verfügt, ist die Überschreibung unzulässig.
   In solchen Fällen, ist der Member mit dem `new`-Modifizierer zu Implementieren, um den selben Effekt zu erzielen

## Was bedeutet Polymorphismus in C#?
 - `Polymorphismus` bedeutet übersetzt, dass eine Sache mehrere Formen annehmen kann.
 - In der objektorientierten Programmierung bedeutet es, dass man Objekte von verschiedenen Typen unter einem Übergeordneten Typen zusammenfassen kann
   Beispiel: Alle Klassen in C# erben automatisch von dem Typen `System.Object`. So kann man ein Array erstellen, welches Objekte vom Typen
             `System.Object` enthält. In diesem Array dürfen sich nun Objekte von jedem Typen befinden, welche vom Typen `System.Object` erben,
             beispielsweise also `System.String`, `System.Int32` oder `System.Diagnostics.Stopwatch`. Auch wenn der Typ `System.Int32` zwar zusätzlich
             von `System.ValueType` erbt, erbt er übergeordnet dazu von `System.Object`, ist also auch möglich, als `System.Object` zu behandeln