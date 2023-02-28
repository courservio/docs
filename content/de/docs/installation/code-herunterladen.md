---
title: "1. Code herunterladen"
description: "In diesem ersten Schritt laden wir den Sourcecode herunter/auf den Server."
lead: "In diesem ersten Schritt laden wir den Sourcecode herunter/auf den Server."
date: 2023-02-18T14:26:14+01:00
lastmod: 2023-02-18T14:26:14+01:00
draft: false
images: []
menu:
  docs:
    parent: "installation"
    identifier: "installation-code-herunterladen"
weight: 130
toc: true
---

## Kopieren vorbereiten

### per SSH verbinden

In einem ersten Schritt verbinden wir uns per SSH auf den Server. Der Befehl in der Kommandozeile hierfür ist

```bash
ssh <nutzer>@<server>.uberspace.de
```

`<nutzer>` und `<server>` müssen entsprechen durch die eigenen Daten ersetzt werden. Der fertige Befehl sieht beispielsweise (keine funktionierenden Daten) so aus

```bash
ssh isabell@stardust.uberspace.de
```

{{< alert icon="👉" text="Das zu verwendende Passwort ist <strong>nicht</strong> das Login-Passwort für uberspace. Das Passwort für den SSH-Zugang muss auf der Weboberfläche von uberspace separat festgelegt werden." />}}


### in den Zielordner wechseln

Wir müssen den code für courservio außerhalb des *öffentlich* erreichbaren Bereiches legen. Um in den entsprechenden Ordner zu wechseln, nutzen wir den Befehl

```bash
cd /var/www/virtual/$USER/
```

## Code von github kopieren

Wir *kopieren* nun in den *aktuellen* Ordner die aktuelle Version von courservio.

```bash
git clone https://github.com/courservio/courservio.git courservio
```

Damit ist courservio auf den Server kopiert und wird im nächsten Schritt installiert und konfiguriert.
