Antworten Phase 4

Teil A

1. Bei push, bei pull_request auf main und bei workflow_dispatch, also wenn man ihn per Hand startet.

2. Auf ubuntu-latest. Den Rechner stellt GitHub bereit, der wird für jeden Lauf neu gestartet und danach wieder gelöscht.

3. Der Job heißt stack-test bzw. Compose-Stack testen (Port 8085) und hat 10 Steps.

4. Step 1 nutzt eine fertige Action (actions/checkout), die holt den Code. Die anderen Steps führen eigene Befehle mit run aus.

5. Nur contents: read, er darf also nur lesen. Wenn was schiefgeht oder jemand einen Step manipuliert, kann er so nicht viel kaputt machen.

6. In der Vorlage wird der Job übersprungen, weil da noch kein Stack drin ist und sonst alles rot wäre. In meinem Repo läuft er normal.

Teil B

7. a) Step 3, YAML-Syntax
   b) Step 7, Inhalt prüfen, weil die index.html fehlt
   c) Step 6, Erreichbarkeit, weil nginx im Container auf 80 lauscht und nicht auf 8080
   d) Step 2, die Compose-Datei wird nicht gefunden

8. Weil der Server auch antworten kann, wenn er die falsche Seite ausliefert, z. B. die Standardseite von Apache, wenn das Volume falsch eingebunden ist. Das merkt man nur, wenn man den Inhalt vergleicht.

9. Damit keine Container oder Netzwerke übrig bleiben. Bei eigenen Runnern, die wiederverwendet werden, würden die sonst Ports blockieren.

Teil C

10. Continuous Integration, weil jede Änderung automatisch getestet wird. Es wird aber nichts automatisch auf den Server ausgerollt, das mache ich selbst mit git pull.

11. Der Test läuft bei jeder Änderung von selbst und immer gleich, man kann ihn also nicht vergessen. Außerdem sieht jeder am Haken, ob es funktioniert, und Fehler fallen auf, bevor sie im Betrieb landen.
