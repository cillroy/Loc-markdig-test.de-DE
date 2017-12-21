---
title: "Zurücksetzen und Entfernen von Gerätekennungen mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Kennung von Geräten zurücksetzen oder entfernen, die Sie mit Intune verwalten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfa94d11f978bbe4d23b6672423c849e1f061986
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a>Zurücksetzen und Entfernen der Kennung auf von Intune verwalteten Geräten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Begriffe *entfernen* und *zurücksetzen* sind im Kontext dieses Artikels austauschbar.

Durch die Aktion **Kennung entfernen** wird eine neue Kennung für das Gerät generiert, die auf dem Blatt <*Gerätename*> **Übersicht** angezeigt wird.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone – Unterstützt unter Windows Phone 8.1 bis Windows 10 Creators Update nicht in Azure AD eingebunden, Windows 10 Creators Update und höher
- iOS – Unterstützt
- macOS – Nicht unterstützt
- Android– Unterstützt für ältere Versionen vor Android 7. Android for Work wird nicht unterstützt.

## <a name="how-to-reset-a-passcode"></a>So setzen Sie eine Kennung zurück

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Kennung entfernen**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
