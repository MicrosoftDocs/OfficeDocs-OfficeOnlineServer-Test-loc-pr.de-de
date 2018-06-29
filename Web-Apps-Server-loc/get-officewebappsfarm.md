---
title: Get-OfficeWebAppsFarm
TOCTitle: Get-OfficeWebAppsFarm
ms:assetid: 1f0704e1-a41d-40e6-a31b-08b1926ce811
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219434(v=office.15)
ms:contentKeyID: 49633152
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsFarm

 

_**Gilt für:**  Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:**  2013-12-18_

Gibt Details zum "OfficeWebAppsFarm"-Objekt zurück, zu dem der aktuelle Server gehört.

## Syntax

```PowerShell
Get-OfficeWebAppsFarm
```

## Detaillierte Beschreibung

Das Cmdlet **Get-OfficeWebAppsFarm** gibt Details zum OfficeWebAppsFarm -Objekt zurück, zu dem der aktuelle Server gehört. Dieses Objekt stellt eine Gruppe von Servern dar, die als Einheit zusammenarbeiten, um die Bearbeitung und Anzeige von Office-Dokumenten im Browser zu ermöglichen. Für das Cmdlet **Get-OfficeWebAppsFarm** gibt es keine Parameter.

## Parameter

## Eingabetypen

## Rückgabetypen

## Beispiel

\------------------BEISPIEL 1---------------------

```PowerShell
Get-OfficeWebAppsFarm
```

Dieses Beispiel gibt Einzelheiten zum "OfficeWebAppsFarm"-Objekt zurück.

\------------------BEISPIEL 2---------------------

```PowerShell
(Get-OfficeWebAppsFarm).Machines
```

Dieses Beispiel gibt Details zu den Servern zurück, die zur Office Web Apps Server-Farm gehören. Dazu gehören der Integritätsstatus und die Rollen jedes Servers.

## Siehe auch


[New-OfficeWebAppsFarm](new-officewebappsfarm.md)  
[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

