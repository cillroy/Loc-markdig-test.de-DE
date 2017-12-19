---
title: "So erstellen Sie eine Konformitätsrichtlinie für iOS"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie eine Konformitätsrichtlinie für iOS-Geräte erstellen.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3cfb8222-d05b-49e3-ae6f-36ce1a16c61d
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3b0fdb06b072c325d30b3e5ee72f1982c5f61849
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-create-a-device-compliance-policy-for-ios-devices-in-intune"></a>Erstellen einer Gerätekonformitätsrichtlinie für iOS-Geräte in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Konformitätsrichtlinien werden für jede Plattform erstellt.  Sie können eine Konformitätsrichtlinie im Azure-Portal erstellen. Weitere Informationen dazu, was eine Konformitätsrichtlinie ist, finden Sie unter dem Thema [Was ist Gerätekonformität](device-compliance.md). Weitere Informationen zu den Voraussetzungen für das Erstellen einer Konformitätsrichtlinie finden Sie unter dem Thema [Erste Schritte mit der Gerätekonformität](device-compliance-get-started.md).

In der Tabelle unten wird beschrieben, wie nicht konforme Einstellungen verwaltet werden, wenn eine Konformitätsrichtlinie mit einer Richtlinie für bedingten Zugriff verwendet wird.

-------------------------------


| **Richtlinieneinstellung** | **iOS 8.0 und höher** |
| --- | --- |
| **PIN- oder Kennwortkonfiguration** | Wiederhergestellt |   
| **Geräteverschlüsselung** | Wiederhergestellt (durch Festlegen der PIN) |
| **Per Jailbreak oder Rootzugriff manipuliertes Gerät** | Unter Quarantäne gestellt (keine Einstellung)
| **E-Mail-Profil** | Isoliert |
|**Minimale Version des Betriebssystems** | Isoliert |
| **Maximale Version des Betriebssystems** | Isoliert |  
| **Windows-Integritätsnachweis** | Nicht verfügbar |  
----------------------------


**Wiederhergestellt** = Das Betriebssystem des Geräts erzwingt die Kompatibilität. (Beispiel: Der Benutzer ist gezwungen, eine PIN festzulegen.)

**Isoliert** = Das Betriebssystem des Geräts erzwingt keine Kompatibilität. (Beispiel: Android-Geräte zwingen den Benutzer nicht, das Gerät zu verschlüsseln.) Wenn die Geräte nicht kompatibel sind, erfolgen die folgenden Aktionen:

- Das Gerät wird blockiert, wenn eine Richtlinie für bedingten Zugriff für den Benutzer gilt.
- Das Unternehmensportal benachrichtigt den Benutzer über Kompatibilitätsprobleme.

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Erstellen einer Konformitätsrichtlinie im Azure-Portal

1. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekompatibilität festlegen** aus. Wählen Sie unter **Verwalten** die Option **Alle Gerätekonformitätsrichtlinien** und dann **Erstellen** aus.
2. Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie die Plattform aus, auf die Sie diese Richtlinie anwenden möchten.
3. Wählen **Kompatibilitätsanforderungen** aus, um hier die Einstellungen **Sicherheit**, **Geräteintegrität** und **Geräteeigenschaft** anzugeben. Wählen Sie abschließend **OK** aus.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** blade, choose **Add** to create a new action.  The action parameters blade allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
7. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Zuweisen von Benutzergruppen

Wählen Sie zum Zuweisen einer Konformitätsrichtlinie zu Benutzern eine Richtlinie aus, die Sie konfiguriert haben. Vorhandene Richtlinien finden Sie auf dem Blatt **Kompatibilitätsrichtlinien**.

1. Wählen Sie die Richtlinie, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus. Damit öffnen Sie das Blatt, auf dem Sie **Azure Active Directory-Sicherheitsgruppen** auswählen und der Richtlinie zuweisen können.
2. Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen.  Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.

Sie haben die Richtlinie auf Benutzer angewendet.  Die von den Benutzern, denen die Richtlinie zugewiesen wurde, verwendeten Geräte werden auf Konformität überprüft.

<!---## Compliance policy settings--->

## <a name="system-security-settings"></a>Einstellungen für die Systemsicherheit

### <a name="password"></a>Kennwort

- **Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie **Ja** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können. iOS-Geräte mit Kennwort sind verschlüsselt.
- **Einfache Kennwörter zulassen:** Legen Sie **Ja** fest, damit Benutzer einfache Kennwörter wie **1234** oder **1111** erstellen können.
- **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Kennwort enthalten muss.
- **Erforderlicher Kennworttyp:** Geben Sie an, ob der Benutzer ein **alphanumerisches** oder ein **numerisches** Kennwort erstellen muss.
- **Minimale Anzahl von Zeichensätzen:** Wenn Sie **Erforderlicher Kennworttyp** auf **Alphanumerisch** festlegen, gibt diese Einstellung die Mindestanzahl von Zeichensätzen an, die das Kennwort enthalten muss. Es gibt vier Zeichensätze:
  - Kleinbuchstaben
  - Großbuchstaben
  - Symbole
  - Zahlen

Wenn Sie eine höhere Anzahl festlegen, muss der Benutzer ein komplexeres Kennwort erstellen.

Bei iOS-Geräten bezieht sich diese Einstellung auf die Anzahl von Sonderzeichen (z.B. **!** , **#**, **&amp;**), die im Kennwort enthalten sein müssen.

- **Minuten Inaktivität vor erneuter Anforderung des Kennworts:** Geben Sie die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.
- **Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen aus, bevor das Kennwort abläuft und ein neues erstellt werden muss.
- **Kennwortverlauf speichern:** Verwenden Sie diese Einstellung in Verbindung mit **Wiederverwendung vorheriger Kennwörter verhindern**, um zu verhindern, dass der Benutzer zuvor bereits verwendete Kennwörter erstellt.
- **Wiederverwendung vorheriger Kennwörter verhindern:** Wenn Sie **Kennwortverlauf speichern** aktiviert haben, geben Sie die Anzahl der zuvor verwendeten Kennwörter ein, die nicht erneut verwendet werden dürfen.
- **Kennworteingabe verlangen, wenn das Gerät aus dem Leerlauf zurückkehrt:** Verwenden Sie diese Einstellung zusammen mit der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts**. Der Benutzer wird zur Eingabe eines Kennworts aufgefordert, um auf ein Gerät zugreifen zu können, das für die in der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** angegebene Zeit inaktiv war.

### <a name="email-profile"></a>E-Mail-Profil

- **E-Mail-Konto muss von Intune verwaltet werden:** Wenn diese Option auf **Ja** festgelegt ist, muss das Gerät das auf dem Gerät bereitgestellte E-Mail-Profil verwenden. Das Gerät wird in den folgenden Situationen als nicht kompatibel betrachtet:
  - Das E-Mail-Profil wird für eine andere Benutzergruppe bereitgestellt als die Benutzergruppe, auf die die Kompatibilitätsrichtlinie ausgerichtet ist.
  - Der Benutzer hat bereits ein E-Mail-Konto auf dem Gerät eingerichtet, das dem Intune-E-Mail-Profil entspricht, das auf dem Gerät bereitgestellt wurde. Intune kann das vom Benutzer bereitgestellte Profil nicht überschreiben und daher nicht verwalten. Zum Sicherstellen der Kompatibilität muss der Benutzer die vorhandenen E-Mail-Einstellungen entfernen. Anschließend kann Intune das verwaltete E-Mail-Profil installieren.
- **Wählen Sie das E-Mail-Profil aus, das von Intune verwaltet werden muss:** Wenn die Einstellung **E-Mail-Konto muss von Intune verwaltet werden** aktiviert ist, wählen Sie **Auswählen** aus, um das Intune-E-Mail-Profil anzugeben. Das E-Mail-Profil muss auf dem Gerät vorhanden sein.

Weitere Informationen zu E-Mail-Profilen finden Sie unter [Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune).

## <a name="device-health-settings"></a>Einstellungen für die Geräteintegrität

- **Gerät darf keinen Jailbreak oder Rootzugriff verwenden:** Wenn Sie diese Einstellung aktivieren, sind Geräte mit Jailbreak nicht konform.

## <a name="device-properties"></a>Geräteeigenschaften

- **Minimal erforderliches Betriebssystem:** Wenn ein Gerät die Anforderungen an die erforderliche Mindestversion des Betriebssystems nicht erfüllt, wird es als nicht konform gemeldet. Ein Link mit Informationen zum Upgradevorgang wird angezeigt. Der Benutzer kann sein Gerät aktualisieren. Danach kann er auf Unternehmensressourcen zugreifen.
- **Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
