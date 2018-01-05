---
title: Erstellen und Bereitstellen von App-Schutzrichtlinien
titleSuffix: Azure portal
description: "Erfahren Sie, wie Intune-App-Schutzrichtlinien dabei helfen, Unternehmensdaten zu schützen, die von den von Ihnen verwalteten Apps verwendet werden.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47b3051e2cdeabd36115f48e0987fd162bdf3b77
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a>Erstellen und Zuweisen von App-Schutzrichtlinien

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Vorbereitung

Wenn Sie nach Anweisungen für das klassische Intune-Portal suchen, finden Sie weitere Informationen unter [Erstellen von App-Schutzrichtlinien](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).

App-Schutzrichtlinien können angewendet werden, unabhängig davon, ob die Geräte, auf denen die Apps ausgeführt werden, von Intune verwaltet werden. Eine ausführlichere Beschreibung der Funktionsweise von App-Schutzrichtlinien und der von Intune-App-Schutzrichtlinien unterstützten Szenarien finden Sie im Thema [Was sind Microsoft Intune-App-Schutzrichtlinien](app-protection-policy.md).

Wenn Sie nach einer Liste der unterstützten MAM-Apps suchen, finden Sie weitere Informationen in der [Liste der MAM-Apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

##  <a name="create-an-app-protection-policy"></a>Erstellen einer App-Schutzrichtlinie
1. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **App-Schutzrichtlinien** aus.

2. Hiermit wird das Blatt **App-Schutzrichtlinien** geöffnet, auf dem Sie neue Richtlinien erstellen und vorhandene bearbeiten können. Wählen Sie **Richtlinie hinzufügen** aus.

   ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/app-protection-add-policy.png)

3. Geben Sie einen Namen für die Richtlinie sowie eine kurze Beschreibung ein, und wählen Sie den Plattformtyp aus, um eine Richtlinie für iOS oder Android zu erstellen. Sie können für jede Plattform mehr als eine Richtlinie erstellen.

4. Wählen Sie **Apps** aus, um das Blatt **Apps** zu öffnen, auf dem eine Liste der verfügbaren Apps angezeigt wird. Wählen Sie eine oder mehrere Apps in der Liste aus, mit denen Sie die von Ihnen zu erstellende Richtlinie verknüpfen möchten. Nachdem Sie die Apps ausgewählt haben, wählen Sie **Auswählen** unten auf dem Blatt **Apps** aus, um Ihre Auswahl zu speichern.

   > [!IMPORTANT]
   > Sie müssen mindestens eine App auswählen, um eine Richtlinie erstellen zu können.

5. Wählen Sie auf dem Blatt **Richtlinie hinzufügen** **Erforderliche Einstellungen konfigurieren** aus, um das Blatt mit den Richtlinieneinstellungen zu öffnen.

   Es gibt zwei Kategorien von Richtlinieneinstellungen: **Datenverlagerung** und **Zugriff**.  Richtlinien für die Datenverlagerung beziehen sich auf die Datenverschiebung in und aus Apps, während mit Zugriffsrichtlinien bestimmt wird, wie der Endbenutzer auf die Apps im beruflichen Kontext zugreift.
   Um Ihnen bei den ersten Schritten zu helfen, enthalten die Richtlinieneinstellung Standardwerte. Sie müssen keine Änderungen vornehmen, wenn die Standardwerte Ihren Anforderungen entsprechen.

   > [!TIP]
   > Diese Richtlinieneinstellungen werden nur durchgesetzt, wenn Apps im beruflichen Kontext verwendet werden.  Wenn der Endbenutzer die App zum Erledigen einer privaten Aufgabe verwendet, ist er von diesen Richtlinien nicht betroffen.



6. Wählen Sie **OK** aus, um diese Konfiguration zu speichern. Damit befinden Sie sich wieder auf dem Blatt **Richtlinie hinzufügen** . Wählen Sie **Erstellen** aus, um die Richtlinie zu erstellen und Ihre Einstellungen zu speichern.


Wenn Sie mit dem Erstellen einer Richtlinie wie im vorherigen Verfahren beschrieben fertig sind, wird sie noch nicht für Benutzer bereitgestellt. Informationen zum Bereitstellen einer Richtlinie finden Sie im Abschnitt „Bereitstellen einer Richtlinie für Benutzer“.

## <a name="deploy-a-policy-to-users"></a>Bereitstellen einer Richtlinie für Benutzer

1. Wählen Sie auf dem Blatt **Richtlinie** **Benutzergruppen** aus. Damit wird das Blatt **Benutzergruppen**geöffnet. Wählen Sie auf dem Blatt **Benutzergruppen** **Benutzergruppe hinzufügen** aus, um das Blatt **Benutzergruppe hinzufügen** zu öffnen.

   ![Screenshot des Blatts „Benutzergruppen“ mit hervorgehobener Menüoption „Benutzergruppe hinzufügen“](./media/app-protection-policy-add-users.png)

2. Auf dem Blatt **Benutzergruppe hinzufügen** wird eine Liste der Benutzergruppen angezeigt. Dies ist eine Liste aller Sicherheitsgruppen in Ihrem **Azure Active Directory**. Wählen Sie die Benutzergruppen aus, auf die diese Richtlinie angewendet werden soll, und anschließend **Auswählen**. Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.
   ![Screenshot des Blatts „Benutzergruppe hinzufügen“ mit der Liste der Azure Active Directory-Benutzer](./media/azure-ad-user-group-list.png)

Damit haben Sie eine Richtlinie erstellt und für die Benutzer bereitgestellt.

Von der Richtlinie sind nur Benutzer betroffen, denen Microsoft Intune-Lizenzen zugewiesen wurden. Benutzer, die sich in der von Ihnen ausgewählten Sicherheitsgruppe befinden und nicht über eine Microsoft Intune-Lizenz verfügen, sind nicht betroffen.

>[!IMPORTANT]
> Wenn Sie Intune mit Configuration Manager verwenden, um Ihre iOS- und Android-Geräte zu verwalten, wird die Richtlinie nur auf Benutzer in der Gruppe angewendet, die Sie ausgewählt haben. Mitglieder untergeordneter Gruppen, die in der ausgewählten Gruppe geschachtelt sind, sind nicht betroffen.

Endbenutzer können die Apps aus dem App Store oder aus Google Play herunterladen. Weitere Informationen finden Sie in folgenden Quellen:
* [Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-android.md)
* [Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a>Ändern vorhandener Richtlinien
Sie können eine vorhandene Richtlinie bearbeiten und sie auf die als Ziel festgelegten Benutzer anwenden. Wenn Sie vorhandene Richtlinien ändern, werden diese Änderungen für Benutzer, die bereits bei der App angemeldet sind, jedoch in den nächsten acht Stunden nicht wirksam.

Um die Auswirkungen der Änderungen sofort zu erfahren, muss der Endbenutzer sich bei der App abmelden und sich dann erneut anmelden.

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a>So ändern Sie die Liste der Apps, die einer Richtlinie zugeordnet sind

1.  Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten. Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.

2.  Wählen Sie auf diesem Richtlinienblatt **Ziel-Apps** aus, um eine Liste der Apps zu öffnen.

3.  Fügen Sie der Liste Apps hinzu, oder entfernen Sie Apps hieraus, und wählen Sie dann das Symbol **Speichern** aus, um die Änderungen zu speichern.

### <a name="to-change-the-list-of-user-groups"></a>So ändern Sie die Liste der Benutzergruppen

1.  Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten. Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.

2.  Wählen Sie auf dem Richtlinienblatt **Benutzergruppen** aus, um das Blatt **Benutzergruppe** zu öffnen, auf dem die Liste der Benutzergruppen angezeigt wird, auf die die Richtlinie gegenwärtig angewendet wird.

3.  Zum Hinzufügen einer neuen Benutzergruppe wählen Sie **Benutzergruppe hinzufügen** und anschließend die Benutzergruppe aus. Wählen Sie **Auswählen** aus, um die Richtlinie für die ausgewählte Gruppe bereitzustellen.

4.  Zum Löschen einer Benutzergruppe markieren Sie die Benutzergruppe, die Sie entfernen möchten. Anschließend wählen Sie die Auslassungspunkte (...) und die Option **Löschen** aus, um die Benutzergruppe zu entfernen.
  ![Screenshot mit Löschoption](./media/app-protection-policy-delete-user.png)

### <a name="to-change-policy-settings"></a>So ändern Sie Richtlinieneinstellungen

1.  Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten. Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.


2.  Wählen Sie **Richtlinieneinstellungen** aus, um das Blatt **Richtlinieneinstellungen** zu öffnen.

3.  Ändern Sie die Einstellungen, und wählen Sie das Symbol **Speichern** aus, um die Änderungen zu speichern.

## <a name="policy-settings"></a>Richtlinieneinstellungen
Eine vollständige Liste der Richtlinieneinstellungen für iOS und Android finden Sie in den folgenden Themen:

- [iOS-Richtlinien](app-protection-policy-settings-ios.md)
- [Android-Richtlinien](app-protection-policy-settings-android.md)

## <a name="next-steps"></a>Nächste Schritte
[Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](app-protection-policies-monitor.md)

### <a name="see-also"></a>Siehe auch
* [Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-android.md)
* [Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-ios.md)
