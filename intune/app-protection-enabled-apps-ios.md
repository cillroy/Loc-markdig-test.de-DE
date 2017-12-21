---
title: iOS-Apps mit App-Schutzrichtlinien
titlesuffix: Azure portal
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7f0761124ccb425151ca7b06a9982b61b765db0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a>Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema beschreibt die Benutzererfahrung für Apps mit App-Schutzrichtlinien. App-Schutzrichtlinien gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z.B. wenn Sie Ihr Geschäftskonto für den Zugriff auf Apps verwenden oder auf Dateien zugreifen, die am OneDrive for Business-Speicherort Ihres Unternehmens gespeichert sind.
##  <a name="accessing-apps"></a>Zugreifen auf Apps

Wenn das Gerät **nicht bei Intune registriert** ist, wird der Endbenutzer beim ersten Verwenden der App dazu aufgefordert, die App neu zu starten.  Ein Neustart ist erforderlich, damit App-Schutzrichtlinien auf die App angewendet werden können. Der folgende Screenshot stellt dies mithilfe der Skype-App dar:


![Screenshot des iOS-Geräts mit der PIN-Eingabeaufforderung](./media/ios-pin-prompt.png)

Bei Geräten, die **für die Verwaltung in Intune registriert** sind, wird dem Endbenutzer eine Meldung angezeigt, dass seine App nun verwaltet wird:

![Screenshot des iOS-Geräts mit der Meldung zur Verwaltung durch das Unternehmen und der Eingabeaufforderung](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a>Verwenden von Apps mit Multi-Identity Support (Unterstützung für mehrere Identitäten)

App-Schutzrichtlinien gelten nur, wenn die App im geschäftlichen Kontext verwendet wird. Daher kann das App-Verhalten abhängig vom Kontext (geschäftlich oder privat) abweichen.  

Bei Apps, die mehrere Identitäten unterstützen, wendet Intune die App-Schutzrichtlinien nur an, wenn der Endbenutzer die App im geschäftlichen Kontext verwendet.  Beispielsweise erhalten Endbenutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.  Bei der **Outlook-App** wird der Endbenutzer beim Starten der App zur Eingabe einer PIN aufgefordert. Bei der **OneDrive-App** erfolgt diese Aufforderung, wenn der Endbenutzer das Geschäftskonto eingibt.  Bei Microsoft **Word**, **PowerPoint* und **Excel** erfolgt diese Aufforderung, wenn der Endbenutzer auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.
##  <a name="managing-user-accounts-on-the-device"></a>Verwalten von Benutzerkonten auf dem Gerät

Intune unterstützt nur die Bereitstellung von App-Schutzrichtlinien auf je einem Benutzerkonto pro Gerät.

* Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert oder auch nicht. Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.
  * **Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.  

  * Für **OneDrive- und Outlook-Apps** kann nur ein geschäftliches Konto verwendet werden.  Das Hinzufügen weiterer Geschäftskonten wird von diesen Apps blockiert.  Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.

* Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.


Lesen Sie das Beispielszenario unten, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.

Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien. **Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.
### <a name="adding-a-second-account"></a>Hinzufügen eines zweiten Kontos

Wenn Sie ein iOS-Gerät verwenden und versuchen, auf demselben Gerät ein zweites Geschäftskonto einzurichten, wird möglicherweise eine Sperrnachricht angezeigt.  Die Konten werden angezeigt, und Sie können das Konto auswählen, das Sie entfernen möchten.

![Screenshot des Dialogfelds mit der Sperrnachricht und den Optionen „Ja“ und „Nein“](./media/ios-switch-user.PNG)

## <a name="next-steps"></a>Nächste Schritte
[Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-android.md)
### <a name="see-also"></a>Weitere Informationen:
[Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune](app-protection-policies.md)
