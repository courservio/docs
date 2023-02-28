---
title: "2. Installation"
description: "In diesem Schritt wird die Installation und grundlegende Konfiguration erläutert."
lead: "In diesem Schritt wird die Installation und grundlegende Konfiguration erläutert."
date: 2023-02-18T16:05:07+01:00
lastmod: 2023-02-18T16:05:07+01:00
draft: false
images: []
menu:
  docs:
    parent: "installation"
    identifier: "installation-installation"
weight: 140
toc: true
---

{{< alert icon="👉" text="Eine <em>externe</em> Domain sollte <strong>vor</strong> diesem Schritt konfiguriert sein, da das Installations-Script die Domain-Konfiguration ausliest. Fragen hierzu bitte im <a href=\"https://forum.courservio.de\">Forum</a> stellen." />}}

## Angaben die benötigt werden

Im folgenden Installations-Script müssen verschiedene Angaben gemacht werden. Hierunter u.a.

- Firmenname
- die eigene E-Mail-Adresse (zum Anlegen des ersten Accounts)
- SMTP Zugangsdaten inkl. Server zum E-Mail-Versand.
- Absender E-Mail-Adresse (für ausgehende E-Mails)

## Weitere Vorbereitungen treffen

In diesem Schritt werden einige *Programme* und *Scripte* sog. *Abhängigkeiten* installiert.\
Die Ausführung der einzelnen Befehle dauern jeweils einen Moment, sollten aber selbstständig *durchlaufen*.

### Ins richtige Verzeichnis wechseln

```bash
cd /var/www/virtual/$USER/courservio
```

### composer ausführen

Zum Ausführen des Installations-Scripts müssen einige Voraussetzungen sog. <em>Abhängigkeiten</em> installiert werden. Der Befehl hierzu ist:

```bash
composer install
```

## Installation

### Installations-Script starten

Nachdem nun die minimalen Voraussetzungen erfüllt sind, können wir das Installations-Script starten, welches weitere Schritte durchführt. Hierbei werden einige Informationen abgefragt, die einfach eingegeben werden können. Das Script ist auf Englisch, die Punkte hier jedoch erklärt. Ja kann mit <em>yes</em> oder einfach <em>y</em> und Nein mit <em>no</em> oder einfach <em>n</em> eingegeben werden. Nach jedem Befehl muss mit der `Enter` Taste bestätigt werden. Die Maus kann nicht verwendet werden.

Der Befehl für das Installationsscript ist:

```bash
php artisan setup
```

## Fragen des Installations-Scripts

### Firmenname

Die erste Frage des Scriptes ist `What is the Name of your company?` übersetzt `Wie lautet Ihr Firmenname?`\
Der hier eingegebene Name wird u.a. beim Versand von E-Mails verwendet.

### Domain

`What is the domain for courservio?` fragt nach der für courservio zu verwendenden Domain. Diese kann durch Eingabe der Nummer ausgewählt werden. Die erste Domain (mit der `0` auswählen) ist standardmäßig die uberspace eigene Domain `nutzername.uber.space`. Aus diesem Grund sollten eigene Domains vor Start des Installations-Scripts festgelegt werden.\
Aufgelistet werden alle auf dem uberspace eingerichteten Domains.

### QSEH ermächtigte Stellen

Die Frage `QSEH authorized entity?` bezieht sich darauf, ob das Unternehmen *ermächtigte Stelle* ist. Für Ja kann dies mit `y` oder `yes` bestätigt werden. Nein kann mit `n` oder `no` ausgewählt werden.

Wählt man an dieser Stelle *nein* aus, können die folgenden Unterpunkte übersprungen werden, da diese Fragen nicht gestellt werden.

#### Kennziffer

Mit `What is your QSEH Number (Format X.XXXX)?` wird nach der Ermächtigungsnummer gefragt, die im Format X.XXXX ist und so eingegeben werden muss. Für private Anbieter ist dies 8.XXXX, für Hilfsorganisationen ist bereits die erste Nummer entsprechend anders.

#### Passwort ins QSEH Portal speichern?

Wenn das Passwort für den Zugang zum QSEH Portal (in dem auch die Kurse gemeldet werden) gespeichert werden soll, muss `Do you want to save the QSEH login password? (yes/no)` mit Ja (`y`) beantwortet werden.

Die Speicherung des Passwortes ist notwendig, wenn Kurse automatisch an die QSEH gemeldet werden sollen. Das Passwort wird ausschließlich auf dem uberspace gespeichert. Wir haben **keinen Zugriff** auf diese (und alle anderen) Daten. (Was courservio von Anbietern wie Hiorg-Server und semplan unterscheidet.)

#### QSEH Portal Passwort eingeben

Wenn das Passwort gespeichert werden soll, wird mit `What is your QSEH Password? (Input won't shown)` danach gefragt. Bei der Eingabe wird *keine Eingabe* angezeigt, jedoch dennoch gespeichert.\
Wurde die vorherige Frage mit Nein beantwortet, wird diese Frage nicht gestellt.


### Abfrage der E-Mail-Adresse

`What is your e-mail address?` fragt die eigene E-Mail-Adresse ab. Diese und die folgenden Fragen werden auch für *nicht ermächtigte Stellen* wieder angezeigt.

Die E-Mail-Adresse wird auch zum Anlegen des ersten Accounts (welcher Admin-Rechte bekommt) verwendet. Hier also bitte eine Adresse verwenden, die E-Mails empfangen kann und auf die keine weiteren Personen Zugriff haben.\
Die Adresse wird **nicht** öffentlich angezeigt.

### SMTP Server Daten

#### SMTP Server Adresse

`SMTP server address?` fragt nach der Adresse des SMTP Servers.

#### SMTP Port

Unter `SMTP port?` wird genau dieser abgefragt. *587* ist als Standard vorgegeben und kann durch die `Enter` Taste übernommen werden, sollte dieser passen.

#### SMTP User

`SMTP User?` erwartet als Eingabe den SMTP Nutzer.

#### SMTP Password

Mit `SMTP Password?` wird das zugehörige Passwort für den STMP Server abgefragt. Auch diese Eingabe wird nicht angezeigt.

#### E-Mail-Absender

`From sender e-mail address?` ist die E-Mail-Adresse, die beim Versand von E-Mails durch das System als Absender verwendet wird.

### Cronjob und Worker installieren und aktivieren

Die letzte Abfrage ist `Should schedule and worker be installed and activated?`. Diese fragt danach, ob die *CronJobs* und *Worker* installiert und aktiviert werden sollen. Diese werden zwangsweise für die korrekte Funktion von courservio benötigt. Daher sollte diese Abfrage grundsätzlich immer bestätigt werden.


### Einrichtung im Hintergrund

Nach der letzten Frage arbeitet das Script im Hintergrund, konfiguriert und installiert grundlegende Dinge. Dies dauert einen Moment, zeigt im Normalfall nicht viele Ausgaben und sollte nicht unterbrochen werden.

#### Anlegen des Accounts im Browser

Die letzte Meldung des Scripts ist `Please proceed setup at https://isabell.uber.space/setup`, wobei die Domain die zuvor ausgewählte Domain ist.

Die *Arbeit* auf der Kommandozeile ist an diesem Punkt beendet. Die Verbindung kann durch Eingabe von `exit` beendet werden.\
Die weiteren Schritte werden im nächsten Punkt erläutert.
