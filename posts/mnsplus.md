---
title: MNS Plus
publish_date: 2023-05-01
---


[MNS+](https://mnsplus.bildung-rp.de/) ist ein vom Land Rheinland-Pfalz entwickeltes IT-System für Schulen. Als Schüler in Rheinland-Pfalz konnte ich mir dieses großartige System schon etwas genauer anschauen.

## Geschichte

MNS+ wurde 2005 von der Conciety AG (Zu diesem Unternehmen konnte ich nicht viel herausfinden, aber es wurde wohl 2004 gegründet und 2017 liquidiert) entwickelt und die Rechte wurden vom Land Rheinland-Pfalz gekauft.

2009 wurde anscheinend MNS+ 2.0 veröffentlicht, das die Web UI komplett ersetzte. Sie basiert seitdem auf Sencha Ext.JS 3. 

MNS+ selbst ist eine Sammlung von aus dem Internet zusammengestellten & selbst entwickelten PowerShell, VBS, Batch und Perl-Skripten.

Teilweise sind diese für Linux/Unix geschrieben und nutzen Windows-Ports der GNU-Coreutils und ähnlicher Programme.

Generell ist das System meiner Meinung nach etwas durcheinander und schlecht organisiert.

## Die Entwickler

Anscheinend kennen die Entwickler kein Issue-Managment oder Versionsverwaltungssystem.

(Fast) Jede Datei aus dem MNS+ Code beginnt mit einem Kommentar, der Änderungsverlauf und bekannte Bugs enthält.

_MNS+ ist keine Open-Source-Lösung, und es gibt natürlich keine anderen Möglichkeiten, den Code komplett einzusehen - Es würde ihn ja niemand zusätzlich zu den Binaries in jeder Schule auf dem Server speichern..._

An meiner Schule war weiterhin VLC Media Player von VLC.de installiert - Eine inofizielle Seite, die VLC mit Werbung verbreitet.

Zusätzlich dürfen IT-Admins an Schulen meistens nichts selber machen. Stattdessen wird das vom lokalen "Supportpartner" (z.B. Stadtverwaltungen, aber auch IT-Unternehmen) gemacht. Dank dem Sicherheitsmodell können diese natürlich auch keine Server übernehmen (Ich habe einen entsprechenden Exploit, den veröffentliche ich hier aber nicht).

## Tech-Stack

MNS+ ist für Windows Server 2016 angelegt. Dabei läuft ein Server als Host, mit einer VM mit Windows Server und einer mit einer auf MikroKnoppix basierenden Distribution ("SkoleRouter") mit Squid als Proxy.

Die Clients laufen mit Windows 10. Theoretisch enthält MNS+ aber auch Regeln bis zu Windows XP. Dies führt zu zusätlicher Komplexität, da MNS+ daher z.B. einige eigene Gruppenrichtlinien enthält, die Regeln, die teilweise seit Windows Vista in Windows eingebaut sind, nachbauen, oder welche, die nur für Windows XP gelten.


## "Modular"

Das M in MNS+ steht für modular. Eine wirklich modulare Architektur ist für mich jedoch nicht erkennbar, was genau an dem System modular sein soll, ist mir nicht klar.

## Überwachung

Standardmäßig enthält MNS+ eine Überwachungslösung, um Schülerrechner zu überwachen. Dank der IT-Sicherheitsexperten kann diese Software natürlich nur von Lehrern genutzt werden.

Daher kann auch niemand ein Tool bauen, mit dem Schüler dieses System übernehmen könnten. Wenn es eins gäbe, würde es aber wahrscheinlich [MNSPlusTrasher](https://github.com/basti564/MNSPlusTrasher) heißen.

Bei mir an der Schule läuft auf allen Rechnern zusätzlich ein UltraVNC-Server. Damit könnten auch Lehrer-Computer überwacht werden, ich weiß jedoch nicht, ob dieser vom Land oder lokal eingeführt wurde.

_Natürlich wäre es besonders schlecht, wenn damit ein Schüler irgendwie das Passwort herausfinden würde und Lehrercomputer überwachen würde..._


## TODO

- Sicherheit
- Updates
- Datenschutz
- Überwachung
