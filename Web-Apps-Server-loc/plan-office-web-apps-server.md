---
title: Planen von Office Web Apps Server
TOCTitle: Planen von Office Web Apps Server
ms:assetid: 2e147f11-6f47-46bc-90bf-b2f179958d11
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219435(v=office.15)
ms:contentKeyID: 49633153
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Planen von Office Web Apps Server

 

**Gilt für:** Office Web Apps Server

**Letztes Änderungsdatum des Themas:** 2017-10-10

**Zusammenfassung:** Informationen zu Anforderungen und Voraussetzungen von Office Web Apps Server wie HTTPS, Zertifikate, Virtualisierung, Lastenausgleich, Topologien und Sicherheit.

**Zielgruppe:** IT-Spezialisten

Office Web Apps Server stellt browserbasierte Versionen von Office-Apps in einer lokalen Umgebung bereit, wodurch Benutzern größere Flexibilitäts- und Zusammenarbeitsmöglichkeiten verliehen werden. In diesem Artikel werden die Anforderungen und Schritte erläutert, die zum Installieren von Office Web Apps Server in Ihrer Organisation erforderlich sind.

Das Vorgehen müssen Sie sorgfältig planen, damit alle Hosts, also SharePoint 2013 und Lync Server 2013, mit dem Office Web Apps Server kommunizieren können. Weitere Anleitungen zum Konfigurieren von Hosts finden Sie in den folgenden Ressourcen:

  - [Planen von Office Web Apps (verwendet mit SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)

  - [Bereitstellen von Office Web Apps Server und Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)


> [!TIP]
> SharePoint 2010-Produkte kann kein Host für Office Web Apps Server sein. Office Web Apps Server wird nicht von SharePoint Foundation 2010 oder SharePoint Server 2010 unterstützt. Office Web Apps Server wird auch nicht von Exchange Server 2013 unterstützt.



Inhalt dieses Artikels:

  - Software-, Hardware- und Konfigurationsanforderungen für Office Web Apps Server

  - Unterstützung für die Virtualisierung von Office Web Apps Server

  - Firewallanforderungen für Office Web Apps Server

  - Lastenausgleichsanforderungen für Office Web Apps Server

  - DNS-Anforderungen für Office Web Apps Server

  - Planen von Sprachpaketen für Office Web Apps Server

  - Topologieplanung für Office Web Apps Server

  - Sicherheitsplanung für Office Web Apps Server

  - Planen für Onlineviewer mit Office Web Apps Server

  - Planen von Updates für Office Web Apps Server

## Software-, Hardware- und Konfigurationsanforderungen für Office Web Apps Server

Sie können Office Web Apps Server als einzelne Office Web Apps Server-Serverfarm oder als Office Web Apps Server-Farm mit mehreren Servern und Lastenausgleich installieren. Sie können physische Server oder virtuelle Computerinstanzen verwenden, Sie können jedoch keine anderen Serveranwendungen auf dem Server installieren, auf dem der Office Web Apps Server installiert ist (z. B. SharePoint 2013 oder SQL Server).

In Umgebungen, die tatsächliche Benutzerdaten enthalten, wird die Verwendung von HTTPS empfohlen, für das Sie ein Zertifikat abrufen müssen. Wenn Sie in Ihrer Farm mehrere Server verwenden, müssen Sie eine Lösung für den Hardware- oder Softwarelastenausgleich konfigurieren. Weitere Informationen zu diesen Szenarien finden Sie in den folgenden Abschnitten.

## Hardwareanforderungen für Office Web Apps Server

Für Office Web Apps Server gelten dieselben Mindesthardwareanforderungen wie für SharePoint Server 2013. Eine Auflistung aller SharePoint 2013-Anforderungen finden Sie unter [Hardware requirements—web servers, application servers, and single server installations](https://technet.microsoft.com/de-de/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver).

## Unterstützte Betriebssysteme für Office Web Apps Server

Sie können Office Web Apps Server unter folgenden Betriebssystemen ausführen:

  - Die 64-Bit-Edition von Windows Server 2008 R2 Service Pack 1 (SP1) Standard, Enterprise oder Datacenter mit installiertem [Update für Windows Server 2008 R2 x64 Edition](https://go.microsoft.com/fwlink/p/?linkid=236954)

  - Die 64-Bit-Edition von Windows Server 2012 Standard, Enterprise oder Datacenter

  - Die 64-Bit-Edition von Windows Server 2012 R2. Damit Sie dieses Betriebssystem verwenden können, müssen Sie Office Web Apps Server Service Pack 1 (SP1) verwenden.

## Domänenanforderungen für Office Web Apps Server

Alle Server in der Office Web Apps Server-Farm müssen Teil einer Domäne sein. Sie können sich in derselben Domäne (bewährte Methode) oder in Domänen innerhalb derselben Gesamtstruktur befinden. Office Web Apps Server funktioniert jedoch nicht, wenn Sie versuchen, ihn auf einem Domänencontroller zu installieren.

## Serverrollen, Dienste und andere Software, die für Office Web Apps Server erforderlich sind

Zunächst finden Sie hier ein paar Dinge, die Sie bei der Bereitstellung von Office Web Apps Server vermeiden sollten.

  - **Auf Servern, auf denen Office Web Apps Server** ausgeführt wird, darf keine andere Serveranwendung ausgeführt werden. Hierzu gehören Exchange Server, SharePoint Server, Lync Server und SQL Server. Wenn Hardwareeinschränkungen bestehen, können Sie Office Web Apps Server in einer Instanz eines virtuellen Computers auf einem dieser Server ausführen.

  - **Installieren Sie keine Dienste oder Rollen, die von der Rolle "Webserver (IIS)" an Port 80, 443 oder 809** abhängen, da Office Web Apps Server regelmäßig Webanwendungen an diesen Ports entfernt.

  - **Installieren Sie keine Version von Office**. Falls es bereits installiert ist, müssen Sie es deinstallieren, bevor Sie Office Web Apps Server installieren.

  - **Installieren Sie Office Web Apps Server nicht auf einem Domänencontroller**. Es funktioniert nicht auf einem Server, auf dem Active Directory-Domänendienste (AD DS) ausgeführt werden.

Details zu den Elementen, die Sie installieren müssen, finden Sie in der folgenden Tabelle.


> [!IMPORTANT]
> Office Web Apps Server ist nur im <A href="https://go.microsoft.com/fwlink/p/?linkid=256561">Volume Licensing Service Center (VLSC)</A> zum Download verfügbar. Zum Herunterladen von Office Web Apps Server benötigen Sie eine Lizenz unter einem Volumenlizenzvertrag für Office Professional Plus 2013, Office Standard 2013 oder Office für Mac 2011. Der Download befindet sich unter den Office-Produkten im VLSC-Portal.



### Für Office Web Apps Server erforderliche Downloads, Serverrollen und Features

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Download, Serverrolle oder Feature</th>
<th>Bei Installation unter Windows Server 2008 R2</th>
<th>Bei Installation unter Windows Server 2012</th>
<th>Bei Installation unter Windows Server 2012 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Download:</strong> Office Web Apps Server</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Office Web Apps Server</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Office Web Apps Server</a></p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256561">Office Web Apps Server</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Download:</strong> Office Web Apps Server SP1</p></td>
<td><p>Empfohlen</p></td>
<td><p>Empfohlen</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510097">Office Web Apps Server SP1</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Download:</strong> Richtige Version von .NET Framework</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=256560">.NET Framework 4.5</a></p></td>
<td><p>.NET framework 4.5 ist bereits installiert</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=510096">.NET Framework 4.5.2</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Download:</strong> Update für Windows Server 2008 R2 x64 Edition</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=236954">Update für Windows Server 2008 R2 x64 Edition</a></p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>Nicht zutreffend</p></td>
</tr>
<tr class="odd">
<td><p><strong>Download:</strong> Windows PowerShell 3.0</p></td>
<td><p><a href="https://go.microsoft.com/fwlink/p/?linkid=244693">Windows PowerShell 3.0</a></p></td>
<td><p>Bereits installiert</p></td>
<td><p>Bereits installiert</p></td>
</tr>
<tr class="even">
<td><p><strong>Serverrolle:</strong> Webserver (IIS)</p></td>
<td><p>Nachstehend werden die Rollendienste beschrieben, die für die Serverrolle <strong>Webserver (IIS)</strong> mindestens erforderlich sind.</p>
<p><strong>Allgemeine HTTP-Features</strong></p>
<ul>
<li><p>Statische Inhalte</p></li>
<li><p>Standarddokument</p></li>
</ul>
<p><strong>Anwendungsentwicklung</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET-Erweiterbarkeit</p></li>
<li><p>ISAPI-Erweiterungen</p></li>
<li><p>ISAPI-Filter</p></li>
<li><p>Serverseitige Includes</p></li>
</ul>
<p><strong>Sicherheit</strong></p>
<ul>
<li><p>Windows-Authentifizierung</p></li>
<li><p>Anforderungsfilterung</p></li>
</ul>
<p><strong>Verwaltungstools</strong></p>
<ul>
<li><p>IIS-Verwaltungskonsole</p></li>
</ul>
<p>Die folgenden Optionen werden empfohlen, sind aber nicht erforderlich:</p>
<p><strong>Leistung</strong></p>
<ul>
<li><p>Komprimierung statischer Inhalte</p></li>
<li><p>Komprimierung dynamischer Inhalte</p></li>
</ul></td>
<td><p>Nachstehend werden die Rollendienste beschrieben, die für die Serverrolle <strong>Webserver (IIS)</strong> mindestens erforderlich sind.</p>
<p><strong>Verwaltungstools</strong></p>
<ul>
<li><p>IIS-Verwaltungskonsole</p></li>
</ul>
<p><strong>Webserver</strong></p>
<ul>
<li><p>Allgemeine HTTP-Features</p></li>
<li><p>Standarddokument</p></li>
<li><p>Statischer Inhalt</p></li>
</ul>
<p><strong>Sicherheit</strong></p>
<ul>
<li><p>Anforderungsfilterung</p></li>
<li><p>Windows-Authentifizierung</p></li>
</ul>
<p><strong>Anwendungsentwicklung</strong></p>
<ul>
<li><p>.NET-Erweiterbarkeit 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>ISAPI-Erweiterungen</p></li>
<li><p>ISAPI-Filter</p></li>
<li><p>Serverseitige Includes</p></li>
</ul>
<p>Die folgenden Dienste werden empfohlen, sind aber nicht erforderlich:</p>
<p><strong>Leistung</strong></p>
<ul>
<li><p>Komprimierung statischer Inhalte</p></li>
<li><p>Komprimierung dynamischer Inhalte</p></li>
</ul></td>
<td><p>Nachstehend werden die Rollendienste beschrieben, die für die Serverrolle <strong>Webserver (IIS)</strong> mindestens erforderlich sind.</p>
<p><strong>Verwaltungstools</strong></p>
<ul>
<li><p>IIS-Verwaltungskonsole</p></li>
</ul>
<p><strong>Webserver</strong></p>
<ul>
<li><p>Allgemeine HTTP-Features</p></li>
<li><p>Standarddokument</p></li>
<li><p>Statischer Inhalt</p></li>
</ul>
<p><strong>Sicherheit</strong></p>
<ul>
<li><p>Anforderungsfilterung</p></li>
<li><p>Windows-Authentifizierung</p></li>
</ul>
<p><strong>Anwendungsentwicklung</strong></p>
<ul>
<li><p>.NET-Erweiterbarkeit 4.5</p></li>
<li><p>ASP.NET 4.5</p></li>
<li><p>ISAPI-Erweiterungen</p></li>
<li><p>ISAPI-Filter</p></li>
<li><p>Serverseitige Includes</p></li>
</ul>
<p>Die folgenden Dienste werden empfohlen, sind aber nicht erforderlich:</p>
<p><strong>Leistung</strong></p>
<ul>
<li><p>Komprimierung statischer Inhalte</p></li>
<li><p>Komprimierung dynamischer Inhalte</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Feature:</strong> Freihand- und Handschriftdienste</p></td>
<td><p><strong>Freihand- und Handschriftdienste</strong></p>
<ul>
<li><p>Freihandunterstützung</p></li>
</ul></td>
<td><p><strong>Freihand- und Handschriftdienste</strong></p>
<ul>
<li><p>Freihandunterstützung ist nicht erforderlich.</p></li>
</ul></td>
<td><p><strong>Freihand- und Handschriftdienste</strong></p>
<ul>
<li><p>Freihandunterstützung ist nicht erforderlich.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Unterstützung für die Virtualisierung von Office Web Apps Server

Office Web Apps Server wird vollständig unterstützt, wenn Sie die Software mit der Windows ServerHyper-V-Technologie bereitstellen. Beachten Sie folgende Richtlinien, wenn Sie die Virtualisierung von Office Web Apps Server planen:

  - Installieren Sie Office Web Apps Server in einer eigenen Instanz des virtuellen Computers. Installieren Sie in dieser Instanz keine anderen Serveranwendungen, z. B. SharePoint 2013.

  - Falls erforderlich, können Sie Office Web Apps Server in einer Instanz des virtuellen Computers installieren, die von einem Server gehostet wird, auf dem SharePoint 2013 ausgeführt wird.

  - Bei Office Web Apps Server-Farmen mit mehreren Servern, sollte sich jede Instanz auf einem separaten Host für virtuelle Computer befinden, damit die Office Web Apps Server-Farm weiterhin verfügbar ist, falls einer der Hosts ausfällt.

## Firewallanforderungen für Office Web Apps Server

Firewalls können Probleme verursachen, da diese die Kommunikation zwischen dem Webbrowser, den Servern mit Office Web Apps Server und den Servern mit SharePoint 2013 blockieren. Eine blockierte Kommunikation ist insbesondere problematisch, wenn diese Komponenten sich in verschiedenen Teilen eines Netzwerks befinden.

Stellen Sie sicher, dass die folgenden Ports auf keinem Server, auf dem Office Web Apps Server oder der Lastenausgleich ausgeführt werden, durch Firewalls blockiert sind:

  - Port 443 für HTTPS-Datenverkehr

  - Port 80 für HTTP-Datenverkehr

  - Port 809 für privaten Datenverkehr zwischen den Servern, auf denen Office Web Apps Server ausgeführt wird (wenn Sie eine Farm mit mehreren Servern ausführen)

## Lastenausgleichsanforderungen für Office Web Apps Server

Eine Lastenausgleichslösung wird empfohlen, wenn Sie Office Web Apps Server auf zwei oder mehr Servern ausführen. Sie können eine beliebige Lastenausgleichslösung verwenden. Hierzu gehört ein Server, auf dem die Rolle "Webserver (IIS)" mit Routing von Anwendungsanforderungen (ARR) ausgeführt wird. Tatsächlich können Sie ARR auf einem der Server ausführen, auf denen Office Web Apps Server ausgeführt wird. Wenn Sie keine Lastenausgleichslösung haben, finden Sie hier einige Ressourcen für die Verwendung von Internetinformationsdiensten (IIS) mit ARR:

  - [Installieren von Routing von Anwendungsanforderungen](https://go.microsoft.com/fwlink/?linkid=236955)

  - [Hilfe zu Routing von Anwendungsanforderungen](https://go.microsoft.com/fwlink/?linkid=236956)

Im Idealfall unterstützt die Lastenausgleichslösung, die Sie auswählen, die folgenden Features:

  - Layer 7-Routing

  - Aktivieren der Clientaffinität oder Front-End-Affinität

  - Aktivieren der SSL-Verschiebung

Wenn Sie einen Lastenausgleich verwenden, müssen Sie das Zertifikat auf dem Server mit dem Lastenausgleich installieren, so wie unter Sichern der Office Web Apps Server-Kommunikation mit HTTPS beschrieben.

## DNS-Anforderungen für Office Web Apps Server

In Umgebungen, in denen HTTPS und Lastenausgleich verwendet werden, müssen Sie DNS aktualisieren, damit der vollqualifizierten Domänennamen (FQDN) des Zertifikats sich entweder in die IP-Adresse des Servers mit Office Web Apps Server oder in die IP-Adresse auflöst, die dem Lastenausgleich für die Office Web Apps Server-Farm zugewiesen ist.

## Planen von Sprachpaketen für Office Web Apps Server

Mit Office Web Apps Server 2013-Sprachpaketen können Benutzer webbasierte Office-Dateien aus SharePoint 2013-Dokumentbibliotheken, Outlook Web App (als Anlagenvorschau) und Lync 2013 (als PowerPoint-Übertragungen) in mehreren Sprachen anzeigen. Dies hängt jedoch von den Sprachen ab, die auf dem Host konfiguriert sind. Zum Anzeigen webbasierter Office-Dateien von Hosts in mehreren Sprachen müssen folgende Voraussetzungen erfüllt sein:

  - Der Host (z. B. SharePoint Server 2013 oder Lync Server 2013) ist zum Ausführen von Anwendungen in weiteren Sprachen konfiguriert. Der Prozess zum Installieren und Konfigurieren von Sprachpaketen auf dem Host ist unabhängig von der Sprachpaketinstallation in der Office Web Apps Server-Farm.

  - Die Sprachen werden auf allen Servern in der Office Web Apps Server-Farm installiert.

Laden Sie [die Sprachpakete für Office Web Apps Server hier herunter](https://go.microsoft.com/fwlink/p/?linkid=263945).

## Topologieplanung für Office Web Apps Server

Eine Office Web Apps Server-Topologie umfasst mindestens eine physische oder virtuelle Instanz von Office Web Apps Server und mindestens einen Host (z. B. einen Server, auf dem Lync Server 2013 oder SharePoint 2013 ausgeführt wird). Außerdem benötigen Sie einen Client-PC oder ein Gerät, der oder das sich mit einem der Hosts verbindet und die Office Web Apps-Funktion verwendet. Ausgehend von dieser Mindesttopoplogie können Sie entsprechend der Anforderungen Ihrer Organisation weitere Hosts und Server zu Ihrer Office Web Apps Server-Farm hinzufügen.

Die folgende Liste enthält Empfehlungen, die Sie berücksichtigen sollten, wenn Ihre Office Web Apps Server-Topologie komplexer wird.

  - **Planen der Redundanz.** Wenn Sie Instanzen virtueller Computer verwenden, müssen Sie aus Redundanzgründen darauf achten, dass sie sich auf separaten Hosts für virtuelle Computer befinden. Es ist kein Problem, wenn in anderen Instanzen auf dem Host Serveranwendungen ausgeführt werden. Sie dürfen nur keine anderen Serveranwendungen in der Instanz ausführen, in der Office Web Apps Server läuft.

  - **Bleiben Sie bei einem Rechenzentrum** Server in einer Office Web Apps Server-Farm müssen sich im gleichen Rechenzentrum befinden. Verteilen Sie die Server nicht geografisch. In der Regel benötigen Sie nur eine Farm, sofern Sie keine Sicherheitsanforderungen haben, für die ein isoliertes Netzwerk mit eigener Office Web Apps Server-Farm erforderlich ist.

  - **Je näher sich die Hosts beieinander befinden, desto besser.** Die Office Web Apps Server-Farm muss sich nicht in demselben Datencenter wie die Hosts befinden, für die Dienste bereitgestellt werden. Wenn Sie jedoch umfangreiche Bearbeitungen vornehmen, wird empfohlen, die Office Web Apps Server-Farm so nah wie möglich zu den Hosts zu platzieren. In Organisationen, die Office Web Apps hauptsächlich zum Anzeigen von Office-Dateien verwenden, ist dies weniger wichtig.

  - **Planen Sie Ihre Verbindungen.** Verbinden Sie alle Server in der Office Web Apps Server-Farm nur untereinander. Verwenden Sie zum Verbinden mit einem größeren Netzwerk eine Reverse-Proxy-Lastenausgleich-Firewall.

  - **Konfigurieren der Firewall für HTTP- oder HTTPS-Anforderungen.** Achten Sie darauf, dass die Firewall Server zulässt, auf denen Office Web Apps Server ausgeführt wird, damit HTTP- oder HTTPS-Anforderungen an Hosts initiiert werden können.

  - **Plan für die ein- und ausgehende Kommunikation.** Leiten Sie in einer Bereitstellung, die mit dem Internet verbunden ist, die gesamte ausgehende Kommunikation über ein NAT-Gerät. Verarbeiten Sie die gesamte eingehende Kommunikation in einer Farm mit mehreren Servern über ein Lastenausgleichsmodul.

  - **Achten Sie darauf, dass alle Server in der Office Web Apps Server-Farm zu einer Domäne zusammengeschlossen und Teil derselben Organisationseinheit sind.** Verwenden Sie den Parameter **FarmOU** im [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)-Cmdlet um zu verhindern, dass andere Server, die nicht dieser Organisationseinheit angehören, der Farm beitreten.

  - **Verwenden Sie für alle eingehenden Anforderungen das Hypertext Transfer Protocol Secure (HTTPS).**

  - **Falls Sie IPsec im Netzwerk bereitgestellt haben, verwenden Sie es zum Verschlüsseln von Datenverkehr zwischen den Servern.**

  - **Plan für die Office-Features, die das Internet nutzen.** Falls Sie Features wie Clipart und Übersetzungsdienste benötigen und die Server in der Farm keine Anforderungen an das Internet initiieren können, müssen Sie für die Office Web Apps Server-Farm einen Proxyserver konfigurieren. Dadurch werden HTTP-Anforderungen an externe Websites zugelassen.

## Sicherheitsplanung für Office Web Apps Server

Die folgenden Informationen geben einen ersten Überblick über die Sicherheitsrichtlinien für Office Web Apps Server.

## Sichern der Office Web Apps Server-Kommunikation mit HTTPS

Office Web Apps Server kann mit SharePoint 2013 und Lync Server 2013 über das HTTPS-Protokoll kommunizieren. Es wird dringend empfohlen, in Produktionsumgebungen HTTPS zu verwenden. Sie müssen ein Internetserverzertifikat installieren, das dem Server zugewiesen werden kann, auf dem Office Web Apps Server (bei Verwendung eines einzelnen Servers) oder der Lastenausgleich (bei Verwendung mehrerer Server mit Office Web Apps Server) ausgeführt wird.

In Testumgebungen, die keine Benutzerdaten enthalten, können Sie HTTP für SharePoint 2013 verwenden und die Zertifikatanforderung überspringen. Lync Server 2013 unterstützt nur HTTPS.

Zertifikate, die von Office Web Apps Server verwendet werden, müssen die folgenden Anforderungen erfüllen:

  - Das Zertifikat muss von einer vertrauenswürdigen Zertifizierungsstelle stammen und den vollqualifizierten Domänennamen (FQDN) Ihrer Office Web Apps Server-Farm im Feld SAN (Alternativer Antragstellername) enthalten. (Ist der FQDN nicht im Feld SAN angegeben, wenn Sie das Zertifikat verwenden, zeigt der Browser Sicherheitswarnungen an oder verarbeitet die Anforderung nicht.)

  - Das Zertifikat muss einen exportierbaren privaten Schlüssel haben. Diese Option ist bei Farmen mit nur einem Server standardmäßig aktiviert, wenn Sie das Snap-In Internet Information Services (IIS)-Manager verwenden, um das Zertifikat zu importieren.

  - Das Feld Anzeigename muss im Speicher für vertrauenswürdige Stammzertifizierungsstellen eindeutig sein. Wenn Sie mehrere Zertifikate mit einem gemeinsamen Feld Anzeigename haben, schlägt die Farmerstellung fehl, da dem "New-OfficeWebAppsFarm"-Cmdlet nicht bekannt ist, welches dieser Zertifikate verwendet werden soll.

  - Office Web Apps Server benötigt keine besonderen Zertifikateigenschaften oder Erweiterungen. Die Client-EKU- oder Server-EKU-Erweiterungen (Enhanced Key Usage) sind nicht erforderlich.

  - Auf Windows Server 2012 oder Windows Server 2012 R2 müssen Sie die WCF-Funktion (Windows Communication Foundation) "HTTP-Aktivierung zulassen" installieren.

Das Zertifikat muss folgendermaßen importiert werden:

  - **Bei Farmen mit einem Server**   Sie müssen das Zertifikat direkt auf dem Server importieren, auf dem Office Web Apps Server ausgeführt wird. Binden Sie das Zertifikat nicht manuell. Diese Bindung wird mit dem New-OfficeWebAppsFarm-Cmdlet vorgenommen, das Sie später ausführen. Wenn Sie das Zertifikat manuell binden, wird es bei jedem Neustart des Servers gelöscht.

  - **Bei Farmen mit Lastenausgleich**   Bei einer SSL-Verschiebung muss das Zertifikat in das hardwarebasierte Lastenausgleichsmodul importiert werden. Wenn Sie keine SSL-Verschiebung vornehmen, müssen Sie das Zertifikat auf jedem Server in der Office Web Apps Server-Farm installieren.


> [!TIP]
> Verwenden Sie selbstsignierte Zertifikate nur in unwichtigeren Testumgebungen.



Weitere Informationen zu Zertifikaten finden Sie unter [Abrufen eines SSL-Zertifikats](https://go.microsoft.com/fwlink/p/?linkid=269700).

## Verwenden der SSL-Verschiebung für Hardwarelastenausgleichsmodule

Beim Einrichten einer neuen Office Web Apps Server-Farm ist die SSL-Verschiebung standardmäßig deaktiviert. Wenn SSL ausgelagert wird, kann jeder Office Web Apps Server in der Farm über HTTP mit dem Lastenausgleichsmodul kommunizieren. Allerdings sind sämtliche Verweise auf Ressourcen in der HTML HTTPS-Verweise. Wenn Sie diese Einstellung nicht vornehmen und versuchen, HTTP zu verwenden, werden den Benutzern keine Ressourcen oder aber Sicherheitswarnungen angezeigt. Ist die Verschiebung deaktiviert, wird SSL an den einzelnen Servern terminiert, auf denen Office Web Apps Server ausgeführt wird, anstatt am Hardwarelastenausgleichsmodul. Wenn Sie SSL stattdessen am Lastenausgleichsmodule terminieren, ergeben sich die folgenden Vorteile:

  - Vereinfachte Zertifikatverwaltung

  - Verbesserte Soft Affinity

  - Verbesserte Leistung

Beachten Sie, dass bei der Verwendung von HTTP Datenverkehr vom Lastenausgleichsmodul zu den Servern, auf denen Office Web Apps Server ausgeführt wird, nicht verschlüsselt wird. Aus diesem Grund müssen Sie sicherstellen, dass das Netzwerk selbst sicher ist. Die Verwendung eines privaten Subnetzes kann zum Schutz des Datenverkehrs beitragen­­.

## Beschränken, welche Server basierend auf der Mitgliedschaft in einer Organisationseinheit einer Office Web Apps Server-Farm beitreten können

Sie können verhindern, dass nicht autorisierte Server in eine Office Web Apps Server-Farm aufgenommen werden, indem Sie eine Organisationseinheit für diese Server erstellen und dann beim Erstellen der Farm den Parameter „FarmOU“ angeben. Weitere Informationen zum Parameter „FarmOU“ finden Sie im Artikel [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

## Einschränken des Hostzugriffs für Office Web Apps Server durch Verwendung der Zulassungsliste

Die Liste „Zulassen“ ist ein Sicherheitsfeature, mit dem verhindert wird, dass Hosts unerlaubt der Office Web Apps Server-Farm beitreten und die Farm ohne Ihre Zustimmung für Dateivorgänge verwenden. Indem Sie die Domänen mit genehmigten Hosts der Liste „Zulassen“ hinzufügen, können Sie einschränken, für welche Hosts in Office Web Apps Server Anforderungen in Bezug auf Dateivorgänge, z. B. Dateiabruf, Metadatenabruf und Dateiänderungen, zulässig sind.

Sie können der Liste „Zulassen“ Domänen hinzufügen, nachdem Sie die Office Web Apps Server-Farm erstellt haben. Im Artikel [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps) finden Sie Informationen zum Hinzufügen von Domänen zur Liste.


> [!IMPORTANT]
> Wenn Sie der Liste „Zulassen“ keine Domänen hinzufügen, sind in Office Web Apps Server Dateianforderungen für Hosts in jeder Domäne zulässig. Lassen Sie diese Liste nicht leer, wenn vom Internet aus auf Ihre Office Web Apps Server-Farm zugegriffen werden kann. Andernfalls kann jeder Ihre Office Web Apps Server-Farm zum Anzeigen und Bearbeiten von Inhalten verwenden.



## Plan für Onlineviewer mit Office Web Apps Server

Die Onlineviewerfunktionalität ist nach der Installation von Office Web Apps Server standardmäßig installiert. Prüfen Sie die folgenden Richtlinien, wenn Sie planen, Onlineviewer in Ihrer Organisation zu verwenden. In einigen Fällen kann es sinnvoll sein, einige Features in Onlineviewern zu deinstallieren. Diese Richtlinien beziehen sich auf die Parameter, die mit den Windows PowerShell-Cmdlets [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) und [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps) festgelegt werden.

## Sicherheitsüberlegungen für Onlineviewer

Für Dateien, die mit Onlineviewern in einem Webbrowser angezeigt werden können, darf keine Authentifizierung erforderlich sein. Anders gesagt, die Dateien müssen öffentlich verfügbar sein, da Onlineviewer beim Abrufen von Dateien keine Authentifizierung durchführen können. Es wird dringend empfohlen, dass über die Office Web Apps Server-Farm die Sie für Onlineviewer verwenden, entweder nur auf das Intranet oder auf das Internet zugegriffen werden kann, aber nicht auf beides. Der Grund ist, dass Office Web Apps Server nicht zwischen Anforderungen für Intranet- und Internet-URLs unterscheidet. Wenn beispielsweise aus dem Internet eine Intranet-URL angefordert wird, kann eine Sicherheitslücke entstehen, wenn ein internes Dokument für eine Person bereitgestellt wird, die es über das Internet anfordert.

Aus dem gleichen Grund wird dringend empfohlen, die UNC-Unterstützung in Onlineviewern zu deaktivieren, wenn Sie Office Web Apps Server so konfiguriert haben, dass nur eine Verbindung mit dem Internet hergestellt wird. Legen Sie zum Deaktivieren der UNC-Unterstützung den Parameter „OpenFromUncEnabled“ mit den Windows PowerShell-Cmdlets [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) (für neue Farmen) oder [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps) (für vorhandene Farmen) auf „False“ fest.

Als zusätzliche Sicherheitsvorkehrung können Onlineviewer nur Office-Dateien von höchstens 10 MB anzeigen.

## Konfigurationsoptionen für Onlineviewer

Sie können Onlineviewer mit den folgenden Windows PowerShell-Parametern in [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) (für neue Farmen) oder [Set-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/set-officewebappsfarm?view=officewebapps-ps) (für vorhandene Farmen) konfigurieren.

  - **OpenFromUrlEnabled**   Aktiviert oder deaktiviert die Onlineviewer. Dieser Parameter steuert Onlineviewer für Dateien, die URL- und UNC-Pfade haben. Dieser Parameter ist standardmäßig auf False (deaktiviert) gesetzt, wenn Sie eine neue Office Web Apps Server-Farm erstellen.

  - **OpenFromUncEnabled**   Wenn Onlineviewer aktiviert sind (der Parameter OpenFromUrlEnabled ist auf True gesetzt), kann mit diesem Parameter die Fähigkeit von Onlineviewern, Dateien in UNC-Pfaden anzuzeigen, aktiviert oder deaktiviert werden. Dieser Parameter ist standardmäßig auf True gesetzt. Stellen Sie jedoch sicher, dass OpenFromUrlEnabled auch auf True gesetzt ist, bevor Sie das Öffnen von Dateien über UNC-Pfade ermöglichen. Wie zuvor beschrieben, wird empfohlen, diesen Parameter auf False zu setzen, wenn Sie Office Web Apps Server so konfiguriert haben, dass eine Verbindung mit dem Internet hergestellt wird.

  - **OpenFromUrlThrottlingEnabled**   Begrenzt die Anzahl offener von URLs stammender Anforderungen von einem angegebenen Server in einem festgelegten Zeitraum. Die standardmäßigen Grenzwerte, die nicht konfigurierbar sind, stellen sicher, dass keine Office Web Apps Server-Farm einen einzelnen Server überlastet, indem Anforderungen für das Anzeigen von Inhalten in den Onlineviewern gesendet werden.

## Planen von Updates für Office Web Apps Server

Vor dem Bereitstellen von Office Web Apps Server müssen Sie entscheiden, wie Ihre Organisation Softwareupdates für die Office Web Apps Server-Farm verwaltet. Obwohl Softwareupdates zur Verbesserung der Sicherheit, Leistung und Zuverlässigkeit von Servern beitragen, kann das inkorrekte Installieren von Updates zu Problemen mit dem Office Web Apps Server führen.

Das Anwenden von Office Web Apps Server-Updates über den automatischen Updatevorgang von Microsoft wird für Office Web Apps Server nicht unterstützt. Das liegt daran, dass Updates für Office Web Apps Server wie unter [Anwenden von Softwareupdates auf Office Web Apps Server](apply-software-updates-to-office-web-apps-server.md) beschrieben auf bestimmte Weise angewendet werden müssen. Wenn Office Web Apps Server-Updates automatisch angewendet werden, können Benutzer möglicherweise keine Dokumente in Office Web Apps anzeigen oder bearbeiten. Wenn dies geschieht, müssen Sie Ihre Office Web Apps Server-Farm neu erstellen.

Wir empfehlen, dass Sie Updates unter Verwendung von Windows Server Update Services (WSUS) oder System Center Konfigurations-Manager das WSUS nutzt, verwalten. WSUS ermöglicht es Ihnen, die Bereitstellung von Updates, die über Microsoft Update veröffentlicht werden, für jeden Server in der Office Web Apps Server-Farm zu verwalten. Durch die Verwendung von WSUS können Sie entscheiden, welche Updates automatisch auf die Serverfarm angewendet werden können, und welche Updates, etwa Office Web Apps Server-Updates, manuell angewendet werden müssen. Weitere Informationen zu WSUS finden Sie unter [Windows Server Update Services](https://go.microsoft.com/fwlink/p/?linkid=294822).

Wenn Sie nicht WSUS oder System Center Konfigurations-Manager verwenden, setzen Sie automatische Updates von Microsoft auf jedem Server in der Office Web Apps Server-Farm auf **Automatisch herunterladen, aber Nutzer bei Installation benachrichtigen**. Wenn Sie über ein Office Web Apps Server-Update informiert werden, befolgen Sie die Schritte unter [Anwenden von Softwareupdates auf Office Web Apps Server](apply-software-updates-to-office-web-apps-server.md). Um Windows-Updates anzuwenden und die Sicherheit Ihrer Server aufrecht zu erhalten, müssen Sie die Windows-Updates akzeptieren, wenn Sie informiert werden, dass Updates verfügbar sind.

## Siehe auch


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Übersicht über Office Web Apps Server](office-web-apps-server-overview.md)  
[Bereitstellen von Office Web Apps Server](deploy-office-web-apps-server.md)  
[Anwenden von Softwareupdates auf Office Web Apps Server](apply-software-updates-to-office-web-apps-server.md)  


[Office.com (Hilfe zu Office Web Apps auf Ihrem Desktop-PC oder Mobilgerät)](https://go.microsoft.com/fwlink/p/?linkid=266657)  
  

[](apply-software-updates-to-office-web-apps-server.md)

