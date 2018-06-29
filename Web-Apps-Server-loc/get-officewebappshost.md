---
title: Get-OfficeWebAppsHost
TOCTitle: Get-OfficeWebAppsHost
ms:assetid: a9b766a7-a15c-4bbf-9750-31719406d65f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219446(v=office.15)
ms:contentKeyID: 49633175
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Get-OfficeWebAppsHost

 

_**Gilt für:**  Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:**  2013-12-18_

Gibt die Liste mit den Hostdomänen in der Zulassungsliste einer Office Web Apps Server-Farm zurück.

## Syntax

```PowerShell
Get-OfficeWebAppsHost
```

## Detaillierte Beschreibung

Das Cmdlet **Get-OfficeWebAppsHost** gibt die Liste der Hostdomänen zurück, für die Office Web Apps Server Datenvorgangsanforderungen wie den Abruf von Dateien und Metadaten sowie Dateiänderungen zulässt. Diese auch Zulassungsliste genannte Liste ist ein Sicherheitsmerkmal, das verhindert, dass sich unerwünschte Hosts mit der Office Web Apps Server-Farm verbinden und diese ohne Ihr Wissen für Dateivorgänge verwenden.

Der Platzhalter \* gilt für alle Domänen in der Zulassungsliste, sodass Anforderungen an alle Unterdomänen zugelassen werden. Wenn die Domäne beispielsweise contoso.com in der Zulassungsliste enthalten ist, lässt Office Web Apps Server auch Anforderungen an die Domänen corp.contoso.com und dev.contoso.com zu. Anforderungen an andere Domänen wie fabrikam.com werden nicht zugelassen.


> [!WARNING]
> Wenn die Zulassungsliste keine Domänen enthält, lässt Office Web Apps Server Dateianforderungen an Hosts in allen Domänen zu. Lassen Sie diese Liste nicht leer, wenn auf Ihre Office Web Apps Server-Farm aus dem Internet zugegriffen werden kann. Andernfalls kann Ihre Office Web Apps Server-Farm von Dritten zum Anzeigen und Bearbeiten von Inhalten verwendet werden.



## Parameter

## Eingabetypen

## Rückgabetypen

## Beispiel

\------------------BEISPIEL 1---------------------

```PowerShell
Get-OfficeWebAppsHost
```

Dieses Beispiel gibt die Hostdomänen in der Zulassungsliste zurück.

## Siehe auch


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

