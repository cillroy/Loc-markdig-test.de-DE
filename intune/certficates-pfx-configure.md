---
title: Konfigurieren und Verwalten von PKCS-Zertifikaten mit Intune
titleSuffix: Intune on Azure
description: "Erstellen und weisen Sie PKCS-Zertifikate mit Intune zu.“"
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2731ba102c6a10fa417f43f8f2cd359204f51cbe
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a>Konfigurieren und Verwalten von PKCS-Zertifikaten mit Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a>Anforderungen

Um PKCS-Zertifikate mit Intune zu verwenden, müssen Sie über folgende Infrastruktur verfügen:

* Eine vorhandene konfigurierte AD DS-Domäne (Active Directory Domain Services).
 
  Weitere Informationen zur Installation und Konfiguration von AD DS finden Sie im Artikel [AD DS-Entwurf und Planung](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).

* Eine vorhandene konfigurierte Unternehmenszertifizierungsstelle.

  Weitere Informationen zum Installieren und Konfigurieren von Active Directory-Zertifikatdiensten (AD CS) finden Sie im Artikel [Schrittweise Anleitung zu den Windows Server Active Directory-Zertifikatdiensten](https://technet.microsoft.com/library/cc772393).

  > [!WARNING]
  > Für Intune müssen AD CS mit einer Unternehmenszertifizierungsstelle, nicht mit einer eigenständigen Zertifizierungsstelle ausgeführt werden.

* Ein Client mit Konnektivität zur Unternehmenszertifizierungsstelle.
* Eine exportierte Kopie Ihres Stammzertifikats aus Ihrer Unternehmenszertifizierungsstelle.
* Der Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) muss aus dem Intune-Portal heruntergeladen worden sein.
* Eine verfügbare Windows Server-Instanz zum Hosten des Microsoft Intune Certificate Connectors (NDESConnectorSetup.exe).

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a>Exportieren des Stammzertifikats aus der Unternehmenszertifizierungsstelle

Sie benötigen auf jedem Gerät ein Zertifikat einer Stamm- oder Zwischenzertifizierungsstelle für die Authentifizierung bei VPN, WLAN und anderen Ressourcen. Die folgenden Schritte erläutern, wie das erforderliche Zertifikat von Ihrer Unternehmenszertifizierungsstelle abgerufen wird.

1. Melden Sie sich bei Ihrer Unternehmenszertifizierungsstelle mit einem Konto an, das über Administratorrechte verfügt.
2. Öffnen Sie eine Eingabeaufforderung als Administrator.
3. Exportieren Sie das Zertifikat der Stammzertifizierungsstelle an einen Speicherort, an dem Sie später darauf zugreifen können.

   Beispiel:

4. Nach Abschluss des Assistenten, jedoch vor dem Schließen des Assistenten, klicken Sie auf **Zertifikatconnector-Benutzeroberfläche starten**.

   `certutil -ca.cert certnew.cer`

   Weitere Informationen finden Sie unter [Certutil-Tasks zum Verwalten von Zertifikaten](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).

## <a name="configure-certificate-templates-on-the-certification-authority"></a>Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle

1. Melden Sie sich bei Ihrer Unternehmenszertifizierungsstelle mit einem Konto an, das über Administratorrechte verfügt.
2. Öffnen Sie die Konsole der **Zertifizierungsstelle**.
3. Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, und wählen Sie **Verwalten**.
4. Suchen Sie die Zertifikatvorlage **Benutzer**, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Vorlage duplizieren**. Das Fenster **Eigenschaften der neuen Vorlage** wird geöffnet.
5. Auf der Registerkarte **Kompatibilität**:
   * Legen Sie **Zertifizierungsstelle** auf **Windows Server 2008 R2** fest.
   * Legen Sie **Zertifizierungsstelle** auf **Windows 7/Server 2008 R2** fest.
6. Auf der Registerkarte **Allgemein** :
   * Legen Sie für **Vorlagenanzeigename** einen für Sie aussagekräftigen Namen fest.

   > [!WARNING]
   > **Vorlagenname** entspricht standardmäßig dem **Vorlagenanzeigenamen** *ohne Leerzeichen*. Notieren Sie sich den Vorlagennamen zur späteren Verwendung.

7. Aktivieren Sie auf der Registerkarte **Anforderungsverarbeitung** das Kontrollkästchen **Exportieren von privatem Schlüssel zulassen**.
8. Bestätigen Sie auf der Registerkarte **Kryptografie**, dass die **Minimale Schlüsselgröße** auf 2048 festgelegt ist.
9. Wählen Sie auf der Registerkarte **Antragstellername** das Optionsfeld **Informationen werden in der Anforderung angegeben**.
10. Überprüfen Sie auf der Registerkarte **Erweiterungen**, dass „Verschlüsselndes Dateisystem“, „Sichere E-Mail“ und „Clientauthentifizierung“ unter **Anwendungsrichtlinien** angezeigt werden.
    
      > [!IMPORTANT]
      > Bearbeiten Sie für iOS- und macOS-Zertifikatvorlagen auf der Registerkarte **Erweiterungen** die Option **Schlüsselverwendung**, und stellen Sie sicher, dass die Option **Signatur ist Ursprungsnachweis** nicht aktiviert ist.

11. Fügen Sie auf der Registerkarte **Sicherheit** das Computerkonto für den Server hinzu, auf dem Sie den Microsoft Intune Certificate Connector installieren.
    * Weisen Sie diesem Konto die Berechtigungen **Lesen** und **Registrieren** zu.
12. Klicken Sie auf **Anwenden**, und klicken Sie dann auf **OK**, um die Zertifikatvorlage zu speichern.
13. Schließen Sie die **Zertifikatvorlagenkonsole**.
14. Klicken Sie in der Konsole der **Zertifizierungsstelle** mit der rechten Maustaste auf **Zertifikatvorlagen**, und klicken Sie dann auf **Neu** und auf **Auszustellende Zertifikatvorlage**.
    * Wählen Sie die Vorlage, die Sie in den vorherigen Schritten erstellt haben, und klicken Sie auf **OK**.
15. Gehen Sie folgendermaßen vor, damit der Server Zertifikate im Namen von bei Intune registrierten Geräten und Benutzern verwaltet:

    ein. Klicken Sie mit der rechten Maustaste auf die Zertifizierungsstelle, und wählen Sie **Eigenschaften**.

    b. Fügen Sie auf der Registerkarte „Sicherheit“ das Computerkonto des Servers hinzu, auf dem Sie den Microsoft Intune Certificate Connector ausführen.
      * Erteilen Sie dem Computerkonto die Zulassungsberechtigungen **Zertifikate ausstellen und verwalten** und **Zertifikate anfordern**.
16. Melden Sie sich von der Unternehmenszertifizierungsstelle ab.

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a>Laden Sie den Microsoft Intune Certificate Connector herunter, und installieren und konfigurieren Sie ihn.

![ConnectorDownload][ConnectorDownload]

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung + Verwaltung** > **Intune** aus.
2. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus. 
3. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Zertifizierungsstelle** aus. 
4. Klicken Sie auf **Hinzufügen** und dann auf **Connectordatei herunterladen**. Speichern Sie den Download an einem Speicherort, auf den Sie auf dem Server, auf dem der Connector installiert wird, zugreifen können. 
5.  Melden Sie sich bei dem Server an, auf dem Sie den Microsoft Intune Certificate Connector installieren möchten.
6.  Führen Sie das Installationsprogramm aus, und übernehmen Sie den Standardspeicherort. Der Connector wird unter „C:\Programme\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe“ installiert.
    1. Wählen Sie auf der Seite mit den Optionen des Installationsprogramms **PFX-Verteilung** aus, und klicken Sie auf **Weiter**.
    2. Klicken Sie auf **Installieren**, und warten Sie auf den Abschluss der Installation.
    3. Aktivieren Sie auf der Seite zur Fertigstellung das Kontrollkästchen mit der Bezeichnung **Intune-Connector starten**, und klicken Sie auf **Fertig stellen**.
7.  Das Fensters des NDES-Connectors wird jetzt mit der Registerkarte **Registrierung** geöffnet. Um die Verbindung mit Intune zu aktivieren, klicken Sie auf **Anmelden** und geben ein Konto mit Administratorrechten an.
8.  Auf der Registerkarte **Erweitert** können Sie das Optionsfeld **Konto "SYSTEM" dieses Computers verwenden (Standard)** ausgewählt lassen.
9.  Klicken Sie auf **Anwenden** und dann auf **Schließen**.
10. Wechseln Sie zurück zum Azure-Portal. Unter **Intune** > **Gerätekonfiguration** > **Zertifizierungsstelle** werden Ihnen nach einigen Minuten ein grünes Häkchen und das Wort **Aktiv** unter **Verbindungsstatus** angezeigt. Anhand dieser Bestätigung können Sie erkennen, dass der Connector-Server mit Intune kommunizieren kann.


## <a name="create-a-device-configuration-profile"></a>Erstellen eines Gerätekonfigurationsprofils

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Navigieren Sie zu **Intune** > **Gerätekonfiguration** > **Profile**, und klicken Sie auf **Profil erstellen**.

   ![NavigateIntune][NavigateIntune]

3. Geben Sie die folgenden Informationen ein:
   * **Name** für das Profil
   * Optional eine Beschreibung
   * **Plattform**, auf der das Profil bereitgestellt werden soll
   * Für **Profiltyp** die Option **Vertrauenswürdiges Zertifikat**
4. Navigieren Sie zu **Einstellungen**, und geben Sie die zuvor exportierte CER-Datei mit dem Zertifikat der Stammzertifizierungsstelle an.

   > [!NOTE]
   > Abhängig von der in **Schritt 3** ausgewählten Plattform besitzen Sie möglicherweise die Option zum Auswählen des **Zielspeichers** für das Zertifikat.

   ![ProfileSettings][ProfileSettings]

5. Klicken Sie auf **OK** und dann auf **Erstellen**, um Ihr Profil zu speichern.
6. Informationen zum Zuweisen des neuen Profils zu einem oder mehreren Geräten finden Sie unter [Zuweisen von Microsoft Intune-Geräteprofilen](device-profile-assign.md).

## <a name="create-a-pkcs-certificate-profile"></a>Erstellen eines PKCS-Zertifikatprofils

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Navigieren Sie zu **Intune** > **Gerätekonfiguration** > **Profile**, und klicken Sie auf **Profil erstellen**.
3. Geben Sie die folgenden Informationen ein:
   * **Name** für das Profil
   * Optional eine Beschreibung
   * **Plattform**, auf der das Profil bereitgestellt werden soll
   * Für **Profiltyp** die Option **PKCS-Zertifikat**
4. Wechseln Sie zu **Einstellungen**, und geben Sie die folgenden Informationen an:
   * **Erneuerungsschwellenwert (%)**: Empfohlen wird ein Wert von 20 %.
   * **Gültigkeitsdauer des Zertifikats**: Wenn Sie die Zertifikatvorlage nicht geändert haben, ist diese Option auf ein Jahr festgelegt.
   * **Zertifizierungsstelle**: Diese Option ist der interne vollqualifizierte Domänenname (FQDN) Ihrer Unternehmenszertifizierungsstelle.
   * **Name der Zertifizierungsstelle**: Diese Option ist der Name Ihrer Unternehmenszertifizierungsstelle, der sich ggf. vom vorherigen Element unterscheidet.
   * **Name der Zertifikatvorlage**: Diese Option ist der Name der zuvor erstellten Vorlage. Beachten Sie, dass der **Vorlagenname** standardmäßig dem **Vorlagenanzeigenamen** *ohne Leerzeichen* entspricht.
   * **Format des Antragstellernamens**: Legen Sie diese Option auf **Allgemeiner Name** fest, sofern kein anderes Format erforderlich ist.
   * **Alternativer Antragstellername**: Legen Sie diese Option auf **Benutzerprinzipalname (UPN)** fest, sofern nichts anderes erforderlich ist.
   * **Erweiterte Schlüsselverwendung**: Sofern Sie im vorherigen Abschnitt, **Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle**, in Schritt 10 die Standardeinstellungen verwendet haben, fügen Sie aus dem Auswahlfeld die folgenden **vordefinierten Werte** hinzu:
      * **Verwendung für beliebigen Zweck**
      * **Clientauthentifizierung**
      * **Sichere E-Mail**
   * **Stammzertifikat** (für Android-Profile): Diese Option ist die CER-Datei, die in Schritt 3 im vorherigen Abschnitt [Exportieren des Stammzertifikats aus der Unternehmenszertifizierungsstelle](#export-the-root-certificate-from-the-enterprise-ca) exportiert wurde.

5. Klicken Sie auf **OK** und dann auf **Erstellen**, um Ihr Profil zu speichern.
6. Informationen zum Zuweisen des neuen Profils zu einem oder mehreren Geräten finden Sie im Artikel [Zuweisen von Microsoft Intune-Geräteprofilen](device-profile-assign.md).


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Im Azure-Portal zu Intune navigieren und ein neues Profil für ein vertrauenswürdiges Zertifikat erstellen"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Profil erstellen und ein vertrauenswürdiges Zertifikat hochladen"
[ConnectorDownload]: ./media/certificates-download-connector.png "Certificate Connector aus dem Azure-Portal herunterladen"  
