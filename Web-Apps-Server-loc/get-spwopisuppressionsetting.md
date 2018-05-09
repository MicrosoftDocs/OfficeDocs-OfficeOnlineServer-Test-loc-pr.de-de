---
title: Get-SPWOPISuppressionSetting
TOCTitle: Get-SPWOPISuppressionSetting
ms:assetid: a7924964-e16f-4eca-be91-7aff8d45e0c6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219445(v=office.15)
ms:contentKeyID: 49633174
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-SPWOPISuppressionSetting

 

_**Gilt für:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:**2015-03-09_

Gibt die Unterdrückungseinstellungen für die aktuelle SharePoint-Farm zurück, in der dieses Cmdlet ausgeführt wird.

## Syntax

    Get-SPWOPISuppressionSetting [-AssignmentCollection <SPAssignmentCollection>]

## Detaillierte Beschreibung

Das **Get-SPWOPISuppressionSetting**-Cmdlet gibt die Unterdrückungseinstellungen für die aktuelle SharePoint-Farm zurück, in der dieses Cmdlet ausgeführt wird.

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


</div></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL-----------------

    Get-SPWOPISuppressionSetting

In diesem Beispiel werden die Unterdrückungseinstellungen für die aktuelle SharePoint-Farm zurückgegeben, in der dieses Cmdlet ausgeführt wird. Zu den Unterdrückungseinstellungen gehören **DocType** und **WOPIAction**.

## Siehe auch


[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  
[Remove-SPWOPISuppressionSetting](remove-spwopisuppressionsetting.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

