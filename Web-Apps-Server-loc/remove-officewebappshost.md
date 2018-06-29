---
title: Remove-OfficeWebAppsHost
TOCTitle: Remove-OfficeWebAppsHost
ms:assetid: d0f7b5c2-da0f-421a-8478-c39b247c3ac5
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219453(v=office.15)
ms:contentKeyID: 49633187
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Remove-OfficeWebAppsHost

 

_**Gilt für:** Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Entfernt eine Hostdomäne aus der Zulassungsliste einer Office Web Apps Server-Farm.

## Syntax

```PowerShell
Remove-OfficeWebAppsHost -Domain <String>
```

## Detaillierte Beschreibung

Das Cmdlet **Remove-OfficeWebAppsHost** dient zum Entfernen der angegebenen Hostdomäne aus der Zulassungsliste. Die Zulassungsliste enthält die Hostdomäne, für die Office Web Apps Server Dateivorgangsanforderungen erlaubt.


> [!WARNING]
> Wenn die Zulassungsliste keine Domänen enthält, lässt Office Web Apps Server Dateianforderungen an Hosts in allen Domänen zu. Lassen Sie diese Liste nicht leer, wenn auf Ihre Office Web Apps Server-Farm aus dem Internet zugegriffen werden kann. Andernfalls kann Ihre Office Web Apps Server-Farm von Dritten zum Anzeigen und Bearbeiten von Inhalten verwendet werden.



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
<td><p><strong>Domain</strong></p></td>
<td><p>Erforderlich</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Hostdomäne an, die aus der Zulassungsliste entfernt werden soll.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\------------------BEISPIEL 1---------------------

```PowerShell
Remove-OfficeWebAppsHost -domain "contoso.com"
```

In diesem Beispiel wird die Domäne "contoso.com" aus der Zulassungsliste entfernt.

## Siehe auch


[New-OfficeWebAppsHost](new-officewebappshost.md)  
[Get-OfficeWebAppsHost](get-officewebappshost.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

