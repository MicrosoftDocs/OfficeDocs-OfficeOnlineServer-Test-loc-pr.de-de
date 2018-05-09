---
title: New-OfficeWebAppsFarm
TOCTitle: New-OfficeWebAppsFarm
ms:assetid: 3616a668-f76f-45c6-914c-3103cbded5d2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219436(v=office.15)
ms:contentKeyID: 49633156
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# New-OfficeWebAppsFarm

 

_**Gilt für:**Office Web Apps Server_

_**Letztes Änderungsdatum des Themas:**2015-03-26_

Erstellt eine neue Office Web Apps Server-Farm auf dem lokalen Computer.

## Syntax

    New-OfficeWebAppsFarm [-AllowCEIP <SwitchParameter>] [-AllowHttp <SwitchParameter>] [-AllowHttpSecureStoreConnections <SwitchParameter>] [-CacheLocation <String>] [-CacheSizeInGB <Nullable>] [-CertificateName <String>] [-ClipartEnabled <SwitchParameter>] [-Confirm [<SwitchParameter>]] [-DocumentInfoCacheSize <Nullable>] [-EditingEnabled <SwitchParameter>] [-ExcelAllowExternalData <SwitchParameter>] [-ExcelConnectionLifetime <Nullable>] [-ExcelExternalDataCacheLifetime <Nullable>] [-ExcelPrivateBytesMax <Nullable>] [-ExcelRequestDurationMax <Nullable>] [-ExcelSessionTimeout <Nullable>] [-ExcelWarnOnDataRefresh <SwitchParameter>] [-ExcelWorkbookSizeMax <Nullable>] [-ExternalURL <String>] [-FarmOU <String>] [-Force <SwitchParameter>] [-InternalURL <String>] [-LogLocation <String>] [-LogRetentionInDays <Nullable>] [-LogVerbosity <String>] [-MaxMemoryCacheSizeInMB <Nullable>] [-MaxTranslationCharacterCount <Nullable>] [-OpenFromUncEnabled <SwitchParameter>] [-OpenFromUrlEnabled <SwitchParameter>] [-OpenFromUrlThrottlingEnabled <SwitchParameter>] [-PicturePasteDisabled <SwitchParameter>] [-Proxy <String>] [-RecycleActiveProcessCount <Nullable>] [-RemovePersonalInformationFromLogs <SwitchParameter>] [-RenderingLocalCacheLocation <String>] [-SSLOffloaded <SwitchParameter>] [-TranslationEnabled <SwitchParameter>] [-TranslationServiceAddress <String>] [-TranslationServiceAppId <String>] [-WhatIf [<SwitchParameter>]]

## Detaillierte Beschreibung

Das Cmdlet **New-OfficeWebAppsFarm** erstellt eine neue Office Web Apps Server-Farm auf dem lokalen Computer. Sie führen dieses Cmdlet auf dem ersten Server in der Office Web Apps Server-Farm aus und fügen der Farm anschließend mit dem Cmdlet **New-OfficeWebAppsMachine** weitere Server hinzu.

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
<th><strong>Parameter</strong></th>
<th>Erforderlich</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AllowCEIP</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert die Erstellung von Berichten zum Programm zur Verbesserung der Benutzerfreundlichkeit auf allen Servern in der Office Web Apps Server-Farm.</p></td>
</tr>
<tr class="even">
<td><p><strong>AllowHttp</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Gibt an, dass IIS-Websites an Port 80 für den HTTP-Zugriff bereitgestellt werden sollen. Verwenden Sie <strong>AllowHTTP</strong> nur in Umgebungen, in denen alle Computer IPSec (vollständige Verschlüsselung) anfordern, oder in Testumgebungen ohne sensible Dateien.</p>
<p>Wird bei Aktivierung von <strong>SSLOffloaded</strong> automatisch aktiviert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowHttpSecureStoreConnections</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Gibt an, dass Verbindungen für einmaliges Anmelden durch Verwendung von Verbindungen ohne SSL (z. B. HTTP) hergestellt werden können. Der Standardwert ist <strong>False</strong>.</p>
<p>Verwenden Sie <strong>AllowHTTPSecureStoreConnections</strong> nur in Umgebungen, in denen für alle Computer IPsec (vollständige Verschlüsselung) erforderlich ist, oder in Testumgebungen, die keine vertraulichen Daten enthalten.</p></td>
</tr>
<tr class="even">
<td><p><strong>CacheLocation</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Speicherort des globalen Datenträgercaches an, der zum Speichern gerenderter Bilddateien dient. Der Standardspeicherort ist <strong>%programdata%\Microsoft\OfficeWebApps\Working\d\</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CacheSizeInGB</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Größe des globalen Datenträgercaches in GB an.</p>
<p>Der Typ muss ein ganzzahliger Wert im Bereich von <strong>0</strong> bis zu einer beliebigen ganzen Zahl sein. Der Standardwert ist <strong>15</strong> GB.</p></td>
</tr>
<tr class="even">
<td><p><strong>CertificateName</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Anzeigenamen des Zertifikats an, das Office Web Apps Server zum Erstellen von HTTPS-Bindungen erstellt.</p>
<p>Wenn das angegebene Zertifikat nicht gefunden wird oder abgelaufen ist oder der angegebene Wert mehreren Zertifikaten zugeordnet ist, wird ein Fehler protokolliert. Die Farm wird nicht erstellt.</p>
<div class="alert">

> [!IMPORTANT]
> Dieser Wert wird auf allen Servern verwendet, die der Office Web Apps Server-Farm beitreten. Deshalb müssen alle Server in der Farm über ein Zertifikat mit diesem Anzeigenamen verfügen.


</div>
<p>Sie müssen den <strong>CertificateName</strong>-Parameter nicht angeben, wenn Sie entweder den Parameter <strong>AllowHttp</strong> oder den Parameter <strong>SSLOffloaded</strong> verwenden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClipartEnabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert Unterstützung für das Einfügen von Bing-Bildern in Office-Dokumente. Für dieses Feature ist eine Kommunikation zwischen dem Server und dem Internet erforderlich, die entweder direkt oder über einen Proxy erfolgt, den Sie mit dem <strong>Proxy</strong>-Parameter angeben.</p>
<p>Der <strong>OpenFromUrlEnabled</strong>-Parameter muss auf <strong>True</strong> festgelegt sein, damit Bing-Bilder funktionieren. Der Standardwert ist <strong>False</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
<tr class="odd">
<td><p><strong>DocumentInfoCacheSize</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Anzahl von Dokumentkonvertierungsdatensätzen an, die in einem Arbeitsspeichercache gespeichert werden.</p>
<p>Der Standardwert ist <strong>5000</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>EditingEnabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert die Unterstützung der Bearbeitung im Browser. Der Standardwert ist <strong>False</strong>. Legen Sie <strong>True</strong> nur fest, wenn Sie über eine entsprechende Lizenz zum Verwenden der Bearbeitungsfunktion verfügen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelAllowExternalData</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert die Aktualisierung unterstützter externer Daten in Excel Web App-Arbeitsmappen, wenn die Arbeitsmappen mit externen Daten verknüpft sind. Der Standardwert ist <strong>True</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelConnectionLifetime</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die Dauer (in Sekunden) externer Datenverbindungen für Excel Web App an. Der Standardwert ist <strong>1800</strong> Sekunden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelExternalDataCacheLifetime</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die Gültigkeitsdauer (in Sekunden) des externen Datencache in Excel Web App an. Der Standardwert ist <strong>300</strong> Sekunden.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelPrivateBytesMax</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Anzahl der von Excel Web App verwendeten privaten Bytes in MB an. Bei Festlegung auf <strong>-1</strong> belegt die maximale Anzahl privater Bytes 50 % des physischen Arbeitsspeichers des Computers.</p>
<p>Der Typ muss <strong>-1</strong> oder eine beliebige positive ganze Zahl sein. Der Standardwert ist <strong>-1</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelRequestDurationMax</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Dauer in Sekunden für eine einzelne Anforderung in einer Sitzung an. Nach dem Ablaufen dieses Zeitraums tritt ein Timeout der Anforderung auf.</p>
<p>Der Typ muss <strong>-1</strong> (keine Begrenzung) oder eine ganze Zahl im Bereich von <strong>1</strong> bis <strong>2073600</strong> sein. Der Standardwert ist <strong>300</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelSessionTimeout</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt den Zeitraum in Sekunden an, für den eine Sitzung ohne Benutzeraktivität in Excel Web App aktiv bleibt. Dies sind die gültigen Werte:</p>
<p><strong>-1</strong>. Die Sitzung läuft nicht ab.</p>
<p><strong>0</strong>. Die Sitzung läuft zum Ende einer einzelnen Anforderung ab.</p>
<p><strong>1</strong> bis <strong>2073600</strong>. Die Sitzung bleibt von 1 Sekunde bis zu 24 Tagen aktiv. Der Standardwert ist <strong>450</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExcelWarnOnDataRefresh</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Deaktiviert bzw. aktiviert das Warnungsdialogfeld, das bei Datenaktualisierungen in Excel Web App angezeigt wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExcelWorkbookSizeMax</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Größe einer zu ladenden Arbeitsmappe in MB an.</p>
<p>Der Typ muss ein ganzzahliger Wert im Bereich von <strong>1</strong> bis <strong>2000</strong> sein. Der Standardwert ist <strong>10</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalURL</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den URL-Stamm an, den Clients für den Zugriff auf die Office Web Apps Server-Farm aus dem Internet verwenden. Bei einer Office Web Apps Server-Farm mit mehreren Servern und Lastenausgleich ist die externe URL an die IP-Adresse des dem Internet zugewandten Lastenausgleichsmoduls gebunden.</p>
<p>Eine Office Web Apps Server-Farm erfordert mindestens eine URL, die entweder auf <strong>ExternalURL</strong> oder <strong>InternalURL</strong> festgelegt ist. Sie können auch sowohl interne als auch externe URLs festlegen.</p></td>
</tr>
<tr class="even">
<td><p><strong>FarmOU</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Namen der Active Directory-Organisationseinheit an, zu der Server gehören müssen, um der Office Web Apps Server-Farm beitreten zu können. Mit diesem Parameter können Sie verhindern, dass nicht autorisierte Server (d. h. Server, die nicht in der Organisationseinheit enthalten sind) einer Office Web Apps Server-Farm beitreten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Force</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Unterdrückt sämtliche Eingabeaufforderungen, indem mit &quot;Ja&quot; geantwortet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>InternalURL</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den URL-Stamm an, den Clients für den Zugriff auf die Office Web Apps Server-Farm aus dem Intranet verwenden.</p>
<p>Eine Office Web Apps Server-Farm erfordert mindestens eine URL, die entweder auf <strong>ExternalURL</strong> oder <strong>InternalURL</strong> festgelegt ist. Sie können auch sowohl interne als auch externe URLs festlegen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogLocation</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Speicherort der Aktivitätsprotokolle auf dem lokalen Computer an.</p>
<p>Der Speicherort gilt für alle Server in der Farm und kann nicht serverbezogen angepasst werden. Der Standardspeicherort ist <strong>%programdata%\Microsoft\OfficeWebApps\Data\Logs\ULS\</strong>.</p>
<p>Stellen Sie auf dem Laufwerk, auf dem die Protokolle gespeichert werden, genügend Festplattenspeicher zur Verfügung.</p></td>
</tr>
<tr class="even">
<td><p><strong>LogRetentionInDays</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die Anzahl der Tage an, die Protokolleinträge gespeichert werden sollen. Protokolleinträge, die älter als das konfigurierte Datum sind, werden entfernt.</p>
<p>Der Typ muss ein ganzzahliger Wert im Bereich von <strong>0</strong> bis <strong>365</strong> sein. Der Standardwert ist <strong>7</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>LogVerbosity</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt an, wie viele Informationen in den Ablaufprotokolldateien gespeichert werden. Die Werte sind wie folgt:</p>
<p><strong>VerboseEX</strong>. Schreibt untergeordnete Details in die Ablaufprotokolldatei. Nützlich für Ablaufverfolgungen mit voraussichtlich hohem Volumen.</p>
<p><strong>Verbose</strong>. Schreibt untergeordnete Details in die Ablaufprotokolldatei.</p>
<p><strong>Medium</strong>. Schreibt als mittelwichtig eingestufte Details in die Ablaufprotokolldatei.</p>
<p><strong>High</strong>. Schreibt als wichtig eingestufte Details in die Ablaufprotokolldatei.</p>
<p><strong>Monitorable</strong>. Schreibt Ablaufverfolgungen, die einen ungewöhnlichen Codepfad darstellen, und Aktionen, die überwacht werden sollten.</p>
<p><strong>Unexpected</strong>. Schreibt Ablaufverfolgungen, die einen unerwarteten Codepfad darstellen, und Aktionen, die überwacht werden sollten.</p>
<p><strong>None</strong>. Schreibt keine Ablaufinformationen in die Ablaufprotokolldatei.</p>
<div class="alert">

> [!IMPORTANT]
> Das Belassen von <STRONG>LogVerbosity</STRONG> auf einer niedrigen Stufe über einen längeren Zeitraum kann sich negativ auf die Systemleistung auswirken.


</div></td>
</tr>
<tr class="even">
<td><p><strong>MaxMemoryCacheSizeInMB</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Speichergröße (in MB) an, die vom Rendercache verwendet werden darf.</p>
<p>Der Typ muss ein ganzzahliger Wert im Bereich von <strong>0</strong> bis zu einer beliebigen positiven Zahl sein. Der Standardwert beträgt <strong>75</strong> MB.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxTranslationCharacterCount</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die maximale Anzahl der Zeichen an, die ein Dokument enthalten kann, um übersetzt werden zu können.</p>
<p>Der Typ muss ein ganzzahliger Wert sein. Der Wert kann auf <strong>0</strong> gesetzt werden, was bedeutet, dass keine Grenze vorliegt. Alternativ kann ein Wert zwischen <strong>2000</strong> und <strong>2.000.000</strong> angegeben werden. Der Standardwert ist <strong>125.000</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUncEnabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert bzw. deaktiviert die Funktion, Office-Dateien über einen UNC-Pfad mit Onlineviewern anzuzeigen.</p>
<div class="alert">

> [!TIP]
> Legen Sie für <STRONG>OpenFromUrlEnabled</STRONG> zunächst <STRONG>True</STRONG> fest, um die Anzeige von Dateien über UNC-Pfade mit Onlineviewern zuzulassen.


</div></td>
</tr>
<tr class="odd">
<td><p><strong>OpenFromUrlEnabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert oder deaktiviert die Funktion, mit Onlineviewern Office-Dateien über eine URL oder einen UNC-Pfad anzuzeigen. Der Standardwert ist <strong>False</strong>.</p>
<p>Sie müssen für diesen Paramater &quot;True&quot; festlegen, wenn Sie <strong>ClipartEnabled</strong> verwenden.</p></td>
</tr>
<tr class="even">
<td><p><strong>OpenFromUrlThrottlingEnabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Begrenzt die Anzahl der Anforderungen vom Typ &quot;Aus URL öffnen&quot; von einem angegebenen Server in einem Zeitraum. Die standardmäßigen, nicht konfigurierbaren Grenzwerte stellen sicher, dass keine Office Web Apps Server-Farm einen einzelnen Server mit Anforderungen für das Anzeigen von Inhalten in den Onlineviewern überlastet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>PicturePasteDisabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Deaktiviert die Möglichkeit für Benutzer, Bilder aus einer Webseite in Office Web Apps einzufügen. Der Standardwert ist <strong>False</strong>. Wenn <strong>OpenFromURLEnabled</strong> auf <strong>True</strong> festgelegt ist und <strong>PicturePasteDisabled</strong> nicht festgelegt oder auf <strong>False</strong> festgelegt ist, können Benutzer Bilder in Office Web Apps einfügen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Proxy</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die URL des Proxyservers an, der dafür konfiguriert ist, dass HTTP-Anforderungen an externe Websites erfolgreich sind. Wird zumeist gemeinsam mit den Parametern <strong>ClipartEnabled</strong> und <strong>TranslationEnabled</strong> konfiguriert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecycleActiveProcessCount</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Nullable</p></td>
<td><p>Gibt die Anzahl von Dateien an, die ein einzelner Word- oder PowerPoint-Prozess rendern kann, bevor der Prozess wiederverwendet wird.</p>
<p>Der Typ muss ein ganzzahliger Wert im Bereich von <strong>1</strong> bis <strong>1000</strong> sein. Der Standardwert ist <strong>5</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>RemovePersonalInformationFromLogs</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Ermöglicht das bestmögliche Entfernen von persönlichen Informationen aus Office Web Apps Server-Protokollen und ersetzt Werte durch einen SHA256-Hash. Folgende Informationen werden möglicherweise entfernt:</p>
<ul>
<li><p>Dokumentnamen und URLs</p></li>
<li><p>IP-Adressen</p></li>
<li><p>E-Mail-Adressen</p></li>
<li><p>Benutzernamen</p></li>
</ul>
<p>Der Standardwert ist <strong>False</strong>. Beachten Sie, dass durch Aktivieren dieses Parameters nicht garantiert wird, dass die persönlichen Informationen nicht in den Office Web Apps Server-Protokollen erfasst werden.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RenderingLocalCacheLocation</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt den Speicherort des temporären Caches an, der für die Word- und PowerPointAnzeigedienstanwendung verwendet werden soll.</p>
<p>Der Standardspeicherort ist <strong>%programdata%\Microsoft\OfficeWebApps\Working\waccache\</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SSLOffloaded</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Gibt den Servern in der Office Web Apps Server-Farm an, dass SSL an das Lastenausgleichsmodul ausgelagert wird. Bei Aktivierung von <strong>SSLOffloaded</strong> werden Webanwendungen an Port 80 (HTTP) auf dem lokalen Server gebunden. Für HTML, die auf andere Ressourcen verweist, z. B. CSS oder Bilder, werden allerdings HTTPS-URLs für diese Verweise verwendet.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationEnabled</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Aktiviert Unterstützung für die automatische Dokumentübersetzung mit Microsoft Translator, einem Onlinedienst, der Text zwischen zwei Sprachen übersetzt. Die übersetzte Datei wird in Word Web App angezeigt. Da Microsoft Translator ein Onlinedienst ist, müssen Sie die Kommunikation zwischen dem Server und dem Internet entweder direkt oder über einen Proxy aktivieren, den Sie mit dem <strong>Proxy</strong>-Parameter angeben.</p>
<div class="alert">

> [!IMPORTANT]
> Microsoft Translator sammelt ggf. Daten zur Verbesserung der Qualität von Übersetzungen.


</div></td>
</tr>
<tr class="even">
<td><p><strong>TranslationServiceAddress</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die URL des Übersetzungsservers an, an den Übersetzungsanforderungen gesendet werden. Standardmäßig ist der Microsoft Translator-Onlinedienst angegeben. In der Regel wird dieser Parameter nicht verwendet, es sei denn, Sie müssen die Übersetzungsdienste ändern.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TranslationServiceAppId</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.String</p></td>
<td><p>Gibt die Anwendungs-ID für den Übersetzungsdienst an. Standardmäßig ist die öffentliche Anwendungs-ID für Office Web Apps angegeben. In der Regel wird dieser Parameter nicht verwendet, es sei denn, Sie haben mit Microsoft Translator zusätzliche Dienste ausgehandelt und eine private Anwendungs-ID erhalten.</p></td>
</tr>
<tr class="even">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Zeigt eine Meldung an, die die Auswirkung des Befehls beschreibt, anstatt den Befehl auszuführen. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong></p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\------------------BEISPIEL 1---------------------

    New-OfficeWebAppsFarm -InternalUrl "https://server.corp.contoso.com" -ExternalUrl "https://server.external.contoso.com" -EditingEnabled:$true -SSLOffloaded

In diesem Beispiel wird eine Office Web Apps Server-Farm auf dem lokalen Server erstellt, auf dem die Bearbeitung für Office Web Apps aktiviert ist. Die Farm wird für den Lastenausgleich konfiguriert, indem **SSLOffloaded** aktiviert wird, wodurch **AllowHttp** automatisch aktiviert wird. Wenn Sie keinen Lastenausgleich verwenden, müssen Sie **CertificateName** festlegen.

## Siehe auch


[Set-OfficeWebAppsFarm](set-officewebappsfarm.md)  
[Repair-OfficeWebAppsFarm](repair-officewebappsfarm.md)  
[Get-OfficeWebAppsFarm](get-officewebappsfarm.md)  
[New-OfficeWebAppsMachine](new-officewebappsmachine.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Bereitstellen der Infrastruktur: Office Web Apps Server](deploy-the-infrastructure-office-web-apps-server.md)  
  

[](deploy-the-infrastructure-office-web-apps-server.md)

