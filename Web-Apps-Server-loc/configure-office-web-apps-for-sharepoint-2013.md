---
title: Konfigurieren von Office Web Apps für SharePoint 2013
TOCTitle: Konfigurieren von Office Web Apps für SharePoint 2013
ms:assetid: a5276781-133b-413c-beca-b851e17c2081
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Ff431687(v=office.15)
ms:contentKeyID: 49633173
ms.date: 01/12/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Konfigurieren von Office Web Apps für SharePoint 2013
 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2016-12-16_

**Zusammenfassung:** Erläuterungen zur Konfiguration von SharePoint 2013 für die Verwendung von Office Web Apps.

**Zielgruppe:** IT-Spezialisten

Dieser Artikel fährt an der Stelle fort, an der [Bereitstellen von Office Web Apps Server](deploy-office-web-apps-server.md) aufgehört hat, d. h. beim Einrichten des Servers, auf dem Office Web Apps Server ausgeführt wird. In diesem Artikel konfigurieren Sie SharePoint 2013 für die Verwendung von Office Web Apps Server. Zunächst müssen Sie einige Windows PowerShell-Cmdlets in SharePoint 2013 ausführen. Anschließend können Benutzer Office-Dateien in SharePoint 2013-Dokumentbibliotheken in einem Browser öffnen.

Wenn Sie mit den Features von Office Web Apps Server nicht vertraut sind, [lesen Sie das Übersichtsdokument](office-web-apps-server-overview.md).

Inhalt dieses Artikels:

  - Vorbereiten der Konfiguration von SharePoint 2013 für die Verwendung von Office Web Apps Server

  - Konfigurieren von SharePoint 2013 für die Verwendung von Office Web Apps Server

  - Behandeln von Problemen in Office Web Apps bei Verwendung mit SharePoint 2013

  - Trennen der Verbindung zwischen SharePoint 2013 und Office Web Apps Server

## Vorbereiten der Konfiguration von SharePoint 2013 für die Verwendung von Office Web Apps Server

Führen Sie zunächst die folgenden Schritte aus:

  - Installieren Sie SharePoint 2013. Anleitungen finden Sie unter [Installieren von SharePoint 2013](https://technet.microsoft.com/de-de/library/cc303424\(v=office.15\)).

  - Vergewissern Sie sich, dass von allen SharePoint 2013-Webanwendungen die anspruchsbasierte Authentifizierung verwendet wird. Das Rendering und die Bearbeitung von Office Web Apps funktionieren für SharePoint 2013-Webanwendungen mit klassischem Authentifizierungsmodus nicht. Weitere Informationen finden Sie unter [SharePoint-Authentifizierungsanforderungen für Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

  - Sie benötigen eine Bearbeitungslizenz, um es Benutzern zu ermöglichen, Office-Dokumente in einem Webbrowser zu bearbeiten (und nicht nur zu lesen). Außerdem müssen Sie die Bearbeitung für die Office Web Apps Server-Farm aktivieren. Weitere Informationen zu diesen Lizenzierungsanforderungen finden Sie unter [Lizenzierung von Office Web Apps für die Bearbeitung von Office-Dateien](plan-office-web-apps-used-with-sharepoint-2013.md).

  - Wenn Sie sich bei SharePoint 2013 mit einem Systemkonto anmelden, kann die Verbindung zwischen SharePoint 2013 und Office Web Apps Server nicht getestet werden. Melden Sie sich zum Testen der Verbindung mit einem anderen Konto an.

  - In Umgebungen mit wenig Arbeitsspeicher kann unter Umständen keine Vorschau von Office-Dokumenten in Office Web Apps angezeigt werden. Lesen Sie den Artikel [Hardware requirements—web servers, application servers, and single server installations](https://technet.microsoft.com/de-de/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver) für SharePoint 2013. Hierbei handelt es sich um die gleichen Anforderungen wie bei Office Web Apps Server.

## Konfigurieren von SharePoint 2013 für die Verwendung von Office Web Apps Server

Wählen Sie einen der folgenden Abschnitte je nachdem, ob Sie HTTP oder HTTPS verwenden möchten. HTTP wird generell nur für Testumgebungen empfohlen. In Produktionsumgebungen ist das sicherere HTTPS-Protokoll die bessere Wahl.

## In einer Testumgebung mit HTTP

Für diese Konfiguration müssen Sie Office Web Apps Server gemäß den Schritten unter [Deploy a single-server Office Web Apps Server farm that uses HTTP](deploy-office-web-apps-server.md) einrichten. Dabei ist besonders wichtig, dass die Office Web Apps Server-Farm für die Verwendung einer internen URL sowie von HTTP konfiguriert ist. Das [Video: Konfigurieren von Office Web Apps für SharePoint 2013](video-configure-office-web-apps-for-sharepoint-2013.md) veranschaulicht die Einrichtung von Office Web Apps Server und Konfiguration von SharePoint 2013 für die Verwendung von Office Web Apps Server in einer Testumgebung.

## Schritt 1: Öffnen einer SharePoint 2013-Verwaltungsshell mit erhöhten Rechten

Verwenden Sie die passende Vorgehensweise für Ihr Serverbetriebssystem.

**Unter Windows Server 2008 R2**

1.  Klicken Sie auf **Start** \> **Alle Programme** \> **Microsoft SharePoint 2013-Produkte**.

2.  Klicken Sie mit der rechten Maustaste auf **SharePoint 2013-Verwaltungsshell**, und klicken Sie anschließend auf **Als Administrator ausführen**.

**Unter Windows Server 2012**

1.  Drücken Sie Windows-Logo-Taste+Q, oder führen Sie eine Streifbewegung vom Bildschirmrand aus, um die Charms anzuzeigen, und wählen Sie dann **Suche** aus, um alle auf dem Computer installierten Anwendungen anzuzeigen.

2.  Klicken Sie mit der rechten Maustaste auf **SharePoint 2013-Verwaltungsshell**, um die App-Leiste anzuzeigen.

3.  Wählen Sie auf der App-Leiste **als Administrator ausführen** aus.

## Schritt 2: Erstellen der Bindung zwischen SharePoint 2013 und Office Web Apps Server

Führen Sie den folgenden Befehl aus. "\<WacServerName\>" steht hierbei für den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der URL, die Sie für die interne URL festlegen. Dies ist der Einstiegspunkt für den Datenverkehr von Office Web Apps Server. Für diese Testumgebung muss der Parameter "–AllowHTTP" angegeben werden, damit SharePoint 2013 Ermittlungsinformationen aus der Office Web Apps Server-Farm per HTTP empfangen kann. Ohne den Parameter "–AllowHTTP" wird von SharePoint 2013 versucht, per HTTPS mit der Office Web Apps Server-Farm zu kommunizieren, und der Befehl ist nicht erfolgreich.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> -AllowHTTP
```

Nach Ausführung dieses Befehls wird an der Windows PowerShell-Eingabeaufforderung eine Liste mit Bindungen angezeigt.

Hilfe hierzu finden Sie unter [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Schritt 3: Anzeigen der WOPI-Zonen für die SharePoint-Bindungen

Office Web Apps Server verwendet Zonen, um zu ermitteln, welche URL (intern oder extern) und welches Protokoll (HTTP oder HTTPS) bei der Kommunikation mit dem Host (in diesem Fall: SharePoint 2013) verwendet werden soll. Standardmäßig wird von SharePoint Server 2013 die Zone **internal-https** verwendet. Führen Sie den folgenden Befehl aus, um Ihre aktuelle Zone zu ermitteln.

```PowerShell
    Get-SPWOPIZone
```

Die von diesem Befehl angezeigte WOPI-Zone muss **internal-http** sein. Falls sie ordnungsgemäß angezeigt wird, fahren Sie mit Schritt 5 fort. Falls nicht, befolgen Sie den nächsten Schritt.

Hilfe hierzu finden Sie unter [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Schritt 4: Ändern der WOPI-Zone in "internal-http"

Wenn Sie in Schritt 3 das Ergebnis **internal-https** erhalten haben, führen Sie den folgenden Befehl aus, um die Zone in **internal-http** zu ändern. Diese Änderung ist erforderlich, da die Zone von SharePoint 2013 der Zone der Office Web Apps Server-Farm entsprechen muss.

```PowerShell
    Set-SPWOPIZone -zone "internal-http"
```

Vergewissern Sie sich, dass die neue Zone auf **internal-http** festgelegt ist, indem Sie **Get-SPWOPIZone** erneut ausführen:

Hilfe hierzu finden Sie unter [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps) sowie unter [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Schritt 5: Festlegen der Einstellung "AllowOAuthOverHttp" in SharePoint 2013 auf "True"

Wenn Sie Office Web Apps in einer Testumgebung zusammen mit SharePoint 2013 über HTTP verwenden möchten, müssen Sie "AllowOAuthOverHttp" auf **True** festlegen. Andernfalls kann Office Web Apps nicht verwendet werden. Den aktuellen Status können Sie durch Ausführen des folgenden Beispiels ermitteln:

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Wird von diesem Befehl **False** zurückgegeben, führen Sie die folgenden Befehle aus, um die Einstellung auf **True** festzulegen:

```PowerShell
    $config = (Get-SPSecurityTokenServiceConfig)
```
```PowerShell
   $config.AllowOAuthOverHttp = $true
```
```PowerShell
    $config.Update()
```

Führen Sie den folgenden Befehl erneut aus, um sich zu vergewissern, dass die Einstellung "AllowOAuthOverHttp" nun auf **True** festgelegt ist:

```PowerShell
    (Get-SPSecurityTokenServiceConfig).AllowOAuthOverHttp
```

Hilfe hierzu finden Sie unter [Get-SPSecurityTokenServiceConfig](https://technet.microsoft.com/de-de/library/ff607642\(v=office.15\)).

## Schritt 6: Überprüfen, ob Office Web Apps funktionieren

Vergewissern Sie sich in SharePoint 2013, dass Sie nicht mit dem Systemkonto angemeldet sind, da Sie dann mit Office Web Apps die Dokumente nicht bearbeiten oder anzeigen können. Navigieren Sie zu einer SharePoint 2013-Dokumentbibliothek mit Office-Dokumenten, und zeigen Sie eine Word-, PowerPoint-, Excel- oder OneNote-Datei an. Das Dokument sollte in einem Browser geöffnet werden, der die Datei unter Verwendung von Office Web Apps anzeigt.

Sollte dieser Schritt nicht erfolgreich sein, lesen Sie Behandeln von Problemen in Office Web Apps bei Verwendung mit SharePoint 2013.

## In einer Produktionsumgebung, die HTTPS verwendet

Vergewissern Sie sich zunächst, dass Office Web Apps Server gemäß den Schritten in [Deploy a single-server Office Web Apps Server farm that uses HTTPS](deploy-office-web-apps-server.md#singlehttps) oder [Deploy a multi-server, load-balanced Office Web Apps Server farm that uses HTTPS](deploy-office-web-apps-server.md#multihttps) eingerichtet ist.

## Schritt 1: Öffnen der SharePoint 2013-Verwaltungsshell

Verwenden Sie die passende Vorgehensweise für Ihr Serverbetriebssystem.

**Unter Windows Server 2008 R2**

1.  Wählen Sie **Start** \> **Alle Programme** \> **Microsoft SharePoint 2013-Produkte**.

2.  Klicken Sie mit der rechten Maustaste auf **SharePoint 2013-Verwaltungsshell**, um das Kontextmenü einzublenden, und klicken Sie anschließend auf **Als Administrator ausführen**.

**Unter Windows Server 2012**

1.  Drücken Sie Windows-Logo-Taste+Q, oder führen Sie eine Streifbewegung vom Bildschirmrand aus, um die Charms anzuzeigen, und wählen Sie dann **Suche** aus, um alle auf dem Computer installierten Anwendungen anzuzeigen.

2.  Klicken Sie mit der rechten Maustaste auf **SharePoint 2013-Verwaltungsshell**, um die App-Leiste anzuzeigen.

3.  Wählen Sie auf der App-Leiste **als Administrator ausführen** aus.

## Schritt 2: Erstellen der Bindung zwischen SharePoint 2013 und Office Web Apps Server

Führen Sie den folgenden Befehl aus. "\<WacServerName\>" ist hierbei der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) der URL, die Sie für die interne URL festlegen. Dies ist der Einstiegspunkt für den Datenverkehr von Office Web Apps Server.

```PowerShell
    New-SPWOPIBinding -ServerName <WacServerName> 
```

Hilfe hierzu finden Sie unter [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps).

## Schritt 3: Anzeigen der WOPI-Zone von SharePoint 2013

Office Web Apps Server verwendet Zonen, um zu ermitteln, welche URL (intern oder extern) und welches Protokoll (HTTP oder HTTPS) bei der Kommunikation mit dem Host (in diesem Fall: SharePoint 2013) verwendet werden soll. Standardmäßig wird von SharePoint Server 2013 die Zone **internal-https** verwendet. Führen Sie den folgenden Befehl aus, um sich zu vergewissern, dass diese Zone aktuell verwendet wird:

```PowerShell
    Get-SPWOPIZone
```

Notieren Sie sich die angezeigte WOPI-Zone.

Hilfe hierzu finden Sie unter [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Schritt 4: Ändern der WOPI-Zone (sofern erforderlich)

Abhängig von Ihrer Umgebung ist unter Umständen eine Änderung der WOPI-Zone erforderlich. Geben Sie "external" an, wenn es sich bei Ihrer SharePoint-Farm sowohl um eine interne als auch um eine externe Farm handelt. Handelt es sich bei Ihrer SharePoint-Farm um eine rein interne Farm, geben Sie "internal" an.

Falls Sie in Schritt 3 das Ergebnis **internal-https** erhalten und es sich bei der SharePoint-Farm um eine rein interne Farm handelt, können Sie diesen Schritt überspringen. Falls es sich bei Ihrer SharePoint-Farm sowohl um eine interne als auch um eine externe Farm handelt, müssen Sie den folgenden Befehl ausführen, um die Zone in **external-https** zu ändern:

```PowerShell
    Set-SPWOPIZone -zone "external-https"
```

Hilfe hierzu finden Sie unter [Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps).

## Schritt 5: Überprüfen, ob Office Web Apps funktionieren

Vergewissern Sie sich in SharePoint 2013, dass Sie nicht mit dem Systemkonto angemeldet sind, da Sie dann mit Office Web Apps die Dokumente nicht bearbeiten oder anzeigen können. Navigieren Sie zu einer SharePoint 2013-Dokumentbibliothek mit Office-Dokumenten, und zeigen Sie eine Word-, PowerPoint-, Excel- oder OneNote-Datei an. Das Dokument sollte in einem Browser geöffnet werden, der die Datei unter Verwendung von Office Web Apps anzeigt.

Sollte dieser Schritt nicht erfolgreich sein, lesen Sie Behandeln von Problemen in Office Web Apps bei Verwendung mit SharePoint 2013.

## Behandeln von Problemen in Office Web Apps bei Verwendung mit SharePoint 2013

Falls Office Web Apps in Kombination mit SharePoint 2013 nicht ordnungsgemäß funktioniert, suchen Sie im Anschluss das entsprechende Symptom, und erweitern Sie die Überschrift, um die Problembehandlungsschritte anzuzeigen.

## Problem: Wenn Sie in einer SharePoint-Bibliothek den Link "Neues Dokument" auswählen, wird nicht die Option zum Erstellen eines neuen Office-Dokuments angezeigt. Stattdessen werden Sie aufgefordert, ein Dokument hochzuladen. Durch Auswählen (einmaliges Klicken) eines Office-Dokuments wird die Datei in der Clientanwendung geöffnet. Es wird keine Office-Dokumentvorschau angezeigt.

Im Anschluss finden Sie einige Problembehandlungsvorschläge.

**Vergewissern Sie sich, dass von der SharePoint-Webanwendung, mit der das neue Dokument erstellt wird, die anspruchsbasierte Authentifizierung verwendet wird.**

Dateien können nur von Webanwendungen mit anspruchsbasierter Authentifizierung in Office Web Apps geöffnet werden. Gehen Sie wie folgt vor, um den Authentifizierungsanbieter einer Webanwendung zu ermitteln:

1.  Klicken Sie in der SharePoint 2013-Zentraladministration auf **Webanwendungen verwalten**.

2.  Wählen Sie die zu überprüfende Webanwendung aus, und klicken Sie anschließend auf dem Menüband auf **Authentifizierungsanbieter**.

Als Authentifizierungsanbieter muss **Anspruchsbasierte Authentifizierung** angezeigt werden, damit Office Web Apps in der Webanwendung ordnungsgemäß funktioniert. Zur Behebung dieses Problems können Sie die Webanwendung löschen und sie mit anspruchsbasierter Authentifizierung neu erstellen oder die Authentifizierungsmethode in der Webanwendung ändern. Weitere Informationen finden Sie unter [SharePoint-Authentifizierungsanforderungen für Office Web Apps](plan-office-web-apps-used-with-sharepoint-2013.md).

**Vergewissern Sie sich, dass die WOPI-Zonen von SharePoint 2013 und Office Web Apps Server-Farm übereinstimmen.**

Führen Sie hierzu auf dem Computer mit SharePoint Server den folgenden Befehl aus:

```PowerShell
    Get-SPWopiZone 
```

Mögliche Ergebnisse:

  - internal-https

  - internal-http

  - external-https

  - external-http

Führen Sie anschließend auf dem Computer mit SharePoint Server den folgenden Befehl aus:

```PowerShell
    Get-SPWOPIBinding
```

Suchen Sie in der Ausgabe nach **WopiZone: *Zone***. Entspricht das Ergebnis von "Get-SPWopiZone" nicht der Zone, die von "Get-SPWOPIBinding" zurückgegeben wird, müssen Sie auf dem Computer mit SharePoint Server das Cmdlet **Set-SPWOPIZone -Zone** ausführen, um die WOPI-Zone auf das Ergebnis von "Get-SPWOPIBinding" festzulegen. Hilfe zur Verwendung dieser Cmdlets finden Sie unter [Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps), [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps) sowie unter [Get-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIZone?view=sharepoint-ps).

## Problem: Sie erhalten beim Versuch ein Office-Dokument in Office Web Apps zu bearbeiten eine Fehlermeldung, dass das Dokument nicht zum Bearbeiten geöffnet werden kann.

In manchen Situationen können Benutzer, die Mitglieder der Active Directory-Sicherheitsgruppen sind, Dokumente möglicherweise nicht im Browser bearbeiten. Die Lösung dieses Problems liegt darin zu gewährleisten, dass die Benutzerprofildienst-Anwendung (UPA) ordnungsgemäß konfiguriert und vollständig mit den Benutzer- und Gruppenmitgliedschaften synchronisiert sind. Weitere Informationen dazu finden Sie im KB-Artikel [Benutzer, die Mitglieder der Sicherheitsgruppen sind, können mit SharePoint 2013 keine Office Web Apps 2013-Dateien bearbeiten](https://support.microsoft.com/kb/2908321).

## Problem: Wenn Sie ein Office-Dokument in Office Web Apps anzeigen möchten, werden Sie darüber informiert, dass leider ein Fehler aufgetreten ist.

Vergewissern Sie sich, dass Sie nicht mit dem Systemkonto angemeldet sind, da Sie dann ein Dokument weder bearbeiten noch anzeigen können. Melden Sie sich als anderer Benutzer an, und versuchen Sie anschließend erneut, auf Office Web Apps zuzugreifen.

## Problem: Wenn Sie versuchen, ein Dokument in Office Web Apps anzuzeigen, werden Sie darüber informiert, dass das Dokument leider wegen eines Problems nicht geöffnet werden kann.

Wenn Sie Office Web Apps in einer Testumgebung mit HTTP einrichten, müssen Sie sicherstellen, dass die Einstellung "AllowOAuthOverHttp" gemäß der Beschreibung unter Schritt 5: Festlegen der Einstellung "AllowOAuthOverHttp" in SharePoint 2013 auf "True" auf **True** festgelegt ist.

Haben Sie mithilfe des Cmdlets [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps) Domänen zur Liste "Zulassen hinzugefügt? Falls ja, stellen Sie sicher, dass Sie von einer Hostdomäne, die sich auf der Liste „Zulassen“ befindet, auf Office Web Apps zugreifen. Zum Anzeigen der Hostdomänen auf der Liste "Zulassen" auf dem Office Web Apps Server öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator und führen das Cmdlet [Get-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappshost?view=officewebapps-ps) aus. Wenn Sie eine Domäne zur Liste "Zulassen" hinzufügen möchten, verwenden Sie das Cmdlet [New-OfficeWebAppsHost](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappshost?view=officewebapps-ps).

## Problem: Wenn Sie ein Office-Dokument in Office Web Apps anzeigen möchten, werden Sie darüber informiert, dass der Dienst leider ausgelastet ist.

  - Haben Sie Office Web Apps Server eventuell auf einem Domänencontroller installiert? Office Web Apps Server kann leider nicht auf einem Domänencontroller ausgeführt werden. Office Web Apps Server muss auf einem separaten Server installiert sein, der Teil einer Domäne ist. Weitere Informationen finden Sie unter [Software-, Hardware- und Konfigurationsanforderungen für Office Web Apps Server](plan-office-web-apps-server.md).

  - Vergewissern Sie sich, dass Sie SharePoint 2013 Build 15.0.4420.1017 oder höher ausführen. Führen Sie auf dem SharePoint 2013-Server diese Schritte durch, um die Buildnummer zu überprüfen:
    
    1.  Wechseln Sie zu **Start** \> **Alle Programme** \> **Microsoft SharePoint 2013-Produkte** \> **SharePoint 2013-Zentraladministration**.
    
    2.  Klicken Sie auf **Systemeinstellungen** \> **Server in dieser Farm verwalten**.
    
    Überprüfen Sie, ob die **Konfigurationsdatenbankversion15.0.4420.1017** oder höher ist. Falls das nicht der Fall ist, finden Sie weitere Informationen im [Update Center für Office, Office-Server und verwandte Produkte](https://go.microsoft.com/fwlink/p/?linkid=160585).

## Problem: Wenn Sie ein Office-Document in Office Web Apps über eine benutzergenerierte URL anzeigen wollen, werden Sie darüber informiert, dass die Datei nicht gefunden wurde, da die URL der ursprünglichen Datei ungültig oder das Dokument nicht öffentlich zugänglich ist und Sie die URL überprüfen und sich dann an den Besitzer des Dokuments wenden sollen.

Versuchen Sie, über eine benutzergenerierte URL ein Dokument zu öffnen, das größer ist als 10 Megabyte? Stellen Sie sicher, dass das Dokument nicht größer ist als 10 Megabyte.

## Problem: In SharePoint 2013 wird keine Vorschau für Office-Dokumente angezeigt. Stattdessen wird die Fehlermeldung angezeigt, dass dieser Inhalt nicht nicht in einem Frame angezeigt werden kann.

In Umgebungen mit wenig Arbeitsspeicher können Probleme mit der Dokumentvorschau von Office auftreten. Informationen zu den Arbeitsspeicheranforderungen für SharePoint 2013 finden Sie unter [Hardware requirements—web servers, application servers, and single server installations](https://technet.microsoft.com/de-de/4d88c402-24f2-449b-86a6-6e7afcfec0cd\(office.15\)#hwforwebserver). Hierbei handelt es sich um die gleichen Anforderungen wie bei Office Web Apps Server.

## Problem: Sie erhalten die Fehlermeldung, dass eine Datenverbindung so eingerichtet ist, dass sie immer eine Verbindungsdatei verwendet, und {0:ExcelWebApp} externe Verbindungsdateien nicht unterstützt. Daher kann die Verbindung Datenverbindungen nicht aktualisiert werden.

Die Ursache dafür ist, dass Office Web Apps Server die Office Data Connection-Datei (ODC) nicht unterstützt, in der die Datenverbindungsinformationen gespeichert sind. Führen Sie die folgenden Schritte aus, um dieses Problem zu beheben:

1.  Öffnen Sie die Arbeitsmappe in einer Excel-Clientanwendung.

2.  Klicken Sie auf **Daten** \> **Verbindungen**.

3.  Wählen Sie die in der Meldung aufgeführten Datenverbindungen aus, und klicken Sie dann auf **Eigenschaften**.

4.  Klicken Sie auf die Registerkarte **Definition**.

5.  Deaktivieren Sie das Kontrollkästchen **Immer Verbindungsdatei verwenden**.

6.  Laden Sie die Arbeitsmappe erneut in die SharePoint-Dokumentbibliothek hoch.

Damit andere Personen im Browserfenster mit Arbeitsmappen, die ein Datenmodell enthalten, oder Power View-Ansichten interagieren können, konfigurieren Sie Excel Services in SharePoint Server so, dass Arbeitsmappen angezeigt werden. Dazu muss ein SharePoint-Administrator das Cmdlet "New-SPWOPISupressionSetting" auf dem Server ausführen, auf dem SharePoint Server installiert ist. Weitere Informationen finden Sie unter [New-SPWOPISuppressionSetting](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPISuppressionSetting?view=sharepoint-ps) und [Verwalten von Excel Services in SharePoint Server 2013](https://technet.microsoft.com/de-de/library/ee681487\(v=office.15\)).

## Trennen der Verbindung zwischen SharePoint 2013 und Office Web Apps Server

Falls Sie die Verbindung zwischen SharePoint 2013 und Office Web Apps Server einmal trennen möchten, können Sie das folgende Befehlsbeispiel ausführen:

```PowerShell
    Remove-SPWOPIBinding -All:$true
```

Hilfe hierzu finden Sie unter [Remove-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Remove-SPWOPIBinding?view=sharepoint-ps).

## Siehe auch


[New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps)  
[Set-SPWOPIZone](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIZone?view=sharepoint-ps)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen von Office Web Apps Server](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)

