---
title: "Bestimmen von Szenarien für Anwendungsfälle"
description: "Dieser Artikel hilft Ihnen, Szenarien für Intune-Anwendungsfälle und untergeordnete Anwendungsfälle für eine reine Cloudimplementierung von Microsoft Intune zu bestimmen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a>Bestimmen von Szenarien für Anwendungsfälle für die Verwaltung von Mobilgeräten

Das Bestimmen Ihrer Szenarien für Anwendungsfälle ist ein wichtiger Bestandteil des Planungsprozesses einer erfolgreichen Intune-Bereitstellung. Szenarien für Anwendungsfälle sind hilfreich, da Sie mit ihnen Ihre Benutzer in verwaltbare Gruppen unterteilen können, entweder nach Benutzertyp oder Rolle oder nach Besitzer des Gerät des Benutzers (z.B. das Unternehmen oder der Benutzer selbst).

Betrachten wir einige Beispiele, die Sie Ihre Organisation beim Festlegen der Intune-Anwendungsfallszenarien sowie der Organisationsgruppen und der den einzelnen Anwendungsfällen zugeordneten mobilen Geräteplattformen unterstützen können.

## <a name="device-ownership"></a>Gerätebesitz
Als Erstes können Sie die Intune-Bereitstellungsziele und sonstigen Ziele Ihrer Organisation zurate ziehen, um die Hauptanwendungsszenarien für Ihre Bereitstellung zu bestimmen. Beantworten Sie im Rahmen Ihres Intune-Bereitstellungsplans die folgenden Fragen:

-   Möchten Sie unternehmenseigene Geräte unterstützen?

-   Möchten Sie persönliche Geräte (BYOD) unterstützen?

Dies sind keine Entweder/Oder-Optionen. Sie finden ggf. heraus, dass Sie beide Formen des Gerätebesitzes unterstützen müssen, um die Ziele Ihrer Organisation zu erreichen. Die untergeordneten Anwendungsfälle helfen bei der Klärung, wo die verschiedenen Geräteverwaltungsrichtlinien gelten sollen.

### <a name="user-type-or-device-role"></a>Benutzertyp oder Geräterolle

Bestimmen Sie, ob es für jedes Anwendungsfallszenario untergeordnete Anwendungsfälle gibt. Zum Beispiel hat Ihre Organisation möglicherweise Anforderungen für die Unterstützung eines unternehmensweiten Anwendungsfallszenarios erkannt, das basierend auf Benutzertyp oder Geräterolle zusätzliche untergeordnete Anwendungsfälle aufweist:

-   Information-Worker

-   Management

-   Kiosk

Hier sind einige Beispiele von Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** |
|:---:|:---:|
| Unternehmen | Information-Worker |              
| Unternehmen | Führungskräfte |           
| Unternehmen | Kiosk |
| BYOD | Information-Worker |           
| BYOD | Führungskräfte |

Sie können [eine Vorlage der obigen Tabelle herunterladen](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), um die Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle Ihrer Organisation einzutragen.

## <a name="organizational-groups-for-your-scenarios"></a>Organisationsgruppen für Ihre Szenarien

Jetzt müssen Sie die Organisationsgruppen festlegen, die den einzelnen Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle zugeordnet werden. Beispiel:

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** | **Organisationsgruppen** |
|:---:|:---:|:---:|
| Unternehmen | Information-Worker | Personalabteilung, Finanzabteilung |               
| Unternehmen | Management | Personalabteilung, Finanzabteilung |            
| Unternehmen | Kiosk | Einzelhandel |
| BYOD | Information-Worker | Marketing, Vertrieb |            
| BYOD | Management | Marketing, Vertrieb |


## <a name="mobile-device-platforms-for-your-scenarios"></a>Plattformen für mobile Geräte für Ihre Szenarien

Im nächsten Schritt bestimmen Sie die Plattformen für mobile Geräte , die den einzelnen Anwendungsfallszenarien zugeordnet sind. Es gibt möglicherweise mehr als eine.

Angenommen, im Anwendungsfallszenario Ihres Unternehmens werden die Geräteplattformen iOS und Android Samsung KNOX unterstützt. Ihre BYOD-Richtlinie sieht ggf. Unterstützung für weitere Plattformen für mobile Geräte wie Android (nicht Samsung KNOX) und Windows 10 Mobile vor. Ausgehend von den genannten Beispielen haben wir jedem Anwendungsfallszenario Plattformen für mobile Geräte zugeordnet.

| **Anwendungsfälle** | **Untergeordnete Anwendungsfälle** | **Gruppen** | **Geräteplattformen** |   
|:---:|:---:|:---:|:---:|
| Unternehmen | Information-Worker | Personalabteilung, Finanzabteilung | iOS |                                                           
| Unternehmen | Führungskräfte | Personalabteilung, Finanzabteilung | iOS |                                                           
| Unternehmen | Kiosk | Einzelhandel | Android |
| BYOD | Information-Worker | Marketing, Vertrieb | iOS |                                                           
| BYOD | Führungskräfte | Marketing, Vertrieb | iOS |

## <a name="next-steps"></a>Nächste Schritte

Der nächste Abschnitt enthält Hinweise für das [Identifizieren der Intune-Anforderungen für die einzelnen Anwendungsszenarien](planning-guide-requirements.md).
