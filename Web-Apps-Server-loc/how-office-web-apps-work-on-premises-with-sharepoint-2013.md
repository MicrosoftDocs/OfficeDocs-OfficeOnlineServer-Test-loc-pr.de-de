---
title: Funktionsweise von lokalen Office Web Apps mit SharePoint 2013
TOCTitle: Lokale Office Web Apps mit SharePoint 2013
ms:assetid: 8480064e-14a4-4b46-ad6b-0c836b192af2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Ff431685(v=office.15)
ms:contentKeyID: 49633168
ms.date: 01/29/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Funktionsweise von lokalen Office Web Apps mit SharePoint 2013

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2016-12-16_

**Zusammenfassung:** Artikel mit Informationen zu Office Web Apps, Office Web Apps Server und dazu, wie diese Komponenten lokal mit SharePoint 2013 funktionieren.

**Zielgruppe:** IT-Spezialisten

Bei Verwendung mit SharePoint Server 2013 bietet Office Web Apps Server aktualisierte Versionen von Word Web App, Excel Web App, PowerPoint Web App und OneNote Web App. Benutzer können Office-Dokumente in SharePoint-Bibliotheken mithilfe eines unterstützten Webbrowsers auf Computern und verschiedenen Mobilgeräten wie Windows Phones, iPhones, iPads, Windows 8-Tablets und Android-Geräten anzeigen.


**Abbildung: Anzeige- und Bearbeitungsfunktionen von Office Web Apps auf verschiedenen Arten von Geräten**

![Eine Darstellung, die die Anzeige- und Bearbeitungsfunktionen von Office Web Apps auf verschiedenen Arten von Geräten zusammenfasst. Die für Touchscreens optimierten Funktionen sind hervorgehoben.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Eine Darstellung, die die Anzeige- und Bearbeitungsfunktionen von Office Web Apps auf verschiedenen Arten von Geräten zusammenfasst. Die für Touchscreens optimierten Funktionen sind hervorgehoben.")

## Office Web Apps Server wird nun als eigenständiger Server installiert.

Office Web Apps wird nicht auf denselben Servern installiert, auf denen SharePoint 2013 ausgeführt wird. Stattdessen stellen Sie einen oder mehrere physische oder virtuelle Server bereit, auf denen Office Web Apps Server ausgeführt wird. Dann konfigurieren Sie die SharePoint 2013-Farm zum Verwenden der Office Web Apps Server-Farm, um Benutzern, die Office-Dateien erstellen oder aus SharePoint-Bibliotheken öffnen, Office Web Apps-Funktionalität bereitzustellen. Weitere Informationen finden Sie unter [Übersicht über Office Web Apps Server](office-web-apps-server-overview.md).

## Optionen für die Lizenzierung von Office Web Apps für den Einsatz mit SharePoint 2013

Die Office Web Apps-Lizenzierung bietet zwei Möglichkeiten:

  - **Nur anzeigen**. Office Web Apps erlaubt standardmäßig nur das Anzeigen von Dateien. Diese Funktionalität wird kostenlos bereitgestellt.

  - **Bearbeiten und anzeigen**. Sie müssen eine Lizenz zum Bearbeiten erwerben, um die Bearbeitungsfeatures von Office Web Apps mit SharePoint 2013 verwenden zu können. Sie ermöglichen die Bearbeitung, wenn Sie eine Office Web Apps Server-Farm erstellen.

Wenn Ihre Organisation Office 2013 über ein Volumenlizenzierungsprogramm lizenziert, können Sie lokal die Office Web Apps-Bearbeitung für SharePoint 2013 ermöglichen. Dadurch können Benutzer Office-Bearbeitungsfunktionen zu Hause oder an anderen Orten nutzen, an denen unter Umständen keine Office-Clients installiert sind. Bearbeitungslizenzen für Office Web Apps können nicht separat erworben werden.

Ausführliche Informationen zu Ihrer Lizenz finden Sie in den Microsoft-Software-Lizenzbedingungen, die bei der Installation von Office Web Apps Server angezeigt werden.

SharePoint 2013 stellt eine neue Lizenzerzwingung bereit, die für Office Web Apps verwendet werden kann. Wenn Sie die SharePoint-Lizenzierung und anschließend die Office Web Apps-Bearbeitung aktivieren, können nur Benutzer, die über die entsprechende Lizenz verfügen, Office-Dateien in einem Browser bearbeiten. Falls für Benutzer keine Office Web Apps-Bearbeitungslizenzen angewendet werden, wird nur das Anzeigen unterstützt.

Weitere Informationen zur Funktionsweise der Lizenzierung in SharePoint 2013 finden Sie unter [Konfigurieren der Lizenzierung in SharePoint Server 2013](https://technet.microsoft.com/de-de/library/jj219627\(v=office.15\)). Der Parameter "EditingEnabled", der die Bearbeitung ermöglicht, wird unter [New-OfficeWebAppsFarm](new-officewebappsfarm.md) sowie unter [Set-OfficeWebAppsFarm](set-officewebappsfarm.md) beschrieben.

Dateien, die mit dem Feature "Freigabe per Link" in SharePoint 2013 gesendet werden, können in Office Web Apps bearbeitet werden, auch wenn keine Bearbeitungslizenz vorhanden und die Bearbeitung für die Office Web Apps Server-Farm deaktiviert ist.

## Verwenden der Office Mobile Viewer für den Zugriff auf Dateien auf SharePoint-Websites

Office Web Apps Server bietet Office Mobile Viewer, um Office Web Apps mobilen Benutzern zur Verfügung zu stellen, die auf SharePoint Server-Websites zugreifen. Office Mobile Viewer sind standardmäßig aktiviert, können aber vom SharePoint Server-Websiteadministrator deaktiviert werden. Falls aktiviert, können Benutzer in ihrem Browser zur SharePoint Server-Website navigieren und auf das Dokument tippen, das Sie in der SharePoint Server-Bibliothek öffnen möchten. Das Dokument wird daraufhin im mobilen Browser geöffnet.

Weitere Details zu SharePoint-Bibliotheken auf Mobilgeräten finden Sie unter [What's new for mobile devices in SharePoint 2013](https://technet.microsoft.com/de-de/library/fp161352\(v=office.15\)) und [Übersicht über mobile Geräte und SharePoint Server 2013](https://technet.microsoft.com/de-de/library/fp161351\(v=office.15\)). Unter [Verwenden von Office Web Apps auf Ihrem Android-Smartphone, iPhone oder Windows Phone](http://go.microsoft.com/fwlink/p/?linkid=271045) erfahren Benutzer mehr zur Office Mobile Viewer-Verwendung auf ihrem Mobilgerät. Wenn Sie Office Mobile Viewer für SharePoint 2013 deaktivieren möchten, verwenden Sie das Cmdlet [Remove-SPWOPIBinding](remove-spwopibinding.md).

## Unterschiede zwischen Excel Web App und Excel Services in SharePoint

Excel Web App und Excel Services in SharePoint weisen viele Gemeinsamkeiten auf, sind aber nicht identisch. Excel Services ist ausschließlich in der Enterprise Edition von SharePoint Server 2013 verfügbar. Excel Web App ist in SharePoint Server 2013 und SharePoint Foundation 2013 verfügbar. Beide Anwendungen bieten Ihnen die Möglichkeit, Arbeitsmappen in einem Browserfenster anzuzeigen sowie mit Daten zu arbeiten und Daten zu analysieren.

Es gibt jedoch bestimmte Unterschiede zwischen Excel Web App und Excel Services in SharePoint. So unterstützt Excel Services beispielsweise externe Datenverbindungen, Datenmodelle und die Möglichkeit zum Interagieren mit Elementen, von denen Datenmodelle verwendet werden (beispielsweise PivotChart-Berichte, PivotTable-Berichte oder Zeitachsen-Steuerelemente). Excel Services bietet mehr Business Intelligence-Funktionen als Excel Web App, mit Excel Services können Benutzer allerdings keine Arbeitsmappen in einem Browserfenster erstellen oder bearbeiten.

Einzelheiten zu den Unterschieden zwischen Excel Web App und Excel Services finden Sie unter [Übersicht über Excel Services in SharePoint Server 2013](https://technet.microsoft.com/de-de/library/ee424405\(v=office.15\)) und [Vergleich von Excel Services in SharePoint mit Excel Web App](http://go.microsoft.com/fwlink/p/?linkid=255460).

Wenn Ihre Organisation entscheidet, Excel Services anstelle von Excel Web App zu verwenden, um Arbeitsmappen in einem Browser anzuzeigen, können Sie das Windows PowerShell-Cmdlet **New-SPWOPISuppressionSettings** verwenden, um Excel Web App für Excel-Arbeitsmappen zu deaktivieren. Weitere Informationen finden Sie unter [New-SPWOPISuppressionSetting](new-spwopisuppressionsetting.md).

## Siehe auch


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Planen von Office Web Apps (verwendet mit SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
  

[](plan-office-web-apps-used-with-sharepoint-2013.md)

