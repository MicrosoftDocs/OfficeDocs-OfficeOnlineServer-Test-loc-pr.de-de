---
title: Set-SPWOPIZone
TOCTitle: Set-SPWOPIZone
ms:assetid: bc751cc4-8ac8-45f7-b6ea-da6fcb5473ac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219451(v=office.15)
ms:contentKeyID: 49633182
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIZone

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Konfiguriert die Zone, die von der aktuellen SharePoint-Farm verwendet wird, um im Browser zur WOPI-Anwendung zu navigieren.

## Syntax

```PowerShell
Set-SPWOPIZone 
    [[-Zone] <String>] 
    [-AssignmentCollection <SPAssignmentCollection>] 
    [-Confirm[<SwitchParameter>]] 
    [-WhatIf[<SwitchParameter>]]
```

## Detaillierte Beschreibung

Das **Set-SPWOPIZone**-Cmdlet konfiguriert die Zone, die von der aktuellen SharePoint-Farm verwendet wird, um mit dem Browser WOPI-Anwendung (z. B. ein Server, auf dem Office Web Apps Server ausgeführt wird) die von der aktuellen SharePoint-Farm verwendet wird, um mit dem Browser WOPI-Anwendung zu navigieren. Die SharePoint Server-Seite im Browser erstellt einen Frame in der WOPI-Anwendung, der eine Seite enthält. Die Zone für die URL der WOPI-Anwendungsseite wird von dieser Einstellung bestimmt.

Wenn Sie die Zone nicht festlegen, ist die Standardeinstellung “internal-HTTPS.” Wenn Sie eine Zone wählen, die von der WOPI-Anwendung nicht unterstützt wird, funktioniert Office Web Apps nicht. Verwenden Sie HTTP nur in einem vollkommen sicheren Netzwerk, das IPSEC (vollständige Verschlüsselung) verwendet, oder in einer Testumgebung, die keine sensiblen Daten enthält.

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
<td><p><strong>Zone</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Zone an. Führen Sie <strong>Get-SPWOPIBinding</strong> aus, um eine Liste mit von der WOPI-Anwendung unterstützten Zonen zu erhalten.</p>
<p>Wenn Sie eine sowohl interne als auch externe SharePoint-Farm verwenden, geben Sie &quot;extern&quot; an. Wenn Sie eine ausschließlich interne SharePoint-Farm verwenden, geben Sie &quot;intern&quot; an. Verwenden Sie HTTP nur in einem vollkommen sicheren Netzwerk, das IPSEC (vollständige Verschlüsselung) verwendet, oder in einer Testumgebung, die keine sensiblen Daten enthält. Folgende Optionen stehen zur Verfügung:</p>
<p>- Internal-HTTP</p>
<p>- Internal-HTTPS</p>
<p>- External-HTTP</p>
<p>- External-HTTPS</p></td>
</tr>
<tr class="even">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Verwaltet Objekte zum Zweck der ordnungsgemäßen Beseitigung. Die Verwendung von Objekten wie beispielsweise <strong>SPWeb</strong> oder <strong>SPSite</strong> kann sehr viel Arbeitsspeicher erfordern, und für die Verwendung dieser Objekte in Windows PowerShell-Skripts muss der Arbeitsspeicher entsprechend verwaltet werden. Mit dem <strong>SPAssignment</strong>-Objekt können Sie einer Variablen Objekte zuweisen und die Objekte beseitigen, wenn sie nicht mehr benötigt werden, um Arbeitsspeicher freizugeben. Wenn die Objekte <strong>SPWeb</strong>, <strong>SPSite</strong> oder<strong>SPSiteAdministration</strong> verwendet werden, werden diese automatisch beseitigt, falls keine Zuweisungsauflistung oder kein <strong>Global</strong>-Parameter verwendet wird.</p>
<div class="alert">

> [!TIP]
> Wenn der <STRONG>Global</STRONG>-Parameter verwendet wird, sind alle Objekte im globalen Speicher enthalten. Es kann vorkommen, dass nicht genügend Arbeitsspeicher vorhanden ist, falls Objekte nicht sofort verwendet werden oder mit dem Befehl <STRONG>Stop-SPAssignment</STRONG> beseitigt werden.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Zeigt eine Meldung an, die die Auswirkung des Befehls beschreibt, anstatt den Befehl auszuführen. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL-----------------

```PowerShell
Set-SPWOPIZone -Zone "external-https"
```

In diesem Beispiel wird die aktuelle SharePoint-Farm so konfiguriert, dass sie über HTTPS externe Verbindungen mit der WOPI-Anwendung (z. B. mit einem Server, auf dem Office Web Apps Server ausgeführt wird) herstellt.

## Siehe auch


[Get-SPWOPIZone](get-spwopizone.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

