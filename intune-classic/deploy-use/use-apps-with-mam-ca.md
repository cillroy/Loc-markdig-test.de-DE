---
title: "Verwenden von Apps mit bedingtem Zugriff für die Verwaltung mobiler Anwendungen"
description: "Informationen dazu, wie Sie mit bedingtem Zugriff für die Verwaltung mobiler Anwendungen bestimmen können, welche Apps auf O365-Dienste zugreifen dürfen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 71dcf9bc-bfd1-4e06-b7ad-14b33a2288d0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a8873a300e34bd62e184b9df1727f856eac71b81
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="what-to-expect-when-using-an-app-with-app-based-ca"></a><span data-ttu-id="5e789-103">Was ist bei der Verwendung einer App mit App-basierter Zertifizierungsstelle (CA) zu erwarten?</span><span class="sxs-lookup"><span data-stu-id="5e789-103">What to expect when using an app with app-based CA</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5e789-104">Die App-basierte CA überprüft die Identität der genehmigten Anwendung mithilfe einer Broker-App, die auf dem Gerät vorhanden sein muss:</span><span class="sxs-lookup"><span data-stu-id="5e789-104">App-based CA verifies the identity of the approved application by means of a broker app that must be present on the device:</span></span>
*  <span data-ttu-id="5e789-105">Unter **iOS** ist die **Azure Authenticator-App** die Broker-App.</span><span class="sxs-lookup"><span data-stu-id="5e789-105">On **iOS**, the **Azure Authenticator app** is the broker app.</span></span>
* <span data-ttu-id="5e789-106">Unter **Android** ist die **Intune-Unternehmensportal-App** die Broker-App.</span><span class="sxs-lookup"><span data-stu-id="5e789-106">On **Android**, the **Intune Company Portal app** is the broker app.</span></span> 

<span data-ttu-id="5e789-107">Benutzer, die sich zum ersten Mal bei einer mit einer App-basierten CA wie OneDrive oder Outlook anmelden, werden aufgefordert, die Broker-App zu installieren und das Gerät bei Azure AD zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="5e789-107">End-users signing in for the first time, to an app that is supported by app-based CA, like OneDrive or Outlook, are prompted to install the broker app and register the device with Azure AD.</span></span> <span data-ttu-id="5e789-108">Beim Registrieren des Geräts in Azure AD (früher als Arbeitsplatzeinbindung bekannt) werden ein Gerätedatensatz und -zertifikat erstellt, für die Token ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5e789-108">Device registration in Azure AD (previously known as Workplace Join) will create a device record and certificate against which tokens are issued.</span></span>  <span data-ttu-id="5e789-109">Hierbei handelt es sich **nicht** um eine **MDM-Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="5e789-109">This is **not** the same as **MDM enrollment**.</span></span> <span data-ttu-id="5e789-110">Hier werden keine Verwaltungsprofile oder -richtlinien angewendet, und es wird keine Bestandsaufnahme für Apps auf dem Gerät durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e789-110">There are no management profiles or policies that are applied, and there is no inventory taken of apps on the device.</span></span>  <span data-ttu-id="5e789-111">Der Prozess der Installation der Broker-App und der Registrierung des Geräts wurde nur bei der ersten Verwendung einer verwalteten App durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="5e789-111">The process of installing the broker app and registering the device will only happen on the first use of a managed app.</span></span>

<span data-ttu-id="5e789-112">Im Folgenden finden Sie eine Liste der Eigenschaften, die direkt vom Gerät abgeleitet sind:</span><span class="sxs-lookup"><span data-stu-id="5e789-112">The following is a list of properties that are directly derived from the device:</span></span>

* <span data-ttu-id="5e789-113">alternativeSecurityIds (Azure Active Directory-Zertifikatfingerabdruck und -Hash für öffentliche Schlüssel)</span><span class="sxs-lookup"><span data-stu-id="5e789-113">alternativeSecurityIds (Azure Active Directory Certificate thumbprint and public key hash)</span></span>
* <span data-ttu-id="5e789-114">deviceOSType</span><span class="sxs-lookup"><span data-stu-id="5e789-114">deviceOSType</span></span>
* <span data-ttu-id="5e789-115">deviceOSVersion</span><span class="sxs-lookup"><span data-stu-id="5e789-115">deviceOSVersion</span></span>
* <span data-ttu-id="5e789-116">displayName</span><span class="sxs-lookup"><span data-stu-id="5e789-116">displayName</span></span>

> [!NOTE]
> <span data-ttu-id="5e789-117">Auf Android-Geräten:</span><span class="sxs-lookup"><span data-stu-id="5e789-117">On Android devices:</span></span>
>   * <span data-ttu-id="5e789-118">Die Unternehmensportal-App muss auf dem Gerät installiert sein, der Endbenutzer muss sich aber nicht bei der App anmelden.</span><span class="sxs-lookup"><span data-stu-id="5e789-118">It is required that the Company Portal app is installed on the device, but end-user is not required to log in into app.</span></span>
>   * <span data-ttu-id="5e789-119">Die Geräteregistrierung muss über die OneDrive- oder Outlook-App erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5e789-119">Device registration must be done through the OneDrive or Outlook app.</span></span>

## <a name="to-remove-a-device-from-azure-ad-registration"></a><span data-ttu-id="5e789-120">So entfernen Sie ein Gerät aus der Azure AD-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="5e789-120">To remove a device from Azure AD registration.</span></span>
<span data-ttu-id="5e789-121">Eine Möglichkeit ist, die Geräteregistrierung über die Azure AD-Verwaltungskonsole zu entfernen, was normalerweise vom IT-Administrator durchgeführt wird.  Es kann aber auch vom Endbenutzer auf dem Gerät selbst durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5e789-121">You can remove the device registration either through the Azure AD admin console which is typically done by the IT admin.  It can also be done by the end-user on the device itself.</span></span>

* <span data-ttu-id="5e789-122">**Azure AD-Verwaltungskonsole**: Löschen Sie in der Azure AD-Verwaltungskonsole** das Gerät, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="5e789-122">**Azure AD admin console**: In the Azure AD admin console**, delete the device that you want to remove.</span></span>
* <span data-ttu-id="5e789-123">**iOS-Gerät**: Öffnen Sie die Azure Authenticator-App, wischen Sie für das Konto nach links, und wählen Sie „Registrierung aufheben“ aus.</span><span class="sxs-lookup"><span data-stu-id="5e789-123">**iOS device**: Open the Azure Authenticator app, swipe left on the account, and choose unregister.</span></span>  
* <span data-ttu-id="5e789-124">**Android-Gerät**: Deinstallieren Sie die Unternehmensportal-App, oder entfernen Sie das Konto aus den **Systemeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5e789-124">**Android device**: Uninstall the company portal app or remove the account from the **System settings**.</span></span>

## <a name="app-based-ca-with-device-based-ca"></a><span data-ttu-id="5e789-125">App-basierte Zertifizierungsstelle mit gerätebasierter Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="5e789-125">App-based CA with Device-based CA</span></span>  

<span data-ttu-id="5e789-126">Sie können konfigurieren, [bedingten Zugriff basierend auf dem Gerätekompatibilität](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (<strong>Gerät Zertifizierungsstelle</strong>) auf die [Intune-Administratorkonsole](https://manage.microsoft.com) oder die [Azure AD Premium Verwaltungskonsole](https://manage.windowsazure.com).</span><span class="sxs-lookup"><span data-stu-id="5e789-126">You can configure [Conditional access based on device compliance](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) (<strong>Device CA</strong>) on the [Intune administrator console](https://manage.microsoft.com) or the [Azure AD Premium management console](https://manage.windowsazure.com).</span></span> <span data-ttu-id="5e789-127">Bei diesem bedingten Zugriff dürfen Benutzer nur über mit Intune verwaltete Geräte, die mit der Intune-Gerätekompatibilitätsrichtlinie kompatibel sind, oder über in die Domäne eingebundene PCs eine Verbindung mit Exchange Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="5e789-127">Device CA require users to connect to Exchange Online only through Intune-managed  devices that are compliant with the Intune device compliance policy or domain-joined PCs.</span></span>  <span data-ttu-id="5e789-128">Wenn ein Benutzer mindestens einer Sicherheitsgruppe angehört, die sowohl für die App-basierte CA als auch für Richtlinien für den bedingten Zugriff für Geräte (Device CA) vorgesehen ist, muss der Benutzer eine der beiden folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="5e789-128">If a user belongs to one or more security groups that are targeted for both app-based CA and Device CA policies, the user must meet one of the two requirements:</span></span>
* <span data-ttu-id="5e789-129">Die App, die für den Zugriff auf den Dienst verwendet wird, ist eine mobile App, die von</span><span class="sxs-lookup"><span data-stu-id="5e789-129">The app used to access the service is a mobile app that is supported by</span></span> 
* <span data-ttu-id="5e789-130">unterstützt wird. Auf dem Gerät auf dem die App ausgeführt wird, ist **iOS Authenticator (für iOS-Geräte)** bzw. die **Unternehmensportal-App (für Android-Geräte)** installiert.</span><span class="sxs-lookup"><span data-stu-id="5e789-130">, and the device that the app is running on, has **iOS Authenticator (for iOS devices)**, or the **Company Portal app (for Android devices)** installed.</span></span>
* <span data-ttu-id="5e789-131">Das Gerät, das für den Zugriff auf den Dienst verwendet wird, wird von **Intune verwaltet und ist kompatibel** mit der Intune-Gerätekompatibilitätsrichtlinie, oder es handelt sich um einen **in die Domäne eingebundenen PC**.</span><span class="sxs-lookup"><span data-stu-id="5e789-131">The device used to access the service is **Intune-managed and compliant** with the Intune device compliance policy, or it is a **domain-joined PC**.</span></span>  <span data-ttu-id="5e789-132">Im Folgenden finden Sie einige Beispiele zur Veranschaulichung:</span><span class="sxs-lookup"><span data-stu-id="5e789-132">Here are some examples to help illustrate this:</span></span>
  * <span data-ttu-id="5e789-133">Wenn ein Benutzer versucht, über die **native iOS-E-Mail-App** eine Verbindung herzustellen, muss er ein **verwaltetes und kompatibles Gerät** verwenden, da die native Mail-App von der App-basierten CA nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5e789-133">If a user tries to connect from the **native iOS email app**, he or she will be required to be on a **managed and compliant device** since the native mail app is not supported by app-based CA.</span></span>
  * <span data-ttu-id="5e789-134">Wenn ein Benutzer versucht, über einen **privaten Windows-PC** eine Verbindung herzustellen, wird die **Geräte-Richtlinie für bedingten Zugriff** angewendet, die verlangt, dass ein in die Domäne eingebundener PC verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5e789-134">If a user tries to connect from a **Windows home PC**, the **Device CA policy** will apply, requiring that the he or she must use a domain-joined PC.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e789-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5e789-135">Next steps</span></span>
[<span data-ttu-id="5e789-136">Erstellen einer Exchange Online-Richtlinie für MAM-Apps</span><span class="sxs-lookup"><span data-stu-id="5e789-136">Create an Exchange Online Policy for MAM apps</span></span>](mam-ca-for-exchange-online.md)

[<span data-ttu-id="5e789-137">Blockieren von Apps, die über keine moderne Authentifizierung verfügen</span><span class="sxs-lookup"><span data-stu-id="5e789-137">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a><span data-ttu-id="5e789-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e789-138">See also</span></span>

[<span data-ttu-id="5e789-139">Protect app data with app protection policies (Schützen von App-Daten mithilfe von App-Schutzrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="5e789-139">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
