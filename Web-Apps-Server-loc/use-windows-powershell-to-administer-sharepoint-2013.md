---
title: Verwenden von Windows Powershell zur Verwaltung von SharePoint 2013
TOCTitle: Verwenden von Windows Powershell zur Verwaltung von SharePoint 2013
ms:assetid: ae4901b4-505a-42a9-b8d4-fca778abc12e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Ee806878(v=office.15)
ms:contentKeyID: 49633178
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Verwenden von Windows Powershell zur Verwaltung von SharePoint 2013

 

_**Gilt für:**SharePoint Foundation 2013, SharePoint Server 2013 Enterprise, SharePoint Server 2013 Standard_

_**Letztes Änderungsdatum des Themas:**2016-12-16_

**Zusammenfassung:**Hier erfahren Sie mehr über einfache Windows PowerShell-Cmdlets und -Konzepte sowie die Verwendung von Windows PowerShell mit SharePoint 2013.

Inhalt dieses Artikels

  - Übersicht

  - ugreifen auf Windows PowerShell für SharePoint 2013-Produkte

  - Berechtigungen

  - Skripts und Ausführungsrichtlinien

  - Erlernen von Windows PowerShell

## Übersicht

Windows PowerShell ist eine Befehlsshell und Skriptsprache, die einem Administrator den Vollzugriff auf entsprechende Anwendungsprogrammierschnittstellen (Application Programming Interfaces, APIs) bietet. Administratoren können direkt mit SharePoint 2013 kommunizieren, um Webanwendungen, Websitesammlungen, Websites, Listen und viele andere Elemente zu bearbeiten. Darüber hinaus können Administratoren Skripts für Cmdlets (ausgesprochen "Command-lets") schreiben.

Windows PowerShell 3.0 ist eine Voraussetzung für die Installation von SharePoint 2013 und wird beim Ausführen von Vorbereitungstool für Microsoft SharePoint-Produkte installiert (sofern nicht bereits installiert). Standardmäßig befindet sich Windows PowerShell unter folgendem Pfad: \<%SystemRoot%\>\\System32\\WindowsPowerShell\\v1.0\\PowerShell.exe.

Eine Liste der neuen Features für Windows PowerShell 3.0 finden Sie unter [Windows Management Framework 3.0](http://go.microsoft.com/fwlink/p/?linkid=272782)

Ein interaktives Tool und eine Anleitung, die Ihnen beim Erlernen der Windows PowerShell-Syntax helfen, finden Sie unter [Windows PowerShell Command Builder](http://go.microsoft.com/fwlink/p/?linkid=229854) sowie im [Handbuch für die ersten Schritte](http://www.microsoft.com/en-us/download/details.aspx?id=27588).

Es wird empfohlen, Windows PowerShell zum Ausführen von administrativen Befehlszeilenaufgaben zu verwenden. Das Befehlszeilentool Stsadm ist veraltet, aber weiterhin vorhanden, um die Kompatibilität mit früheren Produktversionen zu gewährleisten.

## Zugreifen auf Windows PowerShell für SharePoint 2013

Nach der Installation von SharePoint 2013 stehen Ihnen entsprechende Windows PowerShell-Cmdlets in der SharePoint 2013 Management Shell zur Verfügung. Sie können die meisten Aspekte von SharePoint 2013 in der SharePoint-Verwaltungsshell verwalten. Sie können neue Websitesammlungen, Webanwendungen, Benutzerkonten, Dienstanwendungen, Proxys und viele andere Elemente erstellen. Befehle, die Sie in der SharePoint-Verwaltungsshell eingeben, geben SharePoint-Objekte zurück, die auf Microsoft .NET Framework basieren. Sie können diese Objekte als Eingabe für nachfolgende Befehle übernehmen oder die Objekte in lokalen Variablen zur späteren Verwendung speichern.

Sie müssen bei der SharePoint-Verwaltungsshell das Snap-In, das die Cmdlets enthält, nicht registrieren. Die Registrierung des Moduls Microsoft.SharePoint.PowerShell.dll für SharePoint 2013-Cmdlets erfolgt automatisch als Folge der Zeile `Add-PSSnapin Microsoft.SharePoint.PowerShell` in der Datei SharePoint.ps1, die sich in *%CommonProgramFiles%*\\Microsoft Shared\\Web Server Extensions\\15\\Config\\PowerShell\\Registration befindet. Zur Verwendung der Windows PowerShell-Konsole müssen Sie dieses Snap-In manuell registrieren.

Unabhängig davon, ob Sie die SharePoint-Verwaltungsshell oder die Windows PowerShell-Konsole verwenden, können Sie auch zusätzliche Snap-Ins laden. Weitere Informationen finden Sie unter [Anpassen von Profilen](http://go.microsoft.com/fwlink/p/?linkid=183166).

**So greifen Sie auf die SharePoint-Verwaltungsshell zu**

1.  Starten Sie SharePoint-Verwaltungsshell.
    
      - Unter Windows Server 2008 R2:
        
          - Klicken Sie auf **Start**, **Microsoft SharePoint 2013-Produkte** und dann auf **SharePoint-Verwaltungsshell**.
    
      - Für Windows Server 2012:
        
          - Klicken Sie auf der **Startseite**auf **SharePoint-Verwaltungsshell**.
            
            Falls sich **SharePoint-Verwaltungsshell** nicht auf der **Startseite** befindet:
        
        <!-- end list -->
        
          - Klicken Sie mit der rechten Maustaste auf **Computer**, und klicken Sie auf **Alle Apps** und dann auf **SharePoint-Verwaltungsshell**.
    
    Weitere Informationen zur Interaktion mit Windows Server 2012 finden Sie unter [Allgemeine Verwaltungsaufgaben und Navigation in Windows Server 2012](http://technet.microsoft.com/de-de/library/hh831491.aspx).


> [!TIP]
> Die SharePoint 2013 Management Shell und die Windows PowerShell-Konsole unterscheiden sich auch bezüglich der Verwendung der <CODE>ReuseThread</CODE>-Option, die definiert, wie das Threadmodell verwendet wird. Die Verwendung durch die SharePoint 2013 Management Shell wird durch die Zeile <CODE>{Host.Runspace.ThreadOptions = "ReuseThread"}</CODE> definiert, die sich in der Datei "SharePoint.ps1" befindet. Weitere Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=183145">PSThreadOptions-Enumeration</A>.



## Berechtigungen

## Lokal

Um Benutzern die Berechtigung zu erteilen, SharePoint 2013-Cmdlets ausführen zu können, Stellen Sie vor der Verwendung des **Add-SPShellAdmin**-Cmdlets sicher, dass die folgenden Mindestanforderungen vollständig erfüllt sind:

  - Sie müssen Mitglied der festen Serverrolle **securityadmin** auf der SQL Server-Instanz sein.

  - Sie müssen Mitglied der festen Datenbankrolle **db\_owner** in allen Datenbanken sein, die aktualisiert werden sollen.

  - Sie müssen Mitglied der Gruppe Administratoren auf dem Server sein, auf dem das Windows PowerShell-Cmdlet ausgeführt wird.


> [!TIP]
> Wenn diese Voraussetzungen nicht erfüllt sind, setzen Sie sich mit dem Setup-Administrator oder SQL&nbsp;Server-Administrator in Verbindung, damit Ihnen diese Berechtigungen erteilt werden.



Zusätzliche Informationen über Windows PowerShell-Berechtigungen finden Sie unter Berechtigungen und unter [Add-SPShellAdmin](https://technet.microsoft.com/de-de/library/ff607596\(v=office.15\))

Wenn Sie nicht Mitglied der **SharePoint\_Shell\_Access**-Rolle oder der lokalen Gruppe **WSS\_Admin\_WPG** sind, fügen Sie die **WSS\_Admin\_WPG**-Gruppe mithilfe des **Add-SPShellAdmin**-Cmdlets auf allen Front-End-Webservern in der SharePoint-Farm und der **SharePoint\_Shell\_Access**-Rolle hinzu. Wenn die SQL Server-Datenbank nicht über eine **SharePoint\_Shell\_Access**-Rolle verfügt, wird die Rolle automatisch beim Ausführen des **Add-SPShellAdmin**-Cmdlets erstellt. Nach dem Ausführen des **Add-SPShellAdmin**-Cmdlets können Benutzer SharePoint Windows PowerShell-Cmdlets in einer Farmumgebung mit mehreren Servern ausführen.


> [!TIP]
> Wenn Sie SharePoint 2013 installieren, wird dem Benutzerkonto, das Sie zur Ausführung der Installation verwenden, die entsprechenden Berechtigungen zur Ausführung von Windows PowerShell-Cmdlets erteilt. Wenn noch keine Benutzer hinzugefügt wurden, um ein Windows PowerShell-Cmdlet auszuführen, können Sie sie mithilfe des <STRONG>Add-SPShellAdmin</STRONG>-Cmdlets hinzufügen.



Sie müssen das **Add-SPShellAdmin**-Cmdlet für alle Datenbanken ausführen, für die Sie Zugriff gewähren möchten. Wenn keine Datenbank angegeben wird, wird die Serverfarm-Konfigurationsdatenbank verwendet. Wenn Sie eine Datenbank angeben, wird die Serverfarm-Inhaltsdatenbank zusätzlich zur angegebenen Serverfarm-Konfigurationsdatenbank berücksichtigt.

Wenn Sie eine Liste aller **SPShellAdmin**-Cmdlets anzeigen möchten, geben Sie an einer Windows PowerShell-Eingabeaufforderung `Get-Command -Noun SPShellAdmin` ein.

## SharePoint Online

Vergewissern Sie sich, dass Sie über die folgenden Administratorrechte verfügen:

  - Ihnen muss die globale Administratorrolle auf der SharePoint Online-Website zugewiesen sein, auf der Sie das Windows PowerShell-Cmdlet ausführen. Weitere Informationen finden Sie unter [Standardadministratorrollen und -benutzergruppen](http://go.microsoft.com/fwlink/p/?linkid=242451).
    

    > [!IMPORTANT]
    > Sie können eine bestimmte Windows PowerShell-Gruppe mit SharePoint Online verwenden. Weitere Informationen finden Sie unter <A href="https://technet.microsoft.com/de-de/library/fp161362(v=office.15)">Office 365 PowerShell für SharePoint Online</A>.



## Skripts und Ausführungsrichtlinien

Obwohl Sie mit Windows PowerShell auch einzelne administrative Aufgaben ausführen können, können Sie auch ein Skript zum Automatisieren einer Serie von Aufgaben erstellen. Ein Skript ist eine Textdatei, die einen oder mehrere Windows PowerShell-Befehle enthält. Windows PowerShell-Skripts haben die Dateinamenerweiterung PS1.

Zur Ausführung von Skripts ist "RemoteSigned" die mindestens erforderliche Ausführungsrichtlinie für SharePoint 2013, während die Standardrichtlinie für Windows PowerShell "Restricted" ist. Wenn die Richtlinie "Restricted" beibehalten wird, ändert die SharePoint 2013 Management Shell die Richtlinie für Windows PowerShell zu "RemoteSigned". Das bedeutet, dass Sie **Als Administrator ausführen** auswählen müssen, um die SharePoint 2013 Management Shell mit erhöhten Administratorrechten auszuführen. Diese Änderung gilt dann für alle Windows PowerShell-Sitzungen. Weitere Informationen finden Sie unter [ExecutionPolicy-Enumeration](http://go.microsoft.com/fwlink/p/?linkid=242452).

Zusätzliche Informationen über Skripts und Ausführungsrichtlinien finden Sie unter [about\_scripts](http://go.microsoft.com/fwlink/p/?linkid=144310) bzw. [about\_Execution\_Policies](http://go.microsoft.com/fwlink/p/?linkid=193050).

## Erlernen von Windows PowerShell

Es stehen verschiedene Windows PowerShell-Lernressourcen für SharePoint-IT-Experten zur Verfügung.

**TechNet Scripting Center**

Das TechNet Scripting Center enthält zahlreiche Ressourcen, um Ihnen beim Erlernen der Grundlagen von Windows PowerShell zu helfen. Es enthält auch Skriptrepositorys mit Beispielen für Skripts, die normalerweise mit verschiedenen Microsoft-Produkten verwendet werden. In der folgenden Tabelle sind die wichtigsten Lernressourcen aufgelistet.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Seite</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187813">Windows PowerShell-Dokumentation in TechNet</a></p></td>
<td><p>Dieser Abschnitt der TechNet Library enthält Webkopien der wichtigsten Windows PowerShell-Hilfethemen. Der Abschnitt bietet außerdem Webkopien des Erste Schritte-Dokuments für Windows PowerShell, der Hilfe zu PowerShell.exe und eine Einführung in Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187815">Skripterstellung mit Windows PowerShell</a></p></td>
<td><p>Die Homepage für Schulungsressourcen für die Skripterstellung mit Windows PowerShell.</p></td>
</tr>
<tr class="odd">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187817">Windows PowerShell Owner's Manual</a></p></td>
<td><p>Webbasiertes Handbuch für die ersten Schritte mit Windows PowerShell.</p></td>
</tr>
<tr class="even">
<td><p><a href="http://go.microsoft.com/fwlink/p/?linkid=187819">Windows PowerShell-Kurzübersicht</a></p></td>
<td><p>Herunterladbare Kopie der Kurzübersicht, die mit Windows PowerShell installiert wird.</p></td>
</tr>
</tbody>
</table>


Sie sollten sich beim Durchlesen dieser Ressourcen vor der Verwendung von Windows PowerShell für SharePoint 2013 mit den folgenden Konzepten und Cmdlets vertraut machen:

  - [Get-Command](http://go.microsoft.com/fwlink/p/?linkid=171069)

  - [Get-Member](http://go.microsoft.com/fwlink/p/?linkid=171070)

  - [Get-Help](http://go.microsoft.com/fwlink/p/?linkid=171068)

  - [about\_Aliases](http://go.microsoft.com/fwlink/p/?linkid=113207)

  - [Piping und die Pipeline in Windows PowerShell](http://go.microsoft.com/fwlink/p/?linkid=187808)

  - [Cmdlet-Parametersätze](http://go.microsoft.com/fwlink/p/?linkid=187810)

  - [Foreach-Object](http://go.microsoft.com/fwlink/p/?linkid=187812)

  - [Where-Object](http://go.microsoft.com/fwlink/p/?linkid=187811)

