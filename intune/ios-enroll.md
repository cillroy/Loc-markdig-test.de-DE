---
title: "Auswählen, wie Windows-Geräte in Intune registriert werden"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Registrierung von Windows-Geräten in Microsoft Intune einrichten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 307f4b8d5ba27ce8136569e0c58711f9b1364d93
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-ios-devices-in-intune"></a><span data-ttu-id="81331-103">Registrieren von iOS-Geräten in Intune</span><span class="sxs-lookup"><span data-stu-id="81331-103">Enroll iOS devices in Intune</span></span>

<span data-ttu-id="81331-104">Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads und iPhones, was Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="81331-104">Intune enables mobile device management (MDM) of iPads and iPhones to give users access to company email and apps.</span></span>

<span data-ttu-id="81331-105">Als Intune-Administrator können Sie die Registrierung für iOS-Geräte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81331-105">As an Intune admin, you can enable enrollment for iOS devices.</span></span> <span data-ttu-id="81331-106">Sie können Benutzern erlauben, persönliche Geräte zu registrieren, was auch als BYOD-Registrierung („bring your own device“) bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="81331-106">You can allow users to enroll personally owned devices, known as "bring your own device" (BYOD) enrollment.</span></span> <span data-ttu-id="81331-107">Sie können auch die Registrierung von unternehmenseigenen Geräten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81331-107">You can also enable enrollment of company-owned devices.</span></span>

## <a name="prerequisites-for-ios-enrollment"></a><span data-ttu-id="81331-108">Voraussetzungen für die iOS-Registrierung</span><span class="sxs-lookup"><span data-stu-id="81331-108">Prerequisites for iOS enrollment</span></span>
<span data-ttu-id="81331-109">Bevor Sie iOS-Geräte aktivieren können, schließen Sie die folgenden Schritte ab:</span><span class="sxs-lookup"><span data-stu-id="81331-109">Before you can enable iOS devices, complete the following steps:</span></span>
- <span data-ttu-id="81331-110">[Einrichten von Intune:](setup-steps.md) Mit diesen Schritten wird Ihre Intune-Infrastruktur eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="81331-110">[Set up Intune](setup-steps.md) - These steps set up your Intune infrastructure.</span></span> <span data-ttu-id="81331-111">Besonders für die Geräteregistrierung ist es erforderlich, dass Sie [die MDM-Autorität festlegen](mdm-authority-set.md).</span><span class="sxs-lookup"><span data-stu-id="81331-111">In particular, device enrollment requires that you [set your MDM authority](mdm-authority-set.md).</span></span>
- <span data-ttu-id="81331-112">[Abrufen eines Apple-MDM-Push-Zertifikats:](apple-mdm-push-certificate-get.md) Apple benötigt ein Zertifikat, um die Verwaltung von iOS- und macOS-Geräten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="81331-112">[Get an Apple MDM Push certificate](apple-mdm-push-certificate-get.md) - Apple requires a certificate to enable management of iOS and macOS devices.</span></span>

## <a name="user-owned-ios-devices-byod"></a><span data-ttu-id="81331-113">iOS-Gerät im Besitz des Benutzers (BYOD)</span><span class="sxs-lookup"><span data-stu-id="81331-113">User-owned iOS devices (BYOD)</span></span>

<span data-ttu-id="81331-114">Benutzer können ihre persönlichen Geräte für die Intune-Verwaltung registrieren. Dies wird als „bring your own device“ oder BYOD bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="81331-114">You can let users enroll their personal devices for Intune management, know as "bring your own device" or BYOD.</span></span> <span data-ttu-id="81331-115">Sobald Sie über die Voraussetzungen verfügen und den Benutzern Lizenzen zugewiesen haben, können diese die Unternehmensportal-App für iOS aus dem App Store herunterladen und den Registrierungsanweisungen in der App folgen.</span><span class="sxs-lookup"><span data-stu-id="81331-115">Once you've completed the prerequisites and assigned users licenses, they can download the iOS Company Portal app from the App Store, and follow enrollment instructions in the app.</span></span>

## <a name="company-owned-ios-devices"></a><span data-ttu-id="81331-116">Unternehmenseigenes iOS-Gerät</span><span class="sxs-lookup"><span data-stu-id="81331-116">Company-owned iOS devices</span></span>
<span data-ttu-id="81331-117">Für Organisationen, die Geräte für Ihre Benutzer erwerben, unterstützt Intune die folgenden Methoden für die Registrierung von firmeneigenen iOS-Geräten:</span><span class="sxs-lookup"><span data-stu-id="81331-117">For organizations that purchase devices for their users, Intune supports the following iOS company-owned device enrollment methods:</span></span>

- <span data-ttu-id="81331-118">Apple-Programm zur Geräteregistrierung (DEP)</span><span class="sxs-lookup"><span data-stu-id="81331-118">Apple's Device Enrollment Program (DEP)</span></span>
- <span data-ttu-id="81331-119">Apple School Manager</span><span class="sxs-lookup"><span data-stu-id="81331-119">Apple School Manager</span></span>
- <span data-ttu-id="81331-120">Registrierung über den Setup-Assistenten für Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="81331-120">Apple Configurator Setup Assistant enrollment</span></span>
- <span data-ttu-id="81331-121">Apple Configurator – Direkte Registrierung</span><span class="sxs-lookup"><span data-stu-id="81331-121">Apple Configurator direct enrollment</span></span>

<span data-ttu-id="81331-122">Sie können firmeneigene iOS-Geräte auch mit einem Konto für den [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) registrieren.</span><span class="sxs-lookup"><span data-stu-id="81331-122">You can also enroll company-owned iOS devices with a [device enrollment manager](device-enrollment-manager-enroll.md) account.</span></span>

## <a name="device-enrollment-program"></a><span data-ttu-id="81331-123">Geräteregistrierungsprogramm</span><span class="sxs-lookup"><span data-stu-id="81331-123">Device Enrollment Program</span></span>
<span data-ttu-id="81331-124">Organisationen können iOS-Geräte über das Apple Device Enrollment Program (DEP) erwerben.</span><span class="sxs-lookup"><span data-stu-id="81331-124">Organizations can purchase iOS devices through Apple's Device Enrollment Program (DEP).</span></span> <span data-ttu-id="81331-125">Mit DEP können Sie drahtlos (Over The Air) ein Registrierungsprofil bereitstellen, das Geräte für die Verwaltung registriert.</span><span class="sxs-lookup"><span data-stu-id="81331-125">DEP lets you deploy an enrollment profile “over the air” to bring devices into management.</span></span> <span data-ttu-id="81331-126">Erfahren Sie mehr über das [Programm zur Geräteregistrierung](device-enrollment-program-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="81331-126">Learn more about [Device Enrollment Program](device-enrollment-program-enroll-ios.md).</span></span>

## <a name="apple-school-manager"></a><span data-ttu-id="81331-127">Apple School Manager</span><span class="sxs-lookup"><span data-stu-id="81331-127">Apple School Manager</span></span>
<span data-ttu-id="81331-128">Apple School Manager ist Programm zum Kauf von Geräten und deren Registrierung für Schulen.</span><span class="sxs-lookup"><span data-stu-id="81331-128">Apple School Manager is a device purchase and enrollment program for schools.</span></span> <span data-ttu-id="81331-129">Wie bei DEP können Sie ein Profil zum Registrieren von Geräten in der Verwaltung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="81331-129">Like DEP, you can deploy a profile to enroll devices in management.</span></span> <span data-ttu-id="81331-130">Erfahren Sie mehr über [Apple School Manager](apple-school-manager-set-up-ios.md).</span><span class="sxs-lookup"><span data-stu-id="81331-130">Learn more about [Apple School Manager](apple-school-manager-set-up-ios.md).</span></span>

## <a name="apple-configurator"></a><span data-ttu-id="81331-131">Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="81331-131">Apple Configurator</span></span>
<span data-ttu-id="81331-132">Sie können iOS-Geräte mit Apple Configurator auf einem Mac-Computer registrieren.</span><span class="sxs-lookup"><span data-stu-id="81331-132">You can enroll iOS devices with Apple Configurator running on a Mac computer.</span></span> <span data-ttu-id="81331-133">Um Geräte vorzubereiten, verbinden Sie sie über USB, und installieren Sie das Registrierungsprogramm.</span><span class="sxs-lookup"><span data-stu-id="81331-133">To prepare devices, you USB-connect them and install an enrollment profile.</span></span> <span data-ttu-id="81331-134">Sie können Geräte mit Apple Configurator auf zwei Arten registrieren:</span><span class="sxs-lookup"><span data-stu-id="81331-134">You can enroll devices with Apple Configurator in two ways:</span></span>
- <span data-ttu-id="81331-135">Registrierung per Setup-Assistent: Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück, bereitet es auf die Ausführung des Setup-Assistenten vor und installiert die Unternehmensrichtlinien für den neuen Benutzer des Geräts.</span><span class="sxs-lookup"><span data-stu-id="81331-135">Setup Assistant enrollment - Factory resets the device, prepares it to run Setup Assistant, and installs the company's policies for the device’s new user.</span></span>
- <span data-ttu-id="81331-136">Direkte Registrierung: Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="81331-136">Direct enrollment - Does not factory-reset the device and enrolls the device with a predefined policy.</span></span> <span data-ttu-id="81331-137">Diese Methode eignet sich für Geräte ohne Benutzeraffinität.</span><span class="sxs-lookup"><span data-stu-id="81331-137">This method is for devices with no user affinity.</span></span>

<span data-ttu-id="81331-138">Erfahren Sie mehr über die [Apple Configurator-Registrierung](apple-configurator-setup-assistant-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="81331-138">Learn more about [Apple Configurator enrollment](apple-configurator-setup-assistant-enroll-ios.md).</span></span>
