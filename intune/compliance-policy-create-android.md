---
title: "So erstellen Sie eine Konformitätsrichtlinie für Android"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie eine Konformitätsrichtlinie für Android-Geräte erstellen.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 64e16233a9acb021c0a50b32f3eb750125eb0638
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-android-devices-in-intune"></a>Erstellen einer Gerätekonformitätsrichtlinie für Android-Geräte in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Gerätekonformitätsrichtlinien werden für jede Plattform im Intune Azure-Portal erstellt. 

- Weitere Informationen dazu, was eine Konformitätsrichtlinie ist, finden Sie unter dem Thema [Was ist Gerätekonformität](device-compliance.md).
- Weitere Informationen zu den Voraussetzungen für das Erstellen einer Konformitätsrichtlinie finden Sie unter dem Thema [Erste Schritte mit der Gerätekonformität](device-compliance-get-started.md).

## <a name="to-create-a-device-compliance-policy"></a>So erstellen Sie eine Gerätekompatibilitätsrichtlinie

1. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekompatibilität festlegen** aus. Wählen Sie unter **Verwalten** die Option **Alle Gerätekonformitätsrichtlinien** und dann **Erstellen** aus.
2. Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie die Plattform aus, auf die Sie diese Richtlinie anwenden möchten.
3. Wählen **Kompatibilitätsanforderungen** aus, um hier die Einstellungen **Sicherheit**, **Geräteintegrität** und **Geräteeigenschaft** anzugeben. Wählen Sie abschließend **OK** aus.

<!-- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.-->

## <a name="to-assign-user-groups"></a>So weisen Sie Benutzergruppen zu

Wählen Sie zum Zuweisen einer Konformitätsrichtlinie zu Benutzern eine Richtlinie aus, die Sie konfiguriert haben. Vorhandene Richtlinien finden Sie auf dem Blatt **Kompatibilitätsrichtlinien**.

1. Wählen Sie die Richtlinie und dann **Zuweisungen** aus. Damit öffnen Sie das Blatt, auf dem Sie **Azure Active Directory-Sicherheitsgruppen** auswählen und der Richtlinie zuweisen können.
2. Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen. Dies sind die Sicherheitsgruppen in Ihrer Azure Active Directory-Instanz.  Sie können die Benutzergruppen auswählen, auf die diese Richtlinie angewendet werden soll, und dann **Auswählen** auswählen. Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.

Sie haben die Richtlinie auf Benutzer angewendet.  Die von den Benutzern, denen die Richtlinie zugewiesen wurde, verwendeten Geräte werden auf Konformität überprüft.

<!---##  Compliance policy settings--->

## <a name="device-health-and-security-settings"></a>Einstellungen für Geräteintegrität und Sicherheit

- **Gerät darf keinen Jailbreak oder Rootzugriff verwenden:** Wenn Sie diese Einstellung aktivieren, werden Geräte mit Jailbreak als nicht konform eingestuft.
- **Installation von Apps aus unbekannten Quellen muss auf Geräten gesperrt sein (Android 4.0 und höher):** Um Geräte zu blockieren, bei denen die Option **Sicherheit** > **Unbekannte Quellen** aktiviert ist, aktivieren Sie diese Einstellung, und legen Sie sie auf **Ja** fest.

### <a name="important"></a>Wichtig

Das Sideloading von Anwendungen erfordert, dass die Einstellung **Unbekannte Quellen** aktiviert ist. Erzwingen Sie diese Kompatibilitätsrichtlinie nur, wenn Sie kein Sideloading von Android-Apps auf Geräten durchführen.

- **USB-Debuggen muss deaktiviert sein (Android 4.2 und höher)**: Diese Einstellung gibt an, ob die Option für USB-Debuggen auf dem Gerät aktiviert ist.
- **Aktivierung von „Gerät auf Sicherheitsbedrohungen überprüfen“ auf Geräten erforderlich (Android 4.2-4.4)**: Diese Einstellung gibt an, dass die Option **Apps überprüfen** auf dem Gerät aktiviert ist.
- **Niedrigste zulässige Android-Sicherheitspatchebene (Android 6.0 und höher)**: Geben Sie mit dieser Einstellung die niedrigste Android-Patchebene an. Geräte, die nicht mindestens diese Patchebene aufweisen, sind nicht kompatibel. Das Datum muss im folgenden Format angegeben werden: JJJJ-MM-TT.
- **Schutz vor Gerätebedrohungen muss aktiviert sein:** Verwenden Sie diese Einstellung, um die Risikobewertung mit der Lookout MTP-Lösung als Konformitätsvoraussetzung zu fordern. Wählen Sie aus den folgenden Optionen die maximal zulässige Bedrohungsstufe aus:
  - **Keine (geschützt)**: Dies ist die sicherste Einstellung. Dies bedeutet, dass das Gerät keinerlei Bedrohungen unterliegen darf. Wenn auf dem Gerät Bedrohungen jeglicher Stufe erkannt werden, wird es als nicht kompatibel bewertet.
  - **Niedrig:** Das Gerät wird als konform bewertet, wenn nur Bedrohungen auf niedrigen Stufen vorliegen. Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.
  - **Mittel:** Das Gerät wird als konform bewertet, wenn auf dem Gerät Bedrohungen auf niedriger oder mittlerer Stufe gefunden werden. Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.
  - **Hoch:** Dies ist die unsicherste Einstellung. Sie lässt im Wesentlichen alle Bedrohungsstufen zu. Es ist möglicherweise hilfreich, diese Lösung nur zu Meldungszwecken zu verwenden.

Weitere Informationen finden Sie unter [Aktivieren der Regel zum Schutz vor Bedrohungen auf dem Gerät in der Kompatibilitätsrichtlinie](https://docs.microsoft.com/intune-classic/deploy-use/enable-device-threat-protection-rule-in-compliance-policy).

## <a name="system-security-settings"></a>Einstellungen für die Systemsicherheit

### <a name="password"></a>Kennwort

- **Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie für diese Einstellung **Ja** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.
- **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Benutzerkennwort enthalten muss.
- **Kennwortstärke:** Mit dieser Einstellung wird erkannt, ob die von Ihnen angegebenen Kennwortanforderungen auf dem Gerät eingerichtet wurden. Aktivieren Sie diese Einstellung, um festzulegen, dass Benutzer für Android-Geräte bestimmte Kennwortanforderungen erfüllen müssen. Wählen Sie aus:
  - **Biometrie auf niedriger Sicherheitsstufe**
  - **Erforderlich**
  - **Mindestens numerisch**
  - **Mindestens alphabetisch**
  - **Mindestens alphanumerisch**
  - **Alphanumerisch mit Symbolen**
- **Minuten Inaktivität vor erneuter Anforderung des Kennworts:** Geben Sie die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.
- **Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen aus, bevor das Kennwort abläuft und ein neues erstellt werden muss.
- **Kennwortverlauf speichern:** Verwenden Sie diese Einstellung zusammen mit **Wiederverwendung vorheriger Kennwörter verhindern**, um zu verhindern, dass der Benutzer zuvor bereits verwendete Kennwörter erstellt.
- **Wiederverwendung vorheriger Kennwörter verhindern:** Wenn Sie **Kennwortverlauf speichern** aktiviert haben, geben Sie die Anzahl der zuvor verwendeten Kennwörter ein, die nicht erneut verwendet werden dürfen.
- **Kennworteingabe verlangen, wenn das Gerät aus dem Leerlauf zurückkehrt:** Verwenden Sie diese Einstellung zusammen mit der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts**. Der Benutzer wird zur Eingabe eines Kennworts aufgefordert, um auf ein Gerät zugreifen zu können, das für die in der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** angegebene Zeit inaktiv war.

### <a name="encryption"></a>Verschlüsselung

- **Verschlüsselung auf mobilen Geräten erforderlich:** Legen Sie diese Einstellung auf **Ja** fest, damit Geräte verschlüsselt werden müssen, um eine Verbindung mit Ressourcen herzustellen. Wenn Sie die Einstellung **Kennwort zum Entsperren mobiler Geräte erforderlich** auswählen, werden Geräte verschlüsselt.

## <a name="device-property-settings"></a>Einstellungen für Geräteeigenschaften

- **Minimal erforderliches Betriebssystem:** Wenn ein Gerät die Anforderungen an die erforderliche Mindestversion des Betriebssystems nicht erfüllt, wird es als nicht konform gemeldet. Ein Link zur Vorgehensweise zum Upgrade wird angezeigt. Der Benutzer kann ein Upgrade des Geräts durchführen und anschließend auf die Unternehmensressourcen zugreifen.
- **Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regeln geändert werden und die betreffende Betriebssystemversion zugelassen wird.

## <a name="how-non-compliant-settings-work-with-conditional-access-policies"></a>Wie werden nicht kompatible Einstellungen im Zusammenhang mit Richtlinien für bedingten Zugriff gehandhabt?

In der folgenden Tabelle erfahren Sie, wie nicht kompatible Einstellungen verwaltet werden, wenn eine Kompatibilitätsrichtlinie mit einer Richtlinie für bedingten Zugriff verwendet wird.

--------------------

|**Richtlinieneinstellung**| **Android 4.0 und höher, Samsung KNOX Standard 4.0 und höher** |
| --- | ----|
| **PIN- oder Kennwortkonfiguration** |  Isoliert |
| **Geräteverschlüsselung** | Isoliert |
| **Per Jailbreak oder Rootzugriff manipuliertes Gerät** | Unter Quarantäne gestellt (keine Einstellung) |
| **E-Mail-Profil** | Nicht verfügbar |
| **Minimale Version des Betriebssystems** | Isoliert |
| **Maximale Version des Betriebssystems** |   Isoliert |
| **Windows-Integritätsnachweis** | Nicht verfügbar |

--------------------------

**Wiederhergestellt** = Das Betriebssystem des Geräts erzwingt die Kompatibilität. (Beispiel: Der Benutzer ist gezwungen, eine PIN festzulegen.)+

**Isoliert** = Das Betriebssystem des Geräts erzwingt keine Kompatibilität. (Beispiel: Android-Geräte zwingen den Benutzer nicht, das Gerät zu verschlüsseln.) Wenn die Geräte nicht konform sind, erfolgen die folgenden Aktionen:+

- Das Gerät wird blockiert, wenn eine Richtlinie für bedingten Zugriff für den Benutzer gilt.
- Das Unternehmensportal benachrichtigt den Benutzer über Kompatibilitätsprobleme.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
