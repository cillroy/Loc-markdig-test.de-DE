---
title: "Schützen von App-Daten mithilfe von MAM-Richtlinien"
description: "In diesem Thema wird erläutert, wie Verwaltungsrichtlinien für mobile Anwendungen helfen können, Ihre Unternehmensdaten zu schützen, Datenverlust zu verhindern sowie persönliche und geschäftliche Daten voneinander zu trennen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ab6cd622-b738-4a63-9c91-56044aaafa6d
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cbaf7ed32d98dd8726bf8718e9f5884f4b20e7fa
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="protect-app-data-using-app-protection-policies-with-microsoft-intune"></a><span data-ttu-id="9a40c-103">Schützen von App-Daten mithilfe der App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9a40c-103">Protect app data using app protection policies with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="how-you-can-protect-app-data"></a><span data-ttu-id="9a40c-104">Wie Sie Ihre App-Daten schützen können</span><span class="sxs-lookup"><span data-stu-id="9a40c-104">How you can protect app data</span></span>
<span data-ttu-id="9a40c-105">Ihre Mitarbeiter verwenden mobile Geräte für private und berufliche Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="9a40c-105">Your employees use mobile devices for both personal and work tasks.</span></span> <span data-ttu-id="9a40c-106">Sie möchten einerseits die Produktivität Ihrer Mitarbeiter sicherstellen, möchten andererseits aber auch Datenverlust verhindern, sei er beabsichtigt oder unbeabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="9a40c-106">While you're making sure your employees can be productive, you also want to prevent data loss—intentional and unintentional.</span></span>  <span data-ttu-id="9a40c-107">Darüber hinaus möchten Sie Unternehmensdaten schützen können, auf die Mitarbeiter mit Geräten zugreifen, die nicht durch Sie verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-107">In addition, you want to have the ability to protect company data that employees access by using devices that you don't manage.</span></span>

<span data-ttu-id="9a40c-108">Sie können Intune-App-Schutzrichtlinien verwenden, um Ihre Unternehmensdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-108">You can use Intune app protection policies to help protect your company’s data.</span></span> <span data-ttu-id="9a40c-109">Da Intune-App-Schutzrichtlinien **unabhängig von Lösungen für die Verwaltung mobiler Geräte (MDM) einsetzbar sind**, können Sie MAM mit oder ohne Registrierung der Geräte bei einer Geräteverwaltungslösung zum Schutz Ihrer Unternehmensdaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-109">Because Intune App protection policies can be used **independent of any mobile device management (MDM) solution**, you can use MAM to protect your company’s data with or without enrolling devices in a device management solution.</span></span> <span data-ttu-id="9a40c-110">Durch die Implementierung von **Richtlinien auf App-Ebene** können Sie den Zugriff auf Unternehmensressourcen einschränken und Daten im Zuständigkeitsbereich der IT-Abteilung halten.</span><span class="sxs-lookup"><span data-stu-id="9a40c-110">By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.</span></span>

<span data-ttu-id="9a40c-111">Sie können App-Schutzrichtlinien für Apps konfigurieren, die auf Geräten ausgeführt werden, die folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="9a40c-111">You can configure app protection policies for apps running on devices that are:</span></span>

-   <span data-ttu-id="9a40c-112">**Registriert bei Microsoft Intune:** Die Geräte in dieser Kategorie sind in der Regel unternehmenseigene Geräte.</span><span class="sxs-lookup"><span data-stu-id="9a40c-112">**Enrolled in Microsoft Intune:** The devices in this category are typically corporate-owned devices.</span></span>

-   <span data-ttu-id="9a40c-113">**Registriert bei einer MDM-Lösung eines Drittanbieters:** Die Geräte in dieser Kategorie sind in der Regel unternehmenseigene Geräte.</span><span class="sxs-lookup"><span data-stu-id="9a40c-113">**Enrolled in a third-party MDM solution:** The devices in this category are typically corporate-owned devices.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a40c-114">Die Verwendung von App-Schutzrichtlinien mit der mobilen Anwendungsverwaltung von Drittanbietern oder sicheren Containerlösungen wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-114">We don't recommend using app protection policies with third-party mobile application management or secure container solutions.</span></span>

-   <span data-ttu-id="9a40c-115">**Nicht bei einer MDM-Lösung registriert:** Die Geräte in dieser Kategorie sind in der Regel mitarbeitereigene Geräte, die weder bei Intune noch anderen MDM-Lösungen registriert sind oder dort verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-115">**Not enrolled in any MDM solution:** The devices in this category are typically employee-owned devices that are not managed or enrolled in Intune or other MDM solutions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9a40c-116">Sie können App-Schutzrichtlinien für mobile Office-Apps erstellen, die eine Verbindung mit Office 365-Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-116">You can create app protection policies for Office mobile apps that connect to Office 365 services.</span></span> <span data-ttu-id="9a40c-117">App-Schutzrichtlinien werden nicht für Apps unterstützt, die eine Verbindung mit Exchange lokal, Skype for Business oder SharePoint-Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-117">App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.</span></span>

## <a name="benefits-of-using-app-protection-policies"></a><span data-ttu-id="9a40c-118">Vorteile der Verwendung von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9a40c-118">Benefits of using app protection policies</span></span>

-   <span data-ttu-id="9a40c-119">**Sie erleichtern den Schutz Ihrer Unternehmensdaten auf App-Ebene.**</span><span class="sxs-lookup"><span data-stu-id="9a40c-119">**They help protect your company data at the app level.**</span></span> <span data-ttu-id="9a40c-120">Da die Verwaltung von mobilen Anwendungen keine Geräteverwaltung voraussetzt, können Sie Unternehmensdaten auf verwalteten und auf unverwalteten Geräten schützen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-120">Because mobile application management doesn't require device management, you can protect company data on both managed and unmanaged devices.</span></span> <span data-ttu-id="9a40c-121">Bei der Verwaltung wird die Benutzeridentität in den Mittelpunkt gestellt, wodurch sich die Geräteverwaltung erübrigt.</span><span class="sxs-lookup"><span data-stu-id="9a40c-121">The management is centered on the user identity, which removes the requirement for device management.</span></span>

-   <span data-ttu-id="9a40c-122">**Die Produktivität der Benutzer wird nicht beeinträchtigt, und die Richtlinien werden nicht angewendet, wenn Sie die App im privaten Kontext verwenden.**</span><span class="sxs-lookup"><span data-stu-id="9a40c-122">**User productivity is not impacted, and the policies aren't applied when you're using the app in a personal context.**</span></span> <span data-ttu-id="9a40c-123">Die Richtlinien werden nur auf den beruflichen Kontext angewendet, wodurch Sie die Möglichkeit haben, Unternehmensdaten zu schützen, ohne dass private Daten einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-123">The policies are applied only in a work context, which gives you the ability to protect company data without touching personal data.</span></span>

<span data-ttu-id="9a40c-124">Es gibt weitere Vorteile bei der Verwendung einer MDM mit App-Schutzrichtlinien, und Unternehmen können MAM gleichzeitig mit und ohne MDM verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-124">There are additional benefits to using MDM with app protection policies, and companies can use MAM with and without MDM at the same time.</span></span> <span data-ttu-id="9a40c-125">So kann ein Mitarbeiter beispielsweise ein unternehmenseigenes Smartphone und ein privates Tablet verwenden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-125">For example, an employee might use a company-issued phone, as well as a personal tablet.</span></span> <span data-ttu-id="9a40c-126">In diesem Fall wird das unternehmenseigene Smartphone in einer MDM registriert und von App-Schutzrichtlinien geschützt, während das private Geräte nur mit App-Schutzrichtlinien geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="9a40c-126">In this case, the company phone is enrolled in MDM and protected by app protection policies, and the personal device is protected by app protection policies only.</span></span>

- <span data-ttu-id="9a40c-127">**Eine MDM-Lösung stellt sicher, dass das Gerät geschützt ist.**</span><span class="sxs-lookup"><span data-stu-id="9a40c-127">**MDM makes sure that the device is protected.**</span></span> <span data-ttu-id="9a40c-128">So können Sie beispielsweise die Eingabe einer PIN für den Zugriff auf das Gerät anfordern, oder Sie können verwaltete Apps auf dem Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-128">For example, you can require a PIN to access the device, or you can deploy managed apps to the device.</span></span> <span data-ttu-id="9a40c-129">Sie können Apps auch über die MDM-Lösung auf Geräten bereitstellen, um mehr Kontrolle über die App-Verwaltung zu haben.</span><span class="sxs-lookup"><span data-stu-id="9a40c-129">You can also deploy apps to devices through your MDM solution to give you more control over app management.</span></span>

- <span data-ttu-id="9a40c-130">**App-Schutzrichtlinien stellen sicher, dass Schutzfunktionen auf App-Ebene vorhanden sind**.</span><span class="sxs-lookup"><span data-stu-id="9a40c-130">**App protection policies make sure that the app-layer protections are in place.**</span></span> <span data-ttu-id="9a40c-131">So können Sie beispielsweise über eine Richtlinie verfügen, die eine PIN anfordert, wenn eine App im beruflichen Kontext geöffnet werden soll, und verhindert, dass Daten zwischen Apps ausgetauscht werden oder dass App-Daten des Unternehmens an einem privaten Speicherort gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-131">For example, you can have a policy that requires a PIN to open an app in a work context, prevents data from being shared between apps, and prevents company app data from being saved to a personal storage location.</span></span>

## <a name="devices-that-support-mam"></a><span data-ttu-id="9a40c-132">Geräte, die MAM unterstützen</span><span class="sxs-lookup"><span data-stu-id="9a40c-132">Devices that support MAM</span></span>
<span data-ttu-id="9a40c-133">App-Schutzrichtlinien werden zurzeit für Folgendes unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9a40c-133">App protection policies are currently supported on:</span></span>
-   <span data-ttu-id="9a40c-134">iOS 8.1 oder höher</span><span class="sxs-lookup"><span data-stu-id="9a40c-134">iOS 8.1 or later</span></span>
-   <span data-ttu-id="9a40c-135">Android 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="9a40c-135">Android 4 or later</span></span>

>[!NOTE]
><span data-ttu-id="9a40c-136">Windows-Geräte werden in der MAM nicht ohne Registrierungsszenario unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9a40c-136">Windows devices are not supported in the MAM without enrollment scenario.</span></span> <span data-ttu-id="9a40c-137">Wenn Sie jedoch Windows 10-Geräte mit Intune registrieren, können Sie Windows Information Protection verwenden, das ähnliche Funktionen bietet.</span><span class="sxs-lookup"><span data-stu-id="9a40c-137">However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality.</span></span> <span data-ttu-id="9a40c-138">Weitere Informationen finden Sie unter [Schutz von Unternehmensdaten mit Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="9a40c-138">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>


##  <a name="how-app-protection-policies-protect-app-data"></a><span data-ttu-id="9a40c-139">So schützen App-Schutzrichtlinien Ihre App-Daten</span><span class="sxs-lookup"><span data-stu-id="9a40c-139">How app protection policies protect app data</span></span>

###  <a name="apps-without-app-protection-policies"></a><span data-ttu-id="9a40c-140">Apps ohne App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9a40c-140">Apps without app protection policies</span></span>

![Die Abbildung zeigt, wie Daten ungehindert zwischen Apps verschoben werden können, wenn keine App-Schutzrichtlinien angewendet werden.](../media/Apps_without_MAM_policies.png)

<span data-ttu-id="9a40c-142">Wenn Sie Apps ohne Einschränkungen verwenden, können Unternehmensdaten und private Daten vermischt werden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-142">When you use apps without restrictions, company and personal data can get intermingled.</span></span> <span data-ttu-id="9a40c-143">Unternehmensdaten könnten damit an Speicherorten wie dem persönlichen Speicher abgelegt oder an Apps außerhalb Ihres Zuständigkeitsbereichs übermittelt werden, was zu Datenverlusten führen könnte.</span><span class="sxs-lookup"><span data-stu-id="9a40c-143">Company data might end up in locations like personal storage or might be transferred to apps outside of your purview, which could result in data loss.</span></span> <span data-ttu-id="9a40c-144">Die Pfeile im Diagramm zeigen die uneingeschränkte Datenbewegung zwischen Apps (geschäftlich und privat) und zu Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="9a40c-144">The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.</span></span>

### <a name="data-protection-with-app-protection-policies"></a><span data-ttu-id="9a40c-145">Datenschutz mit App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9a40c-145">Data protection with app protection policies</span></span>

![Das Bild zeigt, wie Unternehmensdaten durch die Anwendung von App-Schutzrichtlinien geschützt werden](../media/Apps_with_mobile_app_policies.png)

<span data-ttu-id="9a40c-147">Mit App-Schutzrichtlinien können Sie verhindern, dass Unternehmensdaten im lokalen Speicher des Geräts gespeichert werden. Außerdem können Sie das Verschieben von Daten in andere Apps einschränken, die nicht durch App-Schutzrichtlinien geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="9a40c-147">You can use app protection policies to prevent company data from saving to the local storage of the device, and to restrict data movement to other apps that aren't protected by app protection policies.</span></span> <span data-ttu-id="9a40c-148">Einstellungen für App-Schutzrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="9a40c-148">App protection policy settings include:</span></span>
- <span data-ttu-id="9a40c-149">Richtlinien zur Datenverschiebung wie **„Speichern unter“ verhindern**und **Ausschneiden, Kopieren und Einfügen einschränken**.</span><span class="sxs-lookup"><span data-stu-id="9a40c-149">Data relocation policies like **Prevent Save As** and **Restrict cut, copy, and paste**.</span></span>
- <span data-ttu-id="9a40c-150">Einstellungen von Zugriffsrichtlinien wie **Einfache PIN für den Zugriff erforderlich** und **Ausführen verwalteter Apps auf mit Jailbreak oder Rooting manipulierten Geräten blockieren**.</span><span class="sxs-lookup"><span data-stu-id="9a40c-150">Access policy settings like **Require simple PIN for access** and **Block managed apps from running on jailbroken or rooted devices**.</span></span>

### <a name="data-protection-with-app-protection-on-devices-that-are-managed-by-a-mdm-solution"></a><span data-ttu-id="9a40c-151">Schutz von Daten mit App-Schutzrichtlinien auf Geräten, die durch eine MDM-Lösung verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="9a40c-151">Data protection with app protection on devices that are managed by a MDM solution</span></span>

![Das Bild zeigt, wie App-Schutzrichtlinien auf BYOD-Geräten (Bring Your Own Devices) funktionieren](../media/MAM_BYOD_November.png)

<span data-ttu-id="9a40c-153">**Für Geräte, die in einer MDM-Lösung registriert sind**: Das Diagramm oben zeigt die Schutzebenen, die MDM-Richtlinien und App-Schutzichtlinien zusammen bieten.</span><span class="sxs-lookup"><span data-stu-id="9a40c-153">**For devices enrolled in an MDM solution**: The preceding diagram shows the layers of protection that MDM and app protection policies offer together.</span></span>

<span data-ttu-id="9a40c-154">Die MDM-Lösung:</span><span class="sxs-lookup"><span data-stu-id="9a40c-154">The MDM solution:</span></span>

-   <span data-ttu-id="9a40c-155">Registriert das Gerät.</span><span class="sxs-lookup"><span data-stu-id="9a40c-155">Enrolls the device.</span></span>

-   <span data-ttu-id="9a40c-156">Stellt Apps auf dem Gerät bereit.</span><span class="sxs-lookup"><span data-stu-id="9a40c-156">Deploys apps to the device.</span></span>

-   <span data-ttu-id="9a40c-157">Sorgt für kontinuierliche Gerätekompatibilität und -verwaltung.</span><span class="sxs-lookup"><span data-stu-id="9a40c-157">Provides ongoing device compliance and management.</span></span>

<span data-ttu-id="9a40c-158">**App-Schutzrichtlinien bieten Mehrwert wegen folgender Gründe:**</span><span class="sxs-lookup"><span data-stu-id="9a40c-158">**App protection policies add value because they:**</span></span>

-   <span data-ttu-id="9a40c-159">Sie tragen zum Schutz der Unternehmensdaten bei, indem der Zugriff durch Verbraucher-Apps und -Dienste verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="9a40c-159">Help protect company data from leaking to consumer apps and services.</span></span>

-   <span data-ttu-id="9a40c-160">Es werden Einschränkungen („Speichern unter“, Zwischenablage, PIN usw.) auf mobile Apps angewendet.</span><span class="sxs-lookup"><span data-stu-id="9a40c-160">Apply restrictions (save-as, clipboard, PIN, etc.) to mobile apps.</span></span>

-   <span data-ttu-id="9a40c-161">Unternehmensdaten können aus Apps entfernt werden, ohne die Apps vom Gerät zu löschen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-161">Wipe company data from apps without removing those apps from the device.</span></span>


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a><span data-ttu-id="9a40c-162">Schutz von Daten mit App-Schutzrichtlinien für Geräte ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="9a40c-162">Data protection with app protection policies for devices without enrollment</span></span>

![Das Bild zeigt, wie App-Schutzrichtlinien auf verwalteten Geräten funktionieren](../media/MAM_ManagedDevices_November.png)

<span data-ttu-id="9a40c-164">Das voranstehende Diagramm zeigt, wie Datenschutzrichtlinien auf App-Ebene ohne MDM funktionieren.</span><span class="sxs-lookup"><span data-stu-id="9a40c-164">The preceding diagram illustrates how data protection policies work at the app level without MDM.</span></span>

<span data-ttu-id="9a40c-165">Bei BYOD-Geräten, die nicht in einer MDM-Lösung registriert sind, können App-Schutzrichtlinien dazu beitragen, Unternehmensdaten auf App-Ebene zu schützen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-165">For BYOD devices that aren't enrolled in any MDM solution, app protection policies can help protect company data at the app level.</span></span>

<span data-ttu-id="9a40c-166">Es gibt jedoch einige Einschränkungen, die Sie kennen sollten:</span><span class="sxs-lookup"><span data-stu-id="9a40c-166">However, there are some limitations to be aware of:</span></span>

-   <span data-ttu-id="9a40c-167">Sie können auf dem Gerät keine Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-167">You can't deploy apps to the device.</span></span> <span data-ttu-id="9a40c-168">Der Benutzer muss die Apps aus dem Store beziehen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-168">The user has to get the apps from the store.</span></span>

-   <span data-ttu-id="9a40c-169">Sie können auf diesen Geräten keine Zertifikatprofile bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-169">You can't provision certificate profiles on these devices.</span></span>

-   <span data-ttu-id="9a40c-170">Sie können auf diesen Geräten keine unternehmensweiten WLAN- und VPN-Einstellungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="9a40c-170">You can't set up company Wi-Fi and VPN settings on these devices.</span></span>


## <a name="multi-identity"></a><span data-ttu-id="9a40c-171">Mehrere Identitäten</span><span class="sxs-lookup"><span data-stu-id="9a40c-171">Multi-identity</span></span>

<span data-ttu-id="9a40c-172">Apps, die mehrere Identitäten unterstützen, bieten Ihnen die Möglichkeit, verschiedene Konten (Geschäfts- und persönliche Konten) für den Zugriff auf die gleichen Apps zu verwenden. Hierbei werden App-Schutzrichtlinien nur angewendet, wenn die Apps im Arbeitskontext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9a40c-172">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>  

<span data-ttu-id="9a40c-173">Wenn ein Benutzer beispielsweise die OneDrive-App mit seinem Geschäftskonto startet, kann er die Dateien nicht an einen persönlichen Speicherort verschieben.</span><span class="sxs-lookup"><span data-stu-id="9a40c-173">For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location.</span></span> <span data-ttu-id="9a40c-174">Wenn der Benutzer OneDrive jedoch mit einem persönlichen Konto verwendet, kann er Daten ohne Einschränkung aus dem persönlichen OneDrive kopieren und verschieben.</span><span class="sxs-lookup"><span data-stu-id="9a40c-174">However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.</span></span>  

- <span data-ttu-id="9a40c-175">Erfahren Sie mehr über die Apps, die [die Verwaltung mobiler Anwendungen und mehrerer Identitäten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) mit Intune unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9a40c-175">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="9a40c-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9a40c-176">Next steps</span></span>
- [<span data-ttu-id="9a40c-177">Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9a40c-177">Get ready to configure app protection policies</span></span>](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

- [<span data-ttu-id="9a40c-178">Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="9a40c-178">Create and deploy app protection policies with Microsoft Intune</span></span>](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md)
