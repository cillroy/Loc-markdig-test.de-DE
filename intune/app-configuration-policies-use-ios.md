---
title: "Hinzufügen von App-Konfigurationsrichtlinien für verwaltete iOS-Geräte | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien zum Bereitstellen von Konfigurationsdaten für eine iOS-App beim Ausführen verwenden."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d63963af4b95d10abca8f90c86a3b28c5781da68
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a>Hinzufügen App-Konfigurationsrichtlinien für verwaltete iOS-Geräte

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Verwenden Sie App-Konfigurationsrichtlinien in Microsoft Intune, um Einstellungen anzugeben, wenn Benutzer eine iOS-App ausführen. Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu. Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu. Die Richtlinieneinstellungen werden verwendet, wenn die App danach sucht (in der Regel beim ersten Ausführen).

> [!TIP]
> Dieser Richtlinientyp ist zurzeit nur für Geräte unter iOS 8.0 und höher verfügbar. Er unterstützt die folgenden App-Installationstypen:
>
> -   **Verwaltete iOS-App aus dem App Store**
> -   **App-Paket für iOS**
>
> Weitere Informationen zu Installationstypen von Apps finden Sie unter [Hinzufügen von Apps zu Microsoft Intune](apps-add.md).

## <a name="create-an-app-configuration-policy"></a>Erstellen einer Konfigurationsrichtlinie für Apps

1. Melden Sie sich im Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
3. Wählen Sie die Workload **Mobile Apps** aus.
4. Wählen Sie in der Gruppe **Verwalten** **App-Konfigurationsrichtlinien** und dann **Hinzufügen** aus.
5. Legen Sie die folgenden Details fest:
    - **Name**<br>
      Der Name des Profils, das im Azure-Portal angezeigt wird
    - **Beschreibung**<br>
      Die Beschreibung des Profils, das im Azure-Portal angezeigt wird
    - **Geräteregistrierungstyp**<br>
      Klicken Sie auf **Verwaltete Geräte**.
6. Wählen Sie **iOS** als **Plattform** aus.
7.  Wählen Sie **Zugeordnete App** aus. Wählen Sie dann auf dem Blatt **Zugeordnete App** die verwaltete App aus, auf die Sie die Konfiguration anwenden möchten.
8.  Wählen Sie auf dem Blatt **Konfigurationsrichtlinie hinzufügen** die Option **Konfigurationseinstellungen** aus.
9. Wählen Sie das **Format der Konfigurationseinstellungen** aus. Wählen Sie eine der folgenden Einstellungen aus:
    - **[Verwenden des Konfigurations-Designers](#Use-the-configuration-designer)**
    - **[Eingeben von XML-Daten](#enter-xml-data)**
10. Wählen Sie **OK** und dann **Hinzufügen** aus.

## <a name="use-configuration-designer"></a>Verwenden des Konfigurations-Designers

Sie können den Konfigurations-Designer für Apps auf Geräten verwenden, die in Intune registriert sind oder nicht. Der Designer ermöglicht Ihnen das Konfigurieren bestimmter Konfigurationsschlüssel und -werte. Sie müssen ebenfalls den Datentyp für jeden Wert angeben. Die Einstellungen werden für Apps automatisch bei der Installation bereitgestellt.

### <a name="add-a-setting"></a>Hinzufügen einer Einstellung

1. Legen Sie für jeden Schlüssel und jeden Wert in der Konfiguration Folgendes fest:
   - **Konfigurationsschlüssel**<br>
     Der Schlüssel, der die bestimmte Einstellungskonfiguration eindeutig identifiziert.
   - **Werttyp**<br>
     Der Datentyp des Konfigurationswerts. Zu den Typen gehören Integer, Real, String oder Boolean.
   - **Konfigurationswert**<br>
     Der Wert für die Konfiguration.
2. Wählen Sie **OK** aus, um Ihre Konfigurationseinstellungen festzulegen.

### <a name="delete-a-setting"></a>Löschen einer Einstellung

1. Wählen Sie die Auslassungspunkte (**...** ) neben der Einstellung aus.
2. Klicken Sie auf **Löschen**.

Die Zeichen \{\{ und \}\} werden nur von Tokentypen verwendet und dürfen nicht für andere Zwecke verwendet werden.

## <a name="enter-xml-data"></a>Eingeben von XML-Daten

Sie können eine XML-Eigenschaftenliste eingeben oder einfügen, die die App-Konfigurationseinstellungen für in Intune registrierte Geräte enthält. Das Format der XML-Eigenschaftenliste variiert je nach der App, die Sie konfigurieren. Wenden Sie sich an den Hersteller der App, um ausführliche Informationen über das genau zu verwendende Format zu erhalten.

Intune überprüft das XML-Format. Intune überprüft jedoch nicht, ob die XML-Eigenschaftenliste (PList) mit der Ziel-App verwendet werden kann.

Weitere Informationen zu XML-Eigenschaftenlisten:

  -  Lesen Sie [Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).
  -  Lesen Sie unter [Understand XML Property Lists (Grundlegendes zu XML-Eigenschaftenlisten)](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in der iOS-Entwicklerbibliothek nach.

### <a name="example-format-for-an-app-configuration-xml-file"></a>Beispielformat für eine App-Konfigurations-XML-Datei

Wenn Sie eine App-Konfigurationsdatei erstellen, können Sie die folgenden Werte in diesem Format angeben:

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>
```
### <a name="supported-xml-plist-data-types"></a>Unterstützte XML-PList-Datentypen

Intune unterstützt die folgenden Datentypen in einer Eigenschaftenliste:

- &lt;integer&gt;
- &lt;real&gt;
- &lt;string&gt;
- &lt;array&gt;
- &lt;dict&gt;
- &lt;true /&gt; oder &lt;false /&gt;

### <a name="tokens-used-in-the-property-list"></a>Tokens, die in der Eigenschaftenliste verwendet werden.

Darüber hinaus unterstützt Intune die folgenden Tokentypen in der Eigenschaftenliste:
- \{\{userPrincipalName\}\}: z.B.**John@contoso.com**
- \{\{Mail\}\}: z.B.**John@contoso.com**
- \{\{partialupn\}\}: z.B. **John**
- \{\{accountid\}\}: z.B. **fc0dc142-71d8-4b12-bbea-bae2a8514c81**
- \{\{deviceid\}\}: z.B. **b9841cd9-9843-405f-be28-b2265c59ef97**
- \{\{userid\}\}: z.B. **3ec2c00f-b125-4519-acf0-302ac3761822**
- \{\{username\}\}: z.B. **John Doe**
- \{\{serialnumber\}\}: z.B. **F4KN99ZUG5V2** (für iOS-Geräte)
- \{\{serialnumberlast4digits\}\}: z.B. **G5V2** (für iOS-Geräte)

## <a name="next-steps"></a>Nächste Schritte

Fahren Sie wie gewöhnlich mit dem [Zuweisen](apps-deploy.md) und [Überwachen](apps-monitor.md) der App fort.