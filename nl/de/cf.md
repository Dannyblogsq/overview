---


copyright:
  years: 2016, 2018
lastupdated: "2018-01-16"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Gemeinsames Funktionieren von Cloud Foundry mit {{site.data.keyword.cloud_notm}}
{: #howwork}

Wenn Sie auf Cloud Foundry eine App bereitstellen, muss {{site.data.keyword.cloud_notm}} mit genügend Informationen konfiguriert sein, um die App unterstützen zu können.

* Für mobile Apps enthält {{site.data.keyword.cloud_notm}} ein Artefakt, das das Back-End für die mobile App darstellt, z. B. die Services, die von der mobilen App verwendet werden, um mit einem Server zu kommunizieren.
* Für Web-Apps muss sichergestellt werden, dass {{site.data.keyword.cloud_notm}} Informationen zur Laufzeit und zum Framework erhält, sodass {{site.data.keyword.cloud_notm}} die richtige Ausführungsumgebung einrichten kann, in der die App ausgeführt wird.

Beide Ausführungsumgebungen, die für die mobile App
wie auch die für die Web-App, sind von den Ausführungsumgebungen anderer Apps isoliert. Die Ausführungsumgebungen werden isoliert, obwohl sich diese Apps auf derselben physischen Maschine befinden. Die folgende Abbildung stellt die grundlegenden Abläufe für die Verwaltung der App-Bereitstellung in {{site.data.keyword.cloud_notm}} durch Cloud Foundry dar:

![App bereitstellen](images/deploy.png)

Abbildung 1. App bereitstellen

Wenn Sie eine App erstellen und auf Cloud Foundry bereitstellen, bestimmt die {{site.data.keyword.cloud_notm}}-Umgebung einen geeigneten virtuellen Server, an den die App bzw. die Artefakte gesendet werden, die die App darstellt. Für mobile Apps wird auf {{site.data.keyword.cloud_notm}} eine mobile Back-End-Projektion erstellt. Jeder Code für die in der Cloud ausgeführte mobile App wird letztendlich in der {{site.data.keyword.cloud_notm}}-Umgebung ausgeführt. Für Web-Apps ist der Code, der in der Cloud ausgeführt wird, die App selbst, die der Entwickler auf {{site.data.keyword.cloud_notm}} bereitstellt. Welcher virtuelle Server dafür ausgesucht wird, basiert auf mehreren Faktoren, wie zum Beispiel:

* Die bestehende Auslastung der Maschine
* Von diesem virtuellen Server unterstützte Laufzeiten oder Frameworks

Nachdem ein virtueller Server ausgewählt wurde, installiert ein Anwendungsmanager auf jedem virtuellen Server das passende Framework und die passende Laufzeit für die App. Anschließend kann die App in diesem Framework bereitgestellt werden. Sobald die Bereitstellung erfolgt ist, werden die Anwendungsartefakte gestartet.

Die folgende Abbildung zeigt die Struktur eines virtuellen Servers, auch als Droplet Execution Agent (DEA) bezeichnet, auf dem mehrere Apps bereitgestellt wurden:

![Struktur eines virtuellen Servers](images/container-diego.png)

Abbildung 2. Struktur eines virtuellen Servers

In jedem virtuellen Server kommuniziert ein Anwendungsmanager mit der übrigen {{site.data.keyword.cloud_notm}}-Infrastruktur und verwaltet die Apps, die auf diesem virtuellen Server bereitgestellt sind. Jeder virtuelle Server verfügt über Container zum Trennen und Schützen der Apps. In jedem dieser Container installiert {{site.data.keyword.cloud_notm}} das geeignete Framework und die geeignete Laufzeit, die für die einzelnen Apps erforderlich sind.

Wenn die
App bereitgestellt wurde und über eine Webschnittstelle (wie für eine Java-Web-App)
oder andere REST-basierte Services (z. B. mobile Services, die für die mobile App öffentlich zugänglich sind)
verfügt, können Benutzer der App durch normale HTTP-Anforderungen mit ihr kommunizieren.

![{{site.data.keyword.cloud_notm}}-App aufrufen](images/execute.png)

Abbildung 3. {{site.data.keyword.cloud_notm}}-App aufrufen

Jeder App kann mindestens eine URL zugeordnet sein, aber jede dieser URLs muss auf den {{site.data.keyword.cloud_notm}}-Endpunkt verweisen. Wenn eine Anforderung eintrifft, prüft {{site.data.keyword.cloud_notm}} diese Anforderung, stellt fest, an welche App sie gerichtet ist, und wählt eine der Instanzen der App für den Empfang der Anforderung aus.


## Cloud Foundry-Architektur in {{site.data.keyword.cloud_notm}}
{: #architecture}

Im Allgemeinen müssen Sie sich bei der Ausführung von Apps auf {{site.data.keyword.cloud_notm}} in Cloud Foundry keine Gedanken über die Betriebssystem- und Infrastrukturebenen machen. Die Ebenen wie Stammdateisysteme und
Middlewarekomponenten sind so abstrahiert, dass Sie sich auf Ihren Anwendungscode
konzentrieren können. Es gibt jedoch noch weitere Informationen zu diesen Ebenen, wenn Sie
spezielle Angaben dazu benötigen, wo Ihre App ausgeführt wird.

Details finden Sie im Abschnitt zum [Anzeigen von {{site.data.keyword.cloud_notm}}-Infrastrukturebenen](cf.html#infralayers).

Als Entwickler haben Sie die Möglichkeit, über eine browserbasierte Benutzerschnittstelle mit der
{{site.data.keyword.cloud_notm}}-Infrastruktur zu interagieren. Zum
Bereitstellen von Web-Apps können Sie außerdem die Cloud
Foundry-Befehlszeilenschnittstelle 'cf' verwenden.

Clients - mobile Apps, extern ausgeführte Apps, auf {{site.data.keyword.cloud_notm}} aufbauende Apps oder auch Entwickler, die gerade einen Browser verwenden - können mit den von {{site.data.keyword.cloud_notm}} gehosteten Apps interagieren. Mithilfe von REST- oder HTTP-APIs leiten Clients Anforderungen über
{{site.data.keyword.cloud_notm}} an eine der
App-Instanzen oder an die zusammengesetzten Services weiter.

In der folgenden Abbildung ist die allgemeine Cloud Foundry-Architektur unter {{site.data.keyword.cloud_notm}} dargestellt.

![{{site.data.keyword.cloud_notm}}-Architektur](images/arch.png)

Abbildung 4. Cloud Foundry-Architektur unter {{site.data.keyword.cloud_notm}}

Sie können Ihre Apps im Hinblick auf Latenz- und Sicherheitsaspekte für unterschiedliche
{{site.data.keyword.cloud_notm}}-Regionen
bereitstellen. Eine Bereitstellung
kann entweder in einer Region oder in mehreren Regionen stattfinden.


![Anwendungsentwicklung in mehreren Regionen](images/multi-region.png)

Abbildung 5. Anwendungsbereitstellung in mehreren Regionen

{{site.data.keyword.Bluemix_notm}}-Infrastrukturebenen
{: #infralayers}


{{site.data.keyword.Bluemix_notm}} abstrahiert und verdeckt Betriebssystem- und Infrastrukturebenen, damit diese von Ihnen nicht verwaltet werden müssen. Manchmal kann es jedoch wünschenswert sein, mehr über das Betriebssystem und die Middleware für Ihre App zu wissen.
{:shortdesc}

### {{site.data.keyword.Bluemix_notm}}-Infrastrukturebenen anzeigen
{: #viewinfra}

Sie können den Befehl **bluemix app stacks** ausführen, um die verfügbaren Stacks bzw. Rootdateisysteme anzuzeigen, auf denen Ihre Apps bereitgestellt werden sollen. Sie können bei der Verwendung des Befehls **bluemix app push** mit der Option *-s* und dem Stacknamen in *stack_name* auch den Stack angeben; dabei ist der 'stack_name' das Stammdateisystem, zum Beispiel `lucid64` oder `cflinuxfs2`:

```
bluemix app push appName -s stack_name
```

Mithilfe des Befehls `cf buildpacks` können Sie die Middlewarekomponenten anzeigen, z. B. WebSphere Liberty Profile und SDK for Node.js; diese sind als Laufzeiten für die Ausführung Ihrer App verfügbar. Des Weiteren können Sie mithilfe des folgenden Befehls
die Laufzeitumgebung für Ihre App angeben:

```
bluemix app push appName -b buildpackname
```

## Regionen
{: #ov_intro_reg}

Eine {{site.data.keyword.cloud_notm}} Foundry Service-Region ist ein definiertes geografisches Gebiet, in dem Sie Ihre Apps bereitstellen können. Sie können Apps und Serviceinstanzen in unterschiedlichen Regionen mit derselben {{site.data.keyword.cloud_notm}}-Infrastruktur für das Anwendungsmanagement und dieselbe Ansicht mit den Nutzungsdetails zur Gebührenabrechnung erstellen. Sie können Ihre Apps in der Region bereitstellen, die Ihren Kunden am nächsten ist, um eine geringe Latenzzeit zu erreichen. Zum Beheben von Sicherheitsproblemen können Sie auch die Region auswählen, in der die Anwendungsdaten aufbewahrt werden sollen. Wenn Sie Apps in mehreren Regionen erstellen, werden die Apps in den anderen Regionen weiter ausgeführt, falls eine Region nicht mehr verfügbar ist. Die verfügbaren Ressourcen
sind für jede verwendete Region gleich.

Wenn Sie die {{site.data.keyword.cloud_notm}}-Konsole verwenden, werden Ihnen automatisch die Informationen für die am nächsten gelegene geografische Region angezeigt, die sich in einwandfreiem Zustand befindet. Der globale Lastausgleich für die Konsole stellt sicher, dass in dem Fall, dass Ihre nächste geografische Region aus irgendeinem Grund inaktiv ist, Ihre Konsole die Informationen für die nächstgelegene Region anzeigt. Auf diese Weise haben Sie immer Zugriff auf die Konsole, ohne Maßnahmen ergreifen zu müssen, um auf die benötigten Informationen zugreifen zu können.

Verwenden Sie die Regionenauswahl in der Konsole, um Ihre Ansicht zu filtern. Wenn Sie beispielsweise in Ihrer Region Dallas, USA, auf Ihre Apps und Services zugreifen, aber Ihre Apps und Services für die Region London anzeigen möchten, können Sie mit der Regionenauswahl Ihre Ansicht ändern:

1. Klicken Sie auf den Link für Benutzerkontovorgaben.
2. Erweitern Sie das Menü **Region**.
3. Wählen Sie die erforderliche Region aus der Liste aus.

Durch Filtern Ihrer Ansicht nach Region können Sie auch schnell zwischen Ansichten wechseln, um mit Organisationen, Bereichen und Benutzern zu arbeiten, die den verschiedenen Regionen zugeordnet sind.

Wenn Sie die Befehlszeilenschnittstelle 'cf' verwenden, um eine Verbindung zu der {{site.data.keyword.cloud_notm}}-Region herzustellen, mit der Sie arbeiten möchten, verwenden Sie den Befehl 'cf api' und geben Sie den API-Endpunkt der Region an. Geben Sie beispielsweise den folgenden Befehl ein, um eine Verbindung zu der
{{site.data.keyword.cloud_notm}}-Region 'Europe
United Kingdom' herzustellen:

```
cf api https://api.eu-gb.bluemix.net
```

Jeder Region wird ein eindeutiges Präfix zugewiesen. Für {{site.data.keyword.cloud_notm}}
stehen die folgenden Regionen und Regionspräfixe zur Verfügung.

| **Regionsname** | **Standort** | **cf-API-Endpunkt** |
|-----------------|-------------------------|-------------------|
| Region 'Vereinigte Staaten (Süden)' | Dallas, US | api.ng.bluemix.net | 
| Region 'Vereinigte Staaten (Osten)' | Washington, DC, US | api.us-east.bluemix.net |
| Region 'Vereinigtes Königreich' | London, England | api.eu-gb.bluemix.net | 
| Region 'Sydney' | Sydney, Australien | api.au-syd.bluemix.net | 
| Region 'Deutschland' | Frankfurt, Deutschland | api.eu-de.bluemix.net | 
{: caption="Tabelle 1. Liste der {{site.data.keyword.cloud_notm}}-Regionen" caption-side="top"}

## Ausfallsicherheit von {{site.data.keyword.cloud_notm}}
{: #resiliency}

{{site.data.keyword.cloud_notm}} wurde zum Hosten skalierbarer, ausfallsicherer Apps und Anwendungsartefakte entwickelt, die eine bedarfsorientierte Skalierung ermöglichen und gleichzeitig hohe Verfügbarkeit und rasche Wiederherstellbarkeit nach Fehlern bieten. {{site.data.keyword.cloud_notm}} unterscheidet zwischen Komponenten, die den Zustand von Interaktionen verfolgen (mit Zustandsüberwachung) und Komponenten, die dies nicht tun (ohne Zustandsüberwachung). Diese Unterscheidung ermöglicht es {{site.data.keyword.cloud_notm}}, Apps so flexibel wie nötig zu verschieben, um Skalierbarkeit und Ausfallsicherheit zu erreichen.

Sie können für Ihre App eine oder mehrere Instanzen ausführen. Bei mehreren Instanzen für eine App wird die App nur einmal hochgeladen. {{site.data.keyword.cloud_notm}} implementiert jedoch die angeforderte Anzahl der App-Instanzen und verteilt sie auf so viele virtuelle Server wie möglich.

Sie müssen alle persistenten Daten in einem Datenspeicher mit Zustandsüberwachung speichern, der sich außerhalb Ihrer App befindet, wie z. B. einer der von {{site.data.keyword.cloud_notm}} bereitgestellten Datenspeicherservices. Da alle im Hauptspeicher oder auf Platte zwischengespeicherten Daten selbst nach einem Neustart möglicherweise nicht verfügbar sind, können Sie die Hauptspeicherkapazität oder das Dateisystem einer einzelnen {{site.data.keyword.cloud_notm}}-Instanz als Kurzzeitcache für eine einzelne Transaktion verwenden. Bei einem Einzelinstanzsetup wird die Anforderung
an Ihre App aufgrund der Tatsache, dass es für {{site.data.keyword.cloud_notm}}
keine Zustandsüberwachung gibt, möglicherweise unterbrochen. Bewährt hat sich die Verwendung von mindestens drei Instanzen für jede App, um ihre Verfügbarkeit sicherzustellen.

Die gesamte
{{site.data.keyword.cloud_notm}}-Infrastruktur, die Cloud
Foundry-Komponenten und für {{site.data.keyword.cloud_notm}} spezifische Verwaltungskomponenten stellen eine hohe Verfügbarkeit sicher. Zum Lastausgleich
werden mehrere Instanzen der Infrastruktur verwendet.

## Integration mit Systems of Record (Kerndatensystemen)
{: #sor}

{{site.data.keyword.cloud_notm}} kann Entwicklern durch die Verbindung zweier allgemeiner Systemkategorien in einer Cloudumgebung Hilfestellung leisten:

* *Systems of Record* umfassen Apps und Datenbanken, die Geschäftsberichte speichern und
standardisierte Prozesse automatisieren.
* *Systems of Engagement* sind Funktionen, die den Nutzen
von Systems of Record erweitern und für Benutzer attraktiver machen.

Durch die Integration eines System of Record in die App, die Sie in
{{site.data.keyword.cloud_notm}} erstellen,
können Sie die folgenden Aktionen durchführen:

 * Einrichten einer sicheren Kommunikation zwischen der App und der Back-End-Datenbank durch Herunterladen und Installation eines lokalen sicheren Connectors
 * Aufrufen einer Datenbank mit einer sicheren Methode
 * Erstellen von APIs aus Integrationsflüssen mit Datenbanken und Back-End-Systemen wie z. B. einem System für Customer-Relationship-Management
 * Zugänglichmachen nur derjenigen Schemas und Tabellen, die Sie der App zugänglich machen wollen
 * Als {{site.data.keyword.cloud_notm}}-Organisationsmanager:
Veröffentlichen einer API als privaten Service, der nur für die Mitglieder Ihrer Organisation sichtbar ist

Um ein System of Record in die App zu integrieren, die Sie in {{site.data.keyword.cloud_notm}} erstellen,
können Sie den Cloud Integration-Service verwenden. Wenn Sie den Cloud Integration-Service
verwenden, können Sie eine Cloud Integration-API erstellen
und die API als privaten Service für Ihre Organisation veröffentlichen.

<dl>
<dt>Cloud Integration-API</dt>
    <dd>Mit einer Cloud Integration-API haben Sie über Web-APIs sicheren Zugriff auf die Systems of Record, die sich hinter einer Firewall befinden. Bei der Erstellung der
Cloud Integration-API wählen Sie die Ressource aus,
auf die Sie über die Web-API zugreifen möchten, geben die zulässigen Operationen
an und beziehen die SDKs und Beispiele für den Zugriff auf die API ein. Weitere Informationen zur Erstellung
einer Cloud Integration-API finden sie unter
[Erste Schritte mit Cloud Integration](/docs/services/CloudIntegration/CldInt_GetStart.html).</dd>
<dt>Privater Service</dt>
    <dd>Ein privater Service besteht aus einer Cloud Integration-API,
SDKs und Berechtigungsrichtlinien. Der private Service kann außerdem Dokumentation oder andere Elemente des Service-Providers enthalten. Eine Cloud Integration-API kann nur vom Organisationsmanager als privater Service veröffentlicht werden. Wenn Sie die
für Sie zur Verfügung stehenden privaten Services anzeigen möchten, wählen Sie
im {{site.data.keyword.cloud_notm}}-Katalog das Kontrollkästchen 'Privat' aus. Sie können einen privaten Service auswählen und ihn an eine App binden, ohne dass eine Verbindung zum
Cloud Integration-Service erforderlich wäre. Private Services werden wie andere
{{site.data.keyword.cloud_notm}}-Services auch
an Ihre App gebunden. Weitere Informationen zur Veröffentlichung einer API als privaten Service finden Sie im Thema zur Veröffentlichung einer API als privaten Service.</dd>
</dl>

### Szenario: Erstellen einer umfangreichen mobilen App, die mit Ihrem System of Record verbunden werden soll
{: #scenario}

{{site.data.keyword.cloud_notm}} bietet eine Plattform,
auf der Sie ihre mobile App, Cloud-Services und Systems of Record von Unternehmen integrieren können, um eine App einzurichten,
die mit Ihren lokalen Daten interagiert.

Sie können beispielsweise eine mobile App aufbauen, die
mit Ihrem Customer-Relationship-Managementsystem interagiert, welches sich lokal hinter einer Firewall
befindet. Sie können auf sicherem Weg ein System of Record aufrufen und die mobilen Services in
{{site.data.keyword.cloud_notm}} zum Aufbau
einer umfangreichen mobilen App nutzen.

Zunächst erstellt Ihr Integrationsentwickler in {{site.data.keyword.cloud_notm}} die mobile Back-End-App. Er verwendet die Boilerplate aus Mobile Cloud mit der Node.js-Laufzeit, mit der er am besten vertraut ist.

Unter Verwendung des Cloud Integration-Service in der {{site.data.keyword.cloud_notm}}-Benutzerschnittstelle macht er über einen sicheren Connector eine API zugänglich. Ihr Integrationsentwickler lädt den sicheren
Connector herunter und installiert ihn lokal, um eine sichere Kommunikation zwischen seiner API und der
Datenbank zu ermöglichen. Nachdem er den Datenbankendpunkt erstellt hat, kann er sich alle Schemas ansehen und diejenigen Tabellen extrahieren, die er der App als APIs zugänglich machen will.

Um interessierten Kunden mobile Benachrichtigungen senden zu können, fügt der Integrationsentwickler den Push-Service hinzu. Außerdem nimmt er einen Geschäftspartnerservice auf, der über eine Twitter-API einen Tweet versendet, sobald ein neuer Satz von Kundenstammdaten erstellt wird.

Als Nächstes können Sie sich als Anwendungsentwickler bei
{{site.data.keyword.cloud_notm}} anmelden,
das Android-Entwicklungstoolkit herunterladen und Code entwickeln, mit dem die APIs aufgerufen werden, die
Ihr Integrationsentwickler eingerichtet hat. Sie können eine mobile App entwickeln, die es dem Benutzer
ermöglicht, über sein mobiles Gerät Informationen einzugeben. Die mobile App erstellt daraufhin im
Customer-Managementsystem einen Kundenstammdatensatz. Nachdem der Datensatz erstellt ist, übermittelt die
App per Push-Operation eine Benachrichtigung an ein mobiles Gerät und leitet einen Tweet zu dem neuen
Datensatz ein.
