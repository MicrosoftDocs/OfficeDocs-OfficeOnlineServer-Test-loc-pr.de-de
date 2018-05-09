---
title: Remove-SPWOPIBinding
TOCTitle: Remove-SPWOPIBinding
ms:assetid: 52855c21-ee2c-497a-b308-bf5eeabe4bbe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219438(v=office.15)
ms:contentKeyID: 49633160
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPIBinding

 

_**Gilt für:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:**2015-03-09_

Entfernt Bindungen für Anwendungen, Dateinamenerweiterungen und zugehörige Aktionen in der aktuellen SharePoint-Farm, in der dieses Cmdlet ausgeführt wird.

## Syntax

    Remove-SPWOPIBinding [[-Identity] <SPWopiBindingPipeBind>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPIBinding [-Action <String>] [-Application <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-Server <String>] [-WhatIf [<SwitchParameter>]] [-WOPIZone <String>]

    Remove-SPWOPIBinding [-All <SwitchParameter>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-WhatIf [<SwitchParameter>]]

## Detaillierte Beschreibung

Das **Remove-SPWOPIBinding**-Cmdlet entfernt Bindungen für Anwendungen, Dateinamenerweiterungen und zugehörige Aktionen in der aktuellen SharePoint-Farm, in der dieses Cmdlet ausgeführt wird. Nach dem Ausführen dieses Cmdlets können Sie **New-SPWOPIBinding** verwenden, um die Bindungen gegebenenfalls wiederherzustellen. Wenn Sie alle Bindungen für eine Anwendung entfernen, können Benutzer Office Web Apps oder die SharePoint-Funktion zum Freigeben mit Links für die Anwendung nicht nutzen. Wenn Sie alle Bindungen in der SharePoint-Farm entfernen, in der dieses Cmdlet ausgeführt wird, können Benutzer Office Web Apps oder die SharePoint-Funktion zum Freigeben mit Links für die Anwendungen in der SharePoint-Bibliothek nicht nutzen.

Wenn Sie die Verwendung von Office Web Apps für Standardklicks beenden möchten, jedoch die Suchinformationen der Bindungen sowie die Möglichkeit für Benutzer beibehalten möchten, die SharePoint-Funktion zum Freigeben mit Links zu verwenden, um einen Link an ein Dokument zu senden und dem Empfänger die Verwendung von Office Web Apps für diesen Dokumenttyp ermöglichen möchten, verwenden Sie stattdessen das **New-SPWOPISuppression**-Cmdlet.

SharePoint-Verwaltungsshell

## Parameter


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Parameter</th>
<th>Erforderlich</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Gibt die Bindung an.</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Aktion an, für die Bindungen entfernt werden sollen, z. B. &quot;view&quot;, &quot;edit&quot; und &quot;embedview&quot;. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um eine Liste mit Aktionen zu erhalten. In der Regel verwenden Sie diesen Parameter nicht. Wenn Sie einige Aktionen angeben und einige nicht angeben, funktionieren u. U. einige Funktionen in SharePoint nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Entfernt alle Bindungen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Anwendung an, für die Bindungen entfernt werden sollen. Folgende Anwendungen sind möglich: Word, Excel, PowerPoint und OneNote. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um die Liste mit Anwendungen zu erhalten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Verwaltet Objekte zum Zweck der ordnungsgemäßen Beseitigung. Die Verwendung von Objekten wie beispielsweise <strong>SPWeb</strong> oder <strong>SPSite</strong> kann sehr viel Arbeitsspeicher erfordern, und für die Verwendung dieser Objekte in Windows PowerShell-Skripts muss der Arbeitsspeicher entsprechend verwaltet werden. Mit dem <strong>SPAssignment</strong>-Objekt können Sie einer Variablen Objekte zuweisen und die Objekte beseitigen, wenn sie nicht mehr benötigt werden, um Arbeitsspeicher freizugeben. Wenn die Objekte <strong>SPWeb</strong>, <strong>SPSite</strong> oder<strong>SPSiteAdministration</strong> verwendet werden, werden diese automatisch beseitigt, falls keine Zuweisungsauflistung oder kein <strong>Global</strong>-Parameter verwendet wird.</p>
<div class="alert">

> [!TIP]
> Wenn der <STRONG>Global</STRONG>-Parameter verwendet wird, sind alle Objekte im globalen Speicher enthalten. Es kann vorkommen, dass nicht genügend Arbeitsspeicher vorhanden ist, falls Objekte nicht sofort verwendet werden oder mit dem Befehl <STRONG>Stop-SPAssignment</STRONG> beseitigt werden.


</div></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Dateinamenerweiterungen an, für die Bindungen entfernt werden sollen. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um die Liste mit Dateinamenerweiterungen zu erhalten.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Programmkennungen (ProgID) für eine Anwendung an, für die Bindungen entfernt werden sollen. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um die Liste mit ProgIDs zu erhalten. Verwenden Sie diesen Parameter nur zum Entfernen von Bindungen für OneNote.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Server</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Namen der WOPI-Anwendung (z. B. Office Web Apps Server) an, für die Bindungen entfernt werden sollen.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Zeigt eine Meldung an, die die Auswirkung des Befehls beschreibt, anstatt den Befehl auszuführen. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Zone an, für die Bindungen entfernt werden sollen.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL 1-----------------

    Remove-SPWOPIBinding -Application "Excel"

In diesem Beispiel werden alle Bindungen für Excel in der aktuellen SharePoint-Farm entfernt, in der dieses Cmdlet ausgeführt wird.

\--------------BEISPIEL 2-----------------

    Remove-SPWOPIBinding -All:$true

In diesem Beispiel werden alle Bindungen in der aktuellen SharePoint-Farm entfernt, in der dieses Cmdlet ausgeführt wird.

\--------------BEISPIEL 3-----------------

    Get-SPWOPIBinding -Action "MobileView" | Remove-SPWOPIBinding

In diesem Beispiel werden alle Bindungen für Office Mobile Web Apps in der aktuellen SharePoint-Farm entfernt, in der dieses Cmdlet ausgeführt wird.

## Siehe auch


[New-SPWOPIBinding](new-spwopibinding.md)  
[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

