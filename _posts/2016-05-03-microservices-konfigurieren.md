---
ID: 619
post_title: Microservices konfigurieren
author: Bernd Boruttau
post_date: 2016-05-03 14:58:36
post_excerpt: ""
layout: post
permalink: >
  http://berndnet-2000.de/microservices-konfigurieren/
published: true
category_sticky_post:
  - "0"
---
Da sitz ich nun wegen Krankheit allein zu Hause und grübel mit den Kopf wund wie man am besten Microservices konfiguriert. Daher hier mal kurz meine ersten Gedanken zum Thema niedergeschrieben.

Für einen Kunden entwickeln wir auf Arbeit derzeit eine Anwendung mit einer Microservice Architektur. Diese gliedert sich in Domain Services, welche ausschließlich für Änderungen am Domainmodell zuständig sind, und Application Services, welche diverse Domain Services verwenden um daraus Daten für Anwendungen zu generieren oder Daten von den Anwendungen für die Domainservices aufbereiten.

<a href="http://berndnet-2000.de/wp-content/uploads/2016/05/micrsoservices-system-overview.png"><img class="size-thumbnail wp-image-623 aligncenter" src="http://berndnet-2000.de/wp-content/uploads/2016/05/micrsoservices-system-overview-150x150.png" alt="micrsoservices-system-overview" width="150" height="150" /></a>

Das "Problem" ergibt sich nun aus der Konfiguration der Services. Aktuell enthält jeder Service bzw. Anwendung eine Konfigurationsdatei, in der die URLs der zu verwendenden Services hinterlegt sind. Ist nun einer der Services unter einer anderen URL zu erreichen müssen alle Konfigurationsdateien, die auf diesen Service verweisen angepasst werden.

Ich grübel nun darüber, wie man eine Komponente entwickeln könnte, an der sich die Micrsoservices anmelden und über die sie die URLs ihrer benötigen Services beziehen können. Parallel dazu müssten sich die Services noch in Gruppen teilen lassen, so das sich Services aus einem evtl. laufenden Demo System nicht mit denen eines anderen Demo Systems verbinden sondern nur innerhalb ihrer Gruppe.

Zusätzlich sollten sich lokal laufende Debug Versionen nur mit Versionen auf dem selben PC verbinden. Dies ließe sich jedoch mit Buildkonfigurationen lösen ... irgendwie.

Als nettes Feature hätt man immer einen Überblick welche Systeme laufen und welche Abängigkeiten innerhalb diesen besteht.

Nun ja, ich grübel mal noch ein bisschen weiter. Es soll ja Systeme geben, die wohl genau dies können. Tests stehen allerdings noch aus ;-)