---
title: "Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie mit Intune"
titlesuffix: Azure portal
description: "Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie in Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e9b1a3dc42a9c18d61fc9b55d5a7b71f00c3e29
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a>Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie (MTD) mit Intune

> [!NOTE] 
> Dieses Thema gilt für alle Mobile Threat Defense-Partner.

Intune mit MTD hilft Ihnen dabei, Bedrohungen zu erkennen und Risiken auf mobilen Geräten zu bewerten. Sie können eine Regel für eine Intune-Gerätekompatibilitätsrichtlinie erstellen, mit der das Risiko bewertet wird, um zu ermitteln, ob das Gerät kompatibel ist oder nicht. Anschließend können Sie eine Richtlinie für bedingten Zugriff verwenden, um den Zugriff auf Dienste basierend auf der Gerätekompatibilität zu gewähren oder zu blockieren.

## <a name="before-you-begin"></a>Vorbereitung

Beim Einrichten von MTD haben Sie in der MTD-Partnerkonsole eine Richtlinie erstellt, die verschiedene Bedrohungen als hoch, mittel und niedrig klassifiziert. Nun müssen Sie Mobile Threat Defense-Stufe in der Intune-Gerätekompatibilitätsrichtlinie festlegen.

Voraussetzungen für die Gerätekompatibilitätsrichtlinie mit MTD:

-   Einrichten der MTD-Integration in Intune

## <a name="to-create-a-mtd-device-compliance-policy"></a>So erstellen Sie eine MTD-Gerätekompatibilitätsrichtlinie

1.  Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit Ihren Intune-Anmeldeinformationen an.

2.  Wählen Sie im **Azure-Dashboard** im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld **Intune** ein.

3.  Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird geöffnet.

4. Wählen Sie im **Intune-Dashboard** **Gerätekompatibilität** und dann im Abschnitt **Verwalten** die Option **Richtlinien** aus.

5.  Wählen Sie **Richtlinie erstellen** aus, geben Sie den **Namen** und die **Beschreibung** der Gerätekompatibilität ein, wählen Sie die **Plattform** aus, und wählen Sie dann **Konfigurieren** im Abschnitt **Einstellungen** aus.

6.  Wählen Sie auf dem Blatt **Kompatibilitätsrichtlinie** **Geräteintegrität** aus.

7.  Wählen Sie auf dem Blatt **Geräteintegrität** die Mobile Threat-Stufe aus der Dropdownliste unter **Require the device to be at or under the Mobile threat Defense Level** (Fordern Sie, dass das Gerät maximal auf dieser Mobile Threat Defense-Stufe ist) aus.

    a.  **Geschützt**: Dies ist die sicherste Einstellung. Solange auf einem Gerät Bedrohungen vorhanden sind, ist kein Zugriff auf Unternehmensressourcen möglich. Wenn Bedrohungen gefunden werden, wird das Gerät als nicht kompatibel bewertet.

    b.  **Niedrig**: Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Stufe vorliegen. Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.

    c.  **Mittel**: Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind. Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.

    d.  **Hoch**: Dies ist die am wenigsten sichere Option. Sie lässt alle Bedrohungsstufen zu und verwendet Mobile Threat Defense nur zu Berichtszwecken. Auf Geräten muss mit dieser Einstellung die MTD-App aktiviert sein.

8.  Klicken Sie zweimal auf **OK**, und wählen Sie dann **Erstellen** aus.

> [!IMPORTANT]
> Wenn Sie für Office 365 oder andere Dienste Richtlinien für den bedingten Zugriff erstellen, wird die Kompatibilitätsbewertung ausgewertet, und auf nicht kompatiblen Geräten wird der Zugriff auf Unternehmensressourcen gesperrt, bis die Bedrohung auf dem Gerät beseitigt ist.

## <a name="to-assign-a-mtd-device-compliance-policy"></a>So weisen Sie eine MTD-Gerätekompatibilitätsrichtlinie zu

Wählen Sie zum Zuweisen einer Gerätekompatibilitätsrichtlinie zu Benutzern eine Richtlinie aus, die Sie zuvor konfiguriert haben. Vorhandene Richtlinien finden Sie auf dem Blatt **Gerätekompatibilitätsrichtlinien**.

1. Wählen Sie die Richtlinie, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus. Damit öffnen Sie das Blatt, auf dem Sie **Azure Active Directory-Sicherheitsgruppen** auswählen und der Richtlinie zuweisen können.

2. Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen.  Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.

    > [!NOTE] 
    > Sie haben die Richtlinie auf Benutzer angewendet. Die von den Benutzern, denen die Richtlinie zugewiesen wurde, verwendeten Geräte werden auf Konformität überprüft.

## <a name="next-steps"></a>Nächste Schritte

- [Aktivieren von Mobile Threat Defense in Intune](mtd-connector-enable.md)