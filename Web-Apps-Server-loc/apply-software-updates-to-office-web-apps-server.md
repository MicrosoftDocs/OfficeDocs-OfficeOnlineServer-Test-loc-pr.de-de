---
title: Anwenden von Softwareupdates auf Office Web Apps Server
TOCTitle: Anwenden von Softwareupdates auf Office Web Apps Server
ms:assetid: 5d15dbd9-374e-422a-a870-43270dd0a2db
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ966220(v=office.15)
ms:contentKeyID: 56631508
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Anwenden von Softwareupdates auf Office Web Apps Server

 

_**Gilt für:** Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:** 2016-12-16_

**Zusammenfassung:** In diesem Artikel wird erläutert, wie Softwareupdates auf eine Office Web Apps Server-Farm angewendet werden.

**Zielgruppe:** IT-Spezialisten

Nach der Einführung einer neuen Version von Office Web Apps Server stellt Microsoft eine Reihe von Softwareupdates zur Verfügung, um die Sicherheit, die Leistung und die Zuverlässigkeit der Server zu verbessern. In diesem Artikel wird erläutert, wie Softwareupdates auf einzelne Server in einer Office Web Apps Server-Farm angewendet werden.


> [!IMPORTANT]
> Dieser Artikel ist Bestandteil der <A href="content-roadmap-for-office-web-apps-server.md">Inhaltsübersicht für Office Web Apps Server</A>. Verwenden Sie diese Übersicht als Ausgangspunkt für Artikel, Downloads und Videos, die Sie bei der Bereitstellung und Verwaltung von Office Web Apps Server unterstützen.<BR><STRONG>Benötigen Sie Hilfe im Zusammenhang mit Office Web Apps auf Ihrem Desktop oder Ihrem mobilen Gerät?</STRONG> Sie finden diese Informationen, indem Sie nach "Office Web Apps" auf <A href="http://office.microsoft.com/de-de/">Office.com</A> suchen.




> [!WARNING]
> Die Anwendung von Office Web Apps Server-Updates mithilfe des automatischen Updateprozesses wird für Office Web Apps Server nicht unterstützt. Dies ist der Fall, da Updates für einen Office Web Apps Server auf eine spezifische Weise angewendet werden müssen, wie in diesem Artikel erläutert wird. Wenn Updates für Office Web Apps Server automatisch angewendet werden, können Benutzer möglicherweise keine Dokumente in Office Web Apps anzeigen oder bearbeiten. Wenn dies geschieht, müssen Sie Ihre Office Web Apps Server-Farm neu erstellen, Zum Neuerstellen einer Farm müssen Sie den Office Web Apps Server mithilfe von <A href="https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps">Remove-OfficeWebAppsMachine</A> aus der Farm entfernen und den Office Web Apps Server über die Option <STRONG>Software</STRONG> deinstallieren. Anschließend müssen Sie den Office Web Apps Server mithilfe der unter <A href="deploy-office-web-apps-server.md">Bereitstellen von Office Web Apps Server</A> beschriebenen Schritte neu installieren. Wenden Sie nach der Neuinstallation das Update mithilfe der in diesem Artikel erläuterten Schritte an.<BR>Lesen Sie unbedingt die Richtlinien im Artikel zum <A href="plan-office-web-apps-server.md">Planen von Updates für Office Web Apps Server</A>, und richten Sie einen Updateprozess für die Office Web Apps Server-Farm ein.



## Bevor Sie beginnen:

Die aktuelle Liste der verfügbaren Updates für Office Web Apps Server finden Sie im [Blog zu Microsoft Office Updates](http://go.microsoft.com/fwlink/p/?linkid=280269) und im [Update Center für Office, Office-Server und verwandte Produkte](http://technet.microsoft.com/de-de/office/ee748587.aspx).

Mit Updates, die für Office Web Apps Server veröffentlicht wurden, werden Office Web Apps Server und alle installierten Office Web Apps Server-Sprachpakete aktualisiert. Es gibt keine separaten Updates für Office Web Apps Server-Sprachpakete.

Sie müssen die Office Web Apps Server-Farm als Teil des Updateprozesses neu erstellen. Überprüfen Sie zur Vorbereitung des Neuerstellens der Office Web Apps Server-Farm die aktuellen Eigenschaften der Office Web Apps Server-Farm, indem Sie das Windows PowerShell-Cmdlet **Get-OfficeWebAppFarm** ausführen und die Parameter für [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps) überprüfen. Die Parameter, die Sie für **New-OfficeWebAppsFarm** verwenden, sollten dieselben sein, die Sie bei der erstmaligen Einrichtung der Office Web Apps Server-Farm verwendet haben.


> [!NOTE]
> Sie können die Aufgaben in diesem Artikel mit einer Maus, mithilfe von Tastenkombinationen oder per Fingereingabe durchführen. Weitere Informationen finden Sie in den folgenden Ressourcen: 
> <UL>
> <LI>
> <P><A href="http://go.microsoft.com/fwlink/p/?linkid=249150">Tastenkombinationen</A></P>
> <LI>
> <P><A href="http://go.microsoft.com/fwlink/p/?linkid=249151">Fingereingabe</A></P></LI></UL>



## Anwenden von Softwareupdates auf eine Office Web Apps Server-Farm mit einem Server

Entfernen Sie zum Anwenden von Softwareupdates auf eine Office Web Apps Server-Farm mit einem Server den Office Web Apps Server aus der Farm, wenden Sie das Softwareupdate an, und erstellen Sie die Office Web Apps Server-Farm neu. Wenn die Office Web Apps Server-Farm nur einen einzigen Server enthält, können Benutzer Office Web Apps nicht nutzen, während Sie den Server aktualisieren. Aktualisieren Sie den Office Web Apps Server also möglichst außerhalb der Geschäftszeiten.

**So wenden Sie Softwareupdates auf eine Farm mit einem Server an**

1.  Wenn das Update noch nicht auf den Office Web Apps Server heruntergeladen wurde, laden Sie das gewünschte Office Web Apps Server-Update aus dem [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=280274) herunter.

2.  Öffnen Sie auf dem Office Web Apps Server, auf den Sie das Softwareupdate anwenden möchten, die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie den folgenden Befehl aus.
    
    ```PowerShell
        Remove-OfficeWebAppsMachine
    ```
3.  Installieren Sie das Office Web Apps Server-Update auf diesem Server. Starten Sie den Server neu, wenn Sie dazu aufgefordert werden.

4.  Öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie das **New-OfficeWebAppsFarm**-Cmdlet aus, um eine Office Web Apps Server-Farm neu zu erstellen. Die URL, die Sie für **–InternalURL** angeben, ist der Name des Servers, auf dem Office Web Apps Server ausgeführt wird (beispielsweise **http://Contoso-WAC**). In diesem Fall verwenden Sie denselben Namen, den Sie für die vorherige Office Web Apps Server-Farm verwendet haben. Verwenden Sie die gleichen zusätzlichen Parameter, die Sie beim erstmaligen Erstellen der Office Web Apps Server-Farm verwendet haben. Beispielsweise wird die Farm mit dem Parameter **–AllowHttp** für die Verwendung von HTTP konfiguriert, und der Parameter **–EditingEnabled** ermöglicht die Bearbeitung in Office Web Apps wenn diese Anwendung zusammen mit SharePoint 2013 verwendet wird. Der Parameter **–EditingEnabled** wird von Lync Server 2013 oder Exchange Server 2013 nicht verwendet, da diese Hosts keine Bearbeitungsfunktionen unterstützen.
    
    Mit dem Code im folgenden Beispiel wird eine neue Office Web Apps Server-Farm mit dem Namen **http://Contoso-WAC** erstellt.
    
    ```PowerShell
        New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    ```
    
    Informationen zu weiteren Parametern zum Konfigurieren von Übersetzungsdiensten, Proxyservern, ClipArt-Unterstützung und Onlineviewern finden Sie unter [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

## Anwenden von Softwareupdates auf eine Office Web Apps Server-Farm mit mehreren Servern

Entfernen Sie zum Anwenden von Softwareupdates auf eine Office Web Apps Server-Farm mit mehreren Servern zunächst einen der Server aus dem Lastenausgleichspool und aus der Farm, wenden Sie das Softwareupdate an, und erstellen Sie eine aktualisierte Office Web Apps Server-Farm. Anschließend entfernen und aktualisieren Sie die verbleibenden Server in der Office Web Apps Server-Farm und fügen sie der neuen aktualisierten Farm hinzu. Sie führen einen Lastenausgleich des Datenverkehrs der neuen Farm durch, wenn Sie über ausreichend Server zur Unterstützung des aktuellen Datenverkehrs in der neuen Farm verfügen. Durch diesen Updateprozess können Benutzer Dokumente in Office Web Apps ohne Unterbrechung öffnen und bearbeiten.

**So wenden Sie Softwareupdates auf eine Farm mit mehreren Servern an**

1.  Laden Sie das gewünschte Office Web Apps Server-Update aus dem [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=280274) in einen Netzwerkspeicherort herunter, der für die Office Web Apps Server-Farm verfügbar ist.

2.  Entfernen Sie den Office Web Apps Server, auf den Sie das Softwareupdate anwenden möchten, aus dem Lastenausgleichspool.

3.  Öffnen Sie auf diesem Office Web Apps Server die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie den folgenden Befehl aus.
    
    ```PowerShell
        Remove-OfficeWebAppsMachine
    ```

4.  Installieren Sie das Office Web Apps Server-Update auf diesem Server. Starten Sie den Server neu, wenn Sie dazu aufgefordert werden.

5.  Öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator, und erstellen Sie eine aktualisierte Office Web Apps Server-Farm mithilfe des **New-OfficeWebAppsFarm**-Cmdlets. Die URL, die Sie für **–InternalURL** angeben, ist der Name des Servers, auf dem Office Web Apps Server ausgeführt wird (beispielsweise **http://Contoso-WAC**). In diesem Fall verwenden Sie denselben Namen wie für die bestehende Office Web Apps Server-Farm. Verwenden Sie die gleichen zusätzlichen Parameter, die Sie beim erstmaligen Erstellen der Office Web Apps Server-Farm verwendet haben. Beispielsweise wird die Farm mit dem Parameter **–AllowHttp** für die Verwendung von HTTP konfiguriert, und der Parameter **–EditingEnabled** ermöglicht die Bearbeitung in Office Web Apps, wenn diese Anwendung zusammen mit SharePoint 2013 verwendet wird. Der Parameter **–EditingEnabled** wird von Lync Server 2013 oder Exchange Server 2013 nicht verwendet, da diese Hosts keine Bearbeitungsfunktionen unterstützen.
    
    Mit dem Code im folgenden Beispiel wird eine neue Office Web Apps Server-Farm mit dem Namen **http://Contoso-WAC** erstellt.
    
    ```PowerShell
       New-OfficeWebAppsFarm -InternalURL "http://Contoso-WAC" -AllowHttp -EditingEnabled
    ```
    
    Informationen zu weiteren Parametern zum Konfigurieren von Übersetzungsdiensten, Proxyservern, ClipArt-Unterstützung und Onlineviewern finden Sie unter [New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps).

6.  Je nachdem, wie viele neue Server die Office Web Apps Server-Farm enthält, führen Sie einen Lastenausgleich des Datenverkehrs für die neue Farm durch. Diesen Schritt können Sie auch später ausführen, wenn mehr aktualisierte Server vorhanden sind, die der Farm hinzugefügt werden sollen.

7.  Führen Sie für jeden verbleibenden Server in der Farm die folgenden Schritte aus.
    
    1.  Entfernen Sie den nächsten Office Web Apps Server aus dem Lastenausgleichspool.
    
    2.  Installieren Sie das Office Web Apps Server-Update auf diesem Server. Starten Sie den Server neu, wenn Sie dazu aufgefordert werden.
    
    3.  Öffnen Sie die Windows PowerShell-Eingabeaufforderung als Administrator, und führen Sie den folgenden Befehl aus. Mit dem Parameter **–MachineToJoin** wird der vorhandene Server einer bestehenden Office Web Apps Server-Farm hinzugefügt. In diesem Fall möchten Sie den Server der aktualisierten Office Web Apps Server-Farm hinzufügen. Verwenden Sie also den Computernamen von einem der Server in der aktualisierten Office Web Apps Server-Farm.
        
        ```PowerShell
            New-OfficeWebAppsMachine -MachineToJoin "server1.contoso.com"
        ```

## Siehe auch


[Remove-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/remove-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsMachine](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsmachine?view=officewebapps-ps)  
[New-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/new-officewebappsfarm?view=officewebapps-ps)  
[Get-OfficeWebAppsFarm](https://docs.microsoft.com/en-us/powershell/module/officewebapps/get-officewebappsfarm?view=officewebapps-ps)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
  

[](content-roadmap-for-office-web-apps-server.md)

