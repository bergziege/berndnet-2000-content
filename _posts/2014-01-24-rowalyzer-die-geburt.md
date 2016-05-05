---
ID: 169
post_title: 'Rowalyzer &#8230; die Geburt'
author: Bernd Boruttau
post_date: 2014-01-24 16:42:48
post_excerpt: ""
layout: post
permalink: >
  http://berndnet-2000.de/rowalyzer-die-geburt/
published: true
---
<a href="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0035.jpg"><img class="alignleft wp-image-172 size-thumbnail" src="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0035-150x150.jpg" alt="DSC_0035" width="150" height="150" /></a>Als Ausgangspunkt für eine kleine Nachmittagsbastelei stellt sich  mir seit 14 Tagen ein gebrauchter Rudertrainer von <a href="http://www.hammer.de/hammer-rudergeraet-cobra.html" target="_blank">Hammer </a>zur Verfügung. Dieser kommt mit einem Batteriegetriebenen Computer zur Anzeige von Schlagzahl, Kalorien, Entfernung usw.

<!--more-->

Leider lies die Funktionalität selbst mit vollen Batterien zu wünschen übrig. Sobald die Stopuhr gestartet wurde, versagte die Schlaganzeige usw.. Lange Rede kurzer Sinn. Es musste ein Ersatz geschaffen werden. Der Computer bezog seine Daten ausschließlich von einem Reedkontakt unter dem Sitz sowie einem (nicht funktionierenden) Herzfrequenzmesser.

Im Ersten Schritt tauschten der Reedkontakt sowie der Magnet die Positionen, so das der Magnet nun unterm Sitz klebt und der Kontakt anstelle des Magneten unterhalb der Schiene montiert ist.

Mutti hat früher immer gesagt ich soll den alten Elektroschrott wegschmeißen ... zum Glück höre ich nicht auf Mutti *g*. Nur aus diesem Grund war noch ein USB-Gameport vorhanden.
Zusätzlich wurde die 3,5mm Monobuchse aus dem Computergehäuse genutzt um den Reedkontakt mit Pin 2 und 4 des Gameport zu verbinden. Somit liegt dieser nun auf Knopf 1 des "Joysticks"

<a href="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0035.jpg"><img class="alignnone wp-image-171" src="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0034.jpg" alt="DSC_0034" width="270" height="360" /><img class="wp-image-172 alignnone" src="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0035.jpg" alt="DSC_0035" width="270" height="360" /></a><a href="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0037.jpg"><img class="wp-image-173 alignnone" src="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0037.jpg" alt="DSC_0037" width="270" height="360" /></a>

Galt es nun nur noch ein kleines Programm zu schrieben, welches die Betätigungen des Reedkontaktes in Schläge pro Minute umrechnet.
Dazu schnell ein C# Programmchen geschrieben, welches über Direct Input den Joystick/Gameport abfragt.
<pre>private void DoPoll(Joystick stick)
        {
            IsPressed = false;
            while (true)
            {
                stick.Poll();
                JoystickState state = stick.GetCurrentState();
                DateTime currentClick = _lastClick;
                if (state.Buttons[0])
                {
                    if (!IsPressed)
                    {
                        IsPressed = true;
                        if (!_skip)
                        {
                            currentClick = DateTime.Now;
                            TimeSpan diff = currentClick.Subtract(_lastClick);
                            if (Math.Abs(diff.TotalSeconds - 0) &gt; 0)
                            {
                                _clicksPerMinute = CalcClickPerMinute(diff);
                                _lastClick = currentClick;
                                _skip = true;
                            }

                        }
                        else
                        {
                            _skip = false;
                        }
                    }
                }
                else
                {
                    IsPressed = false;
                }
            }
        }

        public int CalcClickPerMinute(TimeSpan diff)
        {
            return (int)(60d / (diff.TotalSeconds));
        }</pre>
Somit lässt sich nun schonmal eine einfache Anzeige der Schlagzahl realisieren.

In Zukunft wird die daraus entstehende Software noch eine Stoppuhr, Schlagzähler und wenn möglich eine Anbindung an einen Garmin Ant+ Herzschlagsensor bekommen.
Wenn es halbwegs gescheite Werte zur Schätzung des Raumgewinnes pro Schlag gibt, kommt auch noch eine "Entfernungsmessung" dazu.

Für einen ersten Test soll dies jedoch reichen.

&nbsp;

<a href="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0023.jpg"><img class="wp-image-170 alignnone" src="http://berndnet-2000.de/wp-content/uploads/2014/01/DSC_0023.jpg" alt="DSC_0023" width="270" height="360" /></a>

<strong>Zutaten:</strong>
<ul>
	<li>Hammer Cobra Rudertrainer mit Reedkontakt zur Schlagzahlermittlung</li>
	<li>USB Gameport</li>
	<li>.net C# Anwendung mit SharpDX und WPF</li>
	<li>Lötkolben</li>
	<li>Kneifzange</li>
	<li>2,5h Zeit für Hard und Software</li>
</ul>