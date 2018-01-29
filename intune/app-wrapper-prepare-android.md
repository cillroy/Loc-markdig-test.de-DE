---
title: "Umschließen von Android-Apps mit dem Intune App Wrapping Tool"
description: "In diesem Artikel erfahren Sie, wie Sie Ihre Android-Apps umschließen, ohne den Code der App selbst zu ändern. Bereiten Sie die Apps vor, damit Sie Verwaltungsrichtlinien für mobile Apps anwenden können."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 04b67c4f0771a5c2dc55c39f221a1f96757e2caa
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a>Vorbereiten von Android-Apps für App-Schutzrichtlinien mit dem Intune App Wrapping Tool

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Verwenden Sie das Microsoft Intune App Wrapping Tool für Android zum Ändern des Verhaltens Ihrer internen Android-Apps, indem Sie die Features der App einschränken, ohne den eigentlichen Code der App zu ändern.

Das Tool ist eine Windows-Befehlszeilenanwendung, die in PowerShell ausgeführt wird und einen Wrapper um die Android-App erstellt. Nachdem der Wrapper um die App erstellt wurde, können Sie die App-Funktionalität ändern, indem Sie in Intune [Verwaltungsrichtlinien für mobile Anwendungen](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) konfigurieren.


Lesen Sie vor dem Ausführen des Tools die [Sicherheitsüberlegungen für das Ausführen des App Wrapping Tools](#security-considerations-for-running-the-app-wrapping-tool). Sie können das Tool von der GitHub-Seite [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) herunterladen.



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a>Erfüllen der Voraussetzungen zur Verwendung des App Wrapping Tools

-   Sie müssen das App Wrapping Tool auf einem Windows-Computer unter Windows 7 oder höher ausführen.

-   Die Eingabe-App muss ein gültiges Android-Anwendungspaket mit der Dateierweiterung „APK“ sein und folgende Kriterien aufweisen:

    -   Darf nicht verschlüsselt sein.
    -   Darf nicht zuvor bereits vom Intune App Wrapping Tool umschlossen worden sein.
    -   Muss für Android 4.0 oder höher geschrieben sein.

-   Die App muss von Ihrem oder für Ihr Unternehmen entwickelt werden. Sie können dieses Tool nicht für aus dem Google Play Store heruntergeladene Apps verwenden.

-   Um das App Wrapping Tool auszuführen, müssen Sie die neueste Version der [Java Runtime Environment](http://java.com/download/) installieren und sicherstellen, dass die Java-Pfadvariable in den Windows-Umgebungsvariablen auf C:\ProgramData\Oracle\Java\javapath festgelegt wurde. Weitere Informationen finden Sie in der [Java-Dokumentation](http://java.com/download/help/).

    > [!NOTE]
    > In einigen Fällen kann die 32-Bit-Version von Java zu Speicherproblemen führen. Es ist eine gute Idee, die 64-Bit-Version zu installieren.

- Für Android müssen alle App-Pakete (APK-Dateien) signiert sein. Informationen zum **Wiederverwenden** vorhandener Zertifikate und für allgemeine Anleitungen für Signaturzertifikate finden Sie unter [Wiederverwendung von Signaturzertifikaten und Umschließen von Apps](https://docs.microsoft.com/en-us/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps). Das ausführbare Java-Tool „keytool.exe“ wird zum Generieren **neuer** Anmeldeinformationen verwendet, die zum Signieren der umschlossenen Ausgabe-App erforderlich sind. Kennwörter, die festgelegt werden, müssen sicher sein. Notieren Sie sich diese Kennwörter jedoch, denn sie werden benötigt, um das App Wrapping Tool auszuführen.

## <a name="install-the-app-wrapping-tool"></a>Installieren des App Wrapping Tools

1.  Laden Sie die Installationsdatei „InstallAWT.exe“ für das Intune App Wrapping Tool für Android aus dem [GitHub-Repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) auf einen Windows-Computer herunter. Öffnen Sie die Installationsdatei.

2.  Akzeptieren Sie den Lizenzvertrag, und schließen Sie die Installation ab.

Merken Sie sich den Ordner, in dem Sie das Tool installieren. Der Standardspeicherort lautet: C:\Programme (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.

## <a name="run-the-app-wrapping-tool"></a>Ausführen des App Wrapping Tools

1. Öffnen Sie auf dem Windows-Computer, auf dem Sie das App Wrapping Tool installiert haben, ein PowerShell-Fenster.

2. Importieren Sie das PowerShell-Modul des App Wrapping Tools aus dem Ordner, in dem Sie das Tool installiert haben:

   ```
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. Führen Sie das Tool mit dem Befehl **invoke-AppWrappingTool** aus, der die folgende Verwendungssyntax aufweist:
   ```
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   Die folgende Tabelle führt die Eigenschaften des Befehls **invoke-AppWrappingTool** auf:

|Eigenschaft|Informationen|Beispiel|
|-------------|--------------------|---------|
|**-InputPath**&lt;String&gt;|Pfad der Android-Quelle-App (.apk).| |
|**-OutputPath**&lt;String&gt;|Pfad zur Android-Ausgabe-App. Ist dies der gleiche Verzeichnispfad wie InputPath, schlägt das Verpacken fehl.| |
|**-KeyStorePath**&lt;String&gt;|Pfad zur Keystoredatei, die das öffentliche/private Schlüsselpaar zum Signieren enthält.|Standardmäßig werden Keystoredateien unter „C:\Programme (x86)\Java\jreX.X.X_XX\bin“ gespeichert. |
|**-KeyStorePassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des KeyStore. Für Android müssen alle Anwendungspakete (APK-Dateien) signiert sein. Verwenden Sie das Java-Keytool, um das KeyStorePassword zu generieren. Weitere Informationen über den Java-[Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) finden Sie hier.| |
|**-KeyAlias**&lt;String&gt;|Der Name des Schlüssels, der zum Signieren verwendet werden soll.| |
|**-KeyPassword**&lt;SecureString&gt;|Das Kennwort zum Entschlüsseln des privaten Schlüssels, der zum Signieren verwendet wird.| |
|**-SigAlg**&lt;SecureString&gt;| (Optional) Der Name des Signaturalgorithmus, der zum Signieren verwendet werden soll. Der Algorithmus muss mit dem privaten Schlüssel kompatibel sein.|Beispiele: SHA256withRSA, SHA1withRSA|
| **&lt;CommonParameters&gt;** | (Optional) Der Befehl unterstützt allgemeine PowerShell-Parameter, wie z.B. „verbose“ und „debug“. |


- Eine Liste der allgemeinen Parameter finden Sie im [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).

- Um ausführliche Informationen zu dem Tool zu erhalten, geben Sie folgenden Befehl ein:

    ```
    Help Invoke-AppWrappingTool
    ```

**Beispiel:**

Importieren Sie das PowerShell-Modul.
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
Führen Sie das App Wrapping Tool in der nativen App „HelloWorld.apk“ aus.
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

Sie werden zur Eingabe von **KeyStorePassword** und **KeyPassword**aufgefordert. Geben Sie die Anmeldeinformationen ein, die Sie zum Erstellen der Keystore-Datei verwendet haben.

Es wird sowohl die umschlossene App als auch eine Protokolldatei generiert und in dem von Ihnen angegebenen Ausgabepfad gespeichert.

## <a name="reusing-signing-certificates-and-wrapping-apps"></a>Wiederverwendung von Signaturzertifikaten und Umschließen von Apps
Für Android müssen alle Apps durch ein gültiges Zertifikat signiert sein, um auf Android-Geräten installiert werden zu können.

Umschlossene Apps können entweder als Teil des Umschließungsprozesses oder *nach* der Umschließung mithilfe Ihrer vorhandenen Tools für die Signatur signiert werden (alle Signierungsinformationen in der App, bevor die Umschließung verworfen wird).
 
Wenn möglich sollten die Signierungsinformationen, die bereits während des Erstellungsprozesses verwendet wurden, während der Umschließung verwendet werden. In bestimmten Organisationen erfordert dies möglicherweise eine Zusammenarbeit mit der Person, die über die Keystore-Informationen verfügt (z.B. aus dem App-Entwicklungsteam). 

Wenn das vorherige Signaturzertifikat nicht verwendet werden kann oder die App zuvor nicht bereitgestellt wurde, können Sie möglicherweise ein neues Signaturzertifikat erstellen, indem Sie die Anweisungen im [Android Developer-Handbuch](https://developer.android.com/studio/publish/app-signing.html#signing-manually) befolgen.

Wenn die App zuvor mit einem anderen Signaturzertifikat bereitgestellt wurde, kann sie nach dem Upgrade nicht zu Intune hochgeladen werden. App-Upgradeszenarios sind dann fehlerhaft, wenn Ihre App mit einem anderen Zertifikat signiert wird, als mit dem, mit dem die App erstellt wurde. Deshalb müssen alle neuen Signaturzertifikate für App-Upgrades verwaltet werden. 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a>Sicherheitsüberlegungen zum Ausführen des App Wrapping Tools
So verhindern Sie ein mögliches Spoofing, das Offenlegen von Informationen und Angriffe durch Rechteerweiterungen:

-   Stellen Sie sicher, dass sich die Branchenanwendung für die Eingabe, die Ausgabeanwendung und der Java-Keystore auf demselben Windows-Computer befinden, auf dem auch das App Wrapping Tool ausgeführt wird.

-   Importieren Sie die Ausgabeanwendung auf demselben Computer, auf dem das Tool ausgeführt wird, in die Intune-Konsole. Weitere Informationen zum Java-Keytool finden Sie unter [Keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).

-   Wenn sich die Ausgabeanwendung und das Tool in einem UNC-Pfad (Universal Naming Convention) befinden und Sie das Tool und die Eingabedateien nicht auf demselben Computer ausführen, sichern Sie die Umgebung, indem Sie [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) oder [SMB-Signaturen (Server Message Block)](https://support.microsoft.com/kb/887429) einrichten.

-   Stellen Sie sicher, dass die Anwendung von einer vertrauenswürdigen Quelle stammt.

-   Sichern Sie das Ausgabeverzeichnis, das die umschlossene Anwendung enthält. Erwägen Sie für die Ausgabe ein Verzeichnis auf Benutzerebene zu verwenden.

### <a name="see-also"></a>Siehe auch
- [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](apps-prepare-mobile-application-management.md)

- [Verwenden des SDK zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen](/intune/classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
