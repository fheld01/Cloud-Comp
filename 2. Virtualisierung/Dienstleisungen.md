Grundlagen:
- Basierend auf den **Möglichkeiten zur Virtualisierung** und den **Bestandteilen einer Anwendung** lassen sich folgende Abstraktionsebenen für deren Betrieb unterscheiden
- Die Servicemodelle des Cloud Computing unterscheiden sich in den **Anteilen, die vom Cloud-Provider und jenen Anteilen, die vom Softwareentwickler** verantwortet werden
- Bei den angebotenen Dienstleistungen stehen die **Kontrolle** und die Abstraktion der Hardware in einem **gegensätzlichen** Verhältnis
- Mit der Aufgabe der Kontrolle über die Ausführung der eigenen Anwendung geht die Gefahr einer stärkeren Bindung an den Anbieter(Lock-In) einher.
 ![[Pasted image 20261008111043.png|250]]
 
-> Verknüpfung von Voll- und Prozessvirtualisierung

### Dienstleistungen On-Premise
- Jede Schicht der Ausführungsumgebung ist in eigener Verwaltung des Unternehmens. 
- Implizite Aufgabenteilung durch Entwicklungs-und Betriebsteams, aber tiefgreifende Möglichkeiten zur gegenseitigen Abstimmung
- Weitreichende Anpassungsmöglichkeiten bspw. Hardwareanpassungen (Grafikkartenauswahl, Speicherlösungen, etc.) für genutzte Software.
- Volle Verantwortung des Risikos für Ausfall und Livegang
- **Einsatzmöglichkeit: Hohes Sicherheitsrisiko (Rüstungsmarkt), man kann nicht riskieren, dass Daten, Branchen wie Rüstung, Verteidigung, Gesundheitswesen** 
![[Pasted image 20261008111433.png|100]]
### Infrastructure asa Service (IaaS)
- Cloud Anbieter stellt dem Kunden logische Hardwareressourcen samt Betriebssystem bereit
- Der Cloud Anbieter sichert dem Kunden via Service Level Agreement eine Verfügbarkeitder Hardwareressourcen zu und übernimmt deren Wartung
- Der Kunde kann ein bestehendes Betriebssystem für seine Anwendung anpassen oder eigene VMs zum Cloud Provider hochladen
- Der Kunde ist nicht an die Hardwarekonfiguration gebunden und kann diese flexibel nach Bedarf erhöhen oder reduzieren
- Einsatzmöglichkeit: 
	- Wenn das Unternehmenweiterhin Kontrolle über Betriebssystem und Softwarestack behalten möchte; Lift-and-Shift; Low Level Anforderungen, Minimale Latenz wichtig
	- 1:1 Migration
	- Hardwarenahe Ausführung
	- Minimale Latenz
	- Konkrete Beispiele: GE Oil and Gas: 500 Anwendungen innherhalb von 2 Jahren in AWS Cloud migriert
	- Novatis: Einsparung von 40 Millionen USD gespart
![[Pasted image 20261008111631.png|100]]
### Container as a Service (CaaS)
- Cloud Anbieter stellt eine Container Umgebung bereit, innerhalb derer ein Kunde seine Container betreibt. 
- Cloud Anbieter abstrahiert die konkrete Hardware und OS vom Kunden und sichert diesem ‚nur‘ den Betrieb der Containerumgebung zu
- Der Kunde erstellt das Container-Image, das vom Anbieter ausgeführt wird
- Möglichkeit des Autoscaling, wobei der Cloud-Anbieter selbstständig bei erhöhter Nachfrage mehrere Container-Images startet
- Einsatzmöglichkeiten:
	- Bei hoher Portabililtät
	- Microservices: ohne einheitliche Programmiersprache zb (Poliglot programming)
	- Entlastung des Betriebs
	- Beispiele: Paylal und Kaplan
![[Pasted image 20261008111754.png|100]]

### Platform as a Service (PaaS)
- Der Cloud Anbieter stellt die Laufzeitumgebung für die Ausführung von Code bereit und übernimmt die Isolierung und den Betrieb der Anwendung
- Der Cloud Anbieter ist vollkommen frei wie er die Codeausführung vornimmt und wie er die Virtualisierung zur Isolation der Anwendungen einsetzt
- Der Kunde übergibt nur den Anwendungscode und muss sich nicht mit der Thematik des Hostings und der Isolierung beschäftigen
- Lock-In des Plattformbetreibers bzgl. unterstützter Java Features, Funktionen zum Testen und Funktionen zur Skalierung
- Einsatzmöglichkeiten:
	- Scotiabank, fiserv
![[Pasted image 20261008111943.png|100]]
### Function as a Service (FaaS)
- Der Cloud Anbieter stellt elementare Funktionsblöcke (AudioIF, DocumentIF, ImageRecognitionIF) für die Anwendungen bereit
- Der Kunde erstellt nur noch einen Teil der Endanwendung und stützt sich für den Rest auf fertige Lösungen des Cloud Anbieters
- Der Kunde gibt die Hoheit über die Ausgestaltung und Ausführung der Applikation an den Cloud Anbieter ab
- Großer Lock-In, da die Cloud-Anbieter unterschiedliche Programmierschnittstellen und Funktionen unterstützten
- Einsatzgebiete:
	- Cloud Features notwendig (zb. KI Modelle)
![[Pasted image 20261008112853.png|100]]
### Software as a Service (SaaS)
- Die gesamte Anwendung wird vom Cloud Anbieter entwickelt und betrieben
- Der Kunde hat keinen Einfluss auf den Betrieb und es besteht der maximale Lock-In, da generell nur ein Cloud Anbieter die Anwendung bereitstellt
- Der Funktionsumfang, sowie Teile einzelner Funktionen, können konfiguriert werden
- Der überwiegende Großteil der Anwendung ist jedoch vorgegeben
 ![[Pasted image 20261008112830.png|100]]
![[Pasted image 20261008112932.png]]
- Die verwendete Abstraktion ist zentral zur Bestimmung der Verpflichtungen (Patching, Skalierung, Failover) und Freiheiten (Optimierungen, Bibliotheken) des Softwareentwicklers.
- Es gibt keine generelle Empfehlung, sondern es müssen die individuellen Bedürfnisse des Kunden berücksichtigt werden um die geeignetste Dienstleistungsform zu identifizieren.
	- Nutzung ohne Anpassung
	- Schneller Einsatz
	- Nutzerbasierte Preise
	- Beispiele: Teams @ Ikea; Github @ Xing


