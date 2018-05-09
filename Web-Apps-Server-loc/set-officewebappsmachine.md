---
title: Set-OfficeWebAppsMachine
TOCTitle: Set-OfficeWebAppsMachine
ms:assetid: aeba2638-be88-4030-80fe-7e4bcd30309b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219448(v=office.15)
ms:contentKeyID: 49633179
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-OfficeWebAppsMachine

 

_**Gilt für:**Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:**2015-03-09_

Ändert die Einstellungen des aktuellen Servers in einer Office Web Apps Server-Farm.

## Syntax

    Set-OfficeWebAppsMachine [-Confirm [<SwitchParameter>]] [-Master <String>] [-Roles <String[]>] [-WhatIf [<SwitchParameter>]]

## Detaillierte Beschreibung

Das Cmdlet **Set-OfficeWebAppsMachine** ändert die Einstellungen des aktuellen Servers in einer Office Web Apps Server-Farm. Zu den Einstellungen gehören die Rollen des aktuellen Servers und der für die Farm vorgesehene Masterserver.

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
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Master</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p></p>
<p>Gibt den Server an, auf dem die Konfigurationsdateien des Masterservers der Farm gespeichert sind.</p>
<p>Wenn Sie den lokalen Server als Masterserver festlegen, müssen Sie <strong>Set-OfficeWebAppsMachine -Master</strong> auf allen restlichen Servern in der Office Web Apps Server-Farm so ausführen, dass diese auf den neuen Masterserver verwiesen werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Roles</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String[]</p></td>
<td><p>Gibt die Liste der (durch Kommas getrennten) Serverrollen an, die dem lokalen Server zugewiesen werden sollen.</p>
<p>Es gibt folgende Rollentypen:</p>
<p><strong>All</strong></p>
<p><strong>FrontEnd</strong></p>
<p><strong>WordBackEnd</strong></p>
<p><strong>ExcelBackEnd</strong></p>
<p><strong>PowerPointBackEnd</strong></p>
<div class="alert">

> [!IMPORTANT]
> Ausdrücklich empfohlen wird, auf allen Servern in einer Office Web Apps Server-Farm alle Rollen auszuführen. Das Zuweisen von Rollen ist erst sinnvoll, wenn die Office Web Apps Server-Farm mindestens ca. 50&nbsp;Server enthält.


</div></td>
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

\------------------BEISPIEL 1---------------------

    (Get-OfficeWebAppsFarm).Machines

In diesem Beispiel werden die Rollen der einzelnen Server in der Office Web Apps Server-Farm angezeigt.

\------------------BEISPIEL 2---------------------

    Set-OfficeWebAppsMachine -Roles FrontEnd

In diesem Beispiel wird der aktuelle Server als Front-End-Server konfiguriert.

\------------------BEISPIEL 3---------------------

    Set-OfficeWebAppsMachine -Roles All

In diesem Beispiel wird der aktuelle Server als Host aller Rollen konfiguriert.

## Siehe auch


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

