---
title: Standardöffnungsverhaltens für browserfähige Dokumente (Office Web Apps)
TOCTitle: Konfigurieren des Standardöffnungsverhaltens für browserfähige Dokumente
ms:assetid: e27e0bc8-5fb5-4bb1-8157-d7c90654175e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Ee837425(v=office.15)
ms:contentKeyID: 50181147
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Konfigurieren des Standardöffnungsverhaltens für browserfähige Dokumente (Verwendung von Office Web Apps mit SharePoint 2013)

 

_<strong>Gilt für:</strong>  Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_<strong>Letztes Änderungsdatum des Themas:</strong>  2016-12-16_

**Zusammenfassung:** Erklärt das Konfigurieren des Standardöffnungsverhaltens für Office-Dokumente in SharePoint-Websitesammlungen und -Dokumentbibliotheken.

**Zielgruppe:**  IT-Experten

Klicken Sie zum Öffnen eines Dokuments in einer SharePoint 2013-Dokumentbibliothek auf den entsprechenden Titel. Was als Nächstes passiert (ob sich die Daten in einer Clientanwendung oder im Browser öffnet), hängt von mehreren Faktoren ab, z. B. vom Dateityp, von den Einstellungen Ihrer Office Web Apps Server-Farm und von den OpenInClient-Featureeinstellungen der Bibliothek oder Websitesammlung ab. In den folgenden Schritten sind Informationen zum Konfigurieren des Standardöffnungsverhaltens für Office-Dokumente aufgeführt, bei denen Sie SharePoint 2013 so konfiguriert haben, dass es Office Web Apps Server verwendet.

## Festlegen, wie Dokumente aus SharePoint 2013-Bibliotheken geöffnet werden

Nachdem Sie SharePoint 2013 so konfiguriert haben, dass Office Web Apps Server verwendet werden soll, wird durch Klicken auf eine Word-, PowerPoint-, Excel- oder OneNote-Datei im Browser geöffnet. PDF-Dokumente werden in der Word Web App Web App geöffnet. Es gibt zwei Möglichkeiten das Standardverhalten zu ändern, sodass Dateien stattdessen in den Clientanwendungen (oder dem Standard-PDF-Reader) geöffnet werden:

  - **Für die SharePoint 2013-Farm**   Sie können das Standardöffnungsverhalten für die SharePoint 2013-Farm mithilfe von [New-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/New-SPWOPIBinding?view=sharepoint-ps) und [Set-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Set-SPWOPIBinding?view=sharepoint-ps)Windows PowerShell-Cmdlets dateispezifisch anpassen. Diese Cmdlets können auch zum [Anpassen des Verhaltens von PDF-Dokumenten verwendet werden](http://go.microsoft.com/fwlink/p/?linkid=330246).

  - **In Websitesammlungen und Dokumentbibliotheken**   Administratoren und Benutzer von Websitesammlungen können das OpenInClient-Feature in SharePoint 2013 verwenden, um anzugeben, ob Office-Dateien in der Clientanwendung oder im Browser geöffnet werden. Benutzer können diese Einstellung in den Eigenschaften der Dokumentbibliothek ändern, und Websitesammlungsadministratoren können sie in der Websitesammlungsverwaltung oder mithilfe des [Enable-SPFeature](https://technet.microsoft.com/de-de/library/ff607803\(v=office.15\))-Cmdlets ändern, um das OpenInClient-Feature zu aktivieren. Im nächsten Abschnitt finden Sie verschiedene Methoden zum Aktivieren des OpenInClient-Features.

In der Regel überschreibt das OpenInClient-Feature alle WOPI-Bindungen, die Sie zwischen SharePoint 2013 und Office Web Apps Server festgelegt haben. Anders gesagt, falls das OpenInClient-Feature einer SharePoint 2013-Bibliothek oder -Websitesammlung aktiviert ist, werden Dokumente in der Clientanwendung geöffnet, auch wenn Sie den SharePoint 2013-Server so konfiguriert haben, dass er Office Web Apps Server verwenden soll.


> [!TIP]
> Das Konfigurieren des Standardöffnungsverhaltens für browserfähige Dokumente wirkt sich nicht darauf aus, ob Benutzer die Features <STRONG>Auschecken</STRONG> und <STRONG>Senden an</STRONG> in SharePoint 2013 zum Herunterladen von Dokumenten verwenden können. Weitere Informationen zum Konfigurieren von Berechtigungen zum Auschecken, Herunterladen und Anzeigen in SharePoint 2013 finden Sie unter <A href="https://technet.microsoft.com/de-de/library/cc262939(v=office.15)">Planen der Berechtigungen für Websites und Inhalte in SharePoint 2013</A>.



## So legen Sie das OpenInClient-Feature für eine Dokumentbibliothek oder eine Websitesammlung fest

Zum Festlegen des OpenInClient-Features in SharePoint 2013 können Sie folgende Verfahren verwenden.


> [!TIP]
> Für die Verfahren in diesem Artikel wird die SharePoint 2013 Management Shell zur Ausführung von SharePoint-Cmdlets verwendet. Wenn Sie stattdessen die Windows PowerShell-Konsole verwenden, müssen Sie mit dem Cmdlet <STRONG>Add-PSSnapin</STRONG> das Snap-In "Microsoft.SharePoint.PowerShell" hinzufügen. Weitere Informationen Weitere Informationen zum Verwenden von Windows PowerShell mit SharePoint 2013 finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Verwenden von Windows Powershell zur Verwaltung von SharePoint 2013</A>.




> [!TIP]
> Sie können alle Aufgaben in Office 2013-Produktfamilien mit einer Maus, mit Tastenkombinationen oder per Fingereingabe durchführen. Informationen zum Verwenden von Tastenkombinationen und der Fingereingabe in Office-Produkten und -Diensten finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=249150">Tastenkombinationen</A> und im <A href="http://go.microsoft.com/fwlink/p/?linkid=253163">Office-Leitfaden für die Gestensteuerung</A>.



 **Festlegen des OpenInClient-Features Websitesammlungen**

1.  Klicken Sie in der SharePoint-Websitesammlung auf das Symbol **Einstellungen** und dann auf **Websiteeinstellungen**.

2.  Klicken Sie auf der Seite **Websiteeinstellungen** unter **Websitesammlungsverwaltung** auf **Websitesammlungs-Features**.

3.  Wählen Sie auf der Seite **Features** für das Feature **Dokumente standardmäßig in Clientanwendungen öffnen** die Option **Aktivieren** aus, um das OpenInClient-Feature zu aktivieren (um Dokumente in der Clientanwendung zu öffnen). Wählen Sie **Deaktivieren**, um OpenInClient-Feature zu deaktivieren (um Dokumente im Browser zu öffnen).

 **Festlegen des Standardöffnungsverhaltens für Websitesammlungen mithilfe von Windows PowerShell**

1.  Stellen Sie zunächst sicher, dass Sie über folgende Mitgliedschaften verfügen:
    
      - Die feste Serverrolle **securityadmin** auf der SQL Server-Instanz.
    
      - Die feste Datenbankrolle **db\_owner** auf allen Datenbanken, die aktualisiert werden.
    
      - Mitglied der Gruppe der Administratoren auf dem Server, auf dem die Windows PowerShell-Cmdlets ausgeführt werden.
    
    Lesen Sie die Informationen in [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050), und fügen Sie gegebenenfalls weitere Mitgliedschaften hinzu.
    
    Mit dem Cmdlet **Add-SPShellAdmin** kann ein Administrator die Berechtigung zur Verwendung von SharePoint 2013-Cmdlets gewähren.
    

    > [!TIP]
    > Wenn Sie keine Berechtigungen haben, wenden Sie sich an den Setupadministrator oder SQL&nbsp;Server-Administrator, um Berechtigungen anzufordern. Weitere Informationen über Windows PowerShell-Berechtigungen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Permissions</A> und <A href="https://technet.microsoft.com/de-de/library/ff607596(v=office.15)">Add-SPShellAdmin</A>.



2.  Öffnen Sie eine SharePoint 2013 Management Shell mit erhöhten Rechten:
    
    **Windows Server 2008**
    
    1.  Wählen Sie im **Startmenü**die Option **Alle Programme** aus.
    
    2.  Wählen Sie **Microsoft SharePoint 2013-Produkte** aus.
    
    3.  Wählen Sie **SharePoint 2013-Verwaltungsshell** aus, und zeigen Sie das Kontextmenü an (Rechtsklick).
    
    4.  Wählen Sie im Kontextmenü die Option **Als Administrator ausführen** aus.
    
    **Windows Server 2012**
    
    1.  Führen Sie eine Streifbewegung vom Bildschirmrand aus, um die Charms anzuzeigen, und wählen Sie dann **Suchen** aus, um alle auf dem Computer installierten Apps anzuzeigen.
    
    2.  Wählen Sie (per Rechtsklick) **SharePoint 2013-Verwaltungsshell** aus, und zeigen Sie die App-Leiste an.
    
    3.  Wählen Sie auf der App-Leiste die Option **Als Administrator ausführen** aus.

3.  Geben Sie an der Windows PowerShell-Eingabeaufforderung einen der folgenden Befehle ein:
    
      - Um das OpenInClient-Feature für eine bestimmte Websitesammlung zu aktivieren (Dokumente in der Clientanwendung öffnen), geben Sie folgenden Befehl ein:
      
      ```PowerShell
            Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
      ```
      ```        
        Dabei ist *\<SiteCollURL\>* die URL der Websitesammlung.
      ```
      - Um das OpenInClient-Feature für alle Websitesammlungen zu aktivieren (Dokumente in der Clientanwendung öffnen), geben Sie folgenden Befehl ein:
        
      ```PowerShell
            Get-SPSite -limit ALL |foreach{ Enable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }
      ```
    
      - Um das OpenInClient-Feature für eine bestimmte Websitesammlung zu deaktivieren (Dokumente im Browser öffnen), geben Sie folgenden Befehl ein:

      ```PowerShell  
            Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url <SiteCollURL>
      ```
      ```  
        Dabei ist *\<SiteCollURL\>* die URL der Websitesammlung.
      ```
      - Um das OpenInClient-Feature für alle Websitesammlungen zu deaktivieren (Dokumente im Browser öffnen), geben Sie folgenden Befehl ein:
        
      ```PowerShell
            Get-SPSite -limit ALL |foreach{ Disable-SPFeature 8A4B8DE2-6FD8-41e9-923C-C7C3C00F8295 -url $_.URL }
      ```

 **Festlegen des Standardöffnungsverhaltens für eine Dokumentbibliothek mithilfe der Einstellungsseite der Dokumentbibliothek**

1.  Klicken Sie auf der Seite der Dokumentbibliothek auf die Registerkarte **Bibliothek**.

2.  Klicken Sie in der Gruppe **Einstellungen** auf **Bibliothekeinstellungen**.

3.  Klicken Sie auf der Seite **Dokumentbibliothekseinstellungen** auf **Erweiterte Einstellungen**.

4.  Wählen Sie auf der Seite **Erweiterte Einstellungen** unter **Öffnen eines Dokuments im Browser** eine der folgenden Optionen aus:
    
      - **In der Clientanwendung öffnen**   Wenn ein Benutzer ein Dokument in dieser Bibliothek auswählt, wird das Dokument in der entsprechenden Clientanwendung geöffnet (sofern verfügbar).
    
      - **Im Browser öffnen**   Wenn ein Benutzer ein Dokument in dieser Bibliothek auswählt, wird das Dokument im Webbrowser in der Web App für den betreffenden Dokumenttyp geöffnet. Beim Öffnen des Dokuments in der Web App kann der Benutzer dann angeben, dass er das Dokument in der Clientanwendung öffnen möchte.
    
      - **Serverstandard verwenden**   Wenn ein Benutzer ein Dokument in dieser Bibliothek auswählt, wird das Dokument mithilfe des für den SharePoint 2013-Server angegebenen Standardöffnungsverhaltens geöffnet.

 **Festlegen des Standardöffnungsverhaltens für Websitesammlungen mithilfe von Windows PowerShell**

1.  Stellen Sie zunächst sicher, dass Sie über folgende Mitgliedschaften verfügen:
    
      - Die feste Serverrolle **securityadmin** auf der SQL Server-Instanz.
    
      - Die feste Datenbankrolle **db\_owner** auf allen Datenbanken, die aktualisiert werden.
    
      - Mitglied der Gruppe der Administratoren auf dem Server, auf dem die Windows PowerShell-Cmdlets ausgeführt werden.
    
    Lesen Sie die Informationen in [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050), und fügen Sie gegebenenfalls weitere Mitgliedschaften hinzu.
    
    Mit dem Cmdlet **Add-SPShellAdmin** kann ein Administrator die Berechtigung zur Verwendung von SharePoint 2013-Cmdlets gewähren.
    

    > [!TIP]
    > Wenn Sie keine Berechtigungen haben, wenden Sie sich an den Setupadministrator oder SQL&nbsp;Server-Administrator, um Berechtigungen anzufordern. Weitere Informationen über Windows PowerShell-Berechtigungen finden Sie unter <A href="https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps">Permissions</A> und <A href="https://technet.microsoft.com/de-de/library/ff607596(v=office.15)">Add-SPShellAdmin</A>.



2.  Öffnen Sie eine SharePoint 2013 Management Shell mit erhöhten Rechten:
    
    **Windows Server 2008**
    
    1.  Wählen Sie im **Startmenü** die Option **Alle Programme** aus.
    
    2.  Wählen Sie **Microsoft SharePoint 2013-Produkte** aus.
    
    3.  Wählen Sie **SharePoint 2013-Verwaltungsshell** aus, und zeigen Sie das Kontextmenü an (Rechtsklick).
    
    4.  Wählen Sie im Kontextmenü die Option **Als Administrator ausführen** aus.
    
    **Windows Server 2012**
    
    1.  Führen Sie eine Streifbewegung vom Bildschirmrand aus, um die Charms anzuzeigen, und wählen Sie dann **Suchen** aus, um alle auf dem Computer installierten Apps anzuzeigen.
    
    2.  Wählen Sie **SharePoint 2013-Verwaltungsshell** aus (Rechtsklick), um die App-Leiste anzuzeigen.
    
    3.  Wählen Sie auf der App-Leiste die Option **Als Administrator ausführen** aus.

3.  Geben Sie an der Windows PowerShell-Eingabeaufforderung den folgenden Befehl ein:
    
      ```PowerShell
        Get-SPWeb -site <SiteCollURL> | % {$_.Lists} | where {$_.IrmEnabled -eq $true} | % {$_.DefaultItemOpen =[Microsoft.Sharepoint.DefaultItemOpen]::<DefaultItemOpenSetting>; $_.Update()}
      ```
    
    Dabei gilt:
    
      - *\<SiteCollURL\>* ist die URL der Websitesammlung, in der sich die Dokumentbibliotheken befinden.
    
      - *\<DefaultItemOpenSetting\>* ist ein **DefaultItemOpen**-Aufzählungswert, der das Standardöffnungsverhalten angibt. Verwenden Sie **PreferClient**, um Dokumente in der ihnen zugeordneten Clientanwendung zu öffnen (sofern verfügbar). Verwenden Sie **Browser**, um Dokumente im Browser zu öffnen.

## Siehe auch


[Get-SPWOPIBinding](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/Get-SPWOPIBinding?view=sharepoint-ps)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Windows Powershell zur Verwaltung von SharePoint 2013](https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/?view=sharepoint-ps)  
[Office Web Apps Server](office-web-apps-server.md)  


[Get-SPWeb](https://technet.microsoft.com/de-de/library/ff607807\(v=office.15\))  
[Get-SPSite](https://technet.microsoft.com/de-de/library/ff607950\(v=office.15\))  
[Get-SPFeature](https://technet.microsoft.com/de-de/library/ff607945\(v=office.15\))

