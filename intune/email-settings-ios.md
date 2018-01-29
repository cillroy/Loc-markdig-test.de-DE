---
title: "E-Mail-Einstellungen für iOS-Geräte in Intune"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von E-Mail-Verbindungen auf iOS-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9f0fa6af-3669-439a-bd0d-75d8b1a0b135
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff590506f1549b42554f75dc6f9f1ef29e7f728c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="email-profile-settings-for-ios-devices-in-microsoft-intune"></a><span data-ttu-id="c453b-103">Einstellungen für das E-Mail-Profil für iOS-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c453b-103">Email profile settings for iOS devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

- <span data-ttu-id="c453b-104">**E-Mail-Server:** Der Hostname Ihres Exchange-Servers.</span><span class="sxs-lookup"><span data-stu-id="c453b-104">**Email server** - The host name of your Exchange server.</span></span>
- <span data-ttu-id="c453b-105">**Kontoname:** Der Anzeigename für das E-Mail-Konto so, wie er den Benutzern auf ihren Geräten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c453b-105">**Account name** - The display name for the email account as it will appear to users on their devices.</span></span>
- <span data-ttu-id="c453b-106">**Benutzernamensattribut aus AAD:** Dies ist das Attribut in Active Directory (AD) oder Azure AD, das verwendet wird, um den Benutzernamen für dieses E-Mail-Profil zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c453b-106">**Username attribute from AAD** - This is the attribute in Active Directory (AD) or Azure AD, that will be used to generate the username for this email profile.</span></span> <span data-ttu-id="c453b-107">Wählen Sie **Primäre SMTP-Adresse** aus, z.B. **user1@contoso.com**, oder **Benutzerprinzipalname**, z.B. **user1** oder **user1@contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="c453b-107">Select **Primary SMTP Address**, such as **user1@contoso.com** or **User Principal Name**, such as **user1** or **user1@contoso.com**.</span></span>
- <span data-ttu-id="c453b-108">**E-Mail-Adressattribut aus AAD:** Die Art der Generierung der E-Mail-Adresse für den Benutzer auf den einzelnen Geräten.</span><span class="sxs-lookup"><span data-stu-id="c453b-108">**Email address attribute from AAD** - How the email address for the user on each device is generated.</span></span> <span data-ttu-id="c453b-109">Wählen Sie **Primäre SMTP-Adresse** aus, um die primäre SMTP-Adresse zum Anmelden bei Exchange zu verwenden. Verwenden Sie **Benutzerprinzipalname** aus, um den vollständigen Benutzerprinzipalnamen als E-Mail-Adresse zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c453b-109">Select **Primary SMTP Address** to use the primary SMTP address to log into Exchange or use **User Principal Name** to use the full principal name as the email address.</span></span>
- <span data-ttu-id="c453b-110">**Authentifizierungsmethode:** Wählen Sie entweder **Benutzername und Kennwort** oder **Zertifikate** als Authentifizierungsmethode aus, die vom E-Mail-Profil verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c453b-110">**Authentication method** - Select either **Username and Password** or **Certificates** as the authentication method used by the email profile.</span></span>
    - <span data-ttu-id="c453b-111">Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c453b-111">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="c453b-112">**SSL:** Verwenden Sie SSL-Kommunikation (Secure Sockets Layer) beim Senden und Empfangen von E-Mails sowie bei der Kommunikation mit dem Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="c453b-112">**SSL** - Use Secure Sockets Layer (SSL) communication when sending emails, receiving emails, and communicating with the Exchange server.</span></span>
- <span data-ttu-id="c453b-113">**S/MIME**: Ausgehende E-Mails werden mithilfe der S/MIME-Signatur gesendet.</span><span class="sxs-lookup"><span data-stu-id="c453b-113">**S/MIME** - Send outgoing email using S/MIME signing.</span></span>
    - <span data-ttu-id="c453b-114">Wenn Sie **Zertifikat** ausgewählt haben, wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil aus, das zur Authentifizierung der Exchange-Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c453b-114">If you selected **Certificate**, select a client SCEP or PKCS certificate profile that you previously created that will be used to authenticate the Exchange connection.</span></span>
- <span data-ttu-id="c453b-115">**Menge an E-Mails für die Synchronisierung:** Wählen Sie die Anzahl der Tage von E-Mails aus, die synchronisiert werden sollen, oder wählen Sie **Unbegrenzt** aus, um alle verfügbaren E-Mail-Nachrichten zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="c453b-115">**Amount of email to synchronize** - Choose the number of days of email that you want to synchronize, or select **Unlimited** to synchronize all available email.</span></span>
- <span data-ttu-id="c453b-116">**Verschieben von Nachrichten in andere E-Mail-Konten zulassen:** Hiermit können Benutzer E-Mail-Nachrichten zwischen verschiedenen Konten verschieben, die auf ihrem Gerät konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c453b-116">**Allow messages to be moved to other email accounts** - This allows users to move email messages between different accounts they have configured on their device.</span></span>
- <span data-ttu-id="c453b-117">**E-Mail-Versand aus Drittanbieteranwendungen zulassen:** erlaubt dem Benutzer die Auswahl dieses Profils als das Standardkonto für das Senden von E-Mails und erlaubt Anwendungen von Drittanbietern das Öffnen von E-Mails in der nativen E-Mail-App, um beispielsweise Dateien an E-Mails anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="c453b-117">**Allow email to be sent from third party applications** - Allow the user to select this profile as the default account for sending email, and allow third-party applications to open email in the native email app, for example, to attach files to email.</span></span>
- <span data-ttu-id="c453b-118">**Kürzlich verwendete E-Mail-Adressen synchronisieren:** Mit diesem Feature können Benutzer die Liste der E-Mail-Adressen, die vor Kurzem auf dem Gerät verwendet wurden, mit dem Server synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="c453b-118">**Synchronize recently used email addresses** - This feature allows users to synchronize the list of email addresses that have been recently used on the device with the server.</span></span>
