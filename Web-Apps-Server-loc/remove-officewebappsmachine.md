---
title: Remove-OfficeWebAppsMachine
TOCTitle: Remove-OfficeWebAppsMachine
ms:assetid: 5ad806f2-67c6-41ed-a708-69db800f492a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219440(v=office.15)
ms:contentKeyID: 49633163
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsMachine

 

_**Gilt für:** Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Entfernt den aktuellen Server aus der Office Web Apps Server-Farm.

## Syntax

```PowerShell
Remove-OfficeWebAppsMachine 
       [-Confirm [<SwitchParameter>]] 
       [-WhatIf [<SwitchParameter>]]
```

## Detaillierte Beschreibung

Das Cmdlet **Remove-OfficeWebAppsMachine** entfernt den aktuellen Server aus der Office Web Apps Server-Farm. Im Rahmen dieses Prozesses entfernt das Cmdlet Webanwendungen und fährt die zu Office Web Apps Server gehörenden Dienste herunter. Wenn Sie das Cmdlet **Remove-OfficeWebAppsMachine** nicht auf dem Server ausführen können, den Sie entfernen möchten, führen Sie das Cmdlet **Repair-OfficeWebAppsFarm** auf einem der anderen Server in der Office Web Apps-Farm aus.


> [!TIP]
> Wenn der lokale Server in der Office Web Apps Server-Farm als Masterserver vorgesehen ist, können Sie ihn erst aus der Farm entfernen, nachdem Sie mit dem Cmdlet <STRONG>Set-OfficeWebAppsMachine</STRONG> einen anderen Server als Masterserver zugewiesen oder alle anderen Server aus der Farm entfernt haben.



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
Remove-OfficeWebAppsMachine
```

In diesem Beispiel wird der aktuelle Server aus der Office Web Apps Server-Farm entfernt.

## Siehe auch


[Get-OfficeWebAppsMachine](get-officewebappsmachine.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

