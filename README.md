# fom-latex-master-renew
FOM LaTex Master Renew (2017)

Im Rahmen meiner Master-Thesis habe ich mich recht umfassend mit LaTex auseinandergesetzt. Andreas Grundwald (https://github.com/andygrunwald/FOM-LaTeX-Template) hat mir mit seinem Template sehr gut geholfen, allerdings habe ich das Template abgeändert, sodass die neuen Anforderungen der FOM (Stand: Dezember 2016) an wissenschaftliche Arbeiten berücksichtigt wurden.

Diese Version einer Vorlage basiert somit ausschließlich auf das Template von Andreas Grundwald. 

# Schreib-Umgebung
Für die Bearbeitung der Thesis habe ich neben TexStudio (https://www.texstudio.org/) ebenfalls Citavi (https://www.citavi.com/de/index.html) verwendet. Hierzu habe ich den Export des Literatur-Verzeichnisses verwendet, um automatisiert die Quellen bei der Generierung der PDF-Datei zu berücksichtigen.
Bei der Einrichtung eines Exports sind folgende wichtige Hinweise zu berücksichtigen:
- Sonderzeichen in der Quellenangabe können zu Fehler führen. Es empfiehlt sich die exportierte Datei auf Sonderzeichen zu prüfen und in der Literatur-Verwaltung anschließend zu ändern.
- Die Felder müssen einheitlich mit dem gleichen Inhaltstyp genutzt werden. Dies ist für den Export sehr wichtig!
- Die Dokumenten-Art ist ebenfalls sehr wichtig, da LaTex bei einigen Quellen einige Angaben nicht kennt.

## Besonderheit: Internetdokument
Die Anforderungen der FOM beinhalten, dass das Veröffentlichungsdatum und das eigene Zugriffsdatum anzugeben ist. Aufgrund der Besonderheit der FOM habe ich keine effiziente und zufriedenstellende Lösung gefunden. Hierzu nutzte ich das Feld Notiz  mit dem beispielhaften Inhalt "Zugriff 17-08-06 18:32 MEZ". 

## Besonderheit: Zuordnung der Dokumententypen
Ich habe folgende Dokumententypen folgendermaßen zugeordnet.
Beitrag in... (beliebig) = incollection
Beitrag in Tagungsband = inproceedings
Buch (Monographie) = book
Buch (Sammelwerk) = collection
Internetdokument = online
Interviewmaterial = misc
Zeitschriftenaufsatz = article
Zeitungsartikel = article

# Eigene Änderung der Vorlage
NAátürlich können eigene Änderungen vorgenommen werden, jedoch ist hier eine gewisse Struktur bereits vorhanden.

## Parameter der Titelseite
Die Parameter wie Titel, Standort, etc. können in der Datei 'skripte/meta.tex' angepasst werden.

## Akronyme
Die Acronyme sind in der 'thesis_main.tex' Datei einzufügen. Die Einträge sind aber der Zeile 296 anzupassen.

## Kapitel
Die Thesis besteht aus mehreren Kapitel, die jeweils in eigenen Datei im Ordner 'kapitel' gespeichert sind und aus der 'thesis_main.tex' verlinkt werden. Diese Verlinkung erfolgt ab Zeile 311.

## Literaturverzeichnis
Das Literaturverzeichnis wird automatisch aus der Datei 'literatur/literatur.bib' auf Basis der Zitate angepasst. Treten dort Fehler auf, empfiehlt sich die Tipps oben einmal zu prüfen. In der Datei 'skripte/modsBiblatex.tex' werden die Zitierkommandos und das Literaturverzeichnis definiert. Änderungen sollten lediglich dort und allgemeingültig vorgenommen werden.

## Zitation
Für das Zitieren sind die folgenden Zitierkommandos definiert worden.

```
\blogfootcite[Vgl. ][ ]{Singh.2013} = Internetquellen
\fullfootcite[Vgl. ][S. 7]{ITEMO.2017} = "normale" Literatur
\interviewcite[][S. 3]{Dollinger.05.05.2017} = Interview-Zitierung
```

## Tabellen und Bildbeschriftung
Für die Tabellen- und Bildbeschriftung habe ich die Vorgabe der FOM mit folgendem Befehl erfüllt:
```
\begin{table}[H]
	\caption{Berufliche Erfahrungen in den einzelnen Phasen}
	\begin{tabular}[ht]{|c|c|c|c|c|c|} \hline
		 \multicolumn{1}{|c|}{} & \multicolumn{1}{c|}{Service} & \multicolumn{1}{c|}{Service} & \multicolumn{1}{c|}{Service} & \multicolumn{1}{c|}{Service} & \multicolumn{1}{c|}{Continual} \\ 
		1 & Nein & Ja & Ja & Ja & Ja \\ \hline
		2 & Nein & Nein & Ja & Ja & Nein \\ \hline
		3 & Ja & Nein & Ja & Ja & Nein \\ \hline
		4 & Ja & Ja & Ja & Ja & Ja \\ \hline
		5 & Nein & Ja & Ja & Ja & Nein \\ \hline
		6 & Ja & Ja & Ja & Ja & Ja \\ \hline
	\end{tabular} \\
	
	\text{Quelle: Eigene Darstellung}
	\label{tbl:tabelle3}
\end{table}

```
Die Bildbeschriftung erfolgt anhand folgendem Aufbau:
```
\begin{figure}[H]
	\caption{Externe Sicht}
	\includegraphics[width=\textwidth, frame]{abbildungen/modellExtern.png}
	\label{abb:extern} 
	
	\text{Quelle: Eigene Abbildung}
\end{figure}
```
Die Abbildung werden hierbei in dem Ordner 'abbildungen/' gespeichert. Ich habe das Format von PNG-Dateien verwendet.



