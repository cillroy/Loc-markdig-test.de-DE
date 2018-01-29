---
title: "So weisen Sie Geräteprofile mit Intune zu"
titlesuffix: Azure portal
description: "Nachdem Sie ein Intune-Geräteprofil erstellt haben, lesen Sie dieses Thema, um zu erfahren, wie Sie es Geräten zuweisen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 65bef28ab7fac33e37d7f960237bee391a727a81
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a>Zuweisen von Microsoft Intune-Geräteprofilen

## <a name="assign-a-device-profile"></a>Zuweisen eines Geräteprofils

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
1. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
2. Wählen Sie auf dem Blatt mit der Profilliste das Profil, das Sie verwalten möchten, und dann auf dem Blatt <*Profilname*> **Berichte** die Option **Verwalten** > **Zuweisungen** aus.
3. Wählen Sie auf dem nächsten Blatt entweder die Option **Einschließen** (zum Einschließen von Gruppen) oder die Option **Ausschließen** (zum Ausschließen von Gruppen) aus. Wählen Sie anschließend **Gruppen auswählen** aus.
![Einschließen und Ausschließen von Gruppen aus einer Profilzuweisung.](./media/group-include-exclude.png)
4. Wählen Sie auf dem Blatt **Gruppen auswählen** diejenigen Azure AD-Gruppen aus, die Sie in die Zuordnung einschließen oder aus der Zuordnung ausschließen möchten. Sie können **STRG** gedrückt halten, um mehrere Gruppen auswählen.
4. Wenn Sie fertig sind, wählen Sie auf dem Blatt **Gruppen auswählen** die Option **Auswählen** aus.



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a>Ausschließen von Gruppen aus einer Geräteprofilzuweisung

Mit Intune-Gerätekonfigurationsprofilen können Sie Gruppen aus der Richtlinienzuweisung ausschließen. So könnten Sie z.B. der Gruppe **Alle Unternehmensbenutzer** ein Geräteprofil zuweisen und gleichzeitig alle Mitglieder der Gruppe **Oberes Management** ausschließen.

Achten Sie beim Ausschließen von Gruppen aus einer Zuweisung darauf, dass Sie nur Benutzer oder nur Gerätegruppen ausschließen und keine Kombination aus verschiedenen Gruppen. Intune berücksichtigt beim Ausschließen von Gruppen keine Zuweisung eines Benutzers zu einem Gerät. Es ist unwahrscheinlich, dass das Einschließen von Benutzergruppen und gleichzeitige Ausschließen von Gerätegruppen die von Ihnen gewünschten Ergebnisse liefert. Bei einer Kombination aus verschiedenen Gruppen oder bei anderen Konflikten hat die Funktion „Einschließen“ Vorrang vor der Funktion „Ausschließen“.

Beispiel: Sie möchten allen Geräten in Ihrem Unternehmen, mit Ausnahme von Kioskgeräten, ein Geräteprofil zuweisen. Nun schließen Sie die Gruppe **Alle Benutzer** ein und gleichzeitig die Gruppe **Alle Geräte** aus.

In diesem Fall erhalten alle Benutzer und ihre Geräte die Richtlinie, selbst wenn das Gerät des Benutzers der Gruppe **Alle Geräte** angehört. 

Die Ausschließen-Funktion wertet nur direkte Mitglieder der Gruppen aus. Sie beinhaltet keine Geräte, die einem Benutzer zugeordnet sind. Geräte, die keinen Benutzer besitzen, erhalten die Richtlinie dagegen nicht, da sie der Gruppe **Alle Benutzer** nicht zugeordnet sind. 

Wenn Sie **Alle Geräte** einschließen und gleichzeitig **Alle Benutzer** ausschließen, erhalten alle Geräte die Richtlinie. Damit sollten eigentlich alle Geräte mit einem zugeordneten Benutzer von der Richtlinie ausgeschlossen werden. Dies gelingt jedoch nicht, da die Ausschließen-Funktion nur direkte Mitglieder von Gruppen vergleicht. 

>[!Tip]
>Die Ausschließen-Funktion ist für Konformitätsrichtlinien oder App-Zuweisungen derzeit nicht verfügbar. Zum Ausschließen von Mitgliedern aus einer Zuordnung können Sie die Zuweisungsabsichten „Verfügbar“ und „Nicht verfügbar“ verwenden. Beispiel: Sie weisen der Gruppe **Alle Unternehmensbenutzer** eine App mit der Zuweisungsabsicht **Verfügbar** zu sowie der Gruppe **Oberes Management** mit der Zuweisungsabsicht **Nicht verfügbar**. Die App ist nun allen Benutzern *außer* den Benutzern der Gruppe **Oberes Management** zugewiesen. Weisen Sie die App hingegen der Gruppe **Alle Unternehmensbenutzer** mit der Zuweisungsabsicht **Erforderlich** zu, werden die Benutzer der Gruppe **Oberes Management** nicht ausgeschlossen.
 
    
## <a name="next-steps"></a>Nächste Schritte
Weitere Informationen zum Überwachen der Zuweisungen von Geräteprofilen finden Sie unter [Überwachen von Geräteprofilen](device-profile-monitor.md).
