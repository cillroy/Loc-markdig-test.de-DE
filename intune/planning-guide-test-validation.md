---
title: "Testen und Überprüfen von Intune"
description: "Die Details, die Sie beim Testen und Überprüfen einer Nur-Cloud-Lösung in Ihrer Umgebung bedenken sollten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4f82ee0c-4bd6-4623-9b10-9249d316ccf5
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.openlocfilehash: f10b4b0e7c48e921eb92392edf95bfcfaa83db9f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="intune-testing-and-validation"></a><span data-ttu-id="28ba2-103">Testen und Überprüfen von Intune</span><span class="sxs-lookup"><span data-stu-id="28ba2-103">Intune testing and validation</span></span>

<span data-ttu-id="28ba2-104">Die Testphase tritt jeweils während und nach der Implementierungsphase auf.</span><span class="sxs-lookup"><span data-stu-id="28ba2-104">The testing phase occurs both during and after the implementation phase.</span></span> <span data-ttu-id="28ba2-105">Sie müssen Konten, Gruppen und Geräte für Testzwecke aller erforderlichen IT- (Administrator) und Endbenutzerszenarios (Anwendungsfall) testen, die Sie zuvor angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="28ba2-105">You need test accounts, groups, and devices for testing all required IT (admin) and end user (use case) scenarios you have previously identified.</span></span>

<span data-ttu-id="28ba2-106">Es wird empfohlen, Ihre IT-Support- und Helpdeskmitarbeiter in die Testphase einzubeziehen, damit sie eine Supportdokumentation erstellen und sich mit der Unterstützung des Produkts vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="28ba2-106">We recommend that you incorporate your IT support and helpdesk staff in the testing phase so that support documentation is created, and the IT support and helpdesk staff become comfortable supporting the product.</span></span> <span data-ttu-id="28ba2-107">Wenn eine Komponente oder ein Szenario auf der Grundlage der Anwendungsfälle nicht funktioniert, stellen Sie sicher, dass die notwendigen Änderungen dokumentiert werden. Geben Sie dabei den Grund für die Änderung an.</span><span class="sxs-lookup"><span data-stu-id="28ba2-107">If a component or scenario does not function based on the use cases, make sure to document the necessary changes, and include the reason a change was made.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="28ba2-108">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="28ba2-108">Before you begin</span></span>

<span data-ttu-id="28ba2-109">Wir empfehlen, die folgenden Schritte zu dokumentieren:</span><span class="sxs-lookup"><span data-stu-id="28ba2-109">We recommend that you document the following:</span></span>

-   <span data-ttu-id="28ba2-110">**Testkriterien:** Identifizieren Sie die Benchmarks, anhand derer die Messung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="28ba2-110">**Test criteria:** Identify the benchmarks to be measured against.</span></span>

-   <span data-ttu-id="28ba2-111">**Entwurfskomponenten:** Müssen in mindestens einem Testkriterium vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="28ba2-111">**Design components:** Must exist in at least one testing criteria.</span></span>

<span data-ttu-id="28ba2-112">Wenn eine Entwurfskomponente nicht in mindestens einem auf eine Anforderung oder ein Szenario ausgerichteten Testkriterium vorhanden ist, überlegen Sie, ob die Entwurfskomponente erforderlich ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="28ba2-112">If a design component does not exist in at least one test criteria that aligns to a requirement or scenario, consider whether the design component is required or not.</span></span> <span data-ttu-id="28ba2-113">Stellen Sie darüber hinaus sicher, dass die folgenden Elemente vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="28ba2-113">In addition, make sure to have the following items:</span></span>

-   <span data-ttu-id="28ba2-114">**Konten:** Testkonten, die für EMS und Office 365 lizenziert sind, um alle Anwendungsszenarios testen zu können.</span><span class="sxs-lookup"><span data-stu-id="28ba2-114">**Accounts:** Test accounts that are licensed for EMS and Office 365 to test all use-case scenarios.</span></span>

-   <span data-ttu-id="28ba2-115">**Geräte:** Testgeräte, die zurückgesetzt oder auf Werkseinstellungen zurückgesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="28ba2-115">**Devices:** Test devices that can be wiped or reset to factory defaults.</span></span>

-   <span data-ttu-id="28ba2-116">**Integrationskomponenten:** Alle Integrationskomponenten (Certificate Connector, dienstübergreifender Intune-Connector für gehostetes Exchange und Intune-Connector für lokale Exchange-Umgebungen) müssen bei Bedarf installiert und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="28ba2-116">**Integration components:** All integration components (certificate connector, Intune service-to-service connector for hosted Exchange, and Intune on-premises Exchange connector) should be installed and configured if needed.</span></span>

<span data-ttu-id="28ba2-117">Sie benötigen möglicherweise Entwurfsänderungen, um unvorhergesehene Probleme zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="28ba2-117">You may need design changes to accommodate unforeseen difficulties.</span></span> <span data-ttu-id="28ba2-118">Darüber hinaus müssen alle Entwurfsänderungen vollständig zusammen mit der jeweiligen Begründung dokumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="28ba2-118">In addition, all design changes should be fully documented with the reason for each change.</span></span> <span data-ttu-id="28ba2-119">Hier sehen Sie ein Beispiel für die Veranschaulichung einer Änderung:</span><span class="sxs-lookup"><span data-stu-id="28ba2-119">Here's an example to illustrate what a change could be:</span></span>

<blockquote><span data-ttu-id="28ba2-120">Sie stellen fest, dass Sie die Anforderungen des Registrierungsdiensts für Netzwerkgeräte (SCEP) nicht erfüllen. Zudem erfahren Sie, dass die VPN- und WLAN-Profile mit einer Stammzertifizierungsstelle konfiguriert werden können, die dieselben Anforderungen ohne eine SCEP-Implementierung erfüllt.</span><span class="sxs-lookup"><span data-stu-id="28ba2-120">You realize that you don’t meet the requirements of Network Device Enrollment Service (NDES), and you also learn that the VPN and Wi-Fi profiles can be configured with a root CA satisfying the same requirements without an NDES implementation.</span></span></blockquote>

<span data-ttu-id="28ba2-121">Möglicherweise gibt es Herausforderungen oder Probleme, die technische Hilfe oder eine spezielle Problembehandlung während des Test- und Überprüfungsprozesses erfordern.</span><span class="sxs-lookup"><span data-stu-id="28ba2-121">You might experience challenges or issues that require technical guidance or specialized troubleshooting during the testing and validation process.</span></span> <span data-ttu-id="28ba2-122">Es wird empfohlen, dass Sie sich an die Microsoft-Supportkanäle wenden.</span><span class="sxs-lookup"><span data-stu-id="28ba2-122">We recommend that you seek assistance through the Microsoft support channels.</span></span>

-   [<span data-ttu-id="28ba2-123">Informationen zum Erhalten von Intune-Support</span><span class="sxs-lookup"><span data-stu-id="28ba2-123">Learn how to get Intune support</span></span>](get-support.md)

-   [<span data-ttu-id="28ba2-124">Kontaktieren des telefonischen Supports für Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="28ba2-124">Contact assisted phone support for Microsoft Intune</span></span>](/intune-classic/troubleshoot/contact-assisted-phone-support-for-microsoft-intune)

## <a name="functional-validation-testing"></a><span data-ttu-id="28ba2-125">Test zur Funktionsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="28ba2-125">Functional validation testing</span></span>

<span data-ttu-id="28ba2-126">Bei der Funktionsüberprüfung werden die einzelnen Komponenten und die Konfiguration getestet, um deren ordnungsgemäße Funktionsweise zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="28ba2-126">Functional validation consists of testing each component and configuration to determine if it is working correctly.</span></span> <span data-ttu-id="28ba2-127">Ein Beispiel für einen Überprüfungstest ist in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="28ba2-127">An example of validation testing is in the table below.</span></span>

![Abschnitt 9 Tabelle 1](./media/section-9-image-1-table.PNG)

## <a name="use-case-validation-testing"></a><span data-ttu-id="28ba2-129">Test zur Anwendungsfallüberprüfung</span><span class="sxs-lookup"><span data-stu-id="28ba2-129">Use-case validation testing</span></span>

<span data-ttu-id="28ba2-130">Führen Sie Tests zur Anwendungsfallüberprüfung aus, um sicherzustellen, dass die Szenarios vollständig und funktionsfähig sind.</span><span class="sxs-lookup"><span data-stu-id="28ba2-130">Perform use-case validation testing to verify the scenarios are complete and functional.</span></span> <span data-ttu-id="28ba2-131">Es gibt zwei Arten von Anwendungsszenarios: IT-Administrator und Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="28ba2-131">There are two types of use-case scenarios: IT admin and end user.</span></span>

### <a name="it-admin"></a><span data-ttu-id="28ba2-132">IT-Administrator</span><span class="sxs-lookup"><span data-stu-id="28ba2-132">IT admin</span></span>

<span data-ttu-id="28ba2-133">Führen Sie Überprüfungstests für IT-Administratoren aus, um sicherzustellen, dass administrative Aktionen für ein Gerät oder einen Benutzer ordnungsgemäß funktionieren.</span><span class="sxs-lookup"><span data-stu-id="28ba2-133">Perform IT admin validation testing to validate that administrative actions performed on a device or user function correctly.</span></span> <span data-ttu-id="28ba2-134">Es folgt ein Beispiel für ein umfassendes Überprüfungsszenario für IT-Administratoren.</span><span class="sxs-lookup"><span data-stu-id="28ba2-134">Below is an example of an IT admin end-to-end validation scenario.</span></span>

![Abschnitt 9 Tabelle 2](./media/section-9-image-2-table.PNG)

### <a name="end-user"></a><span data-ttu-id="28ba2-136">Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="28ba2-136">End user</span></span>

<span data-ttu-id="28ba2-137">Führen Sie Überprüfungstests für Endbenutzer aus, um sicherzustellen, dass das Endbenutzererlebnis den Erwartungen entspricht und in der gesamten Benutzerkommunikation korrekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="28ba2-137">Perform end-user validation testing to validate that the end-user experience is as expected and presented correctly in all user communications.</span></span> <span data-ttu-id="28ba2-138">Es ist wichtig, zu überprüfen, dass die Endbenutzererfahrung richtig ist.</span><span class="sxs-lookup"><span data-stu-id="28ba2-138">It is important to validate that the end-user experience is correct.</span></span> <span data-ttu-id="28ba2-139">Wenn Sie dies nicht überprüfen können, kann dies zu einer niedrigen Akzeptanz und höheren Volumen an Helpdesk-Aufrufen führen.</span><span class="sxs-lookup"><span data-stu-id="28ba2-139">If you fail to validate, it can lead to lower adoption rates and higher volumes of helpdesk calls.</span></span>

![Abschnitt 9 Tabelle 3](./media/section-9-image-3-table.PNG)

## <a name="next-steps"></a><span data-ttu-id="28ba2-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28ba2-141">Next steps</span></span>

<span data-ttu-id="28ba2-142">Nachdem Sie Ihre Intune-Funktionen und -Anwendungsszenarios getestet und überprüft haben, sind Sie für den [Intune-Rollout in die Produktion](planning-guide-rollout-plan.md) bereit.</span><span class="sxs-lookup"><span data-stu-id="28ba2-142">Now that you have tested and validated your Intune functional and use-case scenarios, you're ready for your [Intune production rollout](planning-guide-rollout-plan.md).</span></span>

<span data-ttu-id="28ba2-143">Weitere Planungsvorlagen und Informationen finden Sie in den [zusätzlichen Ressourcen](planning-guide-resources.md).</span><span class="sxs-lookup"><span data-stu-id="28ba2-143">See [additional resources](planning-guide-resources.md) for more planning templates and information.</span></span>
