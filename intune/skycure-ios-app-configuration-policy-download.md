---
title: Herunterladen der Skycure iOS-App-Konfigurationsrichtlinie zur Verwendung mit Intune
titlesuffix: Azure portal
description: Laden Sie die Skycure iOS-App-Konfigurationsrichtlinie zur Verwendung mit Intune herunter.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 296d5545530e8001c0648bafac3101b94f45529d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a><span data-ttu-id="c963c-103">Herunterladen der Skycure iOS-App-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c963c-103">Download Skycure iOS app configuration policy</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c963c-104">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="c963c-104">Before you begin</span></span>

<span data-ttu-id="c963c-105">Zur Ausführung der nächsten Schritte müssen Sie sich in der Skycure-Verwaltungskonsole anmelden.</span><span class="sxs-lookup"><span data-stu-id="c963c-105">You need to log in to the Skycure Management Console to perform the next steps.</span></span>

> [!TIP] 
> <span data-ttu-id="c963c-106">Wenn Sie Microsoft Internet Explorer 11 oder Edge verwenden, müssen Sie die Skycure-Verwaltungskonsole möglicherweise im privaten Modus öffnen.</span><span class="sxs-lookup"><span data-stu-id="c963c-106">If using Microsoft Internet explorer 11 or Edge, you might need to open the Skycure Management console using In-Private mode.</span></span>

## <a name="to-download-the-ios-app-configuration-policy"></a><span data-ttu-id="c963c-107">Herunterladen der iOS-App-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c963c-107">To download the iOS app configuration policy</span></span>

1.  <span data-ttu-id="c963c-108">Gehen Sie zur [Skycure-Verwaltungskonsole](https://aad.skycure.com).</span><span class="sxs-lookup"><span data-stu-id="c963c-108">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="c963c-109">Geben Sie Ihre **Skycure-Administratoranmeldeinformationen** ein, und klicken Sie dann auf **Continue** (Weiter).</span><span class="sxs-lookup"><span data-stu-id="c963c-109">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

    ![Skycure-Verwaltungskonsolenanmeldung](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="c963c-111">Der Skycure-Administratorbenutzername ist ein E-Mail-Konto, das eine gültiges Benutzerkonto in Azure Active Directory sein muss, andernfalls schlägt die Anmeldung fehl.</span><span class="sxs-lookup"><span data-stu-id="c963c-111">The Skycure admin username is an e-mail account that must be a valid user account in the Azure Active Directory, otherwise the login will fail.</span></span> <span data-ttu-id="c963c-112">Skycure verwendet Azure Active Directory zum Authentifizieren des Administratorbenutzernamens mithilfe von einmaligem Anmelden (SSO).</span><span class="sxs-lookup"><span data-stu-id="c963c-112">Skycure uses Azure Active Directory to authenticate its admin username using Single Sign On (SSO).</span></span>

3.  <span data-ttu-id="c963c-113">Wechseln Sie zu **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection** (Einstellungen > Geräteverwaltungsintegrationen > EMM-Integrationsauswahl), wählen Sie **Microsoft Intune** aus, und speichern Sie dann Ihre Auswahl.</span><span class="sxs-lookup"><span data-stu-id="c963c-113">Go to **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choose **Microsoft Intune**, then save your selection.</span></span>

4.  <span data-ttu-id="c963c-114">Klicken Sie auf den Link **Integration setup files** (Integrationssetupdateien), und speichern Sie die generierte \*.zip-Datei.</span><span class="sxs-lookup"><span data-stu-id="c963c-114">Click on the **Integration setup files** link and save the generated \*.zip file.</span></span> <span data-ttu-id="c963c-115">Die ZIP-Datei enthält die Datei **skycure\_configuration.plist**, die zum Erstellen der iOS-App-Konfigurationsrichtlinie im klassischen Intune-Portal verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c963c-115">The .zip file contains the **skycure\_configuration.plist** file, which will be used to create the iOS app configuration policy in the Intune classic portal.</span></span>

![Skycure-Integrationssetupdateien](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a><span data-ttu-id="c963c-117">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c963c-117">Next steps</span></span>

[<span data-ttu-id="c963c-118">Hinzufügen und Zuweisen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c963c-118">Add and assign Skycure apps, Microsoft Authenticator app and the iOS configuration policy</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
