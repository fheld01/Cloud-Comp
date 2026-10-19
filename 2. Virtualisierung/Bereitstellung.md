Überblick
- Die Bereitstellungsmodelle des Cloud Computing beschreiben wo und wie die Cloud Dienstleistungen erbracht werden
- Es werden fünf Modelle zur Bereitstellung von Cloud Computing unterschieden, die hinsichtlich des Wartungs aufwands und ihrer Abstraktion der Hardware variieren
- Lokal betriebene Hardware sichert zwar eine hohe Daten souveränität, verhindert aber die Vorteile des Cloud Computing
- Die Empfehlung eines Bereitstellungsmodells muss unternehmensspezifischeFaktoren und Pläne berücksichtigen

### Private Cloud
- Einsatz von Cloud Software zur automatisierten und standardisierten Breitstellung von virtuellen Ressourcen
- Das Unternehmen verantwortet Beschaffung, Betrieb und Wartung der Hard-und Software
- Betrieb in lokalem Rechenzentrum, sodass der physische Zugriff auf die Infrastruktur gesichert wird
- „Airgap“ Umgebungen beschreiben Infrastrukturkonfigurationen, die keinen Internetzugang haben 
- Einsatz bei hochsensiblen Daten, eingeschränkter Bandbreite, bestehender Hardware und Personal.
- <span style="color:green">Maximale Kontrolle über Hardwareauswahl</span>  
- <span style="color:green">Eigene Sicherheitskonzepte</span>
- <span style="color:green">Nutzung vorhandener IT</span>
- <span style="color:red">Eingeschränkte Skalierung</span>  
- <span style="color:red">Keine globale Infrastruktur</span>  
- <span style="color:red">Eingeschränkte Innovation</span>  
### Public Cloud
- Nutzung eines Anbieters, der seine Dienstleistungen der breiten Öffentlichkeit anbietet. 
- Klassische Form des Cloud Computing mit Abgabe der Verantwortung von Betriebsaufgaben
- Realisierung wichtiger Vorteile des Cloud Computing wie Fixkostenvariabilisierung, Skaleneffekte, Globale IT, Skalierbarkeit. 
- Gefahr von Lock-In Effekten. 
- Einsatz bei Projekten mit vielen Unsicherheiten, global verteilten Nutzern und innovativen Funktionen
- <span style="color:green">Volles Skalierungspotential</span>  
- <span style="color:green">Globale Infrastruktur</span>
- <span style="color:red">Eingeschränkte Kontrolle</span>  
- <span style="color:red">Gefahr eines Lock-In Effekts</span>  

### Hybrid Cloud
- Kombinierte Nutzung einer Private Cloud und einer Public Cloud zur Ressourcenbereitstellung
- Über eine einheitliche Verwaltungssoftware können zentrale Governance-und Sicherheitskonzeptesowie die Cloud Vorteile umgesetzt werden
- Durch die kombinierte Nutzung von Private und Public Cloud besteht eine **geringere Gefahr eines Lock-In**
- Verantwortung für Beschaffung und Wartung des lokalen Betriebs, als auch der Konfiguration der Public Cloud Infrastruktur
- Einsatz bei Projekte mit Bedarf an kurzfristiger Skalierung trotz Schutz sensibler Daten.
- <span style="color:green">Nutzung vorhandener Infrastruktur.</span>  
- <span style="color:green">Nutzung der Public Cloud Vorteile</span>
- <span style="color:red">Hohe Komplexität</span>  
- <span style="color:red">Hohe Gesamtkosten</span>  
### Multi Cloud
- Gleichzeitige Nutzung verschiedener Public Clouds über eine einheitliche Verwaltungsoberfläche zur Bereitstellung virtueller Ressourcen
- Durch die einheitliche Verwaltung wird Anbieter Lock In vermieden und zentrale Governance-und Sicherheitskonzepteumgesetzt
- Kostenvorteile entstehen, indem der günstigste Cloud Anbieter für eine Aufgabe ausgewählt werden kann 
- Gefahr eines Lock-Ins bei der Verwaltungssoftware, da diese oft spezifisch von den Cloud Providern ist
- Hohe Komplexität bei Konfiguration
- Einsatz bei: Unternehmen welche bereits intensiv Cloud Anbieter einsetzten.
- <span style="color:green">Vermeidung Lock-In</span>  
- <span style="color:green">Hostenoptimierter Betrieb</span>
- <span style="color:red">Hohe Gesamtkomplexität</span>  
- <span style="color:red">Verwaltungssoftware an Public Cloud gebunden</span>  
### Virtual Private Cloud (VPC)
- Nutzung der nicht öffentlich zugänglichen Infrastrukturbereiche einer Public Cloud zur Bereitstellung virtueller Ressourcen
- Hierbei werden separate Netzwerkbereiche verwendet die nur via VPN erreicht werden können
- Der Aufbau eines VPC erfordert hohe Expertise in Netzwerksicherheit und Cloud Konfiguration
- Einsatz bei neu aufzubauender IT-Infrastruktur welche die Vorteile des Cloud Computing benötigt.
- <span style="color:green">Volles Skalierungspotential</span>  
- <span style="color:green">Globale Infrastruktur</span>
- <span style="color:red">Abhängigkeit von einem Anbieter</span>  
- <span style="color:red">Komplexe Einrichtung</span>  
### Zusammenfassung
- Die Bereitstellungsmodelle unterscheiden sich hinsichtlich ihres **Wartungsaufwands und der Abstraktion der Infrastruktur**. 
- Der Einsatz eigener Hardware erfordert **hohen Wartungsaufwand und eine geringe Abstraktion der verwendeten Infrastruktur**
- Virtual Private Cloud und Multi Cloud erfordern **geringeren Wartungsaufwand mit unterschiedlichem Abstraktionsgrad**
- Die Public Cloud hat den **geringsten Wartungsaufwand und eine hohe Abstraktion von der eingesetzten Infrastruktur.**
![[Pasted image 20261008114905.png|300]]



### Edge Computing
- Edge Computing kennzeichnet die **Verarbeitung von Daten nahe am Entstehungsort**
- Großes Wachstum der daten-produzierenden Geräte erwartet
- Durch Edge Computing müssen nicht **alle Daten in einer Cloud verarbeitet werden** wodurch **Vorteile für die Datensicherheit und Latenz** entstehen
- Edge Computing steht vor Herausforderungen bezüglich der **Wartung und der Heterogenität der Daten und Geräte**
- Dezentrale Verarbeitungsform



Tweet: 
![[Pasted image 20261008115844.png]]
a) Bitte nehmen Sie Stellung zu dem Tweet. Hat Herr Newman recht und die Situation wurde schlimmer? Was wurde nicht berücksichtigt? 
- Modularisierung
Wurde die Situation wirklich schlimmer?

Nicht unbedingt. Newman berücksichtigt nicht, dass moderne Cloud-Technologien viele Aufgaben automatisieren:

- Automatische Sicherheitsupdates
- Zentrales Patch-Management
- Austausch kompletter Container statt manueller Updates
- Managed Services des Cloud-Anbieters
- Infrastructure as Code

b) Beschreiben Sie geeignete Einsatzgebiete für jedes der 5 Dienstleistungsmodelle von Cloud Computing. 
Dienstleistungen On-Premise: Bei hochsensiblen Daten, bestehender Hardware und Personal.
Infrastructure asa Service (IaaS): Anpassung des Betriebssystems erforderlich 
Container as a Service (CaaS)
Platform as a Service (PaaS):
Function as a Service (FaaS):
Software as a Service (SaaS): Keine tiefen Anpassungen notwendig

c) Welche Formen der Bereitstellung von Cloud Computing sind geeignete Start-, Zwischen-und Endziele einer Cloud Migration? 
Hybrid niemals Start
Private -> Hyprid -> Public -> Multi als Ausbauziel
Start
Zwischen
Endziel
d) Wo sehen Sie die Unterschiede zwischen einer Private Cloud und Edge Computing?
Edge Computing
