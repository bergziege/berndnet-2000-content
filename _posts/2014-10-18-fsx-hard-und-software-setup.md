---
ID: 535
post_title: 'FSX &#8211; Hard und Software Setup'
author: Bernd Boruttau
post_date: 2014-10-18 17:37:01
post_excerpt: ""
layout: post
permalink: >
  http://berndnet-2000.de/fsx-hard-und-software-setup/
published: true
---
Die Nächte werden länger und das schlechte Gewissen, schon wieder vorm Rechner zu sitzen, kleiner.
Somit wurde auch der FSX nach längerer Ruhepause mal wieder aktiviert.

In diesem Beitrag geht es vor allem um das Zusammenspiel der Hard und Softwarekomponenten.

<!--more-->
<h3>Aufbau</h3>
Die folgende Abbildung stellt den aktuellen Aufbau mit 3 Computern dar, die unterschiedlichste Aufgaben im Flug- sowie Alltagebetrieb übernehmen.

<a href="http://berndnet-2000.de/wp-content/uploads/2014/10/fsx_setup.png"><img class="alignnone wp-image-536 size-full" src="http://berndnet-2000.de/wp-content/uploads/2014/10/fsx_setup.png" alt="fsx_setup" width="704" height="635" /></a>

Der Alltagsrechner (gelb) ist ein kleiner passiver Intel Atom PC mit Win7, der im allgemeinen 99% der Alltagsaufgaben wie Mails, surfen, TV usw. übernimmt. Ausschließlich an diesem PC sind Tastatur und Maus vorhanden. Diese können durch DirectInput über das Netzwerk an allen anderen PCs verwendet werden. Der Bildschirm dieses Rechners kann wenn gewünscht als Zweitmonitor des FSX PCs genutzt werden.

Das Tablet mit Win8 dient zur Anzeige des Kartenmaterials sowie als Moving Map (Plan-G). Außerdem nutze ich die 5MP Frontkamera mit FacetrackNoIR zur Gesichterkennung.
Plan-G verbindet sich mittels Simconnect zum FSX PC. FacetrackNoIR sendet seine Daten mittels UDP an eine weitere FacetrackNoIR Installation auf dem FSX PC.

Am FSX PC sind nun Joystick und Pedale angeschlossen, der FSX sowie ASE und FacetrackNoIR Installiert. Facetrack empfängt die Daten vom Tablet und gibt sie mittels Simconnect an den FSX weiter.
<h3>Positiv</h3>
Die Moving Map befindet sich auf dem Tablet direkt im Sichtfeld.

Der FSX PC muss sich nicht um die Gesichtserkennung bemühen.

Der Alltags PC ist nicht mit Karten belegt und kann optional als zweiter FSX PC Monitor genutzt werden.
<h3>Negativ</h3>
Durch die Übertragung der Facetrack Daten über WLAN ins interne Netz und weiter über die Zwischenstation zum FSX gibt es ca. eine halbe Sekunde Verzögerung zwischen realer und virtueller Kopfbewegung.
<h3>Offene Punkte</h3>
Noch bin ich mir im Unklaren darüber, wo der Vatsim Client installliert weredn soll. Theoretisch müsste er auf den FSX PC um die Joysticktasten als PPT zu nutzen. Andererseits läuft der FSX im Vollbild, so das ich im Flug den Client nicht sehen kann um z.B. Nachrichten zu lesen.

... 5 Minuten später ...

Beim schreiben dieses Beitrags seh ich soeben in der Dokumentation von vPilot, das es ein Proxy für PPT und Flieger gibt, um den eigentlichen Vatsim Client auf einem anderen Rechner laufen zu lassen. Somit könnte der Client auf dem Tablet installiert werden. Problem: der einzige, eigentlich für das Headset benötigte, USB Port ist bereits durch den Mausempfänger belegt, damit DirectInput unter Win8 einen Mauszeiger anzeigt. Als Lösung des Problems wird dem Tablet wohl ein USB Hub spendiert. Oder der Alltagsrechner bekommt einen zweiten Monitor ...

&nbsp;