---
title: Get-OfficeWebAppsMachine
TOCTitle: Get-OfficeWebAppsMachine
ms:assetid: 02fadf5e-0382-4e73-8d07-e67d088b1a02
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219432(v=office.15)
ms:contentKeyID: 49633150
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsMachine

 

_**Gilt für:**Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:**2013-12-18_

Gibt Einzelheiten zum aktuellen Server in einer Office Web Apps Server-Farm zurück.

## Syntax

    Get-OfficeWebAppsMachine

## Detaillierte Beschreibung

Das Cmdlet **Get-OfficeWebAppsMachine** gibt Einzelheiten zum aktuellen Server in einer Office Web Apps Server-Farm zurück. Dazu zählen die Rolle und der Integritätsstatus des aktuellen Servers sowie der Name des Masterservers der Farm.

## Parameter

## Eingabetypen

## Rückgabetypen

## Beispiel

\------------------BEISPIEL 1---------------------

    Get-OfficeWebAppsMachine

Dieses Beispiel gibt Einzelheiten zum aktuellen Server in einer Office Web Apps Server-Farm zurück.

\------------------BEISPIEL 2---------------------

    (Get-OfficeWebAppsFarm).Machines

Dieses Beispiel gibt Einzelheiten zu allen Servern in einer Office Web Apps Server-Farm zurück.

## Siehe auch


[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  
[Remove-OfficeWebAppsMachine](remove-officewebappsmachine.md)  
[Set-OfficeWebAppsMachine](set-officewebappsmachine.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

