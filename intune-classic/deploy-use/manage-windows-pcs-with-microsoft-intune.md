---
title: Verwalten von PCs mit Softwareclient
description: Verwalten Sie Windows-PCs durch die Installation der Intune-Clientsoftware.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b8d22fe-c318-4796-b760-44f1ccf34312
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 580f6d66fa81308896823c8bcdebe853eb69127a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="manage-windows-pcs-as-computers-via-intune-software-client"></a>Verwalten von Windows-PCs als Computer mit dem Intune-Softwareclient

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Intune bietet Organisationen eine umfassende Lösung für die Verwaltung mobiler Geräte. Intune kann Windows-PCs mithilfe der modernen Geräteverwaltungsfunktionen des Betriebssystems Windows 10 als mobile Geräte verwalten. Zum Erfüllen der Verwaltungsanforderungen Ihrer Organisation kann Intune Windows-PCs mithilfe des Intune-Softwareclients auch als Computer verwalten. Für diese Verwaltungsmethode werden herkömmliche Funktionen für die Computerverwaltung in älteren Windows-Betriebssystemen verwendet.

Der Intune-Softwareclient eignet sich optimal für Windows-PCs mit älteren Betriebssystemen wie Windows 7, die nicht als mobile Geräte verwaltet werden können. Der Intune-Softwareclient verwendet zum Verwalten von PCs in der Cloud Verwaltungsfunktionen wie Gruppenrichtlinien.

Intune unterstützt die Verwaltung von Windows-PCs als Computer mit dem Softwareclient für bis zu 7.000 PCs. Verwalten Sie Windows 10-PCs in größeren Bereitstellungen als mobile Geräte. Alle Versionen von Intune und Updates von Windows 10 bieten Verwaltungsfunktionen, die auf der Architektur für die Verwaltung mobiler Geräte basieren. Es wird ausdrücklich empfohlen, dass Ihre Organisation Windows 10-Geräte als mobile Geräte verwaltet.


> [!NOTE]
> Sie können Geräte mit Windows 8.1 oder höher entweder mithilfe der Intune-Clientsoftware als PCs oder als mobile Geräte verwalten. Sie können nicht beide Methoden auf demselben Gerät verwenden. Treffen Sie Ihre Entscheidung wohlüberlegt, ehe Sie PCs mit der Intune-Clientsoftware verwalten. Dieses Thema gilt nur für das Verwalten von Geräten als PCs mithilfe der Intune-Clientsoftware.

## <a name="requirements-for-intune-pc-client-management"></a>Anforderungen für die Intune-PC-Clientverwaltung

**Hardware**: Im Folgenden sind die Hardwaremindestanforderungen zum Installieren der Intune-Clientsoftware aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Netzwerk|Für den Client ist ein PC mit Internetzugriff erforderlich.|
|Prozessor und Arbeitsspeicher|Weitere Informationen entnehmen Sie den Prozessor- und Arbeitsspeicheranforderungen des PC-Betriebssystems.|
|Speicherplatz|200 MB verfügbarer Speicherplatz vor der Installation der Clientsoftware|

**Software**: Im Folgenden sind die Softwareanforderungen zum Installieren der Clientsoftware aufgeführt:

|Anforderungen|Weitere Informationen|
|---------------|--------------------|
|Betriebssystem | Windows-Gerät, auf dem Windows Vista oder höher ausgeführt wird. </br></br>**Versionen der Home Edition werden nicht unterstützt.**|
|Administratorrechte|Das Konto, mit dem die Clientsoftware installiert wird, muss über lokale Administratorrechte auf diesem Gerät verfügen.|
|Windows Installer 3.1|Auf dem PC wird Windows Installer 3.1 oder höher benötigt.<br /><br />So zeigen Sie die Windows Installer-Version auf einem PC an:<br /><br />  Klicken Sie auf dem PC mit der rechten Maustaste auf **%windir%\System32\msiexec.exe**, und klicken Sie dann auf **Eigenschaften**.<br /><br />Sie können die neueste Version von Windows Installer von der Microsoft Developer Network-Website unter [Windows Installer Redistributables (Weitervertreibbare Komponenten für Windows Installer)](http://go.microsoft.com/fwlink/?LinkID=234258) herunterladen.|
|Entfernen nicht kompatibler Clientsoftware|Bevor Sie die Intune-Clientsoftware installieren, deinstallieren Sie sämtliche Clientsoftware für Configuration Manager, Operations Manager, Operations Management Suite und Service Manager auf diesem PC.|

## <a name="deploying-the-intune-software-client"></a>Bereitstellen des Intune-Softwareclients
Als Intune-Administrator können Sie Benutzern den Intune-Softwareclient auf verschiedene Weisen zur Verfügung stellen. Anleitungen finden Sie unter [Installieren des Intune-Softwareclients auf Windows-PCs](install-the-windows-pc-client-with-microsoft-intune.md).

## <a name="computer-management-capabilities-with-the-intune-client-software"></a>Computerverwaltungsfunktionen mit der Intune-Clientsoftware
In den meisten Szenarios registrieren Sie Ihre Geräte bei Microsoft Intune, sodass Sie über eine größere Anzahl von Funktionen verfügen. Allerdings können Sie PCs auch mit dem Intune-Softwareclient verwalten, der die folgenden Funktionen bietet:

-   **[Softwareupdateverwaltung](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)**: Sie können PCs auf dem aktuellen Stand halten und entscheiden, wann Updates angewendet werden sollen.

-   **[Windows-Firewall-Richtlinie](/intune-classic/deploy-use/help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune)**: Hiermit können Sie sicherstellen, dass die Windows-Firewall auf keinem von Ihrem Unternehmen verwendeten PC inaktiv oder nicht ordnungsgemäß konfiguriert ist.

-   **[Schutz vor Schadsoftware](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)**: Intune umfasst Endpoint Protection, um Ihre PCs vor Schadsoftware zu schützen.

-   **[Remoteunterstützung](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client#request-and-provide-remote-assistance-to-windows-pcs-that-use-the-intune-client-software )**: Über Intune können Benutzer Kontakt mit IT-Supportmitarbeitern aufnehmen, die ihnen über eine in Intune integrierte Remotedesktop-Funktion Unterstützung bieten können (erfordert TeamViewer-Software).

-   **[Verwaltung von Softwarelizenzen](/intune-classic/deploy-use/manage-license-agreements-for-windows-pc-software-in-microsoft-intune)**: Überwachen Sie, wie viele Lizenzen verfügbar sind und wie viele Lizenzen verwendet werden.
-   **[App-Bereitstellung](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)**: Stellen Sie Software auf PCs bereit, die Sie verwalten. Einige App-Verwaltungsfunktionen sind nicht verfügbar, wenn Sie PCs mit dem Softwareclient verwalten.

<!-- - **Compliance settings reporting** -->

## <a name="policies-and-app-deployments-for-the-intune-software-client"></a>Richtlinien und App-Bereitstellungen für den Intune-Softwareclient

Die Intune-Clientsoftware verwaltet Softwareupdates, Windows-Firewall und Endpoint Protection und unterstützt auf diese Weise [Verwaltungsfunktionen zum Schutz von PCs](policies-to-protect-windows-pcs-in-microsoft-intune.md). Allerdings können auf PCs, die mit der Intune-Clientsoftware verwaltet werden, keine anderen Intune-Richtlinien angewendet werden. Dies gilt auch für **Windows**-Richtlinieneinstellungen speziell für die Verwaltung mobiler Geräte.

Wenn Sie die Intune-Clientsoftware zum Verwalten von Windows-PCs verwenden, können Sie nur die Richtlinien im Abschnitt **Computerverwaltung** verwenden.

Intune verwaltet Windows-PCs mithilfe von Richtlinien, ähnlich wie Gruppenrichtlinienobjekte in Windows Server Active Directory Domain Services. Wenn Sie Computer in einer Active Directory-Domäne mit Intune verwalten, [stellen Sie sicher, dass Intune-Richtlinien nicht zu Konflikten mit Gruppenrichtlinienobjekten führen](/intune-classic/deploy-use/resolve-gpo-and-microsoft-intune-policy-conflicts), die für Ihre Organisation eingerichtet sind. Weitere Informationen finden Sie unter [Gruppenrichtlinien für Anfänger](https://technet.microsoft.com/library/hh147307.aspx).

  ![Auswählen der Vorlage für neue Windows-PC-Richtlinien](../media/select-template-for-pc-policy.png)

Zum Bereitstellen von Apps darf nur Windows Installer (EXE, MSI) verwendet werden.

  ![Auswählen von Plattform und Speicherort für PC-Clientsoftwaredateien](../media/select-platform-of-software-files-for-pc-agent.png)

## <a name="common-tasks-for-windows-pcs"></a>Häufige Aufgaben für Windows-PCs

Sie können die Intune-Administratorkonsole nutzen, um andere allgemeine Verwaltungsaufgaben auf Windows-PCs auszuführen, auf denen der Client installiert ist:
- [Verwenden von Richtlinien zur Vereinfachung der Verwaltung von PCs](use-policies-to-simplify-windows-pc-management.md): Beschreibt die Intune-Richtlinien zur **Computerverwaltung** und stellt eine Liste der Einstellungen für das Microsoft Intune Center bereit.

- [Anzeigen des Hardware- und Softwarebestands für Windows-PCs](view-hardware-and-software-inventory-for-windows-pcs-in-microsoft-intune.md): Erläutert, wie Sie einen Bericht mit Informationen zu den Hardwarefunktionen von PCs und der darauf installierten Software erstellen. Erläutert zudem, wie Sie das PC-Inventar aktualisieren, um sicherzustellen, dass es aktuell ist.
- [Abkoppeln eines Windows-PCs](retire-a-windows-pc-with-microsoft-intune.md): Listet die Schritte zum Abkoppeln eines Windows-PCs auf und beschreibt, was geschieht, wenn Sie einen PC abkoppeln.
- [Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs](manage-user-device-linking-for-windows-pcs-with-microsoft-intune.md): Erläutert, wann und wie Sie einen Benutzer mit einem PC verknüpfen müssen, bevor Sie Software für den Benutzer bereitstellen.
- [Anfordern und Bereitstellen von Remoteunterstützung für Windows-PCs](request-and-provide-remote-assistance-for-windows-pcs-in-microsoft-intune.md): Erläutert, wie Intune-PC-Benutzer Remoteunterstützung von Ihnen erhalten, und beschreibt die Voraussetzungen und das TeamViewer-Setup.

Weitere Informationen zu den oben genannten Aufgaben finden Sie unter [allgemeine Verwaltungsaufgaben](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

## <a name="management-limitations-of-the-intune-client-software"></a>Verwaltungseinschränkungen der Intune-Clientsoftware

Einige Verwaltungsoptionen, die zum Verwalten von PCs als mobile Geräte verwendet werden können, sind nicht für PCs geeignet, die mit der Intune-Clientsoftware verwaltet werden:

-   Vollständiges Zurücksetzen (selektives Zurücksetzen ist verfügbar)
-   Bedingter Zugriff

Beachten Sie auch, dass in der Intune-Administratorkonsole bestimmte Abschnitte, z.B. **Updates**, **Schutz** und **Lizenzen** nur angezeigt werden, wenn Sie Geräte mit der Intune-Clientsoftware registriert haben.

  ![Elemente der Verwaltungskonsole, die nur für den PC-Client angezeigt werden](../media/admin-console-settings-only-for-pc-agent.png)

## <a name="help-with-troubleshooting"></a>Hilfe bei der Problembehandlung

Die Intune-Clientsoftware wird in der Regel im Hintergrund ausgeführt, ohne dass viele Benutzerinteraktionen oder Maßnahmen zur Fehlerbehebung erforderlich sind. Wenn Sie Probleme mit der Computerverwaltung beheben müssen, können Sie die Protokolle überprüfen. Die Intune-Clientsoftware und zugehörige Protokolle sind im Verzeichnis „%Program Files%\Microsoft\OnlineManagement“ installiert.

Unter [Behandlung von Problemen bei der Clienteinrichtung in Microsoft Intune](/intune-classic/troubleshoot/troubleshoot-client-setup-in-microsoft-intune) finden Sie auch Hinweise zu möglichen Problemen und etwaige Lösungen oder Problemumgehungen.
