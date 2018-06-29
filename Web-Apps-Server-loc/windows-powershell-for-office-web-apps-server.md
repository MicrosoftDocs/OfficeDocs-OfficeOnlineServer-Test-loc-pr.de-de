---
title: Windows PowerShell für Office Web Apps Server
TOCTitle: Windows PowerShell für Office Web Apps Server
ms:assetid: 56bfd3b3-f563-423d-aea0-65b331f73b96
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Ee890080(v=office.15)
ms:contentKeyID: 49633161
ms.date: 01/12/2018
mtps_version: v=office.15
ms.translationtype: HT
---

# Windows PowerShell für Office Web Apps Server

 

_**Gilt für:** Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:** 2016-12-16_

**Zusammenfassung:** Hier finden Sie Artikel zu Windows PowerShell-Cmdlets vom Typ "OfficeWebApps", die zum Konfigurieren von Office Web Apps Server verwendet werden.

**Zielgruppe:** IT-Spezialisten

Office Web Apps Server ist ein neues Office-Serverprodukt, das browserbasierte Versionen von Word, PowerPoint, Excel und OneNote bereitstellt. Eine einzelne Office Web Apps Server-Farm kann Benutzer unterstützen, die über SharePoint 2013, Lync Server 2013, Exchange Server 2013, freigegebene Ordner und Websites auf Office-Dateien zugreifen.

![Office 2013-Logo](images/Ee890081.a106e261-2cd0-43b7-af77-92de7e4b6fb9(Office.15).png "Office 2013-Logo")In der folgenden Tabelle sind die Artikel für jedes Windows PowerShell-Cmdlet vom Typ "OfficeWebApps" für Office Web Apps Server aufgelistet und beschrieben.


> [!TIP]
> Wenn Windows PowerShell diese auszuführenden Cmdlets nicht erkennt, müssen Sie ggf. das <STRONG>OfficeWebApps</STRONG>-Modul mit diesem Befehl importieren:<BR><CODE>Import-Module -Name OfficeWebApps</CODE>




### Windows PowerShell-Cmdlets vom Typ "OfficeWebApps"

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Artikel</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="get-officewebappsfarm.md">Get-OfficeWebAppsFarm</a></p></td>
<td><p>Gibt Details zum OfficeWebAppsFarm-Objekt zurück, zu dem der aktuelle Server gehört.</p></td>
</tr>
<tr class="even">
<td><p><a href="get-officewebappshost.md">Get-OfficeWebAppsHost</a></p></td>
<td><p>Gibt die Liste mit den Hostdomänen in der Zulassungsliste einer Office Web Apps Server-Farm zurück.</p></td>
</tr>
<tr class="odd">
<td><p><a href="get-officewebappsmachine.md">Get-OfficeWebAppsMachine</a></p></td>
<td><p>Gibt Einzelheiten zum aktuellen Server in einer Office Web Apps Server-Farm zurück.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsfarm.md">New-OfficeWebAppsFarm</a></p></td>
<td><p>Erstellt eine neue Office Web Apps Server-Farm auf dem lokalen Computer.</p></td>
</tr>
<tr class="odd">
<td><p><a href="new-officewebappshost.md">New-OfficeWebAppsHost</a></p></td>
<td><p>Fügt eine Hostdomäne der Zulassungsliste einer Office Web Apps Server-Farm hinzu.</p></td>
</tr>
<tr class="even">
<td><p><a href="new-officewebappsmachine.md">New-OfficeWebAppsMachine</a></p></td>
<td><p>Fügt den aktuellen Server einer vorhandenen Office Web Apps Server-Farm hinzu.</p></td>
</tr>
<tr class="odd">
<td><p><a href="remove-officewebappshost.md">Remove-OfficeWebAppsHost</a></p></td>
<td><p>Entfernt eine Hostdomäne aus der Zulassungsliste einer Office Web Apps Server-Farm.</p></td>
</tr>
<tr class="even">
<td><p><a href="remove-officewebappsmachine.md">Remove-OfficeWebAppsMachine</a></p></td>
<td><p>Entfernt den aktuellen Server aus der Office Web Apps Server-Farm.</p></td>
</tr>
<tr class="odd">
<td><p><a href="repair-officewebappsfarm.md">Repair-OfficeWebAppsFarm</a></p></td>
<td><p>Entfernt alle als instabil gekennzeichneten Server aus einer Office Web Apps Server-Farm.</p></td>
</tr>
<tr class="even">
<td><p><a href="set-officewebappsfarm.md">Set-OfficeWebAppsFarm</a></p></td>
<td><p>Konfiguriert die Einstellungen einer vorhandenen Office Web Apps Server-Farm.</p></td>
</tr>
<tr class="odd">
<td><p><a href="set-officewebappsmachine.md">Set-OfficeWebAppsMachine</a></p></td>
<td><p>Ändert die Einstellungen des aktuellen Servers in einer Office Web Apps Server-Farm.</p></td>
</tr>
</tbody>
</table>


### Andere Office-Ressourcen für IT-Spezialisten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><img src="images/Ee890081.22cad0f4-303d-4a40-90a3-fa08e69dfdaf(Office.15).png" title="Neuerungensymbol (Paket)" alt="Neuerungensymbol (Paket)" /></p></td>
<td><p><strong>Neu veröffentlichte Inhalte</strong></p></td>
<td><p>Im Folgenden finden Sie eine Liste der neuen oder vor kurzem aktualisierten Office Web Apps Server-Artikel.</p>
<ul>
<li><p><a href="https://technet.microsoft.com/de-de/library/ff433481(v=office.15)">Neu veröffentlichte Inhalte für Office Web Apps und Office Web Apps Server</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><img src="images/Ee890081.6b2d6dfa-7dc8-40fb-8335-af68b575f8cb(Office.15).png" title="Erste Schritte" alt="Erste Schritte" /></p></td>
<td><p><strong>Erste Schritte</strong></p></td>
<td><p>Laden Sie Office Web Apps Server herunter.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256561">Volume Licensing Service Center (VLSC)</a></p>
<p>Zum Herunterladen von Office Web Apps Server benötigen Sie eine Lizenz unter einem Volumenlizenzvertrag für Office Professional Plus 2013, Office Standard 2013 oder Office für Mac 2011. Der Download befindet sich unter den betreffenden Office-Produkten im VLSC-Portal.</p></li>
</ul>
<p>Laden Sie die Sprachpakete für Office Web Apps Server herunter.</p>
<ul>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=263945">Microsoft Download Center</a></p></li>
</ul>
<p>Weitere Informationen zu Office Web Apps Server.</p>
<ul>
<li><p><a href="deploy-the-infrastructure-office-web-apps-server.md">Bereitstellen der Infrastruktur: Office Web Apps Server</a></p></li>
</ul>
<p>Erkunden Sie diese Links, um zu erfahren, wie Office-Serverprodukte Office Web Apps Server verwenden können, um das webbasierte Anzeigen und Bearbeiten von Office-Dateien zu ermöglichen.</p>
<ul>
<li><p><a href="use-office-web-apps-with-sharepoint-2013.md">Verwenden von Office Web Apps mit SharePoint 2013</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256902">Bereitstellen von Office Web Apps Server und Lync Server 2013</a></p></li>
<li><p><a href="http://go.microsoft.com/fwlink/p/?linkid=256611">Office Web Apps Server-Integration (Exchange Server 2013)</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><img src="images/Ee890081.6fa793ee-ede9-4476-901c-de96ea37fc3a(Office.15).png" title="Chatsymbol" alt="Chatsymbol" /></p></td>
<td><p><strong>Bereitstellen von Feedback</strong></p></td>
<td><p>Stellen Sie Feedback zur Dokumentation für Office 2013Office 365 ProPlus bereit. Wählen Sie dazu den Feedback-Link am Seitenende. Dadurch wird Ihr Feedback direkt an das Dokumentationsteam übermittelt.</p>
<p><img src="images/Ee890080.1863f854-8ce5-40e4-bd40-9bbe16591834(Office.15).png" title="E-Mail" alt="E-Mail" />Wenn Sie Vorschläge für künftige Inhalte machen oder weitere Dokumentation anfordern (bzw. einen Fehler melden) möchten, senden Sie eine E-Mail an <a href="mailto:feedork@microsoft.com">feedork@microsoft.com</a>.</p></td>
</tr>
</tbody>
</table>


## Informationen zu Schulungsmaterial und anderen Ressourcen zu Office


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Download</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/evalcenter/hh973391">Office 365 ProPlus</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/p/?linkid=507653">Office 365</a></p></li>
<li><p><a href="https://technet.microsoft.com/en-us/evalcenter/ee390818.aspx">Office 2013</a></p></li>
<li><p><a href="https://code.msdn.microsoft.com/de-de/office/">Office-Codebeispiele</a></p></li>
<li><p><a href="https://gallery.technet.microsoft.com/office/de-de/">Office-Skripts und -Beispieldateien</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/office/aa905351">Office-Downloads für Entwickler</a></p></li>
<li><p><a href="http://www.microsoft.com/de-de/download/office.aspx?q=office">Office-Downloads</a></p></li>
<li><p><a href="http://www.microsoft.com/de-de/download/search.aspx?q=office+365">Office 365-Downloads</a></p></li>
</ul></td>
<td><p><strong>Vorgehensweise</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/de-de/library/jj220060.aspx">Erstellen von Apps für Office</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/library/cc178982.aspx">Bereitstellen von Office 2013</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/library/cc179068.aspx">Verwalten von Office 2013</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/office/ff381682.aspx">Schulen von Office 2010-Endbenutzern</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/office/aa905496.aspx">Office-SDKs</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/office/aa905375">Office-Schulung für Entwickler</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/de-de/office/media/video/video.html?cid=odc%26from=mscomodc">Office-Videos für Entwickler</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/msdn/de-de/office/media/video/video.html?cid=o365%26from=mscomo365">Office 365-Videos für Entwickler</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/office/ff519671">Office-Schulung für IT-Experten</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/de-de/office/media/video/video.html?cid=otc%26from=mscomotc">Office-Videos für IT-Experten</a></p></li>
<li><p><a href="http://www.microsoft.com/resources/technet/de-de/office/media/video/video.html?cid=o365%26from=mscomo365">Videos für Office 365 IT-Experten</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/openspecifications/">Open Specifications</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/library/cc307282+(v=office.12).aspx">Office-Protokolle</a></p></li>
</ul></td>
<td><p><strong>Sites</strong></p>
<ul>
<li><p><a href="https://msdn.microsoft.com/de-de/office">Office-Entwickler</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/office">Office für IT-Experten</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/office/hh506337">Office 365-Entwickler</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/hh912691">Office 365-IT-Experten</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/library/cc303401.aspx">Office 2013 Resource Kit</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/sharepoint">SharePoint-Entwickler</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/sharepoint">SharePoint für IT-Experten</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/vstudio/aa718325">Visual Studio-Entwickler</a></p></li>
<li><p><a href="http://office.microsoft.com/">Office.com</a></p></li>
</ul></td>
<td><p><strong>Help</strong></p>
<ul>
<li><p><a href="https://technet.microsoft.com/de-de/office/ee748587.aspx">Office-Updates</a></p></li>
<li><p><a href="https://blogs.msdn.com/b/officeapps">Blog &quot;Apps für Office und SharePoint&quot;</a></p></li>
<li><p><a href="https://social.msdn.microsoft.com/forums/de-de/category/officedev%2coldevelopment%2csharepoint2010%2csharepoint%2cprojectserver2010%2cprojectprofessional2010%2cuc/">Foren: Office für Entwickler</a></p></li>
<li><p><a href="https://answers.microsoft.com/de-de/msoffice">Foren: Office 365</a></p></li>
<li><p><a href="https://social.technet.microsoft.com/wiki">TechNet Wiki</a></p></li>
<li><p><a href="https://stackoverflow.com/search?q=office">StackOverflow: Office</a></p></li>
<li><p><a href="https://mvp.microsoft.com/de-de/mvp/search-mvp.aspx?kw=office">Office-MVPs</a></p></li>
<li><p><a href="https://technet.microsoft.com/de-de/ms772425">Support für Office-IT-Experten</a></p></li>
<li><p><a href="https://msdn.microsoft.com/de-de/office/aa905515">Support für Office-Entwickler</a></p></li>
</ul></td>
</tr>
</tbody>
</table>


[](use-office-web-apps-with-sharepoint-2013.md)

