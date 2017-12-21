---
title: Integrieren der Netzwerkzugriffssteuerung mit Intune
titlesuffix: Azure portal
description: Integrieren der Netzwerkzugriffssteuerung (NAC) mit Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d75d996f4166fb2a760d1ccb518ca7a228c1a0d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a>Integrieren der Netzwerkzugriffssteuerung (NAC) mit Intune

Intune arbeitet mit Partnern der Netzwerkzugriffssteuerung zusammen, um Organisationen beim Schützen von Unternehmensdaten zu helfen, wenn Geräte versuchen, auf lokale Ressourcen zuzugreifen.

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a>Wie helfen Lösungen von Intune und NAC beim Schutz der Ressourcen Ihrer Organisation?

Die Aufgabe von NAC-Lösungen besteht darin, den Registrierungs- und Kompatibilitätsstatus des Geräts mit Intune zu überprüfen, um Entscheidungen bezüglich der Zugriffssteuerung zu treffen. Wenn das Gerät nicht registriert ist oder registriert ist, aber nicht den Intune-Gerätekompatibilitätsrichtlinien entspricht, sollte das Gerät für die Registrierung und/oder eine Kompatibilitätsprüfung an Intune weitergeleitet werden.

### <a name="example"></a>Beispiel

Wenn das Gerät registriert und mit Intune kompatibel ist, sollte die NAC-Lösung dem Gerät den Zugriff auf Unternehmensressourcen erlauben. Benutzern kann beispielsweise der Zugriff auf das Unternehmens-WLAN oder VPN-Ressourcen gewährt oder verweigert werden.

## <a name="nac-and-conditional-access"></a>NAC und bedingter Zugriff

NAC nutzt bei Entscheidungen bezüglich der Zugriffssteuerung den bedingten Zugriff.

- Weitere Informationen finden Sie unter [Common ways to use conditional access with Intune (Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune)](conditional-access-intune-common-ways-use.md).

## <a name="how-the-nac-integration-works"></a>Funktionsweise der NAC-Integration

In dieser Übersicht wird gezeigt, wie die NAC-Integration in Intune funktioniert. Die Schritte 1-3 erläutern den Onboarding-Prozess. Nachdem die NAC-Lösung in Intune integriert wurde, beschreiben die Schritte 4-9 den laufenden Betrieb.

![Wie NAC und Intune zusammenarbeiten](./media/ca-intune-common-ways-2.png)

1.  Registrieren Sie die Lösung des NAC-Partners mit Azure Active Directory (AAD), und gewähren Sie delegierte Berechtigungen an die Intune-NAC-API.

2.  Konfigurieren Sie die Lösung des NAC-Partners mit den geeigneten Einstellungen, darunter die URL für die Intune-Ermittlung.

3.  Konfigurieren Sie die Lösung des NAC-Partners für die Zertifikatauthentifizierung.

4.  Der Benutzer stellt eine Verbindung zum WLAN-Zugriffspunkt her oder fordert eine VPN-Verbindung an.

5.  Die Lösung des NAC-Partners leitet die Geräteinformationen an Intune weiter und fragt Intune nach dem Registrierungs- und Kompatibilitätsstatus des Geräts.

6.  Wenn das Gerät nicht kompatibel oder nicht registriert ist, weist die Lösung des NAC-Partners den Benutzer an, das Gerät zu registrieren oder kompatibel zu machen.

7.  Das Gerät versucht eine erneute Bestätigung seines Kompatibilitäts- und/oder Registrierungsstatus.

8.  Wenn das Gerät registriert wurde und kompatibel ist, erhält die Lösung des NAC-Partners von Intune eine Statusmeldung.

9.  Die Verbindung konnte erfolgreich hergestellt werden, und das Gerät erhält Zugriff auf Unternehmensressourcen.

## <a name="next-steps"></a>Nächste Schritte

-   [Integrieren von Cisco ISE mit Intune](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [Integrieren von Citrix NetScaler mit Intune](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [Integrieren von HPE Aruba ClearPass mit Intune](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
