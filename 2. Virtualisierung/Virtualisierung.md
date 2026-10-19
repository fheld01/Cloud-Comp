Bedeutung:
- Entkopplung der **Ausführungsumgebung der Software** von **der physischen Hardware**
- Diese Entkopplung kann durch **virtuelle Maschinen** umgesetzt werden, die **abstrakte Repräsentationen der physischen Hardware** sind
- Durch die Entkopplung können **mehrere Ausführungsumgebungen auf der gleichen Maschine** ausgeführt werden und **Hardware kann leichter ausgetauscht** werden
- Trotz der Entkopplung wirken sich die **Leistungsgrenzen der physischen Hardware** auf die Ausführungsumgebungen aus (bspw. CPU, RAM, Speicher)
- Geteilten Nutzung der gleichen Hardware
- Praxistauglich: Deutlich geringere Performance defizite als Emulation
- Beispiel: ESX-i, VirtualBox, Xen, KVM, WSL2

Nicht verwechseln: [[Simulation]] vs. [[Emulation]] vs. [[Virtualisierung]]

[[Wichtigste Ressourcen eines Comuters]]
## Ziele Virtualisierung:
##### Isolation der Anwendungen
- Eindämmung von Laufzeitfehler (Sandboxing)
- Einsatz verschiedener Programmiersprachen und Bibliotheken
- Vermeidung ungewolter Seiteneffekte bei Aktualisierung
##### Multiplizität von Systemen (Auslastung)
- Beschaffung neuer Hardware nicht zwangsweise notwendig
- Neue Möglichkeiten zum Parallel betrieb von Alt-und Neu-System
- Ausnutzen von Effekten zur Fixkostendegression (Betrieb, Strom, Hardware).
##### Portabilität der Systemkonfiguration
- Umzug auf neue Hardware (bspw. bei Ausfall, Dev-ProdUnterschied)
- Hardwareänderungen können im Vorfeld geprüft werden
- Leichte & schnelle Bereitstellung neuer Umgebungen

# Arten von Visualisierung
### Vollvirtualisierung
- **[[Hypervisor]]** entkoppelt die **Ausführung** der virtuellen Maschinen von der Hardware indem er die **Ressourcenzugriffe verwaltet und Befehle übersetzt**
- Durch Einsatz von **Hardware Virtualisierung** (bspw. VT-X) können die **Leistungsverluste der Hypervisor Übersetzung** massiv reduziert werden
- Das Gast-OS wird **nicht angepasst** und geht davon aus **direkten Hardwarezugriff** zu haben
- Jede VM hat ein **eigenes Image** und **fest zugewiesene Ressourcen**
![[Pasted image 20261008093229.png|200]]
#### Bare-Metal Hypervisor (Typ 1)
- Hypervisor sitzt **direkt über der Hardware** und wird meist **via Web-IF** gesteuert
- Vorteil Performance: Aufrufe vom Hypervisor gehen direkt zur Hardware
- Vorteil Sicherheit: Kein Gefahrenpotential von anderer Software (bspw. Malware)
- Oft in Rechenzentren verwendet
- Bsp.: VMWareESX-i, Hyper-V
![[Pasted image 20261008093520.png|150]]
#### HostedHypervisor (Typ 2) 
- Hypervisor inkl. GUI wird auf einem **vollwertigen OS installiert**
- Nachteil **Performance**: Aufrufe vom Hypervisor werden übersetzt und an das OS weitergegeben
- Nachteil **Sicherheit**: Nebenläufige Anwendungen können auf dem Host ausgeführt werden (Vorteil Multifunktionalität)
- Bsp.: VirtualBox, VMWareWorksation/Fusion, Parallels
![[Pasted image 20261008093600.png|150]]

### Para-Virtualisierung
- Bei der Para-Virtualisierung wird das Gast-OS so angepasst, dass es **keine physische Hardware sondern API-Aufruf** nutzt
- Der **Hypervisor** verwaltet weiterhin die **Ausführung der Prozesse**
- Gerätespezifische Aufrufe werden v**om Host-OS zur Laufzeit übersetzt**, sodass das Gast-OS nur **einen virtuellen Treiber** nutzt (bspw. für Netzwerkzugriff)
- Vorteil **Performance: Aufgrund der Anpassung des Gast-OS wird eine sehr hohe Performance der Gäste zur Laufzeit erreicht**
- Nachteil **Anpassung: Notwendigen Anpassungen bei Open Source OS möglich, nicht jedoch bei kommerziellen OS (bspw. Windows)**
![[Pasted image 20261008094957.png|250]]
### Prozessvirtualisierung
- Bei der Prozessvirtualisierung wird **keine vollwertige VM** ausgeführt und es wird kein **Hypervisor** eingesetzt
- Stattdessen werden **Funktionen des Kernels** eingesetzt um **isolierte Laufzeitumgebungen** zu erzeugen, die **Container** genannt werden
- Im Gegensatz zu einer VM können in Containern nur **Laufzeitumgebungen** virtualisiert werden, die den gleichen Kernel wie das Host-OS einsetzen
- Ein Container beinhaltet **kein vollwertiges Gast-OS**, sondern nur die **Abhängigkeiten**, die zum Betrieb einer Anwendung notwendig sind
- Bsp. Docker, Cri-o, BSD-Jails
![[Pasted image 20261008095040.png|250]]
cgroup: control group ns: namespaces

- Zur Erstellung der Container werden folgende Kernel-Funktionen verwendet:
	- **cgroups: Einschränkung der Nutzung von Ressourcen (bspw. Ram-Limit, CPU-Limit, Grafikkarte, Dateisystem)**
	- **namespaces: Einschränkung der Sichtbarkeitanderer Prozesse auf die eigenen Kindprozesse**
- Vorteil **Performance: Prozessvirtualisierung erreicht aufgrund der Leichtgewichtigkeit und minimalem Overhead nahezu native Anwendungsgeschwindigkeit und nativen Speicherbedarf**
- Nachteil **Isolation: Trotz Zugriffseinschränkungen sehen alle Containerprozesse die physische Hardware. Ferner gibt es Vorfälle in denen Angreifer aus Containerprozessen ausbrechen konnten.**
### Kontrast
![[Pasted image 20261008095830.png]]

![[Pasted image 20261008100057.png]]
![[Pasted image 20261008100129.png]]

Aufgabe 3:
a) Welche Einsatzszenarien eignen sich für die Voll-Virtualisierung und Prozessvirtualisierung an und welche sollten vermieden werden? 
#### VM
##### Do's
- Nutzung der nativen grafischen Oberfläche
- Voller Funktionsumfang des Betriebssystems benötigt
- Starke Isolation der virtualisierten Gäste
- Garantierte Ressourcenverfügbarkeit
-> Infragtrukturmanagement durch System-Admins
##### Dont's
- Bedarf an flexibel skalierbaren Anwendung (wg. Overhead)
- Einsatz im Enwicklungsprozess 
- Minimierung von Leerlauf
- Flexible Ressourcenzuteilung
-> Entwicklung & Betrieb von skalierbaren Anwendungen
#### Container
##### Do's
- Fokus liegt auf Entwicklung und Betrieb einer skalierten Anwendung
- Bedarf an flexibel skalierbaren Ressourcen
- Nur Teile des Betriebssystems werden benötigt
- Anwendung ausgelegt auf Modularisierung und horizontale Skalierung
- Gleiche Dev/Int/Prod Umgebungen
-> Entwicklung & Betrieb von skalierbaren Anwendungen
##### Dont's
- Nutzung der nativen grafischen Oberfläche
- Voller Funktionsumfang des Betriebssystems benötigt
- Starke Isolation der virtualisierten Gäste
- Garantierte Ressourcenverfügbarkeit
- Betireb monolothischer Anwendung
-> Infragtrukturmanagement durch System-Admins 



b) Was für Vorteile entstehen durch die Kombination von Voll-Virtualisierung und Prozessvirtualisierung? 
Kombination: In einer VM ein Container aufsetzen
![[Container in einer VM|200]]

-> optimierte Ressourcennutzung, Isolation des Gast-OS, Entkoppelung

Hohe Sicherheit und Isolation durch die VM.
Hohe Ressourceneffizienz durch Container.
Container können schnell skaliert werden.
Fehler in Containern bleiben innerhalb der VM isoliert.


c) Vergleichen Sie VM und Container hinsichtlich Gründe für Overhead (Speicher und CPU)? 
CPU: container: nur belegt, was gebraucht wird; vm: alles belegt
Overhead bei Vm durch:
- Abfangen und Übersetzzen von Hardwarebefehlen
- Defragmentierungsprozesse bei Host und Gast OS
- Speicher und Prozessmanagement bei Host und Gast OS
- Viele ungenutzee Programme und Hintergrundprozesse bei Gast OS
- Update und Patching von Host 

d) Welche Vorteile bietet die Prozessvirtualisierung für Entwicklung, Test und Betrieb?

Entwicklung: Abhängigkeiten werden mitgeladen, isoliert, 
Test:
Betrieb: