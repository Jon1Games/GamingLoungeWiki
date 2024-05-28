---
title: Jekyl
layout: default
permalink: software/jekyll/
nav_order: 4
---

# Jekyll

## Warum?

## Erste schritte

Wir haben das Repository von [just-the-docs](https://github.com/just-the-docs/just-the-docs/tree/main) copiert und editiert.

## Commands

Erst wird alles nötige instaliert.(Wir nutzen Alpine, also apk als Packetmanager)
```
apk add git ruby-bundler ruby-jekyll jekyll ruby-dev ruby-libs 
```

Dan wird das Repository von github geladen.
```
git clone https://github.com/Jon1Games/GamingLoungeWiki.git
```

Anschließend werden die gems installiert.
```
bundler install
```

Dannach haben wir die Webseite einmal gebaut.
```
bundler exec jekyll build
```

Da der Webserver keine Rechte auf diesen Ordner hat müssen wir diese setzen.
```
chmod a+rx -R /root/
```

Im Anschluß daran wird die Webseite im Webserver eingebunden.
Wir benutzen dazu [nginx](https://nginx.org/en/).
Er klährt ist dies in unserer [nginx Dokumentation]().

Die Webseite wird im Git Repository bearbeitet und mit dem folgendem Command aktualisiert.
```
git pull && bundler exec jekyll b
```
