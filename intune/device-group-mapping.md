---
title: "Verwenden von Gerätekategorien in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie Gerätekategorien verwenden, die Benutzer beim Registrieren ihrer Geräte in Intune auswählen können.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 85dc67911bb53e258faf6d5ccadcf03d88fa4a0d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="map-device-groups"></a>Zuordnen von Gerätegruppen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Verwenden Sie die Gerätekategorien in Microsoft Intune, damit Geräte basierend auf Kategorien, die Sie definieren, automatisch Gruppen hinzugefügt werden, sodass Sie diese Geräte einfacher verwalten können.

Gerätekategorien verwenden den folgenden Workflow:
1. Erstellen Sie Kategorien, die Benutzer beim Registrieren ihrer Geräte verwenden können.
3. Wenn Endbenutzer von iOS- und Android-Geräten ihre Geräte registrieren, müssen sie aus der Liste der von Ihnen konfigurierten Kategorien eine Kategorie auswählen. Um einem Windows-Gerät eine Kategorie zuzuweisen, müssen Endbenutzer die Unternehmensportal-Website verwenden (weitere Informationen dazu finden Sie in diesem Thema unter **Nach dem Konfigurieren von Gerätegruppen**).
4. Dann können Sie Richtlinien und Apps für diese Gruppen bereitstellen.

Sie können beliebige Gerätekategorien erstellen, z.B.:
- POS-Gerät (Point of Sale)
- Demogerät
- Sales
- Kontoführung
- Manager

## <a name="how-to-configure-device-categories"></a>Konfigurieren von Gerätekategorien

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a>Schritt 1: Erstellen von Gerätekategorien auf dem Blatt „Intune“ im Azure-Portal
1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie im Blatt **Intune** die Option **Geräteregistrierung** aus.
3. Wählen Sie im Blatt **Geräteregistrierung** die Option **Gerätekategorien** aus.
4. Wählen Sie auf der Seite **Gerätekategorien** die Option **Erstellen** aus, um eine neue Kategorie hinzuzufügen.
5. Geben Sie auf dem nächsten Blatt einen **Namen** für die neue Kategorie und optional eine **Beschreibung** ein.
6. Klicken Sie auf **Erstellen**, wenn Sie fertig sind. Die gerade von Ihnen erstellte Kategorie wird in der Liste der Kategorien angezeigt.

Verwenden Sie den Kategorienamen des Geräts zum Erstellen von Azure Active Directory-Sicherheitsgruppen in Schritt 2.

### <a name="step-2---create-azure-active-directory-security-groups"></a>Schritt 2: Erstellen von Active Directory-Sicherheitsgruppen
In diesem Schritt erstellen Sie dynamische Gruppen im Azure-Portal auf Basis der Gerätekategorie und des Gerätekategorienamens.

Lesen Sie das Thema [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in der Dokumentation zu Azure Active Directory, um den Vorgang fortzusetzen.

Verwenden Sie die Informationen in diesem Abschnitt zum Erstellen einer Gerätegruppe mit einer erweiterten Regel mithilfe des Attributs **deviceCategory**. Beispiel: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")

Wenn nach dem Konfigurieren von Gerätegruppen Benutzer ihre Geräte registrieren, wird ihnen eine Liste der von Ihnen konfigurierten Kategorien angezeigt. Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät der Active Directory-Sicherheitsgruppe hinzugefügt, die der gewählten Kategorie entspricht.

### <a name="how-to-view-the-categories-of-devices-you-manage"></a>Anzeigen der Kategorien von Geräten, die Sie verwalten

1.  Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2. Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräte und Gruppen** aus.

3.  Klicken Sie unter **Verwalten** auf **Alle Geräte**.

4.  Sehen Sie sich in der Liste der Geräte die Spalte **Kategorie** an.

Wenn die Spalte **Kategorie** nicht angezeigt wird, klicken Sie auf **Spalten**, wählen Sie in der Liste **Kategorie** aus, und klicken Sie dann auf **Anwenden**.

### <a name="to-change-the-category-of-a-device"></a>So ändern Sie die Kategorie eines Geräts

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte & Gruppen** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Verwalten** > **Alle Geräte** aus.
5. Wählen Sie in der Liste der Geräte das gewünschte Gerät und anschließend auf dem Blatt mit den Geräteeigenschaften **Verwalten** > **Eigenschaften** aus.
6. Auf dem nächsten Blatt können Sie die **Gerätekategorie** des ausgewählten Geräts in einen beliebigen Kategorienamen ändern, den Sie zuvor konfiguriert haben.

## <a name="after-you-configure-device-groups"></a>Nach dem Konfigurieren von Gerätegruppen

Wenn Endbenutzer von iOS- und Android-Geräten ihre Geräte registrieren, müssen sie aus der Liste der von Ihnen konfigurierten Kategorien eine Kategorie auswählen. Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät zu der Intune-Gerätegruppe oder Active Directory-Sicherheitsgruppe hinzugefügt, die der gewählten Kategorie entspricht.

Unabhängig von der Plattform können Ihre Endbenutzer nach der Registrierung des Geräts jederzeit auf „portal.manage.microsoft.com“ zugreifen. Weisen Sie den Benutzer dazu an, auf die Unternehmensportalwebsite zuzugreifen und zu **Meine Geräte** zu navigieren. Er hat dann die Möglichkeit, ein auf der Seite aufgeführtes registriertes Gerät sowie eine Kategorie auszuwählen.

Nach Auswahl der Kategorie wird das Gerät automatisch zur entsprechenden Gruppe hinzugefügt, die Sie erstellt haben. Wenn ein Gerät bereits registriert wurde, bevor Sie Kategorien konfiguriert haben, wird dem Benutzer auf der Unternehmensportal-Website eine Benachrichtigung zu dem Gerät angezeigt, und der Benutzer wird aufgefordert, beim nächsten Zugriff auf die Unternehmensportal-App über ein iOS- oder Android-Gerät eine Kategorie auszuwählen.

## <a name="further-information"></a>Weitere Informationen
- Sie können eine Gerätekategorie im Azure-Portal bearbeiten. Sie müssen dann aber manuell alle Azure Active Directory-Sicherheitsgruppen aktualisieren, die auf diese Kategorie verweisen.

- Wenn Sie eine Kategorie löschen, tragen alle Geräte, die dieser zuvor zugewiesen waren, anschließend den Kategorienamen **Nicht zugewiesen**.
