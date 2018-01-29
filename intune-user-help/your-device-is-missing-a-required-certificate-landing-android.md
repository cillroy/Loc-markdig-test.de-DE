---
title: "Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: d5c2b5202b0ac69d18dff5b12be3c04f60062dee
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="your-device-is-missing-a-required-certificate"></a><span data-ttu-id="0438e-102">Auf Ihrem Gerät ist ein erforderliches Zertifikat nicht vorhanden</span><span class="sxs-lookup"><span data-stu-id="0438e-102">Your device is missing a required certificate</span></span>

## <a name="whats-a-certificate"></a><span data-ttu-id="0438e-103">Was ist ein Zertifikat?</span><span class="sxs-lookup"><span data-stu-id="0438e-103">What's a certificate?</span></span>

<span data-ttu-id="0438e-104">Die [Kryptografie](https://technet.microsoft.com/library/cc962030.aspx) ist die Wissenschaft der Verschlüsselung von Informationen.</span><span class="sxs-lookup"><span data-stu-id="0438e-104">[Cryptography](https://technet.microsoft.com/library/cc962030.aspx) is the science of providing security for information.</span></span> <span data-ttu-id="0438e-105">Traditionell wird Kryptografie zur Weitergabe codierter Nachrichten verwendet, um [sicherzustellen, dass die Kommunikation geheim bleibt](https://technet.microsoft.com/library/cc962019.aspx).</span><span class="sxs-lookup"><span data-stu-id="0438e-105">Traditionally, cryptography has been used to pass coded messages to [ensure that communication is kept secret](https://technet.microsoft.com/library/cc962019.aspx).</span></span> <span data-ttu-id="0438e-106">In ihrer einfachsten Form werden bei der Kryptografie Buchstaben ersetzt oder vertauscht, um eine nicht lesbare, unverständliche oder verborgene Nachricht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0438e-106">In its simpliest form, cryptography substitutes or transposes letters to create a coded message into an unreadable, scrambled, or hidden message.</span></span> <span data-ttu-id="0438e-107">Nur jemand mit einem Decodierungsschlüssel bzw. _Zertifikat_ kann die codierte Nachricht wieder in ihre ursprüngliche, lesbare Form umwandeln.</span><span class="sxs-lookup"><span data-stu-id="0438e-107">Only someone with a decoding key, or _certificate_, can convert the coded message back into its original, readable form.</span></span> <span data-ttu-id="0438e-108">Ihr Android-Gerät verwendet Zertifikate für Intune, um sicherzustellen, dass die Kommunikation zwischen Ihrem Gerät und Ihren Organisationsressourcen – z.B. E-Mails oder Dokumenten – während der drahtlosen Übertragung vom einen bis zum anderen Ende sicher und geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="0438e-108">Your Android device uses certificates with Intune to make sure that communications between your device and your organizational resources, such as email and documents, are kept safe from one end, through the air, to the other.</span></span>

## <a name="fixing-certificate-issues"></a><span data-ttu-id="0438e-109">Beheben von Problemen mit Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="0438e-109">Fixing certificate issues</span></span>

<span data-ttu-id="0438e-110">Wenn Ihr Android-Gerät nicht bei Intune registriert ist und ein bestimmtes Zertifikat fehlt, das vom Support Ihres Unternehmens verlangt wird, können Sie sich nicht bei der Unternehmensportal-App anmelden.</span><span class="sxs-lookup"><span data-stu-id="0438e-110">If your Android device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your company support, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="0438e-111">Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:</span><span class="sxs-lookup"><span data-stu-id="0438e-111">When you try to sign in, you'll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="0438e-113">Zunächst sollten Sie ermitteln, ob auf Ihrem Gerät [ein Zertifikat fehlt, das normalerweise auf dem Gerät vorinstalliert ist](your-device-is-missing-a-preinstalled-certificate-android.md).</span><span class="sxs-lookup"><span data-stu-id="0438e-113">The first step you should try is to see if your device is [missing a certificate that usually comes preinstalled on it](your-device-is-missing-a-preinstalled-certificate-android.md).</span></span>

<span data-ttu-id="0438e-114">Wenn dies nicht funktioniert, fordert der Support Ihres Unternehmens Sie möglicherweise auf, [ein zweites Zertifikat zu installieren, um die Sicherheit zu erhöhen](your-device-is-missing-an-IT-required-certificate-android.md).</span><span class="sxs-lookup"><span data-stu-id="0438e-114">If this doesn't work, your company support could [require you to install a second certificate for additional security](your-device-is-missing-an-IT-required-certificate-android.md).</span></span>

<span data-ttu-id="0438e-115">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="0438e-115">Still need help?</span></span> <span data-ttu-id="0438e-116">Kontaktieren Sie den Support Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="0438e-116">Contact your company support.</span></span> <span data-ttu-id="0438e-117">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="0438e-117">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
