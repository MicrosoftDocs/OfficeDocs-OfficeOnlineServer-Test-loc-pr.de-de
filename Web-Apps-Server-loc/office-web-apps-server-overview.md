---
title: Übersicht über Office Web Apps Server
TOCTitle: 'Übersicht: Office Web Apps Server'
ms:assetid: 4b199a88-387f-4121-820d-7af580e2a3e8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219437(v=office.15)
ms:contentKeyID: 49633159
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Übersicht über Office Web Apps Server

 

_<strong>Gilt für:</strong> Office Web Apps Server_

_<strong>Letztes Änderungsdatum des Themas:</strong> 2017-05-26_

**Zusammenfassung:** Enthält Informationen zu Office Web Apps Server. Außerdem erfahren Sie hier, wie von dieser Anwendung Office-Funktionen für unterstützte Hosts bereitgestellt werden.

**Zielgruppe:** IT-Spezialisten

Office Web Apps Server ist ein neues Office-Serverprodukt, das browserbasierte Versionen von Word, PowerPoint, Excel und OneNote bereitstellt. Eine einzelne Office Web Apps Server-Farm kann Benutzer unterstützen, die über SharePoint 2013, Lync Server 2013, freigegebene Ordner und Websites auf Office-Dateien zugreifen. Das neue eigenständige Bereitstellungsmodell ermöglicht Ihnen, dass Sie Updates für Ihre Office Web Apps Server-Farm unabhängig von anderen in Ihrer Organisation bereitgestellten Office-Serverprodukten verwalten können.


> [!IMPORTANT]
> Dieser Artikel ist Teil der <A href="content-roadmap-for-office-web-apps-server.md">Inhaltsübersicht für Office Web Apps Server</A>. Verwenden Sie diese Übersicht als Ausgangspunkt für Artikel, Downloads und Videos, die Ihnen bei der Bereitstellung und Verwaltung von Office Web Apps Server helfen können.<BR><STRONG>Benötigen Sie Hilfe mit Office Web Apps auf Ihrem Desktop oder mobilen Gerät?</STRONG> Entsprechende Informationen finden Sie, indem Sie auf <A href="https://go.microsoft.com/fwlink/p/?linkid=32496">Office.com</A> nach „Office Web Apps“ suchen.



Inhalt dieses Artikels:

  - Informationen zu Office Web Apps Server

  - Verwenden von Office Web Apps Server in SharePoint 2013 zum Anzeigen und Bearbeiten von Office-Dokumenten

  - Verwenden von Office Web Apps Server in Lync Server 2013 zum Anzeigen von PowerPoint-Übertragungen

  - Verwenden von Office Web Apps Server zum Anzeigen von Office-Dateien in freigegebenen Ordnern und Websites mithilfe von Onlineviewern

## Informationen zu Office Web Apps Server

Office Web Apps Server ist ein Office-Serverprodukt, das für Office-Dateien browserbasierte Dienste zum Anzeigen und Bearbeiten bereitstellt. Office Web Apps Server kann für Produkte und Dienste verwendet werden, die WOPI (das Web App Open Platform Interface-Protokoll) unterstützen. Zu diesen Produkten, die als Hosts bekannt sind, gehören SharePoint 2013 und Lync Server 2013. Eine Office Web Apps Server-Farm kann Office-Dienste für mehrere lokale Hosts bereitstellen, und Sie können die Farm horizontal von einem Server auf mehrere Server skalieren, wenn die Anforderungen in Ihrer Organisation wachsen. Obwohl Office Web Apps Server dedizierte Server erfordert, auf der keine anderen Serveranwendungen ausgeführt werden, können Sie Office Web Apps Server stattdessen in Instanzen virtueller Computer installieren.

Die Bereitstellung und Verwaltung von Office Web Apps in der Organisation ist jetzt einfacher, da es sich um ein eigenständiges Produkt handelt. Wenn Sie beispielsweise SharePoint 2013 bereitstellen, müssen Sie nicht mehr die SharePoint-Infrastruktur optimieren, um Office Web Apps zu unterstützen, die in früheren Versionen eng in SharePoint Server 2010 integriert waren. Sie können auch Updates für die Office Web Apps Server-Farm separat und mit einer anderen Häufigkeit als bei SharePoint oder Lync Server einspielen. Bei einer eigenständigen Office Web Apps Server-Farm können Benutzer auch Office-Dateien anzeigen oder bearbeiten, die sich außerhalb von SharePoint Server befinden (z. B. in freigegebenen Ordnern oder auf anderen Websites). Diese Funktionalität wird durch ein Feature namens Onlineviewer bereitgestellt.

In der folgenden Abbildung werden die Unterschiede zwischen dem vorherigen Bereitstellungsmodell für Office Web Apps und dem neuen eigenständigen Bereitstellungsmodell für Office Web Apps dargestellt.

**Unterschiede zwischen den Office Web Apps-Bereitstellungsmodellen**

![Zeigt den Unterschied zwischen dem bisherigen Bereitstellungsmodell und dem neuen eigenständigen Bereitstellungsmodell für Office Web Apps Server.](images/JJ219437.f16dd9d1-c9b7-4c8b-a8de-f1f82c0ee1e2(Office.15).gif "Zeigt den Unterschied zwischen dem bisherigen Bereitstellungsmodell und dem neuen eigenständigen Bereitstellungsmodell für Office Web Apps Server.")

## Verwenden von Office Web Apps Server in SharePoint 2013 zum Anzeigen und Bearbeiten von Office-Dokumenten

Bei Verwendung mit SharePoint Server 2013 stellt Office Web Apps Server aktualisierte Versionen von Word Web App, Excel Web App, PowerPoint Web App und OneNote Web App bereit. Benutzer können Office-Dokumente in SharePoint-Bibliotheken mit einem unterstützten Webbrowser auf Computern und vielen mobilen Geräten (z. B. Windows Phones, iPhones, iPads und Windows 8-Tablets) anzeigen und in einigen Fällen auch bearbeiten. Zu den vielen neuen Features in Office Web Apps gehören eine verbesserte Fingereingabeunterstützung sowie verbesserte Bearbeitungsfunktionen. Diese ermöglichen den Benutzern von iPads und Windows 8-Tablets, Office-Dokumente direkt auf ihren Geräten anzuzeigen und zu bearbeiten.

In der folgenden Abbildung werden die Anzeige- und Bearbeitungsfunktionen von Office Web Apps für verschiedene Gerätearten zusammengefasst.

**Anzeige- und Bearbeitungsfunktionen von Office Web Apps**

![Eine Darstellung, die die Anzeige- und Bearbeitungsfunktionen von Office Web Apps auf verschiedenen Arten von Geräten zusammenfasst. Die für Touchscreens optimierten Funktionen sind hervorgehoben.](images/Ff431685.8bf76669-f511-4e02-8ed3-d658e9e746f0(Office.15).gif "Eine Darstellung, die die Anzeige- und Bearbeitungsfunktionen von Office Web Apps auf verschiedenen Arten von Geräten zusammenfasst. Die für Touchscreens optimierten Funktionen sind hervorgehoben.")


> [!TIP]
> Die PowerPoint-Übertragung wurde aus SharePoint 2013 entfernt. Sie steht über OneDrive und Lync Server 2013 zur Verfügung.



Weitere Informationen zu den neuen Features in Office Web Apps finden Sie unter [Funktionsweise von lokalen Office Web Apps mit SharePoint 2013](how-office-web-apps-work-on-premises-with-sharepoint-2013.md).

## Verwendung von Office Web Apps Server in Lync Server 2013 zum Anzeigen von PowerPoint-Übertragungen

In Lync Server 2010 werden PowerPoint-Präsentationen auf eine von zwei Arten angezeigt. Für Benutzer, die Lync 2010 ausführen, werden PowerPoint-Präsentationen im PowerPoint 97-2003-Format und mit einer eingebetteten Kopie des PowerPoint Viewers angezeigt. Für Benutzer, die Lync Web App ausführen, werden PowerPoint-Präsentationen in dynamische HTML-Dateien konvertiert und dann mit einer Kombination aus angepassten DHTML-Dateien und Silverlight angezeigt. Obwohl dieser Ansatz generell effizient ist, gibt es einige Einschränkungen:

  - Der eingebettete PowerPoint Viewer (der ein optimaleres Anzeigeerlebnis bietet) ist nur auf der Windows-Plattform verfügbar.

  - Viele mobile Geräte (auch einige der populärsten Mobiltelefone) unterstützen Silverlight nicht.
    
    Weder der PowerPoint Viewer noch der Ansatz mit DHTML-Dateien und Silverlight unterstützen alle Features (einschließlich Folienübergängen und eingebettetem Video), die in den aktuellen Editionen von PowerPoint verfügbar sind.

Um diese Probleme anzugehen und das Gesamterlebnis für alle Benutzer zu verbessern, die PowerPoint-Präsentationen halten oder anzeigen, wird Office Web Apps Server in Lync Server 2013 verwendet, um PowerPoint-Präsentationen zu behandeln. Dieser neue Ansatz ermöglicht – neben anderen Vorteilen – die folgenden Funktionen:

  - Displays mit höherer Auflösung und bessere Unterstützung für PowerPoint-Funktionen, z. B. Animationen, Folienübergänge und eingebettetes Video.

  - Zusätzliche mobile Geräte können auf diese Präsentationen zugreifen. Der Grund ist, dass Lync Server 2013 anstatt angepasster DHTML-Dateien und Silverlight Standard-DHTML und JavaScript zum Übertragen von PowerPoint-Präsentationen verwendet.

  - Benutzer, die über die entsprechenden Berechtigungen verfügen, können unabhängig von der Präsentation selbst einen Bildlauf durch eine PowerPoint-Präsentation durchführen. Während beispielsweise Ken Myer eine Bildschirmpräsentation hält, kann Pilar Ackerman einen Bildlauf in der Präsentationen durchführen und beliebige Folien der Präsentation anzeigen, ohne die Präsentation von Ken zu beeinträchtigen.

Weitere Informationen zum Konfigurieren von Lync Server 2013 für die Verwendung von Office Web Apps Server finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](https://go.microsoft.com/fwlink/p/?linkid=25690).

## Verwenden von Office Web Apps Server zum Anzeigen von Office-Dateien in freigegebenen Ordnern und Websites mithilfe von Onlineviewern

Mit Onlineviewern können Benutzer Excel-, PowerPoint- und Word-Dateien, die in einer Organisation auf Webservern oder in freigegeben Ordner gespeichert sind, in einem Webbrowser anzeigen. Benutzer können Office-Dateien bequem in einem Webbrowser anzeigen, ohne eine separate Anwendung öffnen zu müssen. Zudem muss für Onlineviewer Office 2013 nicht auf den Benutzercomputern installiert werden. Onlineviewer generieren auch den Code, der erforderlich ist, um die URL in einer Webseite zu verlinken oder einzubetten. Sie können Onlineviewer in Ihrem Intranet oder im Internet verwenden.

Office Web Apps Server stellt unter der Adresse "http://*Office Web Apps Server-Name*/op/generate.aspx" eine Seite bereit, die Sie verwenden können, um Links zu öffentlich verfügbaren Dokumenten mit UNC- oder URL-Adresse zu generieren. Wenn ein Benutzer eine generierte URL auswählt, kann Office Web Apps Server die Datei mithilfe von Onlineviewern vom entsprechenden Speicherort abrufen und dann mithilfe von Office Web Apps rendern. Der Benutzer kann die Word-, Excel- oder PowerPoint-Datei in einem Browser mit funktionsfähigen Office-Features anzeigen. Formatierung und Layout in Word-Dokumenten bleiben erhalten, die Daten in Excel-Arbeitsmappen können gefiltert und sortiert werden, und Animationen werden in PowerPoint-Präsentationen wiedergegeben. Beachten Sie jedoch, dass Onlineviewer den Benutzern lediglich das Anzeigen und nicht das Bearbeiten von Dateien ermöglichen. Zudem können in Onlineviewern keine Dateien geöffnet werden, die eine Authentifizierung erfordern.

Weitere Informationen zu Onlineviewern finden Sie unter [Planen für Onlineviewer](plan-office-web-apps-server.md).


> [!TIP]
> Microsoft hostet eine ausschließlich internetbasierte Version zum Erstellen einer URL auf <A href="http://go.microsoft.com/fwlink/?linkid=25654">Office.com</A>.



## Siehe auch


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Planen von Office Web Apps Server](plan-office-web-apps-server.md)  
[Bereitstellen von Office Web Apps Server](deploy-office-web-apps-server.md)  
  

[](deploy-office-web-apps-server.md)

