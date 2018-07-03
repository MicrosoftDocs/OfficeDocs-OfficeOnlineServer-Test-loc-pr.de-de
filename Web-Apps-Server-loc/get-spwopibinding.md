---
title: Get-SPWOPIBinding
TOCTitle: Get-SPWOPIBinding
ms:assetid: b757301b-f6c5-43a5-a8ca-2ef33ede0ae8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219450(v=office.15)
ms:contentKeyID: 49633181
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPIBinding

 

_**Gilt für:**  Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:**  2015-03-09_

Gibt eine Liste mit Bindungen zurück, die mithilfe von **New-SPWOPIBinding** in der aktuellen SharePoint-Farm erstellt wurden, in der dieses Cmdlet ausgeführt wird.

## Syntax

```PowerShell
Get-SPWOPIBinding 
    [-Action <String>] 
    [-Application <String>] 
    [-AssignmentCollection <SPAssignmentCollection>] 
    [-Extension <String>] 
    [-ProgId <String>] 
    [-Server <String>] 
    [-WOPIZone <String>]
```

## Detaillierte Beschreibung

**Get-SPWOPIBinding** gibt eine Liste mit Bindungen zurück, die mithilfe von **New-SPWOPIBinding** in der aktuellen SharePoint-Farm erstellt wurden, in der dieses Cmdlet ausgeführt wird. Die Ergebnisse umfassen Aktionen, Anwendungen, Dateitypen und Zonen, die für eine WOPI-Anwendung (z. B. für einen Server, auf dem Office Web Apps Server ausgeführt wird) konfiguriert sind.

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
<td><p><strong>Action</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Aktion an, für die Bindungen zurückgegeben werden sollen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Anwendung an, für die Bindungen zurückgegeben werden sollen.</p></td>
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
<td><p><strong>Extension</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Dateinamenerweiterung an, für die Bindungen zurückgegeben werden soll.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgId</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Programmkennung (ProgID) für eine Anwendung an, für die Bindungen zurückgegeben werden sollen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Server</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Namen der WOPI-Anwendung (z. B. des Servers, auf dem Office Web Apps Server ausgeführt wird) an, für die Bindungen zurückgegeben werden sollen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WOPIZone</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Zone an, für die Bindungen zurückgegeben werden sollen.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL 1-----------------

```PowerShell
Get-SPWOPIBinding -Server "Server.corp.Contoso.com"
```

In diesem Beispiel wird eine Liste mit Bindungen zurückgegeben, die in der aktuellen SharePoint-Farm erstellt wurden, in der dieses Cmdlet für die WOPI-Anwendung "Server.corp.Contoso.com" ausgeführt wird. Bei der WOPI-Anwendung kann es sich um den Server handeln, auf dem Office Web Apps Server ausgeführt wird.

\--------------BEISPIEL 2-----------------

```PowerShell
Get-SPWOPIZone | Get-SPWOPIBinding
```

In diesem Beispiel wird eine Liste mit Bindungen zurückgegeben, die in der aktuellen SharePoint-Farm erstellt wurden, in der dieses Cmdlet für die für die WOPI-Anwendung konfigurierte Zone ausgeführt wird.

## Siehe auch


[New-SPWOPIBinding](new-spwopibinding.md)  
[Set-SPWOPIBinding](set-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

