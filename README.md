# Dem Zufall auf der Spur

## Einstieg: Münzwurf
Welcome! Platziere den Block ``||basic:zeige Text||`` in die Klammer von ``||basic:beim Start||``um deinen Namen zu scrollen.
Eine Behauptung: Wenn man einen Münze oft genug wirft, dann erhält man etwa gleich viele Kopf und Zahlwürfe. 
![enter image description here](https://microbit.eeducation.at/images/thumb/1/11/Kopf_zahl.jpg/300px-Kopf_zahl.jpg)
Testet man das in der Realität durch Münzenwerfen, so erhält man bei 10 Würfen Ergebnisse, wie etwa 6:4, 7:3 oder gar 5:5 - aber auch 9:1 ist möglich. Also ist man von der Behauptung "gleicher  Kopf und Zahlwürfen" weit entfernt. Vielleicht müsste man aber 1000 mal werfen, aber das ist zu zeitaufwendig.

## Versuch: Münzwurf mit Computer
Micro:bit kann ja Zahlen darstellen - und das Würfeln könnte der  Zufallsgenerator durchführen. (Siehe Menü Mathematik ). Mit Zufallszahl 0 nehmen wir die Kopfseite der Münze und mit Zufallszahl 1 nehmen wir Zahlseite.
```blocks
	input.onButtonPressed(Button.A, function () {
		basic.showNumber(randint(0, 1))
	})
```
 - Du kannst mit dieser Funktion mit dem Computer "eine Münze" werfen 
 - Versuche 20mal zu werfen - notiere die Ergebnisse

### Anzahl der Würfe erhöhen auf 100
100mal die A-Taste zu drücken ist zuviel Aufwand - wir verwenden eine Schleife
```blocks
	input.onButtonPressed(Button.A, function () {
		for (let index = 0; index < 100; index++) {
			basic.showNumber(randint(0, 1))
		}
	})
```
### Probleme und Verbesserung
 - Es dauert sehr lange, diesen Versuch zu beobachten und mitzuzählen
 - Es muss nun der Computer die Zählung übernehme - wir wollen den Versuche dann ja auch auf 10 000 Durchgänge ausbauen

## Arbeit mit Variablen
 - Nun verwenden wir eine Variable, wo die Ergebnisse gezählt werden
 - Wir nennen die eine Variable mit dem Namen **Kopf**
 - Wir addieren bei der Zufallszahl **0** immer die Variable Kopf um eines hoch
 - Wir wählen nun bereits 1000 Durchläufe
```blocks
	let kopf = 0
	input.onButtonPressed(Button.A, function () {
		kopf = 0
		for (let index = 0; index < 1000; index++) {
			if (randint(0, 1) == 0) {
				kopf += 1
			}
		}
		basic.showNumber(kopf)
	})
```
 - Am Ende der Schleife wird die Zahl der **Kopfwürfe** angezeigt
 - Die Anzahl der **Zahlwürfe** kann man dann erreichnen
## Test und Verbesserung
 - Nun soll das Programm sofort nach dem Start aufrufen und gleich 1000 Versuche durchführen
 - Am Schluss soll mit **Taste A** die Zahl der Anzahl der Kopfwürfe darstellen, die **Taste B** sollte die Würfe mit dem Ergebnis **Zahl** darstellen.




```blocks
	input.onButtonPressed(Button.A, function () {
	    basic.showNumber(kopf)
	})
	input.onButtonPressed(Button.B, function () {
	    basic.showNumber(anzahl - kopf)
	})
	let kopf = 0
	let anzahl = 0
	anzahl = 10000
	kopf = 0
	for (let index = 0; index < anzahl; index++) {
	    if (randint(0, 1) == 0) {
	        kopf += 1
	    }
	}
	basic.showString("Fertig")
```
 - Am Ende der Schleife wird das Wort **Fertig** angezeigt
## Ergebnis des Versuches
 - Verändere die Zahl **anzahl** auf höhere Werte, etwa 100 000
 - Wir stellen fest: Je höher die **Anzahl** ist, umso näher rücken die Ergebnissen von **Kopf** und **Zahl** zusammen.

> Written with [StackEdit](https://stackedit.io/).




> Diese Seite bei [https://dlpl-mb.github.io/zufall_test/](https://dlpl-mb.github.io/zufall_test/) öffnen

## Als Erweiterung verwenden

Dieses Repository kann als **Erweiterung** in MakeCode hinzugefügt werden.

* öffne [https://makecode.microbit.org/](https://makecode.microbit.org/)
* klicke auf **Neues Projekt**
* klicke auf **Erweiterungen** unter dem Zahnrad-Menü
* nach **https://github.com/dlpl-mb/zufall_test** suchen und importieren

## Dieses Projekt bearbeiten ![Build Status Abzeichen](https://github.com/dlpl-mb/zufall_test/workflows/MakeCode/badge.svg)

Um dieses Repository in MakeCode zu bearbeiten.

* öffne [https://makecode.microbit.org/](https://makecode.microbit.org/)
* klicke auf **Importieren** und dann auf **Importiere URL**
* füge **https://github.com/dlpl-mb/zufall_test** ein und klicke auf Importieren

## Blockvorschau

Dieses Bild zeigt den Blockcode vom letzten Commit im Master an.
Die Aktualisierung dieses Bildes kann einige Minuten dauern.

![Eine gerenderte Ansicht der Blöcke](https://github.com/dlpl-mb/zufall_test/raw/master/.github/makecode/blocks.png)

#### Metadaten (verwendet für Suche, Rendering)

* for PXT/microbit
<script src="https://makecode.com/gh-pages-embed.js"></script><script>makeCodeRender("{{ site.makecode.home_url }}", "{{ site.github.owner_name }}/{{ site.github.repository_name }}");</script>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTE2Mzc5NjA0MywyMDY0NDY2MjQyLDc3MD
U0MTk4M119
-->