---
title: Blockieren von Apps ohne moderne Authentifizierung in Intune
description: 
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73db3070-d033-40fb-a8f1-58b9d198021e
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8d2e6402fc4d894902bdbdd6e1ae7248bb14468d
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="block-apps-that-do-not-use-modern-authentication-adal"></a><span data-ttu-id="ff7a0-102">Blockieren von Apps, die keine moderne Authentifizierung verwenden (ADAL)</span><span class="sxs-lookup"><span data-stu-id="ff7a0-102">Block apps that do not use modern authentication (ADAL)</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ff7a0-103">Der App-bedingte Zugriff für mit App-Schutzrichtlinien hängt von Anwendungen ab, die die [moderne Authentifizierung](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) nutzen, bei der es sich um eine Implementierung von OAuth2 handelt.</span><span class="sxs-lookup"><span data-stu-id="ff7a0-103">App-based conditional access with app protection policies rely on applications using [modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) which is an implementation of OAuth2.</span></span> <span data-ttu-id="ff7a0-104">Die meisten mobilen Office-Anwendungen und Office-Anwendungen für den Desktop nutzen die moderne Authentifizierung. Es gibt jedoch Apps von Drittanbietern oder ältere Office-Apps, die andere Authentifizierungsmethoden wie die Standardauthentifizierung und die formularbasierte Authentifizierung nutzen.</span><span class="sxs-lookup"><span data-stu-id="ff7a0-104">Most current Office mobile and desktop applications use modern authentication, however there are third-party apps and older Office apps that user other authentication methods like basic authentication and forms based authentication.</span></span>

<span data-ttu-id="ff7a0-105">Zum Blockieren dieser Apps wird Folgendes empfohlen:</span><span class="sxs-lookup"><span data-stu-id="ff7a0-105">To block access to these apps we recommend the following:</span></span>

* <span data-ttu-id="ff7a0-106">Richten Sie die Anspruchsregeln für Active Directory-Verbunddienste (ADFS) dahingehend ein, dass nicht moderne Authentifizierungsprotokolle blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff7a0-106">Set up ADFS claims rules to block non-modern authentication protocols.</span></span> <span data-ttu-id="ff7a0-107">Detaillierte Anleitungen werden in Szenario 3 beschrieben: [Blockieren des gesamten Zugriffs auf Office 365, bis auf browserbasierte Anwendungen](https://technet.microsoft.com/library/dn592182.aspx).</span><span class="sxs-lookup"><span data-stu-id="ff7a0-107">Detailed instructions are provided in scenario 3 - [block all access to O365 except browser-based applications](https://technet.microsoft.com/library/dn592182.aspx).</span></span>
* <span data-ttu-id="ff7a0-108">Für **SharePoint Online** deaktivieren Sie die Verwendung nicht moderner Authentifizierungsmethoden im SharePoint Online-Dienst. Verwenden Sie das PowerShell-Cmdlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx), um die Eigenschaft für ältere Authentifizierungsprotokolle auf „False“ festzulegen:</span><span class="sxs-lookup"><span data-stu-id="ff7a0-108">For **SharePoint Online**, disable non-modern authentication in the SharePoint Online service using the PowerShell commandlet [Set-SPOTenant](https://technet.microsoft.com/library/fp161390.aspx) to set the legacy authentication protocols property to false:</span></span>

```
 Set-SPOTenant -LegacyAuthProtocolsEnabled $false
```


>[!IMPORTANT]
><span data-ttu-id="ff7a0-109">App-basierte CA darf nicht mit der zertifikatbasierten Authentifizierung von Azure Active Directory (Azure AD) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff7a0-109">App-based CA must not be used with Azure Active Directory (Azure AD) certificate based authentication.</span></span> <span data-ttu-id="ff7a0-110">Es darf immer jeweils nur eine Authentifizierungsmethode konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ff7a0-110">You can only have one of these configured at a time.</span></span>

### <a name="see-also"></a><span data-ttu-id="ff7a0-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff7a0-111">See also</span></span>
[<span data-ttu-id="ff7a0-112">App-basierter bedingter Zugriff mit Intune</span><span class="sxs-lookup"><span data-stu-id="ff7a0-112">App-based conditional access with Intune</span></span>](app-based-conditional-access-intune.md)
