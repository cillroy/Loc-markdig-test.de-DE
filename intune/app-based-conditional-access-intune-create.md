---
title: "App-basierte Richtlinie für bedingten Zugriff mit Intune"
description: "In diesem Thema wird beschrieben, wie Sie eine App-basierte Richtlinie für bedingten Zugriff mit Intune konfigurieren können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 88db3730be62a9b481d924b4f09b70be775cb067
ms.sourcegitcommit: 4dc5bed94cc965a54eacac2d87fb2d49c9300c3a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2017
---
# <a name="set-up-app-based-conditional-access-policies"></a>Einrichten App-basierter Richtlinien für bedingten Zugriff

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema enthält Anweisungen zum Einrichten App-basierter Richtlinien für bedingten Zugriff für Apps, die in der Liste der genehmigten Apps aufgeführt sind. Die Liste der genehmigten Apps enthält Apps, die von Microsoft getestet wurden.

> [!IMPORTANT]
> Dieses Thema führt durch die Schritte zum Hinzufügen einer App-basierten Richtlinie für bedingten Zugriff mit Exchange Online. Sie können dieselben Schritte aber auch beim Hinzufügen anderer Apps aus der Liste der genehmigten Apps wie SharePoint Online, Microsoft Teams usw. verwenden.

## <a name="to-create-an-app-based-conditional-access-policy"></a>So erstellen Sie eine App-basierte bedingte Zugriffsrichtlinie
1.  Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.

2.  Wählen Sie **Weitere Dienste** aus, und geben Sie „Intune“ ein.

3.  Wählen Sie **Intune-Schutz für Apps** aus.

4.  Wählen Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** **Alle Einstellungen** aus.

5.  Wählen Sie im Abschnitt **Bedingter Zugriff** **Exchange Online** aus.

    ![Screenshot des Blatts „Einstellungen“, das den Abschnitt „Bedingter Zugriff“ anzeigt, wobei die Option „Exchange Online“ hervorgehoben ist](./media/MAM-conditional-access-1.png)

6. Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Allow apps that support Intune app policies** (Apps zulassen, die Intune-App-Richtlinien unterstützen), um nur Apps zuzulassen, die von Intune-App-Schutzrichtlinien unterstützt werden, damit sie auf Exchange Online zugreifen können. Wenn Sie diese Option auswählen, wird die Liste der unterstützten Apps angezeigt.

    > [!NOTE]
    > Alle E-Mail-Clients von Exchange Active Sync, einschließlich der integrierten E-Mail-Clients unter iOS und Android, die eine Verbindung mit Exchange Online herstellen, werden daran gehindert, E-Mails zu senden oder zu empfangen. Benutzer erhalten stattdessen eine einzige E-Mail, die sie darüber informiert, dass sie die Outlook-E-Mail-App verwenden müssen.

7. Um diese Richtlinie auf Benutzer anzuwenden, öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und wählen Sie **Benutzergruppe hinzufügen** aus. Wählen Sie mindestens eine Benutzergruppe aus, auf die diese Richtlinie angewendet werden soll.

    ![Screenshot des Blatts „Eingeschränkte Benutzergruppen“ mit hervorgehobener Option „Benutzergruppe hinzufügen“](./media/mam-ca-add-user-group.png)

8. Möglicherweise möchten Sie, dass einige Benutzer in der Benutzergruppe, die Sie im vorherigen Schritt ausgewählt haben, nicht von dieser Richtlinie betroffen sind. In solchen Fällen fügen Sie die Gruppe der Benutzer der Liste der ausgenommenen Benutzergruppen hinzu. Wählen Sie auf dem Blatt **Exchange Online** **Exempted user groups** (Ausgenommene Benutzergruppen) aus. Wählen Sie **Benutzergruppe hinzufügen** aus, um die Liste der Benutzergruppen zu öffnen. Wählen Sie die Gruppen aus, die Sie von dieser Richtlinie ausnehmen möchten.

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a>So ändern oder löschen Sie Benutzergruppen einer vorhandenen App-basierten bedingten Zugriffsrichtlinie

1. Öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und markieren Sie die Benutzergruppe, die Sie löschen möchten.
2. Klicken Sie auf die Auslassungspunkte, um die Optionen für den Löschvorgang anzuzeigen.
3. Wählen Sie **Löschen** aus, um die Benutzergruppe aus der Liste zu entfernen.

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a>Erstellen von App-basierten Richtlinien für den bedingten Zugriff in der Azure AD-Workload

Ab Intune-Release 1708 können IT-Administratoren App-basierte Richtlinien für den bedingten Zugriff über die Azure AD-Workload erstellen. Dies bietet Ihnen den Komfort, nicht zwischen den Azure- und Intune-Workloads hin und her wechseln zu müssen.

> [!IMPORTANT]
> Sie benötigen eine Azure AD Premium-Lizenz, um im Azure-Portal für Intune Azure AD-Richtlinien für den bedingten Zugriff zu erstellen.

### <a name="to-create-an-app-based-conditional-access-policy"></a>So erstellen Sie eine App-basierte bedingte Zugriffsrichtlinie

> [!IMPORTANT]
> Bevor Sie App-basierte Richtlinien für den bedingten Zugriff verwenden, müssen Sie Ihren Apps [Intune-App-Schutzrichtlinien](app-protection-policies.md) zugewiesen haben.

1. Wählen Sie auf dem **Intune-Dashboard** die Option **Bedingter Zugriff** aus.

2. Wählen Sie auf dem Blatt **Richtlinien** **Neue Richtlinie** aus, um die neue App-basierte Richtlinie für den bedingten Zugriff zu erstellen.

4. Sobald Sie einen Richtliniennamen eingegeben haben und die verfügbaren Einstellungen im Abschnitt **Zuweisungen** konfiguriert haben, wählen Sie im Abschnitt **Zugriffskontrollen** **Gewähren** aus.

5. Klicken Sie auf **Genehmigte Client-App erforderlich (Vorschau)**, **Auswählen** und dann auf **OK**, um die neue Richtlinie zu speichern.

## <a name="next-steps"></a>Nächste Schritte
[Blockieren von Apps, die über keine moderne Authentifizierung verfügen](app-modern-authentication-block.md)

### <a name="see-also"></a>Weitere Informationen:

[Erstellen und Zuweisen von App-Schutzrichtlinien](app-protection-policies.md)
[Bedingter Zugriff im klassischen Azure-Portal](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
