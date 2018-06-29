---
title: Get-SPWOPIZone
TOCTitle: Get-SPWOPIZone
ms:assetid: 5a37e106-272c-43e9-ae09-20888b296af0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219439(v=office.15)
ms:contentKeyID: 49633162
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPIZone

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Gibt die Zone zurück, die in der aktuellen SharePoint-Farm konfiguriert ist, die die WOPI-Anwendung verwenden soll.

## Syntax

```PowerShell
Get-SPWOPIZone 
    [-AssignmentCollection <SPAssignmentCollection>]
```

## Detaillierte Beschreibung

**Get-SPWOPIZone** gibt die Zone zurück, die in der aktuellen SharePoint-Farm konfiguriert ist, die die WOPI-Anwendung (z. B. ein Server, auf dem Office Web Apps Server ausgeführt wird) verwenden soll.

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
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Verwaltet Objekte zum Zweck der ordnungsgemäßen Beseitigung. Die Verwendung von Objekten wie beispielsweise <strong>SPWeb</strong> oder <strong>SPSite</strong> kann sehr viel Arbeitsspeicher erfordern, und für die Verwendung dieser Objekte in Windows PowerShell-Skripts muss der Arbeitsspeicher entsprechend verwaltet werden. Mit dem <strong>SPAssignment</strong>-Objekt können Sie einer Variablen Objekte zuweisen und die Objekte beseitigen, wenn sie nicht mehr benötigt werden, um Arbeitsspeicher freizugeben. Wenn die Objekte <strong>SPWeb</strong>, <strong>SPSite</strong> oder<strong>SPSiteAdministration</strong> verwendet werden, werden diese automatisch beseitigt, falls keine Zuweisungsauflistung oder kein <strong>Global</strong>-Parameter verwendet wird.</p>
<div class="alert">

> [!TIP]
> Wenn der <STRONG>Global</STRONG>-Parameter verwendet wird, sind alle Objekte im globalen Speicher enthalten. Es kann vorkommen, dass nicht genügend Arbeitsspeicher vorhanden ist, falls Objekte nicht sofort verwendet werden oder mit dem Befehl <STRONG>Stop-SPAssignment</STRONG> beseitigt werden.


</div>
<p></p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL-----------------

```PowerShell
Get-SPWOPIZone
```

In diesem Beispiel wird die Zone zurückgegeben, die in der aktuellen SharePoint-Farm konfiguriert ist, die die WOPI-Anwendung (z. B. ein Server, auf dem Office Web Apps Server) ausgeführt wird) verwenden soll. Mögliche Rückgabewerte: "internal-http", "internal-https", "external-http" oder "external-https".

## Siehe auch


[Set-SPWOPIZone](set-spwopizone.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

