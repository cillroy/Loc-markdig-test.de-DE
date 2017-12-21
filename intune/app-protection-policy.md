---
title: Was sind App-Schutzrichtlinien?
titleSuffix: Azure portal
description: "In diesem Thema erfahren Sie, wie Sie die Daten Ihres Unternehmens mit App-Schutzrichtlinien von Microsoft Intune schützen.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/01/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1c086943-84a0-4d99-8295-490a2bc5be4b
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28c1f92aa4135708dd56fd3947aef739e22f64a4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="what-are-app-protection-policies"></a><span data-ttu-id="1117b-103">Was sind App-Schutzrichtlinien?</span><span class="sxs-lookup"><span data-stu-id="1117b-103">What are app protection policies?</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1117b-104">App-Schutzrichtlinien von Microsoft Intune helfen, Ihre Unternehmensdaten zu schützen und Datenverluste zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1117b-104">Microsoft Intune app protection policies help protect your company data and prevent data loss.</span></span>

## <a name="how-you-can-protect-app-data"></a><span data-ttu-id="1117b-105">Wie Sie Ihre App-Daten schützen können</span><span class="sxs-lookup"><span data-stu-id="1117b-105">How you can protect app data</span></span>
<span data-ttu-id="1117b-106">Ihre Mitarbeiter verwenden mobile Geräte für private und berufliche Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="1117b-106">Your employees use mobile devices for both personal and work tasks.</span></span>  <span data-ttu-id="1117b-107">Sie möchten einerseits die Produktivität Ihrer Mitarbeiter sicherstellen, möchten andererseits aber auch Datenverlust verhindern, sei er beabsichtigt oder unbeabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="1117b-107">While making sure your employees can be productive, you also want to prevent data loss, intentional and unintentional.</span></span>  <span data-ttu-id="1117b-108">Darüber hinaus möchten Sie auch dann die Möglichkeit zum Schützen der Unternehmensdaten haben, wenn der Zugriff darauf über Geräte erfolgt, die nicht von Ihnen verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-108">In addition, you want to have the ability to protect company data accessed using devices even in the case where they are not managed by you.</span></span>

<span data-ttu-id="1117b-109">Sie können Intune-App-Schutzrichtlinien verwenden, um Ihre Unternehmensdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1117b-109">You can use Intune  app protection policies to help protect your company’s data.</span></span> <span data-ttu-id="1117b-110">Da Intune-App-Schutzrichtlinien **unabhängig von Lösungen für die Verwaltung mobiler Geräte (MDM) einsetzbar sind**, können Sie sie mit oder ohne Registrierung der Geräte bei einer Geräteverwaltungslösung zum Schutz Ihrer Unternehmensdaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="1117b-110">Because Intune app protection policies can be used **independent of any mobile-device management (MDM) solution**, you can use it to protect your company’s data with or without enrolling devices in a device management solution.</span></span> <span data-ttu-id="1117b-111">Durch die Implementierung von **Richtlinien auf App-Ebene** können Sie den Zugriff auf Unternehmensressourcen einschränken und Daten im Zuständigkeitsbereich der IT-Abteilung halten.</span><span class="sxs-lookup"><span data-stu-id="1117b-111">By implementing **app-level policies**, you can restrict access to company resources and keep data within the purview of your IT department.</span></span>

<span data-ttu-id="1117b-112">App-Schutzrichtlinien können für Apps konfiguriert werden, die auf Geräten ausgeführt werden, die folgende Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="1117b-112">App protection policies can be configured for app running on devices that are:</span></span>

- <span data-ttu-id="1117b-113">**Registriert bei Microsoft Intune:** Die Geräte in dieser Kategorie sind in der Regel unternehmenseigene Geräte.</span><span class="sxs-lookup"><span data-stu-id="1117b-113">**Enrolled in Microsoft Intune:** The devices in this category are typically corporate owned devices.</span></span>

-   <span data-ttu-id="1117b-114">**Registriert bei einer Drittanbieterlösung für die Verwaltung mobiler Geräte (MDM, Mobile Device Management):** Die Geräte in dieser Kategorie sind in der Regel unternehmenseigene Geräte.</span><span class="sxs-lookup"><span data-stu-id="1117b-114">**Enrolled in a third-party Mobile device management (MDM)  solution:**   The devices in this category are typically corporate owned devices.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1117b-115">Verwaltungsrichtlinien für mobile Apps sollten nicht in Verbindung mit Verwaltungslösungen für mobile Geräte von Drittanbietern oder sicheren Containerlösungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-115">Mobile app management policies should not be used with third party mobile app management  or secure container solutions.</span></span>

-   <span data-ttu-id="1117b-116">**Nicht bei einer Lösung für die Verwaltung mobiler Geräte registriert:** Die Geräte in dieser Kategorie sind in der Regel mitarbeitereigene Geräte, die weder bei Intune noch anderen MDM-Lösungen registriert sind oder dort verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-116">**Not enrolled in any mobile device management solution:**  The devices in this category are typically employee owned devices that are not managed or enrolled in Intune or other MDM solutions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1117b-117">Sie können Verwaltungsrichtlinien für mobile Apps für mobile Office-Apps erstellen, die eine Verbindung mit Office 365-Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="1117b-117">You can create mobile app management policies for Office mobile apps that connect to Office 365 services.</span></span> <span data-ttu-id="1117b-118">App-Schutzrichtlinien werden nicht für Apps unterstützt, die eine Verbindung mit Exchange lokal, Skype for Business oder SharePoint-Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="1117b-118">App protection policies are not supported for apps that connect to on-premises Exchange, Skype for Business, or SharePoint services.</span></span>

<span data-ttu-id="1117b-119">**Die wichtigsten Vorteile von App-Schutzrichtlinien sind:**</span><span class="sxs-lookup"><span data-stu-id="1117b-119">**The important benefits of using App protection policies are**</span></span>

-   <span data-ttu-id="1117b-120">Schutz Ihrer Unternehmensdaten auf App-Ebene.</span><span class="sxs-lookup"><span data-stu-id="1117b-120">Protecting your company data at the app level.</span></span>  <span data-ttu-id="1117b-121">Da die Verwaltung von mobilen Apps keine Geräteverwaltung voraussetzt, können Sie Unternehmensdaten auf verwalteten und auf unverwalteten Geräten schützen.</span><span class="sxs-lookup"><span data-stu-id="1117b-121">Since mobile app management does not require device management, you can protect company data on both managed and unmanaged devices.</span></span> <span data-ttu-id="1117b-122">Bei der Verwaltung wird die Benutzeridentität in den Mittelpunkt gestellt, wodurch sich die Geräteverwaltung erübrigt.</span><span class="sxs-lookup"><span data-stu-id="1117b-122">The management is centered on the user identity, which removes the requirement for device management.</span></span>

-   <span data-ttu-id="1117b-123">Die Produktivität der Endbenutzer wird nicht beeinträchtigt, und die Richtlinien werden nicht angewendet, wenn die App im privaten Kontext verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1117b-123">End user productivity is not impacted, and the policies are not applied when using the app in a personal context.</span></span>  <span data-ttu-id="1117b-124">Die Richtlinien werden nur auf den beruflichen Kontext angewendet, wodurch Sie die Möglichkeit haben, Unternehmensdaten zu schützen, ohne dass private Daten einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-124">The policies are applied only in a work context, thus giving you the ability to protect company data without touching personal data.</span></span>

<span data-ttu-id="1117b-125">Es gibt weitere Vorteile bei der Verwendung einer MDM mit App-Schutzrichtlinien, und Unternehmen können App-Schutzrichtlinien sowohl mit als auch ohne MDM gleichzeitig verwenden.</span><span class="sxs-lookup"><span data-stu-id="1117b-125">There are additional benefits to using MDM with App protection  policies, and companies can use both App protection policies with and without MDM at the same time.</span></span> <span data-ttu-id="1117b-126">So kann ein Mitarbeiter beispielsweise ein unternehmenseigenes Smartphone und ein privates Tablet verwenden.</span><span class="sxs-lookup"><span data-stu-id="1117b-126">For example, an employee may use a phone issued by the company as well as a personal tablet.</span></span>  <span data-ttu-id="1117b-127">In diesem Fall wird das unternehmenseigene Smartphone in einer MDM registriert und von App-Schutzrichtlinien geschützt, während das private Geräte nur mit App-Schutzrichtlinien geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="1117b-127">In this case, the company phone is enrolled in MDM and protected by App protection policies, and the personal device is protected by App protection policies only.</span></span>

- <span data-ttu-id="1117b-128">**Eine MDM-Lösung stellt sicher, dass das Gerät geschützt ist**.</span><span class="sxs-lookup"><span data-stu-id="1117b-128">**MDM makes sure that the device is protected**.</span></span>  <span data-ttu-id="1117b-129">So können Sie beispielsweise die Eingabe einer PIN für den Zugriff auf das Gerät anfordern, oder Sie können verwaltete Apps auf dem Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1117b-129">For example, you can require a PIN to access the device, or you can deploy managed apps to the device.</span></span> <span data-ttu-id="1117b-130">Sie können Apps auch über die MDM-Lösung auf Geräten bereitstellen, um mehr Kontrolle über die App-Verwaltung zu haben.</span><span class="sxs-lookup"><span data-stu-id="1117b-130">You can also deploy apps to devices through your MDM solution, to give you more control over app management.</span></span>

- <span data-ttu-id="1117b-131">**App-Schutzrichtlinien stellen sicher, dass Schutzfunktionen auf App-Ebene vorhanden sind**.</span><span class="sxs-lookup"><span data-stu-id="1117b-131">**App protection policies makes sure that the app-layer protections are in place**.</span></span> <span data-ttu-id="1117b-132">So können Sie beispielsweise eine PIN anfordern, wenn eine App im beruflichen Kontext geöffnet werden soll oder wenn Daten zwischen Apps ausgetauscht werden können oder um zu verhindern, dass App-Daten des Unternehmens an einem privaten Speicherort gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-132">For example, you can require a PIN to open an app in a work context, or if data can be shared between apps, or preventing company app data from being saved to a personal storage location.</span></span>


### <a name="supported-platforms-for-app-protection-polices"></a><span data-ttu-id="1117b-133">Unterstützte Plattformen für App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1117b-133">Supported platforms for app protection polices</span></span>
-   <span data-ttu-id="1117b-134">iOS 9 oder höher</span><span class="sxs-lookup"><span data-stu-id="1117b-134">iOS 9 or later</span></span>
-   <span data-ttu-id="1117b-135">Android 4.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="1117b-135">Android 4.4 or later</span></span>

<span data-ttu-id="1117b-136">Windows-Geräte werden momentan nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1117b-136">Windows devices are currently not supported.</span></span> <span data-ttu-id="1117b-137">Wenn Sie jedoch Windows 10-Geräte mit Intune registrieren, können Sie Windows Information Protection verwenden, das ähnliche Funktionen bietet.</span><span class="sxs-lookup"><span data-stu-id="1117b-137">However, when you enroll Windows 10 devices with Intune, you can use Windows Information Protection, which offers similar functionality.</span></span> <span data-ttu-id="1117b-138">Weitere Informationen finden Sie unter [Schutz von Unternehmensdaten mit Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="1117b-138">For details, see [Protect your enterprise data using Windows Information Protection (WIP)](https://technet.microsoft.com/itpro/windows/keep-secure/protect-enterprise-data-using-wip).</span></span>
##  <a name="how-app-protection-policies-protect-app-data"></a><span data-ttu-id="1117b-139">So schützen App-Schutzrichtlinien Ihre App-Daten</span><span class="sxs-lookup"><span data-stu-id="1117b-139">How app protection policies protect app data</span></span>

####  <a name="apps-without-app-protection-policies"></a><span data-ttu-id="1117b-140">Apps ohne App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1117b-140">Apps without app protection policies</span></span>

![Die Abbildung zeigt, dass Daten ungehindert zwischen Apps verschoben werden können, wenn keine App-Schutzrichtlinien angewendet werden.](./media/apps-without-protection-policies.png)

<span data-ttu-id="1117b-142">Wenn Apps ohne Einschränkungen verwendet werden, können Unternehmensdaten und private Daten vermischt werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-142">When apps are used without restrictions, company and personal data can get intermingled.</span></span>  <span data-ttu-id="1117b-143">Unternehmensdaten könnten damit an Speicherorten wie dem persönlichen Speicher abgelegt oder an Apps außerhalb Ihres Zuständigkeitsbereichs übermittelt werden, was Datenverlust bedeuten würde.</span><span class="sxs-lookup"><span data-stu-id="1117b-143">Company data could end up in locations like personal storage or transferred to apps outside of your  purview,  resulting in data loss.</span></span> <span data-ttu-id="1117b-144">Die Pfeile im Diagramm zeigen die uneingeschränkte Datenbewegung zwischen Apps (geschäftlich und privat) und zu Speicherorten.</span><span class="sxs-lookup"><span data-stu-id="1117b-144">The arrows in the diagram show unrestricted data movement between apps (corporate and personal) and to storage locations.</span></span>

### <a name="data-protection-with-app-protection-policies"></a><span data-ttu-id="1117b-145">Datenschutz mit App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1117b-145">Data protection with app protection policies</span></span>

![<span data-ttu-id="1117b-146">Die Abbildung zeigt, wie Unternehmensdaten durch die Anwendung von App-Schutzrichtlinien geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-146">Image that shows how company data is protect when App protection policies are applied</span></span> ](./media/apps-with-protection-policies.png)


<span data-ttu-id="1117b-147">Mit App-Schutzrichtlinien können Sie verhindern, dass Unternehmensdaten im lokalen Speicher des Geräts gespeichert werden. Außerdem können Sie das Verschieben von Daten in andere Apps einschränken, die nicht durch App-Schutzrichtlinien geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="1117b-147">You can use App protection policies to prevent company data from saving to the local storage of the device, and restrict data movement to other apps that are not protected by App protection policies.</span></span> <span data-ttu-id="1117b-148">Einstellungen für App-Schutzrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="1117b-148">App protection policy settings include:</span></span>
- <span data-ttu-id="1117b-149">Richtlinien zur Datenverschiebung wie **„Speichern unter“ verhindern**, **Ausschneiden, Kopieren und Einfügen einschränken**.</span><span class="sxs-lookup"><span data-stu-id="1117b-149">Data relocation policies like **Prevent Save As**, **Restrict cut, copy, and paste**.</span></span>
- <span data-ttu-id="1117b-150">Einstellungen von Zugriffsrichtlinien wie **Einfache PIN für den Zugriff erforderlich**, **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren**.</span><span class="sxs-lookup"><span data-stu-id="1117b-150">Access policy settings like **Require simple PIN for access**, **Block managed apps from running on jailbroken or rooted devices**.</span></span>

### <a name="data-protection-with-app-protection-policies-on-devices-managed-by-a-mdm-solution"></a><span data-ttu-id="1117b-151">Schutz von Daten mit App-Schutzrichtlinien auf Geräten, die durch eine MDM-Lösung verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="1117b-151">Data protection with app protection policies on devices managed by a MDM solution</span></span>

![Die Abbildung zeigt, wie App-Schutzrichtlinien auf BYOD-Geräten funktionieren.](./media/app-protection-policies-with-mdm.png)

<span data-ttu-id="1117b-153">**Für Geräte, die in einer MDM-Lösung registriert sind**-</span><span class="sxs-lookup"><span data-stu-id="1117b-153">**For devices enrolled in an MDM solution**-</span></span>

<span data-ttu-id="1117b-154">Die obige Abbildung zeigt die Schutzebenen, die durch den gemeinsamen Einsatz von MDM und App-Schutzrichtlinien geboten werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-154">The illustration above shows the layers of protection that MDM and App protection policies offer together.</span></span>

<span data-ttu-id="1117b-155">Die MDM-Lösung:</span><span class="sxs-lookup"><span data-stu-id="1117b-155">The MDM solution:</span></span>

-   <span data-ttu-id="1117b-156">Registrieren das Gerät</span><span class="sxs-lookup"><span data-stu-id="1117b-156">Enrolls the device</span></span>

-   <span data-ttu-id="1117b-157">Stellt die Apps auf dem Gerät bereit</span><span class="sxs-lookup"><span data-stu-id="1117b-157">Deploys the apps to the device</span></span>

-   <span data-ttu-id="1117b-158">Sorgt für kontinuierliche Gerätekonformität und -verwaltung</span><span class="sxs-lookup"><span data-stu-id="1117b-158">Provides ongoing device compliance and management</span></span>

<span data-ttu-id="1117b-159">**App-Schutzrichtlinien bieten Mehrwert:**</span><span class="sxs-lookup"><span data-stu-id="1117b-159">**App protection policies add value by:**</span></span>

-   <span data-ttu-id="1117b-160">Sie tragen zum Schutz der Unternehmensdaten bei, indem der Zugriff durch Verbraucher-Apps und -Dienste verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="1117b-160">Helping protect  company data from leaking to consumer apps and services</span></span>

-   <span data-ttu-id="1117b-161">Es werden Einschränkungen ("Speichern unter", Zwischenablage, PIN usw.) auf mobile Apps angewendet.</span><span class="sxs-lookup"><span data-stu-id="1117b-161">Applying restrictions (save-as, clipboard, PIN, etc.) to mobile apps</span></span>

-   <span data-ttu-id="1117b-162">Unternehmensdaten können aus Apps entfernt werden, ohne die Apps vom Gerät zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1117b-162">Wipe company data from apps without removing those apps from the device</span></span>


### <a name="data-protection-with-app-protection-policies-for-devices-without-enrollment"></a><span data-ttu-id="1117b-163">Schutz von Daten mit App-Schutzrichtlinien für Geräte ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="1117b-163">Data protection with app protection policies for devices without enrollment</span></span>

![Die Abbildung zeigt, wie App-Schutzrichtlinien auf verwalteten Geräten funktionieren.](./media/app-protection-policies-without-mdm.png)

<span data-ttu-id="1117b-165">Das obige Diagramm zeigt, wie die Datenschutzrichtlinien auf App-Ebene ohne MDM funktionieren.</span><span class="sxs-lookup"><span data-stu-id="1117b-165">The diagram above illustrates how the data protection policies work at the app level without MDM.</span></span>

<span data-ttu-id="1117b-166">Bei BYOD-Geräten, die nicht in einer MDM-Lösung registriert sind, können App-Schutzrichtlinien dazu beitragen, Unternehmensdaten auf App-Ebene zu schützen.</span><span class="sxs-lookup"><span data-stu-id="1117b-166">For BYOD devices not enrolled in any MDM solution, App protection policies can help protect company data at the app level.</span></span>
<span data-ttu-id="1117b-167">Es gibt jedoch einige Einschränkungen, die Sie kennen sollten:</span><span class="sxs-lookup"><span data-stu-id="1117b-167">However, there are some limitations to be aware of, like:</span></span>

-   <span data-ttu-id="1117b-168">Sie können auf dem Gerät keine Apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1117b-168">You cannot deploy apps to the device.</span></span>  <span data-ttu-id="1117b-169">Der Endbenutzer muss die Apps aus dem Store beziehen.</span><span class="sxs-lookup"><span data-stu-id="1117b-169">The end user has to get the apps from the store.</span></span>

-   <span data-ttu-id="1117b-170">Sie können auf diesen Geräten keine Zertifikatprofile bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1117b-170">You cannot provision certificate profiles on these devices.</span></span>

-   <span data-ttu-id="1117b-171">Sie können auf diesen Geräten keine unternehmensweiten WLAN- und VPN-Einstellungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1117b-171">You cannot provision company Wi-Fi and VPN settings on these devices.</span></span>


## <a name="multi-identity"></a><span data-ttu-id="1117b-172">Mehrere Identitäten</span><span class="sxs-lookup"><span data-stu-id="1117b-172">Multi-identity</span></span>

<span data-ttu-id="1117b-173">Apps, die mehrere Identitäten unterstützen, bieten Ihnen die Möglichkeit, verschiedene Konten (Geschäfts- und persönliche Konten) für den Zugriff auf die gleichen Apps zu verwenden. Hierbei werden App-Schutzrichtlinien nur angewendet, wenn die Apps im Arbeitskontext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1117b-173">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>

<span data-ttu-id="1117b-174">Wenn ein Benutzer beispielsweise die OneDrive-App mit seinem Geschäftskonto startet, kann er die Dateien nicht an einen persönlichen Speicherort verschieben.</span><span class="sxs-lookup"><span data-stu-id="1117b-174">For example, when a user starts the OneDrive app by using their work account, they can't move the files to a personal storage location.</span></span> <span data-ttu-id="1117b-175">Wenn der Benutzer OneDrive jedoch mit einem persönlichen Konto verwendet, kann er Daten ohne Einschränkung aus dem persönlichen OneDrive kopieren und verschieben.</span><span class="sxs-lookup"><span data-stu-id="1117b-175">However, when they use OneDrive with their personal account, they can copy and move data from their personal OneDrive without restrictions.</span></span>

- <span data-ttu-id="1117b-176">Erfahren Sie mehr über die Apps, die [die Verwaltung mobiler Anwendungen und mehrerer Identitäten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) mit Intune unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1117b-176">Learn more about the apps that support [MAM and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="1117b-177">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1117b-177">Next steps</span></span>

[<span data-ttu-id="1117b-178">Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1117b-178">How to create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
