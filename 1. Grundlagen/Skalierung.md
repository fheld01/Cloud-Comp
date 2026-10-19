- Fähigkeit ein Anwendungsystems Leistung flexibel zu erhöhen oder zu reduzieren
		- durch Ausstattung mit virtuellen Ressourcen 
	- gemessen mit Skalierungsfaktor: Auswirkungen
		- Verlauf linear (Festplatte Speicherplatz erhöhen) oder exponentiell (Speicherplatte Harddisk austauschen mit SSD -> alles schneller)
		- vertikale Skalierung (**Scale-Up**): Tauschen von alter und neuer Hardware 
				- + Software muss nicht angepasst werden, 
				- - System muss aber ausgeschaltet werden
				- - technische Grenzen
		- horizontale Skalierung (**Scale-Out**): Dazuschalten von weiterer Hardware, kein Tauschen
			- - Anwendung (Software) muss angepasst werden
			- + Leistungssteigerung im Betrieb, kein Ausschalten
			- + umfassendere Möglichkeiten zur Skalierung
		- Anwendungsvolumen: zo hoch zb an Black Friday
			- Konsequenz: Tages bzw. Wochenindividuell Entscheidung wie viel Hardwareausstattung wichtig ist

![[Pasted image 20261002134512.png|300]]