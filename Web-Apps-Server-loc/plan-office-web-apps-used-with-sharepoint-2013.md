---
title: Planen von Office Web Apps (verwendet mit SharePoint 2013)
TOCTitle: Planen von Office Web Apps
ms:assetid: 3bd0a617-5f12-4a7e-bb75-b15c86c7e504
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Ff431682(v=office.15)
ms:contentKeyID: 49633158
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Planen von Office Web Apps (verwendet mit SharePoint 2013)

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2016-12-16_

**Zusammenfassung:** Enthält Richtlinien für die Planung der lokalen Verwendung von Office Web Apps mit SharePoint 2013.

**Zielgruppe:** IT-Spezialisten

Machen Sie sich bei der Planung der lokalen Verwendung von Office Web Apps mit SharePoint 2013 zunächst mit der Browserunterstützung, den SharePoint-Authentifizierungsanforderungen und den Lizenzierungsüberlegungen für das Anzeigen und Bearbeiten von Office-Dateien mit Office Web Apps vertraut. Anschließend können Sie entscheiden, ob von SharePoint 2013 der Webbrowser oder eine Clientanwendung verwendet werden soll, wenn ein Benutzer Office-Dateien aus einer SharePoint 2013-Dokumentbibliothek öffnet.


> [!IMPORTANT]
> Dieser Artikel ist Teil der <A href="content-roadmap-for-office-web-apps-server.md">Inhaltsübersicht für Office Web Apps Server</A>. Verwenden Sie diese Übersicht als Ausgangspunkt für Artikel, Downloads und Videos, mit deren Hilfe Sie Office Web Apps Server bereitstellen und verwalten können.<BR><STRONG>Benötigen Sie Hilfe mit Office Web Apps auf Ihrem Desktop oder mobilen Gerät?</STRONG> Diesbezügliche Informationen finden Sie, indem Sie auf <A href="http://office.microsoft.com/de-de/">Office.com</A> nach "Office Web Apps" suchen.



Inhalt dieses Artikels:

  - Informationen zur Planung von Office Web Apps

  - Browserunterstützung für Office Web Apps

  - SharePoint-Authentifizierungsanforderungen für Office Web Apps

  - Lizenzierung von Office Web Apps für die Bearbeitung von Office-Dateien

  - Überlegungen für Kunden, die Office Web Apps mit SharePoint 2010 bereitgestellt haben

  - Standardöffnungsverhalten beim Öffnen von Dokumenten aus SharePoint 2013-Dokumentbibliotheken

## Informationen zur Planung von Office Web Apps

Die Richtlinien in diesem Artikel sind eine Teilmenge der Gesamtplanung, die Sie bei der lokalen Bereitstellung von Office Web Apps Server in Ihrer Organisation durchführen. Beispielsweise sind Hardware-, Software- und Virtualisierungsanforderungen sowie Farmdimensionierung, Topologie und Sicherheit ein Teil der Office Web Apps Server-Planung. Nachdem Sie diese Entscheidungen getroffen haben, können Sie planen, wie die Office Web Apps-Funktionalität konfiguriert werden soll, die für SharePoint 2013 spezifisch ist. Wenn Sie noch nie etwas von Office Web Apps Server gehört haben oder sich noch nicht mit den dazugehörigen Anforderungen und Planungsrichtlinien beschäftigt haben, lesen Sie die Artikel [Übersicht über Office Web Apps Server](office-web-apps-server-overview.md) und [Planen von Office Web Apps Server](plan-office-web-apps-server.md).

## Browserunterstützung für Office Web Apps

Für Office Web Apps gilt dieselbe Browserunterstützung wie für SharePoint 2013. Weitere Informationen finden Sie im Artikel [Planen der Browserunterstützung in SharePoint 2013](https://technet.microsoft.com/de-de/library/cc263526\(v=office.15\)).

## SharePoint-Authentifizierungsanforderungen für Office Web Apps

Office Web Apps kann nur von SharePoint 2013-Webanwendungen verwendet werden, die die anspruchsbasierte Authentifizierung verwenden. Das Rendern und Bearbeiten mit Office Web Apps funktioniert nicht in SharePoint 2013-Webanwendungen, die den klassischen Authentifizierungsmodus verwenden. Wenn Sie SharePoint 2010-Webanwendungen, die den klassischen Authentifizierungsmodus verwenden, zu SharePoint 2013 migrieren, müssen Sie diese Webanwendungen zur anspruchsbasierten Authentifizierung migrieren, damit sie Office Web Apps verwenden können. Weitere Informationen finden Sie unter [Migrieren von der klassischen Authentifizierung zur anspruchsbasierten Authentifizierung in SharePoint 2013](https://technet.microsoft.com/de-de/library/gg251985\(v=office.15\)).

## Lizenzierung von Office Web Apps für die Bearbeitung von Office-Dateien

Unternehmenskunden, die über ein Volumenlizenzierungsprogramm für Office 2013 lizenziert sind, können lokal die Office Web Apps-Bearbeitung für SharePoint 2013 ermöglichen. Dadurch können Benutzer Office-Bearbeitungsfunktionen zu Hause oder an anderen Orten nutzen, an denen unter Umständen keine Office-Clients installiert sind.

Ausführliche Details zu Ihrer Lizenz finden Sie in den Microsoft-Software-Lizenzbedingungen, die bei der Installation von Office Web Apps Server angezeigt werden. Weitere Informationen zur Funktionsweise der Lizenzierung in SharePoint 2013 finden Sie unter [Konfigurieren der Lizenzierung in SharePoint Server 2013](https://technet.microsoft.com/de-de/library/jj219627\(v=office.15\)).

## Überlegungen für Kunden, die unter Verwendung der Datenbankanfügungsmethode ein Upgrade von SharePoint 2010 ausführen

Falls Sie Office Web Apps zusammen mit SharePoint 2010 installiert haben, ist Office Web Apps nach einem Upgrade auf SharePoint 2013 nicht mehr verfügbar. Nach dem Upgrade der Inhaltsdatenbanken muss Office Web Apps Server bereitgestellt und anschließend eine Verbindung mit SharePoint 2013 hergestellt werden. Sie müssen nicht warten, bis die Websitesammlungen aktualisiert wurden, da von Office Web Apps Server sowohl der 2010-Websitesammlungsmodus als auch der 2013-Websitesammlungsmodus von SharePoint 2013 unterstützt wird. Weitere Informationen zur Datenbankanfügungsmethode finden Sie unter [Übersicht über die Verfahren beim Upgrade auf SharePoint 2013](https://technet.microsoft.com/de-de/library/cc262483\(v=office.15\)).

## Standardöffnungsverhalten beim Öffnen von Dokumenten aus SharePoint 2013-Dokumentbibliotheken

Sie können konfigurieren, ob Word-, PowerPoint-, Excel- und OneNote-Dateien in einer Clientanwendung (sofern installiert) oder im Browser geöffnet werden. Nachdem SharePoint 2013 für die Verwendung von Office Web Apps Server konfiguriert wurde, werden Office-Dateien im Browser geöffnet. Es gibt zwei Möglichkeiten, das Standardverhalten so zu ändern, dass Clientanwendungen Dateien direkt öffnen können:

  - **Für die SharePoint 2013-Farm** Das Standardöffnungsverhalten kann mit den Cmdlets [New-SPWOPIBinding](new-spwopibinding.md) und [Set-SPWOPIBinding](set-spwopibinding.md)Windows PowerShell für die SharePoint 2013-Farm dateitypspezifisch angepasst werden.

  - **Lokale Auflistungen oder Dokumentbibliotheken** Administratoren und Benutzer von Websitesammlungen können angeben, ob Office-Dateien in Clientanwendungen geöffnet werden, wenn Office installiert ist. Benutzer können diese Einstellung in den Eigenschaften der Dokumentbibliothek ändern. Administratoren von Websitesammlungen können diese Einstellung in der Websitesammlungsverwaltung oder mit dem Install-SPFeature-Cmdlet ändern, um das OpenInClient-Feature zu installieren. Weitere Informationen finden Sie unter [Install-SPFeature](https://technet.microsoft.com/de-de/library/ff607825\(v=office.15\)).

## Siehe auch


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Funktionsweise von lokalen Office Web Apps mit SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  


[In a test environment that uses HTTP](configure-office-web-apps-for-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

