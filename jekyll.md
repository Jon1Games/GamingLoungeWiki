---
title: Jekyll
layout: default
permalink: software/jekyll/
parent: Software
---

# Jekyll

## Warum Jekyll?

Jekyll ist eine open-source software die es erlaubt aus sogenanntent MarkDown dokumenten webseiten zu bauen.

## Erste schritte

Erst haben das Repository von [just-the-docs](https://github.com/just-the-docs/just-the-docs/tree/main) kopiert.<br>
<br>
Weiterhin wird alles nötige instaliert.(Wir nutzen Alpine, also apk als Packetmanager)
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

Da der Webserver keine Rechte auf diesen Ordner hat müssen wir diese setzen.<br>
(Das kopierte Repository liegt in /root/GamingLoungeWiki/)
```
chmod a+rx -R /root/
```

Im Anschluß daran wird die Webseite im Webserver eingebunden.<br>
Wir benutzen dazu [nginx](https://nginx.org/en/).<br>
Er klährt ist dies in unserer [nginx Dokumentation]().<br>

Wenn wir danach die Webseite im Git Repository bearbeitet wird diese mit dem folgendem Befehl aktualisiert.
```
git pull && bundler exec jekyll b
```
