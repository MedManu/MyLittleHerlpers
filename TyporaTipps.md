#Typora_Tipps_u_Tricks

#Überschriften haben am Anfang  #
Je mehr ### desto kleiner Überschriften
## Noch eine Überschrift nur kleiner
### Und eine nach kleiner
+ Blume + /  switched zischen Quellcodemodus u Anzeigemodus

+ Unter Hilfe- Install and Use Pandoc --> kann Pandoc installiert werden um Dokumente in epub dateien zu verwnadeln

+ Absatz hervorheben:  Bereich Makieren - Darstellung - Fokusmodus

+ Unter Themen lass sich design einstellungen machen

<Header>Hier steht der Header</Header>
<body>Das ist der Body
<h1>Hier sollte eine Überschrift sein</h1>
</body>



##Listen:
+ Listen können mit einer +,* oder - vor dem Zeichanfang angegeben werden, sind aber ungeordnet

1. mit 1. kann dann eine geordnete Liste starten
2. und wird automatisch mit 2. fortgesetzt

- [ ] Eine Taskliste kann mit - [ ] erzeugt werden
- [ ] Wichtig hier ist das Leerzeichen zwischen den einzelneen Zeichen nicht zu vergessen

##Codeblöcke

+ Werden mit ``` am anfang und am Ende gekennzeichenet
+ ```und 2x return öffnet einen Codeblock
  3 x ```(shigt + ´´´) dannach Enter odewr Leertaste um Codeblock zu öffnen
  ```

```

```





## Mathematikblöcke

Nach Eingabe `$$`und Drücken der Eingabetaste wird ein Eingabefeld geöffnet, das die *Tex / LaTex-* Quelle akzeptiert . Es folgt ein Beispiel:


$$
\ mathbf {V} _1 \ times \ mathbf {V} _2 = \ begin {vmatrix}
\ mathbf {i} & \ mathbf {j} & \ mathbf {k} \
\ frac {\ partial X} {\ partiell u} & \ frac {\ partiell Y} {\ partiell u} & 0 \
\ frac {\ partiell X} {\ partiell v} & \ frac {\ partiell Y} {\ partiell v} & 0 \
\ end {vmatrix}
$$

## Tabellen:

+ Durch Eingabe | First Header || Second Header |und Drücken der returnTaste wird eine Tabelle mit zwei Spalten erstellt.

+ Wenn Sie sich nach dem Erstellen der Tabelle auf diese Tabelle konzentrieren, wird eine Symbolleiste für die Tabelle geöffnet, in der Sie die Größe der Tabelle ändern, sie ausrichten oder sie löschen können. Sie können das Kontextmenü auch zum Kopieren und Hinzufügen / Löschen von Spalten / Zeilen verwenden.

| FirstHeader |      | Second Header |
| ----------- | ---- | ------------- |
|  Das ist die erste Spalte|      |Und das die Zweite|
||||

+ Sie können auch Inline-Markdowns wie Links, Fett, Kursiv oder Durchgestrichen einfügen.

+Schließlich können Sie durch Einfügen von Doppelpunkten in der Kopfzeile festlegen, dass der Text linksbündig, rechtsbündig oder zentriert ausgerichtet werden soll:

| Linksbündig | Mitte ausgerichtet | Rechtsbündig |
| :-------- |: ---------------: | -----: |
| Spalte 3 ist | etwas wortreicher text 1600 USD |
| Spalte 2 ist | zentriert | $ 12 |
| Zebrastreifen | sind ordentlich $ 1 |

+ Ein Doppelpunkt ganz links zeigt eine links ausgerichtete Spalte an. Ein Doppelpunkt ganz rechts kennzeichnet eine rechtsbündige Spalte. Ein Doppelpunkt auf beiden Seiten kennzeichnet eine mittig ausgerichtete Spalte.

##Fußnoten

+ werden mit []

# Heighlight

- == Wort ==
- 

### Im Text Referenzen:

[Headers](https://support.typora.io/Markdown-Reference/#headers)