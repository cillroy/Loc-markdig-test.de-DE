---
title: "Testen und Überprüfen von Intune"
description: "Die Details, die Sie beim Testen und Überprüfen einer Nur-Cloud-Lösung in Ihrer Umgebung bedenken sollten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: f10b4b0e7c48e921eb92392edf95bfcfaa83db9f
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="intune-testing-and-validation"></a>Testen und Überprüfen von Intune

Die Testphase tritt jeweils während und nach der Implementierungsphase auf. Sie müssen Konten, Gruppen und Geräte für Testzwecke aller erforderlichen IT- (Administrator) und Endbenutzerszenarios (Anwendungsfall) testen, die Sie zuvor angegeben haben.

Es wird empfohlen, Ihre IT-Support- und Helpdeskmitarbeiter in die Testphase einzubeziehen, damit sie eine Supportdokumentation erstellen und sich mit der Unterstützung des Produkts vertraut machen. Wenn eine Komponente oder ein Szenario auf der Grundlage der Anwendungsfälle nicht funktioniert, stellen Sie sicher, dass die notwendigen Änderungen dokumentiert werden. Geben Sie dabei den Grund für die Änderung an.

## <a name="before-you-begin"></a>Vorbereitung

Wir empfehlen, die folgenden Schritte zu dokumentieren:

-   **Testkriterien:** Identifizieren Sie die Benchmarks, anhand derer die Messung erfolgt.

-   **Entwurfskomponenten:** Müssen in mindestens einem Testkriterium vorhanden sein.

Wenn eine Entwurfskomponente nicht in mindestens einem auf eine Anforderung oder ein Szenario ausgerichteten Testkriterium vorhanden ist, überlegen Sie, ob die Entwurfskomponente erforderlich ist oder nicht. Stellen Sie darüber hinaus sicher, dass die folgenden Elemente vorhanden sind:

-   **Konten:** Testkonten, die für EMS und Office 365 lizenziert sind, um alle Anwendungsszenarios testen zu können.

-   **Geräte:** Testgeräte, die zurückgesetzt oder auf Werkseinstellungen zurückgesetzt werden können.

-   **Integrationskomponenten:** Alle Integrationskomponenten (Certificate Connector, dienstübergreifender Intune-Connector für gehostetes Exchange und Intune-Connector für lokale Exchange-Umgebungen) müssen bei Bedarf installiert und konfiguriert werden.

Sie benötigen möglicherweise Entwurfsänderungen, um unvorhergesehene Probleme zu berücksichtigen. Darüber hinaus müssen alle Entwurfsänderungen vollständig zusammen mit der jeweiligen Begründung dokumentiert werden. Hier sehen Sie ein Beispiel für die Veranschaulichung einer Änderung:

<blockquote>Sie stellen fest, dass Sie die Anforderungen des Registrierungsdiensts für Netzwerkgeräte (SCEP) nicht erfüllen. Zudem erfahren Sie, dass die VPN- und WLAN-Profile mit einer Stammzertifizierungsstelle konfiguriert werden können, die dieselben Anforderungen ohne eine SCEP-Implementierung erfüllt.</blockquote>

Möglicherweise gibt es Herausforderungen oder Probleme, die technische Hilfe oder eine spezielle Problembehandlung während des Test- und Überprüfungsprozesses erfordern. Es wird empfohlen, dass Sie sich an die Microsoft-Supportkanäle wenden.

-   [Informationen zum Erhalten von Intune-Support](get-support.md)

-   [Kontaktieren des telefonischen Supports für Microsoft Intune](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a>Test zur Funktionsüberprüfung

Bei der Funktionsüberprüfung werden die einzelnen Komponenten und die Konfiguration getestet, um deren ordnungsgemäße Funktionsweise zu überprüfen. Ein Beispiel für einen Überprüfungstest ist in der folgenden Tabelle aufgeführt.

![Abschnitt 9 Tabelle 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a>Test zur Anwendungsfallüberprüfung

Führen Sie Tests zur Anwendungsfallüberprüfung aus, um sicherzustellen, dass die Szenarios vollständig und funktionsfähig sind. Es gibt zwei Arten von Anwendungsszenarios: IT-Administrator und Endbenutzer.

### <a name="it-admin"></a>IT-Administrator

Führen Sie Überprüfungstests für IT-Administratoren aus, um sicherzustellen, dass administrative Aktionen für ein Gerät oder einen Benutzer ordnungsgemäß funktionieren. Es folgt ein Beispiel für ein umfassendes Überprüfungsszenario für IT-Administratoren.

![Abschnitt 9 Tabelle 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a>Endbenutzer

Führen Sie Überprüfungstests für Endbenutzer aus, um sicherzustellen, dass das Endbenutzererlebnis den Erwartungen entspricht und in der gesamten Benutzerkommunikation korrekt dargestellt wird. Es ist wichtig, zu überprüfen, dass die Endbenutzererfahrung richtig ist. Wenn Sie dies nicht überprüfen können, kann dies zu einer niedrigen Akzeptanz und höheren Volumen an Helpdesk-Aufrufen führen.

![Abschnitt 9 Tabelle 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie Ihre Intune-Funktionen und -Anwendungsszenarios getestet und überprüft haben, sind Sie für den [Intune-Rollout in die Produktion](planning-guide-rollout-plan.md) bereit.

Weitere Planungsvorlagen und Informationen finden Sie in den [zusätzlichen Ressourcen](planning-guide-resources.md).
