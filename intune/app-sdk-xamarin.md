---
title: Intune App SDK-Xamarin-Komponente
description: 
keywords: sdk, Xamarin, intune
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ed5b883b335bc3755f1bd4947d341c89fbda2dda
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a>Intune App SDK-Xamarin-Komponente

> [!NOTE]
> Lesen Sie am besten zuerst den Leitfaden [Erste Schritte mit dem Microsoft Intune App SDK](app-sdk-get-started.md). Dort finden Sie Informationen zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.



## <a name="overview"></a>Übersicht
Mit der [Intune App SDK-Xamarin-Komponente](https://components.xamarin.com/view/microsoft.intune.mam) können Sie die [Intune-App-Schutzrichtlinie](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in Ihren mit Xamarin erstellten iOS- und Android-Apps aktivieren. Die Komponente erlaubt Entwicklern, App-Schutzfunktionen von Intune auf einfache Weise in ihre Xamarin-basierten App zu integrieren.

> [!NOTE]
> Die Unterstützung für das Intune SDK für Xamarin ist derzeit in der Vorschauversion verfügbar. 

Mit der Microsoft Intune App SDK Xamarin-Komponente können Sie die Intune-App-Schutzrichtlinien (auch als APP- oder MAM-Richtlinien bezeichnet) in Ihre mit Xamarin entwickelten Apps integrieren. MAM-fähige Anwendungen sind in das Intune App SDK integrierte Anwendungen. Sie ermöglichen IT-Administratoren, App-Schutzrichtlinien für Ihre mobile App bereitzustellen, wenn diese aktiv von Intune verwaltet wird.

## <a name="whats-supported"></a>Was wird unterstützt?

### <a name="developer-machines"></a>Entwicklercomputer
* macOS


### <a name="mobile-app-platforms"></a>Mobile App-Plattformen
* Android
* iOS


### <a name="intune-mobile-application-management-scenarios"></a>Intune MAM-Szenarien

* Mit Intune MDM registrierte Geräte
* Mit EMM registrierte Geräte von Drittanbietern
* Nicht verwaltete (bei keiner MDM-Lösung registrierte) Geräte

Xamarin-Apps, die mit der Intune App SDK Xamarin-Komponente erstellt wurden, können jetzt sowohl auf registrierten als auch auf nicht registrierten Geräten mit mobiler Intune-Geräteverwaltung (Mobile Device Management, MDM) Intune-App-Schutzrichtlinien empfangen.

## <a name="prerequisites"></a>Voraussetzungen

* **[Nur Android]** Die aktuelle Microsoft Intune-Unternehmensportal-App muss auf dem Gerät installiert sein.

## <a name="get-started"></a>Erste Schritte

1.  Laden Sie [hier](https://components.xamarin.com/submit/xpkg) die **Xamarin-component.exe** herunter, und extrahieren Sie diese.

2. Lesen Sie die [Lizenzbedingungen](https://components.xamarin.com/license/microsoft.intune.mam) für die Microsoft Intune MAM-Xamarin-Komponente.

3.  Laden Sie den Intune App SDK-Xamarin-Komponentenordner aus [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) oder [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) herunter, und extrahieren Sie diesen. Die beiden in Schritt 1 und Schritt 3 heruntergeladenen Dateien müssen sich auf derselben Verzeichnisebene befinden.

4.  Führen Sie `Xamarin.Component.exe install <.xam> file` in der Befehlszeile als Administrator aus.

5.  Klicken Sie in Visual Studio mit der rechten Maustaste in Ihrem zuvor erstellten Xamarin-Projekt auf **Komponenten**.

6.  Wählen Sie **Komponenten bearbeiten** aus, und fügen Sie die Intune App SDK-Komponente hinzu, die Sie lokal auf Ihren Computer heruntergeladen haben.



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a>Aktivieren der Intune-App-Schutzrichtlinien in Ihrer mobilen iOS-App
1.  Um das Intune App SDK zu starten, müssen Sie eine beliebige API der `AppDelegate.cs`-Klasse aufrufen. Beispiel:

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  Nachdem die Komponente hinzugefügt und gestartet wurde, können die allgemeinen Schritte ausgeführt werden, die zum Einrichten der App-SDK in der mobilen iOS-Anwendung notwendig sind. Die kompletten Unterlagen zur Aktivierung nativer iOS-Apps finden Sie unter [Microsoft Intune App SDK für iOS – Entwicklerhandbuch](app-sdk-ios.md).
3. **Wichtig**: Es gibt verschiedene Modifikationen, die spezifisch für Xamarin-basierte iOS-Apps sind. Wenn beispielsweise Schlüsselbundgruppen aktiviert werden, muss Folgendes hinzugefügt werden, um die Xamarin-Beispiel-App zu integrieren, die von uns in die Komponente integriert wurde. Nachstehend finden Sie das Beispiel einer Gruppe, die Sie in Ihren Schlüsselbund-Zugriffsgruppen benötigen:

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

Sie haben die notwendigen Schritte ausgeführt um die Komponente in Ihrer Xamarin-basierten iOS-App einzurichten. Wenn Sie XCode zur Projekterstellung verwenden, können Sie `Intune App SDK Settings.bundle` verwenden. So können Sie die Intune-Richtlinieneinstellungen ein- und ausschalten, während Sie Ihr Projekt zum Testen und Debuggen erstellen. Um das Paket bestmöglich zu nutzen, folgen Sie den Schritten im [Intune App SDK für iOS – Entwicklerhandbuch](app-sdk-ios.md) und lesen Sie den Abschnitt zu [Debuggen in Xcode](app-sdk-ios.md#status-result-and-debug-notifications).

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a>Aktivieren der App-Schutzrichtlinien in Ihrer mobilen Android-App
Für Xamarin-basierte Android-Apps, die kein Benutzeroberflächenframework verwenden, lesen und befolgen Sie das [Entwicklerhandbuch zum Microsoft Intune App SDK für Android](app-sdk-android.md). Für Xamarin-basierte Android-Apps müssen die Klasse, Methoden und Aktivitäten basierend auf der im Handbuch enthaltenen [Tabelle](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) durch das MAM-Äquivalent ersetzt werden. Wenn Ihre App keine `android.app.Application`-Klasse definiert, müssen Sie eine erstellen. Es muss sichergestellt werden, dass Sie von `MAMApplication` erben.

Für Xamarin.Forms und andere UI-Frameworks haben wir ein Tool bereit gestellt. Es heißt `MAM.Remapper`. Das Tool nimmt den Klassentausch für Sie vor. Folgende Schritte müssen Sie jedoch selbst durchführen:

1. Fügen Sie der Version 0.1.0.0 oder höher des `Microsoft.Intune.MAM.Remapper.Tasks`-NuGet-Pakets einen Verweis hinzu.

2. Fügen Sie Ihrer CSPROJ-Datei von Android die folgende Zeile hinzu:
   ```xml
   <Import
   Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
   ```

3. Legen Sie die Buildaktion der hinzugefügten `remapping-config.json`-Datei mit **RemappingConfigFile** fest. Die integrierte `remapping-config.json`-Datei funktioniert nur mit Xamarin.Forms. Greifen Sie für andere Benutzeroberflächenframeworks auf das Readme im Remapper-NuGet-Paket zurück.

## <a name="next-steps"></a>Nächste Schritte

Sie haben die grundlegenden Schritte zum Erstellen der Komponente auf Ihrer App abgeschlossen. Jetzt können die Schritte ausgeführt werden, die in der Xamarin Android-Beispiel-App zu finden sind. Wir haben zwei Beispiele bereit gestellt, eine für Xamarin.Forms und eine weitere für Android.
