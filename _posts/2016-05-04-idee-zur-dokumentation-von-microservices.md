---
ID: 631
post_title: Idee zur Dokumentation von Microservices
author: Bernd Boruttau
post_date: 2016-05-04 13:38:15
post_excerpt: ""
layout: post
permalink: >
  http://berndnet-2000.de/idee-zur-dokumentation-von-microservices/
published: true
category_sticky_post:
  - "0"
---
Nach einem weiteren Tag abseits eines vernünftigen Entwicklungsrechners entwickelt sich zum <a href="http://berndnet-2000.de/microservices-konfigurieren/">vorherigen Posts zum Thema Micrsoservice Konfiguration</a> langsam eine Idee.

Dabei geht es vor allem um das Teilproblem der Dokumentation von Microservices. In einer ersten, noch Prototypisch zu testenden, Idee geht es darum, das sich die einzelnen Microsservices, evtl. mit einem Namen und einer eindeutigen ID, an einem zentralen Service registrieren. Aus dem Request der Registrierung sollte sich die URL des registrierenden Service ermitteln lassen. Diese kann nun für weitere Zwecke gespeichert werden.

Später ließen sich mit einer geeigneten Methode die Registrierungen durchsuchen und z.B. von dieser zentralen Stelle aus die Swagger Dokumentation oder MVC Hilfeseiten aufrufen.

In einem weiteren Schritt könnten die Services Ihre Abhängigkeiten an den Dokumentationsdienst übermitteln. Somit ließe sich die Struktur der Microservices dokumentieren.

Um wieder an den vorherigen Post anzuknüpfen, könnten in einer weiteren Ausbaustufe die URLs der registrierten Services von anderen Services abgefragt werden um sich zu konfigurieren.