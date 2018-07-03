---
title: Update-SPWOPIProofKey
TOCTitle: Update-SPWOPIProofKey
ms:assetid: fe7f3a87-082e-4a43-a5f3-7be41d8e91a3
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219460(v=office.15)
ms:contentKeyID: 49633196
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Update-SPWOPIProofKey

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Aktualisiert den öffentlichen Schlüssel, der zum Herstellen einer Verbindung mit der WOPI-Anwendung in der aktuellen SharePoint-Farm verwendet wird, in der dieses Cmdlet ausgeführt wird.

## Syntax

```PowerShell
Update-SPWOPIProofKey 
       [-AssignmentCollection <SPAssignmentCollection>] 
       [-ServerName <String>]
```

## Detaillierte Beschreibung

Das **Update-SPWOPIProofKey**-Cmdlet aktualisiert den öffentlichen Schlüssel, der zum Herstellen einer Verbindung mit der WOPI-Anwendung (z. B. ein Server, auf dem Office Web Apps Server ausgeführt wird) in der aktuellen SharePoint-Farm verwendet wird, in der dieses Cmdlet ausgeführt wird. Verwenden Sie dieses Cmdlet wenn die Synchronisierung der Schlüssel zwischen der SharePoint-Farm und der WOPI-Anwendung verloren geht. Sind die Schlüssel nicht synchronisiert, werden Dokumente u. U. im Browser nicht geöffnet, und die Protokolle des vereinheitlichten Protokollierungsdiensts (Unified Logging Service, ULS) enthalten Benachrichtigungen wie z. B. “Ungültige Nachweissignatur für Datei…” oder “Ungültige Nachweissignatur für Ordner...”.

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
<tr class="even">
<td><p><strong>ServerName</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die WOPI-Anwendung an, von der der Schlüssel abgerufen werden soll. Dabei kann es sich um einen Server handeln, auf dem Office Web Apps Server ausgeführt wird. Wenn dieser Parameter fehlt, werden die öffentlichen Schlüssel für alle WOPI-Anwendungen aktualisiert, die mit der aktuellen SharePoint-Farm verbunden sind.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL-----------------

```PowerShell
Update-SPWOPIProofKey -ServerName "Server.corp.Contoso.com"
```

In diesem Beispiel wird der aktuelle öffentliche Schlüssel von der WOPI-Anwendung (z. B. ein Server, auf dem Office Web Apps Server ausgeführt wird) abgerufen, und der in der SharePoint-Farm gespeicherte Schlüssel wird aktualisiert.

## Siehe auch


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

