---
title: New-OfficeWebAppsHost
TOCTitle: New-OfficeWebAppsHost
ms:assetid: f1d523ab-45c6-4e3c-b274-22c0d229a6a0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219459(v=office.15)
ms:contentKeyID: 49633195
ms.date: 12/18/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsHost

 

_**Gilt für:** Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Fügt der Liste "Zulassen" einer Office Web Apps Server-Farm eine Hostdomäne hinzu.

## Syntax

```PowerShell
New-OfficeWebAppsHost 
   -Domain <String>
```
   

## Detaillierte Beschreibung

Das Cmdlet **New-OfficeWebAppsHost** fügt der Liste der Hostdomänen, für die Office Web Apps Server Datenvorgangsanforderungen wie den Abruf von Dateien und Metadaten sowie Dateiänderungen zulässt, eine Hostdomäne hinzu. Diese auch Zulassungsliste genannte Liste ist ein Sicherheitsmerkmal, das verhindert, dass sich unerwünschte Hosts mit der Office Web Apps Server-Farm verbinden und diese ohne Ihr Wissen für Dateivorgänge verwenden.


> [!TIP]
> Sie können einen beliebigen Domänentyp verwenden z. B. öffentliche, Pool-, Farm- und Active Directory-Domänennamen. Sie müssen nur sicherstellen, dass die Domäne, der Sie den Zugriff gewähren möchten, Ihre Sicherheitsanforderungen erfüllt.



Der Platzhalter \* gilt für alle Domänen, die der Zulassungsliste hinzugefügt werden, sodass Anforderungen an alle Unterdomänen zugelassen werden. Wenn die Domäne contoso.com beispielsweise der Zulassungsliste hinzugefügt wird, lässt Office Web Apps Server auch Anforderungen an die Domänen corp.contoso.com und dev.contoso.com zu. Anforderungen an andere Domänen wie fabrikam.com werden nicht zugelassen.


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
<td><p>Gibt die Domäne an, die der Zulassungsliste hinzugefügt werden soll. Ein Sternchen oder als erstes Zeichen ein Punkt sind nicht zulässig.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\------------------BEISPIEL 1---------------------

```PowerShell
New-OfficeWebAppsHost -domain "contoso.com"
```

In diesem Beispiel wird die Domäne contoso.com der Zulassungsliste hinzugefügt.


> [!TIP]
> Es ist nicht möglich, mehere Hostdomänen gleichzeitig zur Zulassungsliste hinzuzufügen. Sie müssen das New-OfficeWebAppsHost-Cmdlet für jede Hostdomäne ausführen, die Sie der Zulassungsliste hinzufügen möchten.



## Siehe auch


[Get-OfficeWebAppsHost](get-officewebappshost.md)  
[Remove-OfficeWebAppsHost](remove-officewebappshost.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

