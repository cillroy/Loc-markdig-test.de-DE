---
title: Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien (Windows Information Protection) in Intune
titlesuffix: Azure portal
description: Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien in Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab0456b58704f17d3dc5885ab5ae6b902c9ef152
ms.sourcegitcommit: dc2595bec05206a826cd10cb834bf6043145c917
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a>Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien (Windows Information Protection) in Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Ab Version Intune 1704 können Sie bei Windows 10 App-Schutzrichtlinien zum Schutz von Apps ohne Registrierung verwenden.

## <a name="before-you-begin"></a>Vorbereitung

Sprechen Sie wir über einige Konzepte, wenn Sie eine WIP-Richtlinie hinzufügen.

### <a name="list-of-allowed-and-exempt-apps"></a>Liste der zulässigen und ausgenommenen Apps

-   **Zulässige Apps:** Dies sind die Apps, die dieser Richtlinie entsprechen müssen.

-   **Ausgenommene Apps:** Diese Apps sind von dieser Richtlinie ausgenommen und können ohne Einschränkungen auf Unternehmensdaten zugreifen.

### <a name="types-of-apps"></a>App-Typen

-   **Empfohlene Apps:** Eine vorab aufgefüllte Liste von Apps (hauptsächlich Microsoft Office), die Ihnen einen einfachen Import in die Richtlinie ermöglicht. <!---I really don't know what you mean by "easily import into policy"--->

-   **Store-Apps:** Sie können der Richtlinie eine beliebige App aus dem Windows Store hinzufügen.

-   **Windows Desktop-Apps:** Sie haben außerdem die Möglichkeit,der Richtlinie traditionelle Windows Desktop-Apps hinzufügen (z.B. .exe, .dll, usw.)

## <a name="pre-requisites"></a>Voraussetzungen

Sie müssen den MAM-Anbieter konfigurieren, bevor Sie eine WIP-App-Schutzrichtlinie erstellen können. Weitere Informationen finden Sie unter [Konfigurieren Ihres MAM-Anbieters in Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).

Darüber hinaus benötigen Sie Folgendes:

-   [Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)-Lizenz
-   [Windows Creators Update](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> WIP unterstützt nicht mehrere Identitäten; nur jeweils eine verwaltete Identität darf vorhanden sein.
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a>Hinzufügen einer WIP-Richtlinie

Nachdem Sie in Ihrer Organisation Intune eingerichtet haben, können Sie eine WIP-spezifische Richtlinie durch das [Azure-Portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) erstellen. <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  Wechseln Sie zum **Intune-Dashboard für die mobile Anwendungsverwaltung**, wählen Sie **Alle Einstellungen** und anschließend **App-Richtlinie** aus.

2.  Wählen Sie auf dem Blatt **App-Richtlinie** die Option **Richtlinie hinzufügen** aus und geben Sie folgende Werte ein:

    a.  **Name:** Geben Sie einen Namen (Pflichtfeld) für Ihre neue Richtlinie ein.

    b.  **Beschreibung:** Geben Sie eine optionale Beschreibung ein.

    c.  **Plattform:** Wählen Sie **Windows 10** als unterstützte Plattform für Ihre App-Schutzrichtlinie aus.

    d.  **Registrierungsstatus:** Wählen Sie **Ohne Registrierung** als Registrierungsstatus für Ihre Richtlinie aus.

3.  Wählen Sie **Erstellen** aus. Die Richtlinie wird erstellt und in der Tabelle auf dem Blatt **App-Richtlinie** angezeigt.

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a>So fügen Sie empfohlene Apps zur Liste der zulässigen Apps hinzu

1.  Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und anschließend die Option **Zulässige Apps** auf dem Blatt **Richtlinie hinzufügen** aus. Das Blatt **Zulässige Apps** wird geöffnet, auf dem alle Apps angezeigt werden, die bereits in der Liste für diese App-Schutzrichtlinie enthalten sind.

2.  Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps hinzufügen** aus. Das Blatt **Apps hinzufügen** wird geöffnet, auf dem alle zu dieser Liste gehörenden Apps angezeigt werden.

3.  Wählen Sie alle Apps aus, die auf Ihre Unternehmensdaten zugreifen dürfen, und wählen Sie dann **OK** aus. Das Blatt **Zulässige Apps** wird aktualisiert und zeigt alle ausgewählten Apps an.

## <a name="add-a-store-app-to-your-allowed-apps-list"></a>Hinzufügen einer Store-App zur Liste der zulässigen Apps

**Hinzufügen eine Store-App**

1.  Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und im angezeigten Menü **Zulässige Apps** aus. Daraufhin werden alle Apps angezeigt, die bereits in der Liste für diese App-Schutzrichtlinie enthalten sind.

2.  Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps hinzufügen** aus.

3.  Wählen Sie auf dem Blatt **Apps hinzufügen** die Option **Store-Apps** aus der Dropdownliste aus. Auf dem Blatt werden dann Felder angezeigt, mit denen Sie einen **Herausgeber** und App-**Namen** hinzufügen können.

4.  Geben Sie den Namen der App und des jeweiligen Herausgebers ein und wählen Sie dann **OK** aus.

    > [!TIP]
    > Im Folgenden wird ein Beispiel für eine App gezeigt: Der **Herausgeber** ist dabei *CN = Microsoft Corporation, O = Microsoft Corporation, L = Redmond, S = Washington, C = US* und der **Name** des Produkts lautet *Microsoft.MicrosoftAppForWindows*.

5.  Nachdem Sie die Informationen in die Felder eingegeben haben, wählen Sie **OK** aus, um die App zur Liste **Zulässige Apps** hinzuzufügen.

> [!NOTE]
> Um mehrere Store-Apps gleichzeitig hinzuzufügen, können Sie auf das Menü **(...)** am Ende der App-Zeile klicken. Anschließend können Sie weitere Apps hinzufügen. Wenn Sie fertig sind, wählen Sie **OK** aus.

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a>Hinzufügen einer Desktop-App zur Liste der zulässigen Apps

**So fügen Sie eine Desktop-App hinzu**

1.  Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und anschließend die Option **Zulässige Apps** aus. Das Blatt **Zulässige Apps** wird geöffnet, auf dem alle Apps angezeigt werden, die bereits in der Liste für diese App-Schutzrichtlinie enthalten sind.

2.  Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps hinzufügen** aus.

3.  Wählen Sie auf dem Blatt **Apps hinzufügen** die Option **Desktop-Apps** aus der Dropdownliste aus.

4.  Nachdem Sie die Informationen in die Felder eingegeben haben, wählen Sie **OK** aus, um die App zur Liste **Zulässige Apps** hinzuzufügen.

> [!NOTE]
> Um mehrere **Desktop-Apps** gleichzeitig hinzuzufügen, können Sie auf das Menü **(...)** am Ende der App-Zeile klicken. Anschließend können Sie weitere Apps hinzufügen. Wenn Sie fertig sind, wählen Sie **OK** aus.

## <a name="wip-learning"></a>WIP Learning
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
Nachdem Sie die Apps hinzugefügt haben, die durch WIP geschützt werden sollen, müssen Sie mittels **WIP Learning** einen Schutzmodus anwenden.

### <a name="before-you-begin"></a>Vorbereitung

WIP Learning ist ein Bericht, mit dem Sie Ihre WIP unbekannten Apps überwachen können. Unbekannte Apps sind Apps, die nicht von der IT-Abteilung Ihrer Organisation bereitgestellt wurden. Sie können diese Apps vor der Erzwingung von WIP im Modus „Blockieren“ über den Bericht exportieren und zu Ihren WIP-Richtlinien hinzufügen, um Produktivitätseinbußen zu verhindern.

Es wird empfohlen, mit **Automatisch** oder **Außerkraftsetzungen zulassen** zu beginnen und bei einer kleinen Gruppe zu überprüfen, ob die Liste der zulässigen Apps die richtigen Apps enthält. Wenn Sie fertig sind, können Sie Ihre endgültige Erzwingungsrichtlinie in **Blockieren** ändern.

### <a name="what-are-the-protection-modes"></a>Was sind Schutzmodi?

#### <a name="block"></a>Blockieren
WIP prüft auf ungeeignete Datenfreigabeverfahren und hindert den Benutzer an der Durchführung der Aktion. Dies kann die Freigabe von Informationen über nicht geschützte Unternehmens-Apps hinweg sowie die Freigabe von Unternehmensdaten zwischen anderen Personen und Geräten außerhalb Ihrer Organisation einschließen.

#### <a name="allow-overrides"></a>Außerkraftsetzungen zulassen
WIP prüft auf ungeeignete Datenfreigabeverfahren, bei dem Benutzer gewarnt werden, wenn sie einen potenziell unsicheren Vorgang durchführen. In diesem Modus können Benutzer jedoch die Richtlinie überschreiben und die Daten freigeben. Die Aktion wird dabei in Ihrem Überwachungsprotokoll protokolliert.

#### <a name="silent"></a>Automatisch
WIP wird automatisch ausgeführt, wobei ungeeignete Datenfreigabeverfahren protokolliert werden. Dabei werden im Modus „Außerkraftsetzungen zulassen“ keine Vorgänge blockiert, die zu einer Mitarbeiterinteraktion auffordern würden. Unzulässige Aktionen wie bei Apps, die unzulässigerweise versuchen, auf eine Netzwerkressource oder auf WIP-geschützte Daten zuzugreifen, werden trotzdem angehalten.

#### <a name="off-not-recommended"></a>Inaktiv (nicht empfohlen)
WIP ist deaktiviert und unterstützt nicht beim Schutz oder der Überwachung Ihrer Daten.

Nachdem Sie WIP deaktiviert haben, wird versucht, WIP-getaggte Dateien auf den lokalen Laufwerken zu entschlüsseln. Denken Sie daran, dass Ihre vorherigen Informationen zu Entschlüsselungen und Richtlinien nicht automatisch erneut angewendet werden, wenn Sie den WIP-Schutz wieder aktivieren.

### <a name="add-a-protection-mode"></a>Hinzufügen eines Schutzmodus

1.  Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und anschließend die Option **Erforderliche Einstellungen** aus.

    ![Screenshot des Learning-Modus](./media/learning-mode-sc1.png)

1.  Wählen Sie **Speichern** aus.

### <a name="use-wip-learning"></a>Verwenden von WIP Learning

1. Öffnen Sie das Azure-Portal. Wählen Sie **Weitere Dienste** aus. Geben Sie **Intune** in das Filtertextfeld ein.

3. Klicken Sie auf **Intune** > **Mobile Apps**.

4. Klicken Sie anschließend auf **Status des App-Schutzes** > **Berichte** > **Windows Information Protection-Tutorial**.  
 
    Wenn dann die Apps im WIP Learning-Protokollierungsbericht angezeigt werden, können Sie sie zu Ihren App-Schutzrichtlinien hinzufügen.

## <a name="deploy-your-wip-app-protection-policy"></a>Bereitstellen der WIP-App-Schutzrichtlinie

> [!IMPORTANT]
> Dies gilt für WIP ohne Geräteregistrierung.

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

Nachdem Sie Ihre WIP-App-Schutzrichtlinie erstellt haben, müssen Sie sie Ihrer Organisation über MAM bereitstellen.

1.  Wählen Sie auf dem Blatt **App-Richtlinie** die neu erstellte App-Schutzrichtlinie aus. Wählen Sie anschließend **Benutzergruppen** > **Benutzergruppe hinzufügen** aus.

    Auf dem Blatt **Benutzergruppe hinzufügen** wird eine Liste von Benutzergruppen geöffnet, die aus allen Sicherheitsgruppen in Azure Active Directory besteht.

1.  Wählen Sie die Gruppe aus, auf die Ihre Richtlinie angewendet werden soll, und klicken Sie dann auf **Auswählen**, um die Richtlinie bereitzustellen.
