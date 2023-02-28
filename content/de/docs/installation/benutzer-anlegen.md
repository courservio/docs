---
title: "3. Benutzer anlegen"
description: "In diesem Punkt erfolgt das Anlegen eines ersten Benutzers und der Abschluss der Installation."
lead: "In diesem Punkt erfolgt das Anlegen eines ersten Benutzers und der Abschluss der Installation."
date: 2023-02-20T00:26:15+01:00
lastmod: 2023-02-20T00:26:15+01:00
draft: false
images: []
menu:
  docs:
    parent: "installation"
    identifier: "installation-benutzer-anlegen"
weight: 150
toc: true
---

Der *schwerste Teil* der Installation ist nun geschafft. Es folgt das Anlegen des ersten Nutzers.

## Im Browser fortsetzen

Zum Anlegen des ersten Benutzers ruft man [https://isabell.uber.space/setup](https://isabell.uber.space/setup) auf, wobei *isabell.uber.space* durch die eigene Domain ersetzt wird.

{{< alert icon="👉" text="Die Setup-Seite ist (aus Sicherheitsgründen) nur erreichbar, wenn noch kein Benutzer angelegt wurde. Nach der Einrichtung wird nur ein <em>404 - Seite nicht gefunden</em> Fehler angezeigt, wenn man die Seite erneut aufruft." />}}

Der erste Aufruf wird voraussichtlich einen kleinen Moment dauern, da notwendige Datenbank Einrichtungen durchgeführt werden. Dies sollte innerhalb von 3 - 5 Sekunden erledigt sein.

## Benutzer anlegen

In die Textfelder müssen (der eigene) *Name* und *E-Mail-Adresse* eingetragen werden. Diese E-Mail-Adresse muss (aus Sicherheitsgründen) die E-Mail-Adresse sein, die im Installations-Script eingegeben wurde.\
Hiermit wird der erste Benutzer-Account eingerichtet, der automatisch vollständige Administratoren-Rechte erhält.

## Auto Update einrichten

In diesem Schritt wird ebenfalls die Art des automatischen Updates eingerichtet. Dieses erfolgt täglich Nachts / Morgens automatisch um 03:45 Uhr.\
Hierbei gibt es folgende Optionen:

### letztes Release

Ein *Release* sind die jeweils veröffentlichten *Versionen*. Diese Option ist die *sicherste* und gleichzeitig *langsamste* Option, da neue Funktionen und Änderungen vor einem Release für gewöhnlich entsprechend getestet werden.

### letztes Commit

Bei dieser Option werden die letzten Änderungen automatisch geladen. Dies ist entsprechend deutlich schneller, die Änderungen jedoch noch nicht (ausführlich) getestet. Neue Funktionen und Fehlerbehebungen werden hierdurch deutlich schneller eingespielt.\
Insbesondere zum Testen von Änderungen und neuen Funktionen sollte diese Option aktiviert werden.

### manuelle Aktualisierung

Diese Option deaktiviert das automatische Update und ist **nicht** empfohlen.\
Bei dieser Auswahl ist es selbstverständlich weiterhin möglich z.B. via `git` zu updaten.

## Warten auf Heartbeat

Am Anfang wird `Warten auf Heartbeat` am Ende der Seite angezeigt. Hier wird automatisch geprüft, ob *CronJobs* und *Worker* (die im letzten Schritt angelegt wurden) korrekt funktionieren.

Diese Prüfung kann bis zu einer Minute dauern, da die *CronJobs* nicht häufiger aufgerufen werden. Der Status kann auf [https://isabell.uber.space/heartbeat](https://isabell.uber.space/heartbeat) (unter der eigenen Domain) geprüft werden. Zuvor muss die Setup-Seite das erste Mal aufgerufen worden sein.

Sollte der Heartbeat auch nach über einer Minute nicht funktionieren, bitte im [Forum](https://forum.courservio.de) bezgl. Fehlerfindung nachfragen.

### Account anlegen

Wurde der *Heartbeat* korrekt erkannt wird die Schaltfläche `Account anlegen` angezeigt. Nach der Betätigung dieser Schaltfläche wird die Datenbank abschließend eingerichtet und im Anschluss auf die Login-Seite weitergeleitet. Diese ist unter [https://isabell.uber.space/login](https://isabell.uber.space/login) (unter der eigenen Domain) zu finden.

#### Passwort festlegen

Vor dem Login muss ein Passwort festgelegt werden. Hierzu wurde automatisch eine E-Mail mit Link zum erstellen/zurücksetzen des Passwortes an die angegebene E-Mail zugeschickt.

Auf diese Weise wird sichergestellt, dass die SMTP Daten korrekt sind und die spätere Versendung von z.B. Bestätigungs-E-Mails an Kund\*innen nach deren Buchung funktionieren wird.
