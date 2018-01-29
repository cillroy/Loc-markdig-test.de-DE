---
title: "Remote-Sperren von verwalteten Geräten durch Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie die von Ihnen verwalteten Geräte mit Intune remote sperren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d31b042c17c18bf087786cccd3e408720bc420ca
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="remotely-lock-managed-devices-with-intune"></a>Remote-Sperren von verwalteten Geräten durch Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mit der Geräteaktion **Remote sperren** wird das ausgewählte Gerät gesperrt. Der Eigentümer des Geräts muss zum Entsperren seine Kennung verwenden. Sie können nur Remotesperrungen von Geräten durchführen, für die eine PIN oder ein Kennwort festgelegt wurde.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone – Unterstützt auf Windows Phone 8.1 und später
- iOS – Unterstützt
- macOs – Unterstützt

    > [!Note]  
    > Legen Sie eine Wiederherstellungs-PIN mit 6 Ziffern fest. Wenn das Gerät gesperrt ist, wird im Blatt **Device overview** (Geräteübersicht) die PIN solange angezeigt, bis eine andere Geräteaktion gesendet wurde.
- Android – Unterstützung

## <a name="how-to-remote-lock-a-device"></a>So sperren Sie ein Gerät aus der Ferne

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Remote sperren**.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.
