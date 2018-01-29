---
title: "Konfigurieren von Windows Information Protection – Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über die Intune-Einstellungen, die Sie für die Verwaltung von Windows Information Protection verwenden können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f233672c-7d9b-4554-af1f-92c001a1a3c5
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ffdf85fccb188b7d792f8745d25f73a632344f8
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-windows-information-protection-in-microsoft-intune"></a><span data-ttu-id="809e5-103">Konfigurieren von Windows Information Protection in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="809e5-103">How to configure Windows Information Protection in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="809e5-104">Immer mehr Mitarbeiter möchten mit ihren eigenen Geräten im Unternehmen arbeiten. Dadurch steigt das Risiko versehentlicher Datenlecks durch Apps und Dienste wie E-Mail, soziale Medien und die öffentliche Cloud, die sich außerhalb der Kontrolle des Unternehmens befinden.</span><span class="sxs-lookup"><span data-stu-id="809e5-104">With the increase of employee-owned devices in the enterprise, there’s also an increasing risk of accidental data leaks through apps and services, like email, social media, and the public cloud, which are outside of the enterprise’s control.</span></span> <span data-ttu-id="809e5-105">Einige Beispiele: Ein Mitarbeiter sendet Fotos der neuesten technischen Entwicklung von einem persönlichen E-Mail-Konto, kopiert Produktinformationen in einen Tweet oder speichert einen laufenden Vertriebsbericht in öffentlichem Cloudspeicher.</span><span class="sxs-lookup"><span data-stu-id="809e5-105">For example, an employee sends the latest engineering pictures from a personal email account, copies and pastes product info into a tweet, or saves an in-progress sales report to public cloud storage.</span></span>

<span data-ttu-id="809e5-106">**Windows Information Protection** unterstützt Sie dabei, das Unternehmen vor solchen potenziellen Datenlecks zu schützen, ohne gleichzeitig die Benutzerfreundlichkeit für die Mitarbeiter einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="809e5-106">**Windows Information Protection** helps to protect against this potential data leakage without otherwise interfering with the employee experience.</span></span> <span data-ttu-id="809e5-107">Die Lösung schützt auch Unternehmens-Apps und -Daten vor versehentlichen Datenlecks auf unternehmenseigenen sowie auf persönlichen Geräten, die die Mitarbeiter zur Arbeit mitbringen – ohne dass Sie Ihre Umgebung oder andere Apps ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="809e5-107">It also helps to protect enterprise apps and data against accidental data leaks on enterprise-owned devices and personal devices that employees bring to work without requiring changes to your environment or other apps.</span></span>

<span data-ttu-id="809e5-108">Die Intune-Richtlinie verwaltet die Liste der von Windows Information Protection geschützten Apps sowie die zugehörigen Speicherorte im Unternehmensnetzwerk, die Schutzebene und Verschlüsselungseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="809e5-108">This Intune policy manages the list of apps protected by Windows Information Protection, enterprise network locations, protection level, and encryption settings.</span></span>

>[!NOTE]
> <span data-ttu-id="809e5-109">Um die Windows 10-Unternehmensportal-App mit Windows Information Protection verwenden zu können, müssen Sie die Unternehmensportal-App unter dem Windows Information Protection-Modus **Ausnahme** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="809e5-109">To use the Windows 10 Company Portal app with Windows Information Protection, you must add the Company Portal app under the Windows Information Protection mode of **Exempt**.</span></span> 

### <a name="next-steps"></a><span data-ttu-id="809e5-110">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="809e5-110">Next steps</span></span>
<span data-ttu-id="809e5-111">Weitere Informationen finden Sie unter [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip) (Schützen Ihrer Unternehmensdaten mit Windows Information Protection).</span><span class="sxs-lookup"><span data-stu-id="809e5-111">For more information, see [Protect your enterprise data using Windows Information Protection](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>
