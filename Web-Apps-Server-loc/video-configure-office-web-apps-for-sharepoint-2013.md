---
title: 'Video: Konfigurieren von Office Web Apps für SharePoint 2013'
TOCTitle: 'Video: Konfigurieren von Office Web Apps für SharePoint 2013'
ms:assetid: 0c02633f-3839-448b-ae83-24f24c254179
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn455088(v=office.15)
ms:contentKeyID: 59152172
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Video: Konfigurieren von Office Web Apps für SharePoint 2013

 

_**Gilt für:**Office Web Apps, Office Web Apps Server, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:**2016-12-16_

**Zusammenfassung:** Vorstellung der neun wesentlichen Schritte zum Konfigurieren einer Office Web Apps Server-Farm für die Zusammenarbeit mit SharePoint 2013.

Die Konfiguration von Office Web Apps für SharePoint 2013 ist relativ einfach. In diesem Video wird das Einrichten von Office Web Apps Server und Konfigurieren von SharePoint 2013 für die Verwendung von Office Web Apps Server gezeigt.


**Sehen Sie sich das Video "Konfigurieren von Office Web Apps für SharePoint 2013" an.**

> [!VIDEO https://www.microsoft.com/de-de/videoplayer/embed/179bf96f-09e1-407a-bb1b-a8e6623eabae]

In diesem Video werden Verfahren behandelt, die auf zwei Servern erfolgen: dem Server mit ausgeführtem Office Web Apps Server und dem Server mit ausgeführtem SharePoint 2013. Es muss sich um zwei getrennte Server handeln (siehe [Software-, Hardware- und Konfigurationsanforderungen für Office Web Apps Server](plan-office-web-apps-server.md)).

**Auf dem Server mit ausgeführtem Office Web Apps Server zeigt das Video die folgende Schrittfolge:**

1\. Öffnen der Windows PowerShell-Eingabeaufforderung und Installieren der für Office Web Apps Server benötigten Rollen und Dienste (siehe [Vorbereiten der Server für Office Web Apps Server](deploy-office-web-apps-server.md)). Dies ist notwendig, da Office Web Apps Server nicht installiert wird, wenn die benötigten Rollen und Dienste fehlen.  
2\. Installieren der Office Web Apps Server-Software nach dem Herunterladen aus dem [Volume Licensing Service Center (VLSC)](http://go.microsoft.com/fwlink/p/?linkid=256561). Zum Herunterladen von Office Web Apps Server benötigen Sie eine Lizenz unter einem Volumenlizenzvertrag für Office Professional Plus 2013, Office Standard 2013 oder Office für Mac 2011. Der Download befindet sich unter den betreffenden Office-Produkten im VLSC-Portal.  
3\. Erstellen der Office Web Apps Server-Farm mithilfe von [New-OfficeWebAppsFarm](new-officewebappsfarm.md).  
4\. Prüfen, ob die Office Web Apps Server-Farm erfolgreich erstellt wurden, indem in einem Browserfenster **http://*ServerName***/hosting/discovery\</ui\> geöffnet wird.

**Auf dem Server mit ausgeführtem SharePoint 2013 zeigt das Video die folgende Schrittfolge:**

5\. Öffnen der SharePoint 2013 Management Shell-Eingabeaufforderung.  
6\. Herstellen der Bindung zwischen Office Web Apps Server und SharePoint 2013 mithilfe von [New-SPWOPIBinding](new-spwopibinding.md). Dadurch wird die Kommunikation zwischen dem Server mit ausgeführtem SharePoint 2013 und dem Server mit ausgeführtem Office Web Apps Server hergestellt.  
7\. Anzeigen der WOPI-Zone von SharePoint 2013 mithilfe von [Get-SPWOPIZone](get-spwopizone.md). In diesem Schritt wird hervorgehoben, dass die beiden Server verschiedene WOPI-Zonen nutzen: SharePoint 2013 verwendet **internal-https**, Office Web Apps Server verwendet **internal-http**. Die Zone muss stimmen, damit Office Web Apps ordnungsgemäß funktionieren kann.  
8\. Ändern der WOPI-Zone für SharePoint 2013 mithilfe von [Set-SPWOPIZone](set-spwopizone.md) in **internal-http**.  
9\. Prüfen, ob Office Web Apps funktioniert, indem ein Office-Dokument in einer SharePoint 2013-Dokumentbibliothek geöffnet wird.

Weitere Informationen zu diesen Schritten finden Sie in den folgenden Abschnitten in den Artikeln: [Bereitstellen von Office Web Apps Server](deploy-office-web-apps-server.md) und [Konfigurieren von Office Web Apps für SharePoint 2013](configure-office-web-apps-for-sharepoint-2013.md).

  - [Vorbereiten von Server für die Ausführung von Office Web Apps Server](deploy-office-web-apps-server.md)

  - [Deploy a single-server Office Web Apps Server farm that uses HTTP](deploy-office-web-apps-server.md)

  - [Vorbereiten der Konfiguration von SharePoint 2013 für die Verwendung von Office Web Apps Server](configure-office-web-apps-for-sharepoint-2013.md)

  - [Konfigurieren von SharePoint 2013 für die Verwendung von Office Web Apps Server in einer Testumgebung, die HTTP verwendet](configure-office-web-apps-for-sharepoint-2013.md)

## Siehe auch


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Planen von Office Web Apps (verwendet mit SharePoint 2013)](plan-office-web-apps-used-with-sharepoint-2013.md)  
[Funktionsweise von lokalen Office Web Apps mit SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)  
  

[](how-office-web-apps-work-on-premises-with-sharepoint-2013.md)

