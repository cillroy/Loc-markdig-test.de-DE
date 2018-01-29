---
title: "Bedingter Zugriff über Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Bedingungen definieren, die Benutzer und Geräte erfüllen müssen, um Zugriff auf Unternehmensressourcen in Microsoft Intune zu erhalten.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c54613db5f8ae3c22b7ab811887874e792cf55bb
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="whats-conditional-access"></a>Was ist bedingter Zugriff?

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dieses Thema beschreibt den bedingten Zugriff für Enterprise Mobility + Security (EMS) und erläutert anschließend häufige Szenarien mit bedingtem Zugriff bei Verwendung von Intune.

Der bedingte Zugriff von Enterprise Mobility + Security (EMS) ist kein eigenständiges Produkt, sondern eine Lösung, die für alle Dienste und Produkte im Rahmen von EMS gilt. Die Lösung bietet eine präzise Zugriffssteuerung, sodass Sie die Sicherheit Ihrer Unternehmensdaten gewährleisten und gleichzeitig dafür sorgen können, dass die Benutzer mit jedem Gerät und an jedem Standort optimal arbeiten können.

Sie können Bedingungen definieren, die den Zugriff auf Ihre Unternehmensdaten basierend auf dem Ort, dem Gerät, dem Benutzerstatus und der Vertraulichkeit der Anwendung einschränken.

> [!NOTE] 
> Der bedingte Zugriff kann auch auf [Office 365-Dienste](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/) angewendet werden.

![Architekturdiagramm für den bedingten Zugriff](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a>Bedingter Zugriff über Intune

Intune fügt Richtlinien für die Konformität mobiler Geräte und für die Verwaltung mobiler Apps hinzu, um die Lösung des bedingten Zugriffs für EMS zu unterstützen.

![Intune und der bedingte Zugriff bei Verwendung von EMS](./media/intune-with-ca-1.png)

Möglichkeiten der Verwendung des bedingten Zugriffs in Intune:

-   **Gerätebasierter bedingter Zugriff**

    -   Bedingter Zugriff für Exchange lokal

    -   Bedingter Zugriff basierend auf der Netzwerkzugriffssteuerung

    -   Bedingter Zugriff basierend auf dem Geräterisiko

    -   Bedingter Zugriff für Windows-PCs

        -   Unternehmenseigene Geräte

        -   Bring Your Own Device (BYOD)

-   **App-basierter bedingter Zugriff**

## <a name="next-steps"></a>Nächste Schritte

[Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune](conditional-access-intune-common-ways-use.md)
