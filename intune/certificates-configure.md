---
title: Konfigurieren von Zertifikaten mit Intune
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune Zertifikate erstellen und zuweisen, mit denen Sie WLAN-, VPN- und andere Verbindungen sichern können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59bd1afa299620b8b2f1d35a9141cf752d459c07
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a>Konfigurieren von Zertifikaten in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Wenn Sie Benutzern den Zugriff auf Unternehmensressourcen über VPN, WLAN oder E-Mail-Profile gestatten, können Sie diese Verbindungen mit Zertifikaten authentifizieren. Wenn Sie Zertifikate verwenden, ist die Eingabe von Benutzernamen und Kennwörtern zum Authentifizieren von Verbindungen überflüssig.

Mit Intune können Sie diese Zertifikate Geräten zuweisen, die Sie verwalten. Intune unterstützt das Zuweisen und Verwalten dieser Zertifikattypen:

- Simple Certificate Enrollment-Protokoll (SCEP)
- PKCS#12 (oder PFX)

Jeder dieser Zertifikattypen hat eigene Voraussetzungen und Infrastrukturanforderungen.

## <a name="general-workflow"></a>Allgemeiner Workflow

1. Stellen Sie sicher, dass Sie die richtige Zertifikatinfrastruktur eingerichtet haben. Sie können [SCEP-Zertifikate](certificates-scep-configure.md) und [PKCS-Zertifikate](certficates-pfx-configure.md) verwenden.
2. Installieren Sie auf jedem Gerät ein Stammzertifikat oder ein Zertifikat einer Zwischenzertifizierungsstelle, damit das Gerät die Rechtmäßigkeit Ihrer Zertifizierungsstelle erkennt. Erstellen Sie zu diesem Zweck ein **vertrauenswürdiges Zertifikatprofil** und weisen Sie es zu. Wenn Sie dieses Profil zuweisen, wird das Stammzertifikat von den Geräten, die Sie mit Intune verwalten, angefordert und empfangen. Sie müssen für jede Plattform ein eigenes Profil erstellen. Vertrauenswürdige Zertifikatprofile sind für folgende Plattformen verfügbar:
    - iOS 8.0 und höher
    - macOS 10.9 und höher
    - Android 4,0 und höher
    - Android for Work
    - Windows 8.1 und höher
    - Windows Phone 8.1 und höher
    - Windows 10 und höher
3. Erstellen Sie Zertifikatprofile, damit Geräte ein Zertifikat für die Authentifizierung des VPN-, WLAN- und E-Mail-Zugriffs anfordern.

   Sie können ein **PKCS**- oder **SCEP**-Zertifikatprofil für Geräte auf diesen Plattformen erstellen und zuweisen:

   - iOS 8.0 und höher
   - Android 4,0 und höher
   - Android for Work
   - Windows 10 (Desktop und Mobile) und höher

   Für Geräte, die diese Plattformen ausführen, können Sie nur ein **SCEP**-Zertifikatprofil verwenden:

   - macOS 10.9 und höher
   - Windows Phone 8.1 und höher

Sie müssen für jede Geräteplattform ein eigenes Profil erstellen. Nachdem Sie das Profil erstellt haben, ordnen Sie es dem bereits erstellten vertrauenswürdigen Stammzertifikatprofil zu.

### <a name="further-considerations"></a>Weitere Überlegungen

- Wenn Sie über keine Unternehmenszertifizierungsstelle verfügen, müssen Sie eine erstellen.
- Sie müssen auch einen NDES-Server (Network Device Enrollment Service, Registrierungsdienst für Netzwerkgeräte) konfigurieren, wenn Sie SCEP-Profile verwenden.
- Unabhängig davon, ob Sie SCEP- oder PKCS-Profile verwenden möchten, müssen Sie den Microsoft Intune Certificate Connector herunterladen und konfigurieren.


## <a name="step-1-configure-your-certificate-infrastructure"></a>Schritt 1: Konfigurieren der Zertifikatinfrastruktur

Unter den folgenden Themen finden Sie Hilfe zum Konfigurieren der Infrastruktur für jeden Zertifikatprofiltyp:

- [Konfigurieren der Zertifikatinfrastruktur für SCEP in Microsoft Intune](certificates-scep-configure.md)
- [Konfigurieren Ihrer Microsoft Intune-Zertifikatsinfrastruktur für PKCS](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a>Schritt 2: Exportieren des vertrauenswürdigen Zertifikats der Stammzertifizierungsstelle

Exportieren Sie das Zertifikat vertrauenswürdigen Stammzertifizierungsstelle als **CER**-Datei aus der ausstellenden Zertifizierungsstelle oder von einem beliebigen Gerät, das die ausstellende Zertifizierungsstelle als vertrauenswürdig erachtet. Exportieren Sie auf keinen Fall den privaten Schlüssel.

Sie importieren dieses Zertifikat, wenn Sie ein vertrauenswürdiges Zertifikatprofil einrichten.

## <a name="step-3-create-trusted-certificate-profiles"></a>Schritt 3: Erstellen von vertrauenswürdigen Zertifikatprofilen
Sie müssen ein Profil mit einem vertrauenswürdigen Zertifikat erstellen, bevor Sie ein SCEP- oder PKCS-Zertifikatprofil erstellen können. Sie benötigen ein Profil mit einem vertrauenswürdigen Zertifikat und ein SCEP- oder PKCS-Profil für jede Geräteplattform. Der Ablauf des Erstellens vertrauenswürdiger Zertifikate ist für jede Geräteplattform ähnlich.

### <a name="to-create-a-trusted-certificate-profile"></a>So erstellen Sie ein vertrauenswürdiges Zertifikatprofil

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das vertrauenswürdige Zertifikatprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform für das vertrauenswürdige Zertifikat aus. Derzeit können Sie eine der folgenden Plattformen für Zertifikateinstellungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 und höher**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Vertrauenswürdiges Zertifikat** aus.
7. Navigieren Sie zu dem Zertifikat, das Sie in Aufgabe 1 gespeichert haben, und klicken Sie dann auf **OK**.
8. Wählen Sie (nur bei Windows 8.1- und Windows 10-Geräten) den **Zielspeicher** für das vertrauenswürdige Zertifikat aus:
    - **Computerzertifikatspeicher – Stamm**
    - **Computerzertifikatspeicher – Zwischenspeicher**
    - **Benutzerzertifikatspeicher – Zwischenspeicher**
8. Klicken Sie zum Abschluss auf **OK**. Navigieren Sie, wenn Sie fertig sind, zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.


> [!Note]
> Android-Geräte zeigen eine Benachrichtigung an, dass ein Drittanbieter ein vertrauenswürdiges Zertifikat installiert hat.

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a>Schritt 4: Erstellen von SCEP- oder PKCS-Zertifikatprofilen

Unter den folgenden Themen finden Sie Hilfe zum Konfigurieren und Zuweisen jedes Zertifikatprofiltyps:

- [Konfigurieren der Zertifikatinfrastruktur für SCEP in Microsoft Intune](certificates-scep-configure.md)
- [Konfigurieren Ihrer Microsoft Intune-Zertifikatsinfrastruktur für PKCS](certficates-pfx-configure.md)

Nachdem Sie ein Profil des vertrauenswürdigen Zertifikats erstellt haben, erstellen Sie SCEP- oder PKCS-Zertifikatprofile für jede Plattform, die Sie verwenden möchten. Wenn Sie ein SCEP-Zertifikatprofil erstellen, müssen Sie ein vertrauenswürdiges Zertifikatprofil für dieselbe Plattform angeben. Auf diese Weise werden die beiden Zertifikatprofile verknüpft. Sie müssen jedes Profil trotzdem separat zuweisen.


## <a name="next-steps"></a>Nächste Schritte
Allgemeine Informationen zum Zuweisen von Geräteprofilen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).
