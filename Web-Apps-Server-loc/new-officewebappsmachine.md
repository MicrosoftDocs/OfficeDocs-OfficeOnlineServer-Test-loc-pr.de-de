---
title: New-OfficeWebAppsMachine
TOCTitle: New-OfficeWebAppsMachine
ms:assetid: b0385c4e-61fc-4607-a48c-64d8f4e80651
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219449(v=office.15)
ms:contentKeyID: 49633180
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsMachine

 

_**Gilt für:**Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:**2015-03-09_

Fügt den aktuellen Server einer vorhandenen Office Web Apps Server-Farm hinzu.

## Syntax

    New-OfficeWebAppsMachine [-MachineToJoin] <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Detaillierte Beschreibung

Das Cmdlet **New-OfficeWebAppsMachine** dient zum Hinzufügen des aktuellen Servers zu einer vorhandenen Office Web Apps Server-Farm und optional zum Festlegen einer oder mehrerer Rollen für den neuen Server.

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
<td><p><strong>MachineToJoin</strong></p></td>
<td><p>Erforderlich</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Namen eines Servers an, der bereits zur Office Web Apps Server-Farm gehört.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Nimmt an, dass die Antwort auf alle Eingabeaufforderungen &quot;Ja&quot; ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>Roles</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Gibt eine oder mehrere (durch Kommas getrennte) Serverrollen an, die dem neuen Server zugewiesen werden sollen. Werden keine Rollen angegeben, werden dem Server alle Rollen zugewiesen.</p>
<p>Es gibt folgende Rollentypen:</p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">

> [!IMPORTANT]
> Ausdrücklich empfohlen wird, auf allen Servern in einer Office Web Apps Server-Farm alle Rollen auszuführen. Das Zuweisen von Rollen ist erst sinnvoll, wenn die Office Web Apps Server-Farm mindestens ca. 50&nbsp;Server enthält.


</div></td>
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

\------------------BEISPIEL 1---------------------

    New-OfficeWebAppsMachine -MachineToJoin server1.contoso.com

In diesem Beispiel wird der aktuelle Server der Office Web Apps Server-Farm hinzugefügt, die auf dem Server "server1.contoso.com" ausgeführt wird.

## Siehe auch


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

