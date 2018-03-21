# Diplomarbeit Mechatronik Vorlage LaTeX

## Installation

### Windows

+ Miktex Download: https://miktex.org/download
+ Texmaker Download: http://www.xm1math.net/texmaker/download.html

### Ubuntu

+ Miktex Installation
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys D6BC243565B2087BC3F897C9277A7293F59E4889
echo "deb http://miktex.org/download/ubuntu xenial universe" | sudo tee /etc/apt/sources.list.d/miktex.list
sudo apt update
```
```
sudo apt install miktex
```

Schritte auf dieser Website befolgen um Installation abzuschließen: https://miktex.org/howto/install-miktex-unx

+ Texmaker Installation:
```
sudo apt install texmaker 
```

### Generell

1. Miktex updaten
2. Texmaker starten und _main.tex_ übersetzen (alle Pakete installieren lassen)
  + Mehrmals übersetzen
  + Wennn nach 3, 4 Durchgängen immer noch ein Fehler ist, Meldung anschauen (oft hilft Miktex noch einmal nach updates checken)
3. _opening.tex_ anpassen
4. Diplomarbeiten aufteilen in eigene _*.tex_ Files
  + Mit `\include{name}` (ohne Dateiendung) wird das File inkludiert
  + Wenn mehrere am selben Dokument arbeiten sollte man nur sein eigenes File inkludieren, sonst dauert das Bauen ewig und das Geeschriebene ist oft weit hinten im Dokument.

### Dateien

+ __main.tex__: Hauptfile mit Präambel (eng: preamble) - Übersetzen nur in diesem File. `\begin{document}` `\end{document}` sind in dieser Datei - Zone die den kompletten Inhalt enthält. Titel wird hier erzeugt und die anderen _*.tex_ Files werden hier eingebunden. 
+ __opening.tex__: Einleitung der Diplomarbeit (Danksagung, Eidestattliche Erklärung, ...)
+ __appendix.tex__: Anhänge
+ __listings.tex__: Codestyles

### Zitierung
Setup:
+ Im Texmaker: Optionen --> Texmaker konfigurieren --> Reiter: Befehle, bei Bib(la)tex: _biber %_ eingeben
+ Danach: Schnell Übersetzen - BibTeX - Schnell Übersetzen (2x)

Zietieren mit `\cite{buchname}` oder als Fußnote: `\footfullcite{buchname}`

Bücher einfügen in der Datei _Literaturverzeichnis.bib_ (Buchtypen: https://en.wikibooks.org/wiki/LaTeX/Bibliography_Management)

### Akronyme

Abkürzungsverzeichnis in der _appendix.tex_.
In der Zone acronym (\begin{acronym}...\begin{acronym}) werden die Abkürzungen definiert.

```
\begin{acronym}
	%Abkürzung hinzufügen: \acro{Kürzel}{Ausgeschrieben}
	\acro{WLAN}{Wireless Local Area Network}
	\acro{WWW}{World Wide Web}
	\acro{uC}[µC]{Mikrocontroller}
\end{acronym}
```

Abkürzungen im Text: `\ac{kürzel}`
