---
title: Remove-SPWOPISuppressionSetting
TOCTitle: Remove-SPWOPISuppressionSetting
ms:assetid: cbaef5a8-e682-4166-be44-15ab1c79acca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219452(v=office.15)
ms:contentKeyID: 49633185
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-SPWOPISuppressionSetting

 

_**Gilt für:**Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:**2015-03-09_

Entfernt die Unterdrückungseinstellungen für eine Dateinamenerweiterung oder Programm-ID und Aktion in der aktuellen SharePoint-Farm, in der dieses Cmdlet ausgeführt wird.

## Syntax

    Remove-SPWOPISuppressionSetting [-Action <String>] [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Extension <String>] [-ProgId <String>] [-WhatIf [<SwitchParameter>]]

    Remove-SPWOPISuppressionSetting [-AssignmentCollection <SPAssignmentCollection>] [-Confirm [<SwitchParameter>]] [-Identity <String>] [-WhatIf [<SwitchParameter>]]

## Detaillierte Beschreibung

Das **Remove-SPWOPISuppressionSetting**-Cmdlet entfernt die Unterdrückungseinstellungen für eine Dateinamenerweiterung oder Programm-ID (ProgID) und Aktion in der aktuellen SharePoint-Farm, in der dieses Cmdlet ausgeführt wird.

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
<td><p>Gibt die Aktion für eine bestimmte Dateinamenerweiterung oder Programmkennung (ProgId) an, z. B. “view”, “edit” und “embedview”.</p></td>
</tr>
<tr class="even">
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
<tr class="odd">
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Extension</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Dateinamenerweiterung an. Führen Sie &quot;Get-SPWOPIBinding&quot; aus, um die Liste mit von der WOPI-Anwendung unterstützten Dateinamenerweiterungen zu erhalten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Identity</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt eine Zeichenfolge an, die ein &quot;SPWOPISuppressionSetting&quot; darstellt. Führen Sie &quot;Get-SPWOPISuppressionSetting&quot; aus, um Beispiele für solche Zeichenfolgen anzuzeigen.</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgId</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die zu unterdrückende Programmkennung (ProgID) für eine Anwendung an. Führen Sie &quot;Get-SPWOPIBinding&quot; aus, um die Liste mit von der WOPI-Anwendung unterstützten ProgIDs zu erhalten.</p></td>
</tr>
<tr class="odd">
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

    Remove-SPWOPISuppressionSetting -Extension "XLSX" -Action "view"

In diesem Beispiel werden die Unterdrückungseinstellungen zum Anzeigen von Excel-Arbeitsmappen mit der Dateinamenerweiterung XLSX entfernt.

\--------------BEISPIEL 2-----------------

    Get-SPWOPISuppressionSetting | Remove-SPWOPISuppressionSetting

In diesem Beispiel werden alle Unterdrückungseinstellungen in der aktuellen SharePoint-Farm entfernt, in der dieses Cmdlet ausgeführt wird.

## Siehe auch


[New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md)  
[Get-SPWOPISuppressionSetting](get-spwopisuppressionsetting.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

