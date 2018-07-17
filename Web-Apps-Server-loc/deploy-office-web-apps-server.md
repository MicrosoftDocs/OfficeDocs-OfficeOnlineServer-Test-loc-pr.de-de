---
title: Bereitstellen von Office Web Apps Server
TOCTitle: Bereitstellen von Office Web Apps Server
ms:assetid: e4d51dc4-6460-437d-aa8e-0ae4d3aa8cc5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219455(v=office.15)
ms:contentKeyID: 49633190
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Bereitstellen von Office Web Apps Server 

_<strong>Gilt für:</strong> Office Web Apps Server_

_<strong>Letztes Änderungsdatum des Themas:</strong> 2017-10-05_

**Zusammenfassung:** Informationen zur lokalen Bereitstellung von Office Web Apps Server für die Verwendung durch SharePoint 2013 und Lync Server 2013.

**Zielgruppe:** IT-Spezialisten

Beachten Sie, dass dieser Artikel das Installieren von Office Web Apps Server für Ihr Unternehmen behandelt. Wenn Sie Hilfe zu Ihrer persönlichen Kopie von Office oder Office Web Apps suchen, besuchen Sie <https://support.office.com>.

Das Bereitstellen von [Office Web Apps Server](office-web-apps-server-overview.md) umfasst die Installation vorausgesetzter Software und Ausführung einiger Windows PowerShell-Befehle und gestaltet sich recht einfach. In diesem Artikel werden zunächst die Schritte zur Inbetriebnahme Ihrer Server und dann die Windows PowerShell-Befehle zum Konfigurieren der Office Web Apps Server-Farm behandelt.

Inhalt dieses Artikels:

  - Video mit den auszuführenden Schritten

  - Zu überprüfende Ressourcen, bevor Sie beginnen

  - Vorbereiten der Server für Office Web Apps Server

  - Bereitstellen der Office Web Apps Server-Farm

  - Vorgehensweise bei den Meldungen "500 Web Service Exceptions" oder "500.21 – Internal Server Error"

## Video mit den auszuführenden Schritten

Sehen Sie sich das folgende Video an, in dem die Einrichtung von Office Web Apps Server in einer Testumgebung gezeigt wird. Außerdem erfahren Sie, wie SharePoint 2013 für die Verwendung von Office Web Apps Server konfiguriert wird.

**Einrichten von Office Web Apps Server in einer Testumgebung**

> [!VIDEO https://www.microsoft.com/de-de/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

## Zu überprüfende Ressourcen, bevor Sie beginnen

Schauen Sie sich diese Ressourcen an, bevor Sie loslegen:

  - Einzelheiten zu den Hardware- und Softwareanforderungen [finden Sie in den Planungsleitfäden](plan-office-web-apps-server.md).

  - Office Web Apps Server ermöglicht Ihnen standardmäßig das Anzeigen von Office, aber nicht deren Bearbeitung. Zum Bearbeiten von Dateien benötigen Sie eine Bearbeitungslizenz, die unter [Planen von Office Web Apps (verwendet mit SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md) und [Konfigurieren der Lizenzierung in SharePoint Server 2013](https://technet.microsoft.com/de-de/library/jj219627\(v=office.15\)) behandelt wird.


> [!NOTE]
> Sie können alle Aufgaben in Office 2013-Produktfamilien mit einer Maus, mit Tastenkombinationen oder per Fingereingabe durchführen. Weitere Informationen zur Verwendung von Tastenkombinationen und Fingereingaben bei Office-Produkten und -Diensten finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=249150">Tastenkombinationen</A> und <A href="https://go.microsoft.com/fwlink/p/?linkid=253163">Office-Leitfaden für die Gestensteuerung</A>.



## Vorbereiten von Servern für die Ausführung von Office Web Apps Server

Führen Sie die folgenden Schritte auf allen Servern durch, auf denen Office Web Apps Server ausgeführt werden soll.

**Abbildung: Die Schritte zum Vorbereiten von Servern für Office Web Apps Server**

![Die Schritte zum Vorbereiten von Servern für Office Web Apps Server](images/JJ219455.af2a4690-4f8b-42c3-aab5-f7066bc0a936(Office.15).gif "Die Schritte zum Vorbereiten von Servern für Office Web Apps Server") 

## Schritt 1: Installieren der vorausgesetzten Software für Office Web Apps Server

Die erforderlichen Komponenten für Windows Server 2008 R2, Windows Server 2012 und Windows Server 2012 R2 unterscheiden sich geringfügig. Achten Sie nachfolgend darauf, dass Sie die ordnungsgemäßen Komponenten für Ihr Betriebssystem installieren.

**Unter Windows Server 2008 R2**

1.  Installieren Sie die folgende Software:
    
      - [Windows Server 2008 R2 Service Pack 1](http://go.microsoft.com/fwlink/p/?linkid=252370)
    
      - [.NET Framework 4.5](https://go.microsoft.com/fwlink/p/?linkid=256560)
    
      - [Windows PowerShell 3.0](https://go.microsoft.com/fwlink/p/?linkid=244693)
    
      - [Plattformupdate für Windows 7 SP1 und Windows Server 2008 R2 SP1 (KB2670838)](https://go.microsoft.com/fwlink/p/?linkid=293629)

2.  Öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie diese Befehle zum Installieren der erforderlichen Rollen und Dienste aus.
    
    ```PowerShell
        Import-Module ServerManager
    ```
    
    Führen Sie danach diesen Befehl aus:
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-WebServer,Web-Common-Http,Web-Static-Content,Web-App-Dev,Web-Asp-Net,Web-Net-Ext,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,Web-Security,Web-Windows-Auth,Web-Filtering,Web-Stat-Compression,Web-Dyn-Compression,Web-Mgmt-Console,Ink-Handwriting,IH-Ink-Support,NET-Framework,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-Win-CFAC
    ```
    
    Wenn Sie aufgefordert werden, starten Sie den Server neu.

**Unter Windows Server 2012**

1.  Öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie diesen Befehl zum Installieren der erforderlichen Rollen und Dienste aus.
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    ```
    
    Wenn Sie aufgefordert werden, starten Sie den Server neu.

**Auf Windows Server 2012 R2**

1.  Installieren Sie die folgende Software:
    
      - [.NET Framework 4.5.2](https://go.microsoft.com/fwlink/p/?linkid=510096)

2.  Öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie diesen Befehl zum Installieren der erforderlichen Rollen und Dienste aus.
    
    ```PowerShell
        Add-WindowsFeature Web-Server,Web-Mgmt-Tools,Web-Mgmt-Console,Web-WebServer,Web-Common-Http,Web-Default-Doc,Web-Static-Content,Web-Performance,Web-Stat-Compression,Web-Dyn-Compression,Web-Security,Web-Filtering,Web-Windows-Auth,Web-App-Dev,Web-Net-Ext45,Web-Asp-Net45,Web-ISAPI-Ext,Web-ISAPI-Filter,Web-Includes,InkandHandwritingServices,NET-Framework-Features,NET-Framework-Core,NET-HTTP-Activation,NET-Non-HTTP-Activ,NET-WCF-HTTP-Activation45
    ```
    
    Wenn Sie aufgefordert werden, starten Sie den Server neu.

## Schritt 2: Installieren von Office Web Apps Server und zugehörigen Updates

Führen Sie die folgenden Schritte auf allen Servern aus, auf denen Office Web Apps Server ausgeführt wird.

1.  Laden Sie Office Web Apps Server aus dem [Volume Licensing Service Center (VLSC)](https://go.microsoft.com/fwlink/p/?linkid=256561) herunter. Zum Herunterladen von Office Web Apps Server benötigen Sie eine Lizenz unter einem Volumenlizenzvertrag für Office Professional Plus 2013, Office Standard 2013 oder Office für Mac 2011. Der Download befindet sich unter den betreffenden Office-Produkten im VLSC-Portal.

2.  Führen Sie einen der folgenden Schritte aus:
    
      - Öffnen Sie bei Windows Server 2012 oder Windows Server 2012 R2 die IMG-Datei direkt, und führen Sie **Setup.exe** aus.
    
      - Windows Server 2008 R2 SP1: Verwenden Sie ein Programm, das zum Einbinden oder Extrahieren von IMG-Dateien geeignet ist. Führen Sie anschließend **Setup.exe** aus.

3.  Aktivieren Sie auf der Seite **Microsoft-Software-Lizenzbedingungen lesen** das Kontrollkästchen **Ich stimme den Bedingungen dieser Vereinbarung zu**, und klicken Sie dann auf **Weiter**.

4.  Wählen Sie auf der Seite **Dateispeicherort auswählen** den Ordner aus, in dem die Office Web Apps Server-Dateien installiert werden sollen (z. B. "C:\\Programme\\Microsoft Office Web Apps"), und wählen Sie anschließend die Option **Jetzt installieren** aus. Wenn dieser Ordner nicht vorhanden ist, wird er vom Setup erstellt.
    
    Es wird empfohlen, Office Web Apps Server auf dem Systemlaufwerk zu installieren.

5.  Klicken Sie nach Abschluss der Installation von Office Web Apps Server auf **Schließen**.

6.  Laden Sie [Office Web Apps Server SP1](https://go.microsoft.com/fwlink/p/?linkid=510097) (Empfohlen für Windows Server 2012 und Windows Server 2008 R2 SP1. Erforderlich für Windows Server 2012 R2.) herunter, und installieren Sie das Update.    

    > [!TIP]
    > Wenn Sie Office Web Apps Server&nbsp;SP1 zu einem späteren Zeitpunkt anwenden, befolgen Sie die Anweisungen unter <A href="apply-software-updates-to-office-web-apps-server.md">Anwenden von Softwareupdates auf Office Web Apps Server</A>.

7.  Suchen Sie die neuesten Office Web Apps Server-Updates in der Liste im [TechNet Update Center für Office, Office-Server und verwandte Produkte](https://go.microsoft.com/fwlink/p/?linkid=280271).    

    > [!TIP]
    > Wenn Sie Office Web Apps Server&nbsp;SP1 nicht installieren, wenden Sie <A href="https://go.microsoft.com/fwlink/p/?linkid=296579">KB2810007</A> an.

## Schritt 3: Installieren von Sprachpaketen für Office Web Apps Server

Dank der Sprachpakete für Office Web Apps Server 2013 können Benutzer webbasierte Office-Dateien aus SharePoint 2013-Dokumentbibliotheken, Outlook Web Access (in Form einer Anlagenvorschau) und Lync 2013 (in Form von PowerPoint-Übertragung) in mehreren Sprachen anzeigen. Weitere Informationen zur Funktionsweise der Sprachpakete finden Sie unter [Planen von Sprachpaketen für Office Web Apps Server](plan-office-web-apps-server.md).

Gehen Sie zum Installieren der Sprachpakete wie folgt vor:


1.  Laden Sie die Office Web Apps Server-Sprachpakete aus dem [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?linkid=263945) herunter.

2.  Führen Sie **WebAppsServerLP\_en-us\_x64.exe** aus.

3.  Wählen Sie im Setup-Assistenten für Office Web Apps Server 2013-Sprachpakete auf der Seite **Microsoft-Software-Lizenzbedingungen lesen** die Option **Ich stimme den Bedingungen dieser Vereinbarung zu** und anschließend **Weiter** aus.

4.  Wählen Sie nach Abschluss der Installation von Office Web Apps Server die Option **Schließen** aus.


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Wenn Sie Sprachpakete nach Erstellung der Office Web Apps Server-Farm installieren möchten, müssen Sie einen Server aus der Farm entfernen, das Sprachpaket auf diesem Server installieren und ihn anschließend wieder der Farm hinzufügen.</P>
> <LI>
> <P>Damit ein Sprachpaket ordnungsgemäß funktioniert, müssen Sie es auf allen Servern in der Farm installieren.</P></LI></UL>



## Bereitstellen der Office Web Apps Server-Farm

Führen Sie basierend auf dem Typ der Office Web Apps Server-Farm, die Sie erstellen möchten, die Schritte in einem der folgenden drei Abschnitte aus.


> [!TIP]
> Falls Windows PowerShell das <STRONG>New-OfficeWebAppsFarm</STRONG>-Cmdlet beim Ausführen nicht erkennt, müssen Sie möglicherweise das <STRONG>OfficeWebApps</STRONG>-Modul importieren. Verwenden Sie dazu diesen Befehl:<BR><CODE>Import-Module -Name OfficeWebApps</CODE>



## Bereitstellen einer Office Web Apps Server-Farm mit einem Server, der HTTPS verwendet

Wenn Sie Office Web Apps Server nur für Test- oder interne Zwecke bereitstellen und Lync Server 2013 keine Office Web Apps Server-Funktionalität bereitstellen müssen, befolgen Sie die folgenden Schritte zum Installieren einer Office Web Apps Server-Farm mit einem Server, die HTTP verwendet. Sie brauchen kein Zertifikat und keinen Lastenausgleich, jedoch einen dedizierten physischen Server oder eine Instanz einer virtuellen Maschine, auf dem/der keine andere Serveranwendung ausgeführt wird.

Mit dieser Office Web Apps Server-Farm können Sie Office Web Apps-Funktionen für SharePoint 2013 bereitstellen.

**Abbildung: Die Schritte zum Bereitstellen von Office Web Apps Server**

![Die drei Hauptschritte zum Bereitstellen einer Office Web Apps Server-Farm mit einem Server](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Die drei Hauptschritte zum Bereitstellen einer Office Web Apps Server-Farm mit einem Server")

## Schritt 1: Erstellen der Office Web Apps Server-Farm

Erstellen Sie mit dem Befehl **New-OfficeWebAppsFarm** eine neue Office Web Apps Server-Farm mit nur einem Server (siehe das folgende Beispiel).

```PowerShell
    New-OfficeWebAppsFarm -InternalURL "http://servername" -AllowHttp -EditingEnabled
```
**Parameter**

  - **–InternalURL** ist der Name des Servers, auf dem Office Web Apps Server ausgeführt wird, z. B. **http://Servername**.

  - **–AllowHttp** konfiguriert die Farm für die Verwendung von HTTP.

  - **–EditingEnabled** ermöglicht die Bearbeitung in Office Web Apps bei Verwendung mit SharePoint 2013. Dieser Parameter wird von Lync Server 2013 nicht verwendet, da dieser Host die Bearbeitung nicht unterstützt.

Informationen zu weiteren Parametern zum Konfigurieren von Übersetzungsdiensten, Proxyservern, ClipArt-Unterstützung und Onlineviewern finden Sie unter [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

Vorgehensweise bei den Meldungen "500 Web Service Exceptions" oder "500.21 – Internal Server Error"

## Schritt 2: Sicherstellen, dass die Office Web Apps Server-Farm erfolgreich erstellt wurde

Nach Erstellung der Farm werden Details zur Farm an der Windows PowerShell-Eingabeaufforderung angezeigt. Vergewissern Sie sich, dass Office Web Apps Server ordnungsgemäß installiert und konfiguriert ist, indem Sie wie im folgenden Beispiel über einen Webbrowser auf die URL für die Office Web Apps Server-Serverermittlung zugreifen. Diese URL besteht aus dem Wert, den Sie dem *InternalUrl*-Parameter beim Konfigurieren der Office Web Apps Server-Farm zugewiesen haben, gefolgt von **/hosting/discovery**. Beispiel:

    http://servername/hosting/discovery

Wenn Office Web Apps Server wie erwartet ausgeführt wird, sollte in Ihrem Webbrowser eine WOPI-Such-XML-Datei (Web Application Open Platform Interface Protocol) angezeigt werden. Die ersten Zeilen der Datei sollten ähnlich wie im folgenden Beispiel aussehen:

```XML
    <?xml version="1.0" encoding="utf-8" ?> 
    - <wopi-discovery>
    - <net-zone name="internal-http">
    - <app name="Excel" favIconUrl="http://servername/x/_layouts/images/FavIcon_Excel.ico" checkLicense="true">
    <action name="view" ext="ods" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xls" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsb" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
    <action name="view" ext="xlsm" default="true" urlsrc="http://servername/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" /> 
```

## Schritt 3: Konfigurieren des Hosts

Die Farm ist jetzt bereit, Office Web Apps-Funktionalität über HTTP für Hosts bereitzustellen. Weitere Informationen zum Konfigurieren von Hosts finden Sie unter [Konfigurieren von Office Web Apps für SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

## Bereitstellen einer Office Web Apps Server-Farm mit einem Server, die HTTPS verwendet
<a name="singlehttps"> </a>

Für die meisten Produktionsumgebungen wird HTTPS aufgrund seiner Sicherheitsfunktionen ausdrücklich empfohlen. HTTPS ist außerdem erforderlich, wenn Sie Lync Server 2013 Funktionalität von Office Web Apps Server zur Verfügung stellen möchten. Benutzer können anschließend PowerPoint-Übertragungen in einem Browser anzeigen. Nachfolgend wird die Installation einer Office Web Apps Server-Farm mit einem Server beschrieben, der HTTPS verwendet. Sie können gemäß den Anweisungen unter [Securing Office Web Apps Server communications by using HTTPS](plan-office-web-apps-server.md) ein Zertifikat auf dem Server installieren.

Mit dieser Office Web Apps Server-Farm können Sie Office Web Apps-Funktionen für SharePoint 2013 und Lync Server 2013 bereitstellen.

**Abbildung: Die Schritte zum Bereitstellen von Office Web Apps Server**

![Die drei Hauptschritte zum Bereitstellen einer Office Web Apps Server-Farm mit einem Server](images/JJ219455.de5b3ed2-d7a7-489e-9de2-f3f068ebe836(Office.15).gif "Die drei Hauptschritte zum Bereitstellen einer Office Web Apps Server-Farm mit einem Server")

## Schritt 1: Erstellen der Office Web Apps Server-Farm

Erstellen Sie mit dem Befehl **New-OfficeWebAppsFarm** eine neue Office Web Apps Server-Farm mit nur einem Server (siehe das folgende Beispiel).

```PowerShell
    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -CertificateName "OfficeWebApps Certificate" -EditingEnabled
```

**Parameter**

  - **–InternalURL** ist der vollqualifizierte Domänenname (FQDN) des Servers, auf dem Office Web Apps Server ausgeführt wird, z. B. **http://Servername.contoso.com**.

  - **–ExternalURL** ist der FQDN, auf den über das Internet zugegriffen werden kann.

  - **–CertificateName** ist der angezeigte Name des Zertifikats.

  - **–EditingEnabled** ist optional und ermöglicht die Bearbeitung in Office Web Apps bei Verwendung mit SharePoint 2013. Dieser Parameter wird von Lync Server 2013 nicht verwendet, da dieser Host die Bearbeitung nicht unterstützt.

Informationen zu weiteren Parametern zum Konfigurieren von Übersetzungsdiensten, Proxyservern, ClipArt-Unterstützung und Onlineviewern finden Sie unter [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

Vorgehensweise bei den Meldungen "500 Web Service Exceptions" oder "500.21 – Internal Server Error"

## Schritt 2: Sicherstellen, dass die Office Web Apps Server-Farm erfolgreich erstellt wurde

Nach Erstellung der Farm werden Details zur Farm an der Windows PowerShell-Eingabeaufforderung angezeigt. Vergewissern Sie sich, dass Office Web Apps Server ordnungsgemäß installiert und konfiguriert ist, indem Sie wie im folgenden Beispiel über einen Webbrowser auf die URL für die Office Web Apps Server-Serverermittlung zugreifen. Diese URL besteht aus dem Wert, den Sie dem *InternalUrl*-Parameter beim Konfigurieren der Office Web Apps Server-Farm zugewiesen haben, gefolgt von **/hosting/discovery**. Beispiel:

    https://server.contoso.com/hosting/discovery

Wenn Office Web Apps Server wie erwartet ausgeführt wird, sollte in Ihrem Webbrowser eine WOPI-Such-XML-Datei (Web Application Open Platform Interface Protocol) angezeigt werden. Die ersten Zeilen der Datei sollten ähnlich wie im folgenden Beispiel aussehen:

```XML
<?xml version="1.0" encoding="UTF-8"?>
<wopi-discovery><net-zone 
name="internal-https"><app name="Excel" checkLicense="true" 
favIconUrl="https://wac.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action 
name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="ods"/><action name="view" 
urlsrc="https://wac.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" 
default="true" ext="xls"/><action name="view" 
```

> [!TIP]
> Abhängig von den Sicherheitseinstellungen Ihres Webbrowser sehen Sie ggf. eine Meldung, die Sie zur Auswahl von <STRONG>Alle Inhalte anzeigen</STRONG> auffordert, bevor der Inhalt der Such-XML-Datei angezeigt wird.


## Schritt 3: Konfigurieren des Hosts

Die Farm ist jetzt bereit, über HTTPS Office Web Apps-Funktionalität für Hosts bereitzustellen. Weitere Informationen zum Konfigurieren von Hosts finden Sie in den folgenden Artikeln.

  - [Konfigurieren von Office Web Apps für SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Bereitstellen von Office Web Apps Server und Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Bereitstellen einer Office Web Apps Server-Farm mit mehreren Servern, die Lastenausgleich und HTTPS verwendet
<a name="multihttps"> </a>

Wenn Sie in Ihrer Office Web Apps Server-Farm viel Datenverkehr erwarten und diese sowohl über das Internet als auch das interne Netzwerk verfügbar sein soll, sollten Sie die folgende Topologie wählen. In diesem Abschnitt wird erklärt, wie Sie eine Office Web Apps Server-Farm mit mehreren Servern installieren, die Lastenausgleich und HTTPS verwendet. Wenn Sie es Sie interessiert, [lesen Sie mehr über diese Topologie](plan-office-web-apps-server.md).

Ehe Sie anfangen, vergewissern Sie sich, dass Ihr Lastenausgleich wie unter [Lastenausgleichsanforderungen für Office Web Apps Server](plan-office-web-apps-server.md) beschrieben konfiguriert ist. Außerdem müssen Sie für den Lastenausgleich ein Zertifikat installieren (siehe [Securing Office Web Apps Server communications by using HTTPS](plan-office-web-apps-server.md)). Diese Office Web Apps Server-Farm stellt SharePoint 2013 und Lync Server 2013 die Funktionalität von Office Web Apps bereit.

**Abbildung: Die Schritte zum Bereitstellen von Office Web Apps Server**

![Die vier Hauptschritte zum Bereitstellen einer Office Web Apps Server-Farm mit mehreren Servern](images/JJ219455.4c4b31cb-961b-4efd-b755-a18bdcb5c191(Office.15).gif "Die vier Hauptschritte zum Bereitstellen einer Office Web Apps Server-Farm mit mehreren Servern")

## Schritt 1: Erstellen der Office Web Apps Server-Farm auf dem ersten Server

Erstellen Sie mit dem Befehl **New-OfficeWebAppsFarm** eine neue Office Web Apps Server-Farm auf dem ersten Server (siehe das folgende Beispiel).

```PowerShell
    New-OfficeWebAppsFarm -InternalUrl "https://server.contoso.com" -ExternalUrl "https://wacweb01.contoso.com" -SSLOffloaded -EditingEnabled
```

**Parameter**

  - **–InternalURL** ist der vollqualifizierte Domänenname (FQDN) des Servers, auf dem Office Web Apps Server ausgeführt wird, z. B. **http://Servername.contoso.com**.

  - **–ExternalURL** ist der FQDN, auf den über das Internet zugegriffen werden kann.

  - **-SSLOffloaded** ermöglicht das Verschieben der SSL-Beendigung zum Lastenausgleich.

  - **–EditingEnabled** ist optional und ermöglicht die Bearbeitung in Office Web Apps bei Verwendung mit SharePoint 2013. Dieser Parameter wird von Lync Server 2013 nicht verwendet, da dieser Host die Bearbeitung nicht unterstützt.

Informationen zu weiteren Parametern zum Konfigurieren von Übersetzungsdiensten, Proxyservern, ClipArt-Unterstützung und Onlineviewern finden Sie unter [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

Vorgehensweise bei den Meldungen "500 Web Service Exceptions" oder "500.21 – Internal Server Error"

## Schritt 2: Hinzufügen weiterer Server zur Farm

Sobald Office Web Apps Server auf dem ersten Server ausgeführt wird, müssen Sie den Befehl **New-OfficeWebAppsMachine** auf jedem Server ausführen, den Sie der Office Web Apps Server-Farm hinzufügen möchten. Der Parameter **–MachineToJoin** fügt einer vorhandenen Office Web Apps Server-Farm den aktuellen Server hinzu. Verwenden Sie daher den Computernamen eines Servers, der bereits in der Office Web Apps Server-Farm vorhanden ist. Wenn beispielsweise server1.contoso.com bereits zur Farm gehört, geben Sie Folgendes an:

```PowerShell
    New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"
```

Sind Sie an weiteren Informationen zu diesen Parametern interessiert? Diese Parameter sind unter [New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps) aufgeführt.

## Schritt 3: Sicherstellen, dass die Office Web Apps Server-Farm erfolgreich erstellt wurde

Nach Erstellung der Farm werden Details zur Farm an der Windows PowerShell-Eingabeaufforderung angezeigt. Vergewissern Sie sich, dass Office Web Apps Server ordnungsgemäß installiert und konfiguriert ist, indem Sie wie im folgenden Beispiel über einen Webbrowser auf die URL für die Office Web Apps Server-Serverermittlung zugreifen. Diese URL besteht aus dem Wert, den Sie dem *InternalUrl*-Parameter beim Konfigurieren der Office Web Apps Server-Farm zugewiesen haben, gefolgt von **/hosting/discovery**. Beispiel:

    https://server.contoso.com/hosting/discovery

Wenn Office Web Apps Server wie erwartet ausgeführt wird, sollte in Ihrem Webbrowser eine WOPI-Such-XML-Datei (Web Application Open Platform Interface Protocol) angezeigt werden. Die ersten Zeilen der Datei sollten ähnlich wie im folgenden Beispiel aussehen:

```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <wopi-discovery><net-zone name="internal-https"><app name="Excel" checkLicense="true" favIconUrl="https://officewebapps.contoso.com/x/_layouts/images/FavIcon_Excel.ico"><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="ods"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xls"/><action name="view" urlsrc="https://officewebapps.contoso.com/x/_layouts/xlviewerinternal.aspx?<ui=UI_LLCC&><rs=DC_LLCC&>" default="true" ext="xlsb"/>
``` 

> [!TIP]
> Abhängig von den Sicherheitseinstellungen Ihres Webbrowser sehen Sie ggf. eine Meldung, die Sie zur Auswahl von <STRONG>Alle Inhalte anzeigen</STRONG> auffordert, bevor der Inhalt der Such-XML-Datei angezeigt wird.


## Schritt 4: Konfigurieren des Hosts

Die Farm ist jetzt bereit, über HTTPS Office Web Apps-Funktionalität für Hosts bereitzustellen. Weitere Informationen zum Konfigurieren von Hosts finden Sie in den folgenden Artikeln.

  - [Konfigurieren von Office Web Apps für SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)

  - [Bereitstellen von Office Web Apps Server und Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)

## Vorgehensweise bei den Meldungen "500 Web Service Exceptions" oder "500.21 – Internal Server Error"

Falls .NET Framework 3.5-Features installiert und später wieder entfernt wurden, erscheint beim Ausführen von Office Web Apps-Cmdlets unter Umständen die Meldung "500 Web Service Exceptions" oder "500.21 – Internal Server Error". Führen Sie zum Beheben dieses Fehlers an einer Eingabeaufforderung mit erhöhten Rechten die folgenden Beispielbefehle aus, um die Einstellungen zu bereinigen, die möglicherweise dazu führen, dass Office Web Apps Server nicht ordnungsgemäß funktioniert:

**Für Windows Server 2008 R2**

```PowerShell
    %systemroot%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -iru
```

```PowerShell
    iisreset /restart /noforce
```

**Für Windows Server 2012 oder Windows Server 2012 R2**

```PowerShell
    dism /online /enable-feature /featurename:IIS-ASPNET45
```

## Siehe auch


[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Planen von Office Web Apps Server](plan-office-web-apps-server.md)  
[Konfigurieren von Office Web Apps für SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md)  


[Bereitstellen von Office Web Apps Server und Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=256902)  
  

[](configure-office-web-apps-for-sharepoint-2013.md)

