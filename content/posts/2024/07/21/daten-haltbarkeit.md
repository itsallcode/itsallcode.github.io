---
title: "Datenhaltbarkeit"
slug: "data-durability"
date: "2024-07-21T14:01:46+02:00"
draft: false
author: "Sebastian"
lang: "de"
---

Wir leben in einer Wegwerfgesellschaft. Erstaunlicherweise gilt das auch für wichtige Daten.

Es gibt viele Wege, Daten zu verlieren:

1. Verlorene Datenträger
2. Keine Backups
3. Defekte Backups
4. Kein Platz mehr auf Datenträger
5. Krypto-Ransomware
6. Dateiformat wird nicht mehr unterstützt

Den letzten Punkt finde ich am peinlichsten. So viele Leute haben einen Großteil ihrer Dokumente in proprietären Datenformaten (z.B. Word-Dateien) angelegt und sind später überrascht, wenn man sie mit aktuellen Versionen der Software nicht oder nur noch fehlerhaft lesen kann.

## Warum Datenbanken für Langzeitspeicherung problematisch sind

Ich erinnere mich noch lebhaft daran, dass ich selbst die Lektion auf die harte Tour lernen musste. In der Zeit, als ich am aktivsten fotografiert habe, benutzte ich [Apple Aperture](https://en.wikipedia.org/wiki/Aperture_(software)) als mein Foto-Workflow-Management. Es war von der Bedienung her ein tolles Programm und hatte großartige Tutorials. Ich war schlau genug, alle Fotos im Raw-Format zu schießen und zu speichern. Aperture arbeitete verlustfrei, das heißt es speicherte alle Bearbeitungen als Anweisungen in einer Datenbank. Und die Datenbank ist, was mir zum Verhängnis wurde. Als Apple Aperture abkündigte — und damals ernsthaft meinte, man solle doch stattdessen Apple Photos verwenden — war mir klar, dass ich umsteigen musste auf eine professionelle und vor allem _haltbare_ Lösung.

Allerdings kam die Ernüchterung mit dem Export. Ich hatte nur die Wahl, entweder die Raw-Dateien zu exportieren, oder JPGs mit den Änderungen. Die Originale zu verlieren war für mich keine Option, also exportierte ich schweren Herzens die Raw-Dateien, die Änderungsaufträge allerdings behielt Aperture für sich.

Ich wechselte also auf Linux und [Darktable](https://www.darktable.org/). Erstens ist Darktable OpenSource, d.h. Abkündigen heißt nicht zwangsläufig, dass die Software verschwindet. Zweitens legt Darktable alles in Dateien ab. Auch die Änderungsanweisungen in sogenannten [Sidecar Files](https://docs.darktable.org/usermanual/4.0/en/overview/sidecar-files/sidecar/). D.h. selbst wenn Darktable aufhört zu existieren, sind die Änderungsanweisungen und ihre Spezifikation weiter verfügbar. Beste Voraussetzungen für ein langes glückliches Datenleben.

Aus dem gleichen Grund halte ich alle meine wichtigen Informationen auf meinem Rechner in Markdown Dateien. Ich bin mir sicher, dass ich die noch werde lesen können, wenn ich Großvater bin.

## Datenhaltbarkeit in Spezifikationen

Beim Design von [OpenFastTrace](https://github.com/itsallcode/openfasttrace) haben wir uns an der Philosophie der Internet RFCs orientiert. Der konsequente Einsatz simpler Textdateien bedeutet, dass die Daten nicht irgendwann zu Rauschen werden, nur weil niemand mehr einen Dekoder dafür pflegt. OFT unterstützt Markdown, reStructured Text und bald auch AsciiDoc. Alles Formate, die mit absolut jedem Texteditor gelesen und bearbeitet werden können.

## Die Cloud - 1001 Wege Daten zu verlieren

Für Menschen, die ihre Daten Cloud-Anbietern anvertrauen gibt es noch jede Menge zusätzliche Szenarien:

1. Cloud-Dienst bietet keine Exportmöglichkeit
2. Export verstümmelt die Daten
3. Abo läuft aus und die Daten wurden nicht rechtzeitig exportiert
4. Kein Backup (ja, auch Cloud-Anbieter verlieren Daten)
5. Datenkorruption beim Anbieter
6. Zugangsdaten verloren
7. Verschlüsselungspasswörter verloren

Man sollte sich immer ein paar Dinge bewusst machen, bevor man Daten in die Cloud schiebt. Cloud-Anbieter — wie die meisten Anbieter proprietärer Dienste — haben ein sehr großes Interesse daran, Kunden an sich zu binden. Im Englischen spricht man vom "vendor lock-in", also dem Eingesperrtsein bei einem bestimmten Anbieter. Aus kommerzieller Sicht ist das das Beste, das dem Anbieter gelingen kann. Sind die Kunden erst ausreichend abhängig, kann man die Preise drastisch erhöhen, die Qualität verschlechtern oder noch besser beides gleichzeitig!

Mittlerweile gibt es in der EU Gesetzgebung, die Anbieter dazu anhält, Exportmöglichkeiten anzubieten. Dem kommen die Cloud-Betreiber im besten Falle zögerlich im schlechtesten Falle gar nicht nach. Und dann ist da noch die Option der böswilligen Befolgung. Bei dieser perfiden Variante bauen die Betreiber etwas, das mit beiden Augen zugedrückt gerade noch als gesetzeskonform durchgehen mag, aber so umständlich, langsam, fehlerhaft und womöglich noch kostenpflichtig ist, dass es Kunden von einer Datenmigration  abschreckt.

Coulds operieren unter kommerziellen Zwängen, dazu gehört auch Sparzwang. Nur weil ein Cloud-Anbieter groß ist, heißt das nicht, dass er immer alle seine Prozesse im Griff hat. Wer das nicht glaubt, kann ja mal nach "cloud provider incidents" suchen. Aber Vorsicht! Das Ergebnis könnte schlechte Laune erzeugen.

## Was tun?

Der Schlüssel liegt darin, sich nicht an proprietäre Lösungen zu Binden. Einige unserer Benutzer haben uns gesagt, dass sie OFT ausgewählt habe, weil sie wissen, dass sie immer die Kontrolle über ihre Daten behalten werden und sie gegebenenfalls mit anderer Software verarbeiten, wenn ihnen OFT nicht mehr gefällt. Das ist eindeutig eine gesunde Einstellung, wir nehmen das nicht persönlich, sondern freuen uns darüber, dass unsere Nutzer den Wert von Migrierbarkeit schätzen.

Als Daumenregel für haltbare Daten gilt für mich:

1. Dateien verwenden statt Datenbanken
2. Einfache Standardformate verwenden
3. Dateien lokal auf der eigenen Maschine bearbeiten und speichern
4. Backup auf selbst kontrollierte Hardware, daheim oder in der Firma
5. Zusätzliches verschlüsseltes Backup in der Cloud ist sinnvoll, solange man ein Backupformat wählt, dass sich jederzeit auch woanders speichern lässt
6. Physisches Backup der Backup-Schlüssel im Tresor (feuerfest)

PS: Und die nächste Person, die mir erzählt, dass Word ein "Standard" ist, weil es so viele benutzen, setze ich auf einem Stuhl und spiele ihr die Definition des Wortes "Standard" einen Tag lang in Dauerschleife in allen Sprachen der Welt vor.