---
title: "Registrierungsoptionen für Intune"
description: 
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cf4ad6d4-423f-4826-ab8d-6eb7a7cfb559
ms.openlocfilehash: 22efa23e989ed949d22c3c25b2ea4d37559b0a25
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enrollment-options-for-intune"></a><span data-ttu-id="1c28b-102">Registrierungsoptionen für Intune</span><span class="sxs-lookup"><span data-stu-id="1c28b-102">Enrollment options for Intune</span></span>

<span data-ttu-id="1c28b-103">Als Intune-Administrator können Sie die Geräteregistrierung konfigurieren, um Benutzer zu unterstützen und Intune-Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c28b-103">As an Intune admin, you can configure device enrollment to help users and enable Intune capabilities.</span></span>  <span data-ttu-id="1c28b-104">Intune umfasst folgende Registrierungsoptionen:</span><span class="sxs-lookup"><span data-stu-id="1c28b-104">Intune includes the following enrollment options:</span></span>

## <a name="terms-and-conditions"></a><span data-ttu-id="1c28b-105">Nutzungsbedingungen</span><span class="sxs-lookup"><span data-stu-id="1c28b-105">Terms and conditions</span></span>

<span data-ttu-id="1c28b-106">Sie können festlegen, dass für Benutzer die Annahme der Geschäftsbedingungen Ihres Unternehmens erforderlich ist, bevor diese das Unternehmensportal verwenden können, um ihre Geräte zu registrieren und auf Ressourcen wie Unternehmens-Apps und -E-Mails zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1c28b-106">You can require that users accept your company's terms and conditions before they can use the Company Portal to enroll their devices and access resources like company apps and email.</span></span> <span data-ttu-id="1c28b-107">Die Konfiguration der Geschäftsbedingungen ist optional.</span><span class="sxs-lookup"><span data-stu-id="1c28b-107">Configuration of terms and conditions is optional.</span></span> <span data-ttu-id="1c28b-108">Weitere Informationen zu den [Nutzungsbedingungen](terms-and-conditions-create.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-108">Learn more about [terms and conditions](terms-and-conditions-create.md).</span></span>

## <a name="enrollment-restrictions"></a><span data-ttu-id="1c28b-109">Registrierungseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="1c28b-109">Enrollment restrictions</span></span>

<span data-ttu-id="1c28b-110">Sie können auswählen, ob die Geräteregistrierung beschränkt werden soll, und zwar durch:</span><span class="sxs-lookup"><span data-stu-id="1c28b-110">You can choose to restrict device enrollment by:</span></span>
- <span data-ttu-id="1c28b-111">Geräteplattform</span><span class="sxs-lookup"><span data-stu-id="1c28b-111">Device platform</span></span>
- <span data-ttu-id="1c28b-112">Anzahl von Geräten pro Benutzer</span><span class="sxs-lookup"><span data-stu-id="1c28b-112">Number of devices per user</span></span>
- <span data-ttu-id="1c28b-113">Blockieren persönlicher Geräte</span><span class="sxs-lookup"><span data-stu-id="1c28b-113">Block personal devices</span></span>

<span data-ttu-id="1c28b-114">Weitere Informationen zu [Registrierungseinschränkungen](enrollment-restrictions-set.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-114">Learn more about [enrollment restrictions](enrollment-restrictions-set.md).</span></span>

## <a name="enable-apple-device-enrollment"></a><span data-ttu-id="1c28b-115">Aktivieren der Apple-Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="1c28b-115">Enable Apple device enrollment</span></span>

<span data-ttu-id="1c28b-116">Für die iOS- und macOS-Geräteregistrierung ist ein MDM-Push-Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1c28b-116">An MDM push certificate is required for iOS and macOS device enrollment.</span></span> <span data-ttu-id="1c28b-117">Weitere Informationen zu [MDM-Push-Zertifikaten](apple-mdm-push-certificate-get.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-117">Learn more about [MDM push certificates](apple-mdm-push-certificate-get.md).</span></span>

## <a name="corporate-identifiers"></a><span data-ttu-id="1c28b-118">Unternehmensbezeichner</span><span class="sxs-lookup"><span data-stu-id="1c28b-118">Corporate identifiers</span></span>

<span data-ttu-id="1c28b-119">Sie können IMEI-Nummern (IMEI = International Mobile Equipment Identifier) und Seriennummern auflisten, um unternehmenseigene Geräte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1c28b-119">You can list international mobile equipment identifier (IMEI) numbers and serial numbers to identify corporate-owned devices.</span></span> <span data-ttu-id="1c28b-120">Weitere Informationen zu [Unternehmensbezeichnern](corporate-identifiers-add.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-120">Learn more about [corporate identifiers](corporate-identifiers-add.md).</span></span>
## <a name="multi-factor-authentication"></a><span data-ttu-id="1c28b-121">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1c28b-121">Multi-factor authentication</span></span>

<span data-ttu-id="1c28b-122">Sie können Benutzer dazu auffordern, eine zusätzliche Überprüfungsmethode wie eine Telefonnummer, eine PIN oder biometrische Daten zu verwenden, wenn sie ein Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="1c28b-122">You can require users to use an additional verification method, such as a phone, PIN or biometric data, when they enroll a device.</span></span> <span data-ttu-id="1c28b-123">Erfahren Sie mehr über die [mehrstufige Authentifizierung](multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-123">Learn more about [multi-factor authentication](multi-factor-authentication.md).</span></span>

## <a name="device-enrollment-manager"></a><span data-ttu-id="1c28b-124">Geräteregistrierungs-Manager</span><span class="sxs-lookup"><span data-stu-id="1c28b-124">Device enrollment manager</span></span>
<span data-ttu-id="1c28b-125">Sie können Benutzer zu Geräteregistrierungs-Managern machen.</span><span class="sxs-lookup"><span data-stu-id="1c28b-125">You can make users device enrollment managers.</span></span>  <span data-ttu-id="1c28b-126">DEM-Benutzer (DEM = Device Enrollment Manager, Geräteregistrierungs-Manager) können eine große Anzahl mobiler Geräte mit einem einzelnen Benutzerkonto registrieren.</span><span class="sxs-lookup"><span data-stu-id="1c28b-126">DEM users can enroll large numbers of mobile devices with a single user account.</span></span> <span data-ttu-id="1c28b-127">Das DEM-Konto kann bis zu 1.000 Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="1c28b-127">The device enrollment manager (DEM) account can enroll up to 1,000 devices.</span></span> <span data-ttu-id="1c28b-128">Weitere Informationen zu [Geräteregistrierungs-Managern](device-enrollment-manager-enroll.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-128">Learn more about [device enrollment managers](device-enrollment-manager-enroll.md).</span></span>

## <a name="device-categories"></a><span data-ttu-id="1c28b-129">Gerätekategorien</span><span class="sxs-lookup"><span data-stu-id="1c28b-129">Device categories</span></span>

<span data-ttu-id="1c28b-130">Sie können mithilfe von Gerätekategorien basierend auf definierten Kategorien automatisch Geräte zu Gruppen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c28b-130">You can use device categories to automatically add devices to groups based on categories that you define.</span></span> <span data-ttu-id="1c28b-131">Durch die Organisation von Geräten in Gruppen wird die Verwaltung dieser Geräte vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="1c28b-131">Organizing devices into groups makes it easier for you to manage those devices.</span></span> <span data-ttu-id="1c28b-132">Weitere Informationen zu [Gerätekategorien](device-group-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="1c28b-132">Learn more about [device categories](device-group-mapping.md).</span></span>
