---
title: Set-SPWOPIBinding
TOCTitle: Set-SPWOPIBinding
ms:assetid: e373528f-e69b-4e25-9df4-3a5f80ab64ac
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ219454(v=office.15)
ms:contentKeyID: 49633189
ms.date: 12/22/2017
mtps_version: v=office.15
ms.translationtype: HT
---

# Set-SPWOPIBinding

 

_**Gilt für:** Office Web Apps, SharePoint Foundation 2013, SharePoint Server 2013_

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Aktualisiert die Standardklickaktion für die Bindung einer Anwendung oder Dateinamenerweiterung.

## Syntax

```PowerShell
Set-SPWOPIBinding 
    [-Identity] <SPWopiBindingPipeBind> -DefaultAction <SwitchParameter> 
    [-AssignmentCollection <SPAssignmentCollection>] 
    [-Confirm[<SwitchParameter>]] 
    [-WhatIf[<SwitchParameter>]]
```

## Detaillierte Beschreibung

Das **Set-SPWOPIBinding**-Cmdlet aktualisiert die Standardklickaktion für die Bindung einer Anwendung oder Dateinamenerweiterung. Sie können beispielsweise die Standardklickaktion zum Anzeigen für ein Word-Dokument in einer SharePoint-Bibliothek festlegen. Dazu setzen Sie die Standardaktion für die “view”-“Word”-Bindungen auf "true".

Normalerweise würden Sie die Ausgabe des **Get-SPWOPIBinding**-Befehls als Wert für die Identity-Eigenschaft dieses Befehls verwenden. Weitere Informationen finden Sie unter [Get-SPWOPIBinding](get-spwopibinding.md)


> [!IMPORTANT]
> Sie können nur Bindungen festlegen, die mithilfe des <STRONG>New-SPWOPIBinding</STRONG>-Befehls erstellt wurden. Um eine integrierte Bindung zu überschreiben, z. B. die Aktion, die beim Anzeigen eines Word-Dokuments in einer SharePoint-Bibliothek durchgeführt wird, erstellen Sie mit <STRONG>New-SPWOPIBinding</STRONG> eine neue Bindung, und weisen Sie eine andere Aktion zu. Weitere Informationen finden Sie unter <A href="new-spwopibinding.md">New-SPWOPIBinding</A>.



SharePoint-Verwaltungsshell

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
<td><p><strong>Identity</strong></p></td>
<td><p>Erforderlich</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPWopiBindingPipeBind</p></td>
<td><p>Gibt die Bindung an. Normalerweise würden Sie die Ausgabe des <strong>Get-SPWOPIBinding</strong>-Befehls als Wert für die Identity-Eigenschaft verwenden.</p></td>
</tr>
<tr class="even">
<td><p><strong>DefaultAction</strong></p></td>
<td><p>Erforderlich</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Gibt an, ob die Bindung als Standardklickaktion für eine Anwendung oder eine Dateinamenerweiterung in der Bindung festgelegt werden soll.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AssignmentCollection</strong></p></td>
<td><p>Optional</p></td>
<td><p>Microsoft.SharePoint.PowerShell.SPAssignmentCollection</p></td>
<td><p>Verwaltet Objekte zum Zweck der ordnungsgemäßen Beseitigung. Die Verwendung von Objekten wie beispielsweise <strong>SPWeb</strong> oder <strong>SPSite</strong> kann sehr viel Arbeitsspeicher erfordern, und für die Verwendung dieser Objekte in Windows PowerShell-Skripts muss der Arbeitsspeicher entsprechend verwaltet werden. Mit dem <strong>SPAssignment</strong>-Objekt können Sie einer Variablen Objekte zuweisen und die Objekte beseitigen, wenn sie nicht mehr benötigt werden, um Arbeitsspeicher freizugeben. Wenn die Objekte <strong>SPWeb</strong>, <strong>SPSite</strong> oder<strong>SPSiteAdministration</strong> verwendet werden, werden diese automatisch beseitigt, falls keine Zuweisungsauflistung oder kein <strong>Global</strong>-Parameter verwendet wird.</p>
<div class="alert">

> [!TIP]
> Wenn der <STRONG>Global</STRONG>-Parameter verwendet wird, sind alle Objekte im globalen Speicher enthalten. Es kann vorkommen, dass nicht genügend Arbeitsspeicher vorhanden ist, falls Objekte nicht sofort verwendet werden oder mit dem Befehl <STRONG>Stop-SPAssignment</STRONG> beseitigt werden.


</div>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Confirm</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Fordert Sie vor der Ausführung eines Befehls zur Bestätigung auf. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>WhatIf</strong></p></td>
<td><p>Optional</p></td>
<td><p>System.Management.Automation.SwitchParameter</p></td>
<td><p>Zeigt eine Meldung an, die die Auswirkung des Befehls beschreibt, anstatt den Befehl auszuführen. Um weitere Informationen zu erhalten, geben Sie den folgenden Befehl ein: <strong>get-help about_commonparameters</strong>.</p></td>
</tr>
</tbody>
</table>


## Eingabetypen

## Rückgabetypen

## Beispiel

\--------------BEISPIEL-----------------

```PowerShell
Get-SPWOPIBinding -Action "view" -Application "Word"| Set-SPWOPIBinding -DefaultAction
```

In diesem Beispiel wird die Standardklickaktion zum Anzeigen für ein Word-Dokument in einer SharePoint-Bibliothek festgelegt. Sie können überprüfen, ob die Standardklickaktion zum Anzeigen für Word festgelegt ist, indem Sie das Cmdlet **Get-SPWOPIBinding –Action “view” –Application “Word”** ausführen. Der Wert **IsDefaultAction** ist auf “True” festgelegt.

## Siehe auch


[Get-SPWOPIBinding](get-spwopibinding.md)  
[Remove-SPWOPIBinding](remove-spwopibinding.md)  
[New-SPWOPIBinding](new-spwopibinding.md)  


[Inhaltsübersicht für Office Web Apps Server](content-roadmap-for-office-web-apps-server.md)  
[Verwenden von Office Web Apps mit SharePoint 2013](use-office-web-apps-with-sharepoint-2013.md)

