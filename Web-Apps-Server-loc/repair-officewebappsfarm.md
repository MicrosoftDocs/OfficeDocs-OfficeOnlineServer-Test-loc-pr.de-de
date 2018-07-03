---
title: Repair-OfficeWebAppsFarm
TOCTitle: Repair-OfficeWebAppsFarm
ms:assetid: 083d8e25-ce82-4884-9bbc-06375185011c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219433(v=office.15)
ms:contentKeyID: 49633151
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Repair-OfficeWebAppsFarm

 

_**Gilt für:** Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Entfernt alle als instabil gekennzeichneten Server aus einer Office Web Apps Server-Farm.

## Syntax

```PowerShell
Repair-OfficeWebAppsFarm 
      [-Confirm[<SwitchParameter>]] 
      [-Force <SwitchParameter>] 
      [-WhatIf[<SwitchParameter>]]
```

## Detaillierte Beschreibung

Das Cmdlet **Repair-OfficeWebAppsFarm** entfernt alle als instabil gekennzeichneten Server aus einer Office Web Apps Server-Farm. Dieses Cmdlet aktualisiert die Farmtopologie, bereinigt jedoch keine Dienste und Webanwendungen auf den Servern, die entfernt werden. Aus diesem Grund sollte unbedingt das Cmdlet **Remove-OfficeWebAppsMachine** auf den instabilen Servern ausgeführt werden, um diese ordnungsgemäß aus der Farm zu entfernen. Verwenden Sie das Cmdlet **Repair-OfficeWebAppsFarm** nur, wenn die instabilen Server ausgefallen sind und deshalb das Cmdlet **Remove-OfficeWebAppsMachine** nicht direkt auf ihnen ausgeführt werden kann.

Wenn es mehrere instabile Server gibt, wird vor dem Entfernen der einzelnen Server eine Eingabeaufforderung angezeigt. Sind keine instabilen Server vorhanden, führt dieses Cmdlet nichts aus.

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
<th>Description</th>
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
<td><p><strong>Force</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Nimmt an, dass die Antwort auf alle Eingabeaufforderungen &quot;Ja&quot; ist.</p></td>
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

```PowerShell
(Get-OfficeWebAppsFarm).Machines
```

In diesem Beispiel wird der Integritätsstatus aller Server in der Office Web Apps Server-Farm angezeigt.

\------------------BEISPIEL 2---------------------

```PowerShell
Repair-OfficeWebAppsFarm
```

In diesem Beispiel werden alle instabilen Server aus der Office Web Apps Server-Farm entfernt.

## Siehe auch


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

