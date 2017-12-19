---
title: "So erstellen Sie eine Konformitätsrichtlinie für macOS"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie eine Konformitätsrichtlinie für macOS-Geräte erstellen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0444183e-f924-4605-96a8-48fdfbc58fd1
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3cf085ff2ee4668ea4c14718719c466bcb982b10
ms.sourcegitcommit: d4623cbfe296ae370c3d88c3213fffbda255e474
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2017
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>Erstellen einer Gerätekonformitätsrichtlinie für macOS-Geräte in Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a>Vorbereitung

Bevor Sie eine Gerätekonformitätsrichtlinie erstellen und zuweisen, überprüfen Sie die Konzepte für die Intune-Gerätekonformitätsrichtlinie.

- Weitere Informationen über Gerätekonformitätsrichtlinien finden Sie unter [Erste Schritte bei der Gerätekonformität in Intune](device-compliance.md).

> [!IMPORTANT]
> Sie müssen Gerätekonformitätsrichtlinien für jede Plattform erstellen. Gerätekonformitätsrichtlinien-Einstellungen für Intune hängen von den Plattformfunktionen ab, die über das MDM-Protokoll bereitgestellte Einstellungen sind.

In der Tabelle unten wird beschrieben, wie nicht konforme Einstellungen verwaltet werden, wenn eine Konformitätsrichtlinie mit einer Richtlinie für bedingten Zugriff verwendet wird.

-------------------------------


| **Richtlinieneinstellung** | **macOS 10.11 und höher** |
| --- | --- |
| **PIN- oder Kennwortkonfiguration** | Wiederhergestellt |   
| **Geräteverschlüsselung** | Wiederhergestellt (durch Festlegen der PIN) |
| **E-Mail-Profil** | Isoliert |
|**Minimale Version des Betriebssystems** | Isoliert |
| **Maximale Version des Betriebssystems** | Isoliert |  
| **Windows-Integritätsnachweis** | Nicht verfügbar |  
----------------------------


**Wiederhergestellt** = Das Betriebssystem des Geräts erzwingt die Kompatibilität. (Beispiel: Der Benutzer ist gezwungen, eine PIN festzulegen.)

**Isoliert** = Das Betriebssystem des Geräts erzwingt keine Kompatibilität. (Beispiel: Android-Geräte zwingen den Benutzer nicht, das Gerät zu verschlüsseln.) Wenn die Geräte nicht kompatibel sind, erfolgen die folgenden Aktionen:

- Das Gerät wird blockiert, wenn eine Richtlinie für bedingten Zugriff für den Benutzer gilt.
- Das Unternehmensportal benachrichtigt den Benutzer über Kompatibilitätsprobleme.

## <a name="macos-compliance-policy-settings"></a>Einstellungen für die MacOS-Konformitätsrichtlinie

Sie haben verschiedene Kategorien mit unterschiedlichen Einstellungen, aus denen Sie wählen können, wenn Sie eine neue Gerätekompatibilität mit Intune erstellen.

- Geräteintegrität

- Geräteeigenschaften

- Systemsicherheit

### <a name="device-health"></a>Geräteintegrität

- **Ein Systemintegritätsschutz ist vonnöten**: Legen Sie dies auf **Erforderlich** fest, um zu überprüfen, ob Ihre macOS-Geräte den Systemintegritätsschutz aktiviert haben.

### <a name="device-properties"></a>Geräteeigenschaften

- **Minimale Betriebssystemversion:** Wenn ein Gerät die Anforderungen an die erforderliche Mindestversion des Betriebssystems nicht erfüllt, wird es als nicht konform gemeldet. Ein Link mit Informationen zum Upgradevorgang wird angezeigt. Der Benutzer kann sein Gerät aktualisieren. Danach kann er auf Unternehmensressourcen zugreifen.

- **Maximale Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.

### <a name="system-security-settings"></a>Einstellungen für die Systemsicherheit

#### <a name="password"></a>Kennwort

- **Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie für diese Einstellung auf **Erforderlich** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.

- **Einfache Kennwörter:** Legen Sie **Blockieren** fest, damit Benutzer keine einfache Kennwörter wie **1234** oder **1111** erstellen können.

- **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Kennwort enthalten muss.

- **Kennworttyp:** Geben Sie an, ob der Benutzer ein **alphanumerisches** oder ein **numerisches** Kennwort erstellen muss.

- **Anzahl von nicht-alphabetischen Zeichen im Kennwort:** Wenn Sie **Erforderlicher Kennworttyp** auf **Alphanumerisch** festlegen, gibt diese Einstellung die Mindestanzahl von Zeichensätzen an, die das Kennwort enthalten muss. 

    > [!NOTE]
    > Wenn Sie eine höhere Anzahl festlegen, muss der Benutzer ein komplexeres Kennwort erstellen.

    > [!IMPORTANT]
    > Bei macOS-Geräten bezieht sich diese Einstellung auf die Anzahl von Sonderzeichen (z.B. **!** , **#**, **&amp;**), die im Kennwort enthalten sein müssen.

- **Maximale Anzahl von Minuten der Inaktivität vor erneuter Anforderung des Kennworts:** Geben Sie die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.

- **Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen aus (zwischen 1 und 250), bevor das Kennwort abläuft und ein neues erstellt werden muss.

- **Anzahl der vorherigen Kennwörter zur Verhinderung von Wiederverwendung:**: Geben Sie die Anzahl von vorherigen Kennwörtern an, die nicht erneut verwendet werden dürfen.

    > [!IMPORTANT]
    > Wenn die Kennwortanforderung auf einem macOS-Gerät geändert wird, werden die Änderungen erst wirksam, bis der Benutzer sein Kennwort ändert. Wenn Sie beispielsweise die Längeneinschränkung des Kennworts auf acht Ziffern festlegen, und das macOS-Gerät derzeit ein Kennwort mit sechs Ziffern besitzt, bleibt das Gerät kompatibel, bis der Benutzer das nächste Mal das Kennwort auf dem Gerät ändert.

## <a name="to-create-a-device-compliance-policy"></a>So erstellen Sie eine Gerätekompatibilitätsrichtlinie

1. Melden Sie sich im [Azure-Portal](https://portal.azure.com) mit Ihren Intune-Anmeldeinformationen an.

2. Sobald Sie erfolgreich angemeldet sind, wird das **Azure-Dashboard** angezeigt.

3. Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.

4. Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird angezeigt.

5. Wählen Sie **Gerätekompatibilität** aus, dann **Richtlinien** unter **Verwaltung**.

6. Wählen Sie **Richtlinie erstellen** aus.

7. Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie die Plattform aus, auf die Sie diese Richtlinie anwenden möchten.

8. Das Blatt **macOS-Konformitätsrichtlinie** wird geöffnet. Wählen Sie die Kategorien der Konformitätsrichtlinieneinstellung **Sicherheit**, **Geräteintegrität** und **Geräteeigenschaften** aus, um Ihre Einstellungen anzugeben.

10. Sobald Sie mit der Auswahl Ihrer Einstellungen fertig sind, klicken Sie unter jeder Kategorie der Konformitätsrichtlinieneinstellung auf **OK**.

11. Wählen Sie **OK** und dann **Erstellen** aus.

## <a name="assign-user-groups"></a>Zuweisen von Benutzergruppen

Wählen Sie zum Zuweisen einer Konformitätsrichtlinie zu Benutzern eine Richtlinie aus, die Sie konfiguriert haben. Vorhandene Richtlinien finden Sie auf dem Blatt **Kompatibilitätsrichtlinien**.

1. Wählen Sie die Gerätekonformitätsrichtlinie aus, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus. Damit öffnen Sie das Blatt, auf dem Sie **Azure Active Directory-Sicherheitsgruppen** auswählen und der Richtlinie zuweisen können.

2. Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen.

3. Wählen Sie **Auswählen** und dann **Speichern** aus, um die Gerätekonformitätsrichtlinie den Azure AD-Sicherheitsgruppen zuzuweisen.

4. Sobald Sie mit der Zuweisung der Gerätekonformitätsrichtlinie an Ihre Gruppen fertig sind, können Sie das Blatt **Zuweisungen** schließen.

    > [!TIP]
    > Standardmäßig überprüfen Geräte alle 8 Stunden die Konformität. Benutzer können diesen Prozess jedoch nicht über die Intune-Unternehmensportal-App erzwingen.

## <a name="next-steps"></a>Nächste Schritte

[Überwachen von Intune-Richtlinien zur Gerätekompatibilität](compliance-policy-monitor.md)
