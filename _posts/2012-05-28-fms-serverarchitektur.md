---
ID: 136
post_title: 'FMS &#8211; Serverarchitektur'
author: Bernd Boruttau
post_date: 2012-05-28 11:29:26
post_excerpt: ""
layout: post
permalink: >
  http://berndnet-2000.de/fms-serverarchitektur/
published: true
---
<a href="http://berndnet-2000.de/wp-content/uploads/2012/05/blog_fms_20120503_db_structure.png"><img class="size-thumbnail wp-image-104 alignleft" src="http://berndnet-2000.de/wp-content/uploads/2012/05/blog_fms_20120503_db_structure-e1401303963987-150x143.png" alt="blog_fms_20120503_db_structure" width="150" height="143" /></a>Wie baut man eigentlich einen Server? Was Anfangs noch recht simpel klingt, wird bei diesem Projekt langsam zum Problem. Da das FMS keine Webanwendung oder ein einfacher Webservice wird, sondern die einzelnen Komponenten in "Echtzeit" miteinander kommunizieren sollen, tauchen einige Fragen auf:

<!--more-->
<ul>
	<li>Struktur der Webservices</li>
	<li>Datenmodell</li>
	<li>Kommunikation der einzelnen Komponenten</li>
	<li>Datenbankzugriffe</li>
	<li>usw.</li>
</ul>
Diese Fragen können hoffentlich innerhalb der nächsten Woche geklärt werden, um anschließend einen Prototypen der Architektur zu erstellen. Auf dessen Basis wird dann die Serveranwendung aufbauen.

Der Server wird später für die Nutzerauthentifizierung und  Weiterleitung aller Nachrichten der Komponenten zuständig sein. Dabei geht es z.B. um die Weiterleitung einer Statusänderung eines Rettungsmittels an die Leitstelle, oder um das Senden eines Einsatzes an ein bestimmtes Rettungsmittel.

Es bleibt spannend!