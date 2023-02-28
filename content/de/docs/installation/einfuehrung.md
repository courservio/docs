---
title: "Einführung"
description: "courservio ist die freie Kursverwaltungssoftware mit Schwerpunkt auf Erste-Hilfe-Kurse."
lead: "courservio ist die freie Kursverwaltungssoftware mit Schwerpunkt auf Erste-Hilfe-Kurse."
date: 2020-10-06T08:48:57+00:00
lastmod: 2020-10-06T08:48:57+00:00
draft: false
images: []
menu:
  docs:
    parent: "installation"
    identifier: "installation-einfuehrung"
weight: 110
toc: false
---

## Vorwort

courservio ist *self hosted*. Dies hat den Vorteil, dass die Datenhoheit und Kontrolle über das gesamte System bei der Anwender\*in liegt. Gleichzeitig hat es jedoch den *Nachteil*, dass (zu Anfang) ein wenig mehr Aufwand notwendig ist. In dieser Anleitung wird versucht Schrittweise alle Voraussetzungen und notwendigen Schritte zu erklären.\
Fragen, Fehler und Verbesserungsvorschläge können im [Forum](https://forum.courservio.de) gestellt/gemeldet und diskutiert werden.

## Voraussetzungen

### Hoster

Als *self hosted Software* benötigt es selbstverständlich einen Ort (Webhoster) um diese zu *betreiben*. Die klare Empfehlung ist hierbei der Anbieter [uberspace](https://uberspace.de).\
Jeder andere Anbieter der PHP, MySQL **und** SSH-Zugang anbietet, sollte grundsätzlich funktionieren. (Selbige sind nur sehr selten.) Alternativ ist selbstverständlich der Betrieb auf einem eigenen (virtuellen) Server möglich. Dieser Fall wird hier jedoch nicht weiter beschrieben, da man in diesem Fall die notwendigen Schritte aus den vorhandenen Anleitungen ableiten kann. Andernfalls sollte keine eigene Server-Instanz betrieben werden.

Alle Anleitungen beziehen sich auf die Verwendung mit [uberspace](https://uberspace.de). courservio wird zur Verwendung mit diesem Anbieter regelmäßig getestet.

Ein vorhandener [uberspace](https://uberspace.de) Account wird im weiteren Verlauf vorausgesetzt.\
Dieser kann kostenfrei und datensparsam erstellt werden. Erst wenn der Account länger als einen Monat genutzt werden soll, wird dieser kostenpflichtig. [uberspace](https://uberspace.de) hat hierzu ein außergewöhnliches, extrem faires [Preismodell](https://uberspace.de/de/product/#preise).

{{< alert icon="👉" text="Wir haben keine Verbindung/Beziehung zu uberspace (oder einem der anderen vorgeschlagenen Anbieter) und sind selbst <em>nur</em> (seit Jahren) begeisterte Kunden." />}}

### E-Mail / SMTP

Zum Versand der E-Mails wird ein E-Mail bzw. SMTP Anbieter benötigt. Dies kann grundsätzlich auch der aktuell genutzte E-Mail-Anbieter sein. Gerade eine hohe Zahl von *Transaktionellen* E-Mails sind diese jedoch häufig nicht geeignet.

Als Anbieter empfehlen wir hier [mailpace](https://mailpace.com/).

Die Dienste werden ausschließlich in der EU angeboten, wir hatten noch nie merkliche Ausfälle und der Support gleicht eher dem *Kumpel von nebenan*, den man jederzeit anrufen und mit seinen Sorgen *nerven* kann. Außerdem ist der Dienst extrem schnell, in der Preisgestaltung sehr fair und wir hatten in der Nutzung noch nie Anbieter abhängige Probleme bei der E-Mail Zustellung.

### Domain

courservio sollte unter einer Subdomain z.B. *termine*.meine-firma.de betrieben werden. Als Anbieter würden wir (aus eigener Erfahrung) [inwx](https://inwx.de) empfehlen.\
Selbstverständlich funktioniert grundsätzlich auch jeder andere Domain-Registrar.

[uberspace](https://uberspace.de) stellt eine Domain im Format *nutzername*.uber.space zur Verfügung, die selbstverständlich ebenso genutzt werden kann. Für den *produktiven Betrieb* sieht eine *eigene Domain* jedoch *professioneller* aus.

## Grundlagen



### SSH-Zugang

Zur Installation muss eine *SSH-Verbindung* zum eigenen [uberspace](https://uberspace.de) hergestellt werden.

Unter MacOS und Linux ist dies über die *Kommandozeile* möglich. Das zu verwendende Program heißt für gewöhnlich *Terminal*. Der Befehl eine SSH-Verbindung herzustellen ist:\
`ssh <username>@<server>.uberspace.de`

Die Daten *<username>* und *<server>* müssen jeweils durch die eigenen Angaben ersetzt werden.

{{< alert icon="👉" text="Bei der Aufforderung zur Passworteingabe werden <strong>keine</strong> Zeichen, Sternchen oder ähnliches angezeigt. Dies ist ein normales Verhalten. Die Eingabe funktioniert dennoch!" />}}

Unter Windows kann das Programm [putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) verwendet werden. Wahlweise sollte Windows 10 und höher mit der *Powershell* inzwischen auch eine Terminal-Anwendung anbieten.

Fragen und Unklarheiten können im [Forum →](https://forum.courservio.de) geklärt werden. Die Anleitung würde in diesem Fall später entsprechend ergänzt.
