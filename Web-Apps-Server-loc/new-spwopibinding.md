---
title: New-SPWOPIBinding
TOCTitle: New-SPWOPIBinding
ms:assetid: 696f01b4-a144-431b-9bae-1c3ede78609d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219441(v=office.15)
ms:contentKeyID: 49633164
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-SPWOPIBinding

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Erstellt eine neue Bindung, um Dateinamenerweiterungen oder Anwendungen Aktionen in der aktuellen SharePoint-Farm zuzuordnen, in der dieses Cmdlet ausgeführt wird.

## Syntax

```PowerShell
New-SPWOPIBinding -ServerName <String> 
    [-Action <String>] 
    [-AllowHTTP <SwitchParameter>] 
    [-Application <String>] 
    [-AssignmentCollection <SPAssignmentCollection>] 
    [-Confirm[<SwitchParameter>]] 
    [-Extension <String>] 
    [-FileName <String>] 
    [-ProgId <String>] 
    [-WhatIf[<SwitchParameter>]]
```

## Detaillierte Beschreibung

Das **New-SPWOPIBinding**-Cmdlet ordnet Dateinamenerweiterungen oder Anwendungen den Aktionen in der aktuellen SharePoint-Farm zu, in der dieses Cmdlet ausgeführt wird. Jede Bindung ermöglicht Ihnen die Verwendung der WOPI-Anwendung zum Anzeigen oder Bearbeiten von Dateien in Ihrer SharePoint-Bibliothek. Sieht ein Benutzer beispielsweise ein Word-Dokument in einer SharePoint-Dokumentliste, zeigt die SharePoint-List basierend auf den Aktionen, die in dieser SharePoint-Farm an Word gebunden sind, die verfügbaren Optionen zum Anzeigen oder Bearbeiten des Dokuments an.

Zum Verwenden einer WOPI-Anwendung, z. B. ein Server, auf dem Office Web Apps Server ausgeführt wird, für Office Web Apps müssen Sie dieses Cmdlet in der SharePoint-Farm ausführen, bevor Sie Office Web Apps verwenden können.

Wenn Sie **New-SPWOPIBinding** für eine Anwendung oder Dateinamenerweiterung ausführen, für die die Bindung (oder Zuordnung) bereits vorhanden ist, schlägt das Cmdlet fehl.

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
<td><p><strong>ServerName</strong></p></td>
<td><p>Erforderlich</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Namen bzw. den vollqualifizierten Domänennamen (FQDN) der WOPI-Anwendung an (z. B. ein Server, auf dem Office Web Apps Server ausgeführt wird).</p></td>
</tr>
<tr class="even">
<td><p><strong>Action</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die zu bindende Aktion an, z. B. “view”, “edit” und “embedview.” Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um eine Liste mit von der WOPI-Anwendung unterstützten Aktionen zu erhalten. In der Regel verwenden Sie diesen Parameter nicht. Wenn Sie einige Aktionen angeben und einige nicht angeben, funktionieren u. U. einige SharePoint-Funktionen nicht.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHTTP</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Gibt an, dass das Cmdlet zum HTTP verwenden kann, um zu ermitteln, das von der WOPI-Anwendung unterstützt wird. Ist hierfür &quot;True&quot; festgelegt, werden die Suchinformationen von der WOPI-Anwendung über eine nicht sichere Verbindung gesendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die zu bindenden Anwendungen an. Folgende Anwendungen sind möglich: “Word&quot;, “Excel&quot;, “PowerPoint&quot; und “OneNote&quot;. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um die vollständige Liste mit von der WOPI-Anwendung unterstützten Anwendungen zu erhalten.</p></td>
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
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Extension</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die zu bindenden Dateinamenerweiterungen an. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um die Liste mit von der WOPI-Anwendung unterstützten Dateinamenerweiterungen zu erhalten.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileName</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Pfad der XML-Datei an, die die Suchinformationen für die WOPI-Anwendung enthält. Sie können Suchinformationen aus einer XML-Datei laden, anstatt sie direkt von der WOPI-Anwendung anzufordern.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Programmkennungen (ProgID) für eine zu bindende Anwendung an. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um die Liste mit von der WOPI-Anwendung unterstützten ProgIDs zu erhalten. Verwenden Sie diesen Parameter nur, um eine Aktion einem OneNote-Ordner zuzuordnen.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Zeigt eine Meldung an, die die Auswirkung des Befehls beschreibt, anstatt den Befehl auszuführen. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL 1-----------------

```PowerShell
New-SPWOPIBinding -ServerName "Server.corp.Contoso.com"
```

In diesem Beispiel werden Bindungen für alle Anwendungen und Dateinamenerweiterungen erstellt, die die WOPI-Anwendung in der aktuellen SharePoint-Farm unterstützt, in der dieses Cmdlet ausgeführt wird.

\--------------BEISPIEL 2-----------------

```PowerShell
New-SPWOPIBinding -ServerName "Server.corp.Contoso.com" -Application "Excel"
```

In diesem Beispiel wird Excel allen Aktionen zugeordnet, die die WOPI-Anwendung in der aktuellen SharePoint-Farm für Excel unterstützt, in der dieses Cmdlet ausgeführt wird.

## Siehe auch


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

