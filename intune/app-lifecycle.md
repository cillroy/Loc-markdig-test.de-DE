---
title: "Übersicht über den App-Lebenszyklus für Intune"
description: "Informationen zum Lebenszyklus von durch Intune verwalteten Apps – vom Hinzufügen bis zu ihrer endgültigen Deaktivierung."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60347012-bc3f-4b9a-a4f4-6d3c5021a6e6
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a08ff917de1029abefa1598a69dd668f1bf4dafe
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="overview-of-the-app-lifecycle"></a>Übersicht über den App-Lebenszyklus

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Der Intune-Lebenszyklus von Apps beginnt, wenn eine App hinzugefügt wird, und durchläuft weitere Phasen, bis Sie die App entfernen.

![Der App-Lebenszyklus](./media/app-lifecycle.png "Der Intune-App-Lebenszyklus")

## <a name="add"></a>Hinzufügen

Der erste Schritt bei der App-Bereitstellung besteht darin, die Apps, die Sie verwalten und zuweisen möchten, zu Intune hinzuzufügen. Sie können zwar mit vielen verschiedenen App-Typen arbeiten, aber die grundlegenden Verfahren sind identisch. Intune ermöglicht das Hinzufügen von Apps sowohl für [registrierte Geräte](apps-add.md) ([klassisches Portal](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)) als auch für [Windows-PCs, die Sie mit der Intune-Clientsoftware verwalten](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune).

## <a name="deploy"></a>Bereitstellen

Nachdem Sie die App in Intune hinzugefügt haben, können Sie sie [auf den verwalteten Geräten bereitstellen](apps-deploy.md) ([klassisches Portal](/intune-classic/deploy-use/deploy-apps)). Intune vereinfacht diesen Vorgang, und nachdem die App bereitgestellt wurde, können Sie den [Erfolg der Bereitstellung über die Intune-Verwaltungskonsole überwachen](apps-monitor.md) ([klassisches Portal](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune)). Darüber hinaus können Sie in einigen App-Stores, wie z.B. dem [Apple](vpp-apps-ios.md) ([klassisches Portal](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)) und dem [Windows](windows-store-for-business.md) App Store ([klassisches Portal](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)), in großem Umfang App-Lizenzen für Ihr Unternehmen erwerben. Intune kann Daten mit diesen Stores synchronisieren, sodass Sie die Bereitstellung und Verfolgung der Lizenznutzung für diese Typen von Apps direkt von der Intune-Verwaltungskonsole aus bereitstellen und verfolgen können.

## <a name="configure"></a>Konfigurieren

Im Rahmen des App-Lebenszyklus werden regelmäßig neue Versionen von Apps veröffentlicht. Intune bietet Tools, mit denen Sie die bereitgestellten Apps ([klassisches Portal](/intune-classic/deploy-use/update-apps-using-microsoft-intune)) leicht auf eine neuere Version [aktualisieren können](apps-add.md). Darüber hinaus können Sie für einige Apps zusätzliche Funktionalität konfigurieren, zum Beispiel:
- Mit [iOS-App-Konfigurationsrichtlinien](app-configuration-policies-use-ios.md) ([klassisches Portal](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)) können Sie Einstellungen für kompatible iOS-Apps angeben, die bei Ausführung der App verwendet werden. Eine App kann beispielsweise bestimmte Brandingeinstellungen oder den Namen eines Servers für die Verbindungsherstellung abfragen.
- [Verwaltete Browserrichtlinien](app-configuration-managed-browser.md) ([klassisches Portal](/intune-classic/deploy-use/manage-internet-access-using-managed-browser-policies)) helfen Ihnen beim Konfigurieren von Einstellungen für den Intune Managed Browser, der den Standardbrowser für das Gerät ersetzt und Ihnen das Einschränken der Websites ermöglicht, die die Benutzer besuchen können.

## <a name="protect"></a>Schützen

Intune bietet Ihnen viele Möglichkeiten zum Schutz der Daten in Ihren Apps. Die wichtigsten Methoden sind:
- Der [bedingte Zugriff](conditional-access.md) ([klassisches Portal](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)) steuert den Zugriff auf E-Mails und andere Dienste basierend auf Bedingungen, die Sie festlegen. Bedingungen sind z.B. Gerätetypen oder die Einhaltung einer von Ihnen bereitgestellten [Gerätekompatibilitätsrichtlinie](device-compliance.md) ([klassisches Portal](/intune-classic/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)).
- [App-Schutzrichtlinien](app-protection-policy.md) ([klassisches Portal](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)) arbeiten mit einzelnen Apps, mit denen Sie die von diesen Apps verwendeten Unternehmensdaten schützen können. Beispielsweise können Sie das Kopieren von Daten zwischen nicht verwalteten Apps und von Ihnen verwalteten Apps einschränken, oder Sie können die Ausführung von Apps auf Geräten verhindern, die per Jailbreak oder Rooting manipuliert wurden.

## <a name="retire"></a>Außerkraftsetzen

Letztlich ist es wahrscheinlich, dass von Ihnen bereitgestellte Apps irgendwann nicht mehr aktuell sind und entfernt werden müssen. Intune vereinfacht die [Außerbetriebnahme von Apps](device-management.md) ([klassisches Portal](/intune-classic/deploy-use/retire-apps-using-microsoft-intune)).
