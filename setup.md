# Installation
## Einrichtung der Umgebung
Die Java-Architektur erlaubt es die NextBill Server-Version auf fast jedem System auszuführen. 
Hinsichtlich des Zugriffs lassen sich im Wesentlichen zwei Szenarien unterscheiden:

1. Sie installieren NextBill auf Ihrem NAS- oder Desktop-Computer (Windows, Mac oder ein unixiodes System) zu Hause. In diesem Fall haben Sie nur im lokalen Netzwerk (bspw. per WLAN) Zugriff. NextBill ist dann über eine IP in jedem Browser und in der Android-App erreichbar. Sobald Sie das Haus verlassen, schaltet die Android-App in den Offline-Modus, synchronisiert sich aber bei der Rückkehr. (empfohlen)

2. Sie installieren NextBill auf einem (Cloud-) Server. In diesem Fall können Sie von überall aus über einen Browser oder die Android-App auf Ihre Daten zugreifen. Bedenken Sie aber, dass diese Option fortgeschrittene Kenntnisse voraussetzt und höhere Sicherheitsrisiken birgt.

## Variationen
1. Manuelle Installation
2. Installation per Docker
`

### 1. Manuelle Installation

### Download
Bitte laden Sie die aktuelle Version der NextBill-Server Instanz von der Release-Seite auf GitHub herunter und kopieren Sie die Datei in einen Ordner Ihrer Wahl. Bitte geben Sie dem Ordner ausreichend Rechte, damit NextBill in diesem Ihre Datenbank-Datei verwalten kann.

**[Zur Release-Seite](https://github.com/nextbill-project/server/releases){:target="_blank"}**

### Setup auf dem System
1. Version 1.8 der Java-Laufzeitumgebung installieren. [Download](https://www.oracle.com/java/technologies/javase-jre8-downloads.html){:target="_blank"}
2. Legen Sie auf Ihrem System einen Ordner (mit ausreichenden Rechten) an.
3. Führen Sie das im  Abschnitt "Download" heruntergeladene "Jar"-Programm aus.

**Unter Windows oder Mac** Doppelklicken Sie auf das heruntergeladene Jar, warten Sie 10 Sekunden

**Unter unixoiden Systemen oder ohne Anzeige** Öffnen Sie ein Terminal und geben Sie ein:
```
cd 'Pfad/zur/jar'
java -jar nextbill.jar
```

4. Öffnen Sie danach einen Browser mit der URL [http://localhost:8010](http://localhost:8010){:target="_blank"} und folgen Sie dem Setup.
5. Laden Sie bei Bedarf die Android-App aus dem Play Store.

### 2. Installation per Docker

Das Setup per Docker gestaltet sich, natürlich Kenntnisse in Docker selbst vorausgesetzt, sehr einfach. Sie können das aktuelle Image vom DockerHub-Repository durch beispielsweise folgende Eingabe in die Shell (bitte den Tag mit der aktuellen Version ersetzen) laden:

`
  docker pull nextbillproject/server:v1.2
`

Sämtliche Daten werden im Container unter "/nextbill" gespeichert und der Port ist 8010. Ein Container mit diesem Image kann beispielsweise folgendermaßen gestartet werden:

`
docker run -v /host/system/path:/nextbill -p 8020:8010 nextbillproject/server:v1.2