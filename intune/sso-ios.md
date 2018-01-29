---
title: "Konfigurieren von Intune für einmaliges Anmelden von iOS-Geräten"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune für einmaliges Anmelden von iOS-Geräten konfigurieren."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0224238f4f84c0731f27469e03f16eece313ec60
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="configure-intune-for-ios-device-single-sign-on"></a><span data-ttu-id="f89d8-103">Konfigurieren von Intune für einmaliges Anmelden von iOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="f89d8-103">Configure Intune for iOS device single sign-on</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="f89d8-104">Die meisten branchenspezifischen Apps erfordern eine bestimmte Form von Benutzerauthentifizierung, um Sicherheitsfeatures unterstützen zu können.</span><span class="sxs-lookup"><span data-stu-id="f89d8-104">Most Line of Business (LOB) apps require some level of user authentication to support security.</span></span> <span data-ttu-id="f89d8-105">In vielen Fällen muss der Benutzer hierfür die gleichen Anmeldeinformationen mehrfach eingeben, was sich als frustrierend erweisen kann.</span><span class="sxs-lookup"><span data-stu-id="f89d8-105">In many cases this requires the user to type the same credentials multiple times, which can be frustrating for users.</span></span> <span data-ttu-id="f89d8-106">Zur Verbesserung der Benutzerfreundlichkeit können Entwickler Apps erstellen, die einmaliges Anmelden verwenden. So kann die Häufigkeit reduziert werden, mit der ein Benutzer Anmeldeinformationen angeben muss.</span><span class="sxs-lookup"><span data-stu-id="f89d8-106">To improve the user experience, developers can create apps that use single sign-on, reducing the number of times a user must provide credentials.</span></span>

<span data-ttu-id="f89d8-107">Um einmaliges Anmelden von iOS-Geräten nutzen zu können, müssen folgende Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="f89d8-107">To take advantage of iOS device Single Sign-on, you must have the following conditions:</span></span>

- <span data-ttu-id="f89d8-108">Es muss eine App vorhanden sein, die dafür codiert ist, den Anmeldeinformationsspeicher des Benutzers in der Nutzlast zum einmaligen Anmelden auf dem iOS-Gerät zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f89d8-108">An app coded to look for the user credential store in the single sign-on payload on the iOS device.</span></span>
- <span data-ttu-id="f89d8-109">Intune muss für einmaliges Anmelden von iOS-Geräten konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="f89d8-109">Intune configured for iOS device single sign-on.</span></span>

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a><span data-ttu-id="f89d8-110">Konfigurieren von Intune für einmaliges Anmelden von iOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="f89d8-110">To configure Intune for iOS device single sign-on</span></span>


1. <span data-ttu-id="f89d8-111">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="f89d8-111">Sign into the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="f89d8-112">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="f89d8-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="f89d8-113">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="f89d8-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="f89d8-114">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="f89d8-114">On the **Device configuration** blade, choose **Profiles**.</span></span>
3. <span data-ttu-id="f89d8-115">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen**, geben Sie einen Namen und eine Beschreibung ein, und konfigurieren Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f89d8-115">On the profiles blade, choose **Create Profile**, provide a name and description, and configure the following settings:</span></span>
   - <span data-ttu-id="f89d8-116">**Plattform**: Wählen Sie **iOS**.</span><span class="sxs-lookup"><span data-stu-id="f89d8-116">**Platform**: Choose **iOS**.</span></span> 
   - <span data-ttu-id="f89d8-117">**Profiltyp**: Wählen Sie **Gerätefunktionen**.</span><span class="sxs-lookup"><span data-stu-id="f89d8-117">**Profile type**: Choose **Device features**.</span></span>
4. <span data-ttu-id="f89d8-118">Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **Einmaliges Anmelden** aus.</span><span class="sxs-lookup"><span data-stu-id="f89d8-118">On the **Device features** blade, choose **Single Sign On**.</span></span>

   ![Blatt „Einmaliges Anmelden“](./media/sso-blade.png)

2. <span data-ttu-id="f89d8-120">Verwenden Sie die folgende Zusammenfassungstabelle, um die Felder auf dem Blatt **Einmaliges Anmelden** auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="f89d8-120">Use the following summary table to help you fill in the fields on the **Single Sign On** blade.</span></span> <span data-ttu-id="f89d8-121">Weitere Informationen finden Sie in den Abschnitten nach der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f89d8-121">For details, see the sections after the table.</span></span>
   
   |<span data-ttu-id="f89d8-122">Feld</span><span class="sxs-lookup"><span data-stu-id="f89d8-122">Field</span></span>  |<span data-ttu-id="f89d8-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f89d8-123">Notes</span></span>|
   |---------|---------|
   |<span data-ttu-id="f89d8-124">**Benutzernamensattribut aus AAD**</span><span class="sxs-lookup"><span data-stu-id="f89d8-124">**Username attribute from AAD**</span></span>|<span data-ttu-id="f89d8-125">Das Attribut, nach dem Intune vor Generierung der auf dem Gerät zu installierenden XML-Nutzlast für jeden Benutzer in AAD sucht und das entsprechende Feld (z.B. UPN) auffüllt</span><span class="sxs-lookup"><span data-stu-id="f89d8-125">The attribute that Intune looks at for each user in AAD and populates the respective field (such as UPN) before generating the XML payload that gets installed on the device.</span></span>|
   |<span data-ttu-id="f89d8-126">**Bereich**</span><span class="sxs-lookup"><span data-stu-id="f89d8-126">**Realm**</span></span>|<span data-ttu-id="f89d8-127">Der Domänenteil der URL</span><span class="sxs-lookup"><span data-stu-id="f89d8-127">The domain portion of the URL.</span></span>|
   |<span data-ttu-id="f89d8-128">**URL-Präfixe, die einmaliges Anmelden verwenden**</span><span class="sxs-lookup"><span data-stu-id="f89d8-128">**URL prefixes that will use Single Sign On**</span></span>|<span data-ttu-id="f89d8-129">Alle URLs in Ihrer Organisation, für die Benutzer eine Authentifizierung durch einmaliges Anmelden durchführen müssen</span><span class="sxs-lookup"><span data-stu-id="f89d8-129">Any URLs in your organization that require user single sign-on authentication</span></span>|
   |<span data-ttu-id="f89d8-130">**Apps, die einmaliges Anmelden verwenden**</span><span class="sxs-lookup"><span data-stu-id="f89d8-130">**Apps that will use Single Sign On**</span></span>|<span data-ttu-id="f89d8-131">Apps auf dem Gerät des Endbenutzers, die die Nutzlast zum einmaligen Anmelden verwenden</span><span class="sxs-lookup"><span data-stu-id="f89d8-131">Apps on end user’s device that use the single sign-on payload.</span></span>|
   |<span data-ttu-id="f89d8-132">**Zertifikat zum Erneuern der Anmeldeinformationen**</span><span class="sxs-lookup"><span data-stu-id="f89d8-132">**Credential renewal certificate**</span></span>|<span data-ttu-id="f89d8-133">Erfolgt die Authentifizierung anhand von Zertifikaten, wählen Sie als für den Benutzer bereitgestelltes Authentifizierungszertifikat das SCEP- oder PFX-Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="f89d8-133">If using certificates for authentication, select the SCEP or PFX certificate that is deployed to the user as the authentication certificate.</span></span>|

<span data-ttu-id="f89d8-134">Die folgenden Abschnitte enthalten weitere Informationen zu den Feldern bei der einmaligen Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="f89d8-134">The following sections provide more details about each of the single sign-on fields.</span></span>

### <a name="username-attribute-from-aad-and-realm"></a><span data-ttu-id="f89d8-135">Benutzernamensattribut aus AAD und dem Bereich</span><span class="sxs-lookup"><span data-stu-id="f89d8-135">Username attribute from AAD and Realm</span></span>

- <span data-ttu-id="f89d8-136">Wenn für dieses Feld **Benutzerprinzipalname** ausgewählt ist, wird es wie folgt analysiert:</span><span class="sxs-lookup"><span data-stu-id="f89d8-136">If **User Principle Name** is selected for this field, it is parsed in the following way:</span></span>

   ![Benutzernamensattribut](media/User-name-attribute.png)

   <span data-ttu-id="f89d8-138">Sie haben auch die Möglichkeit, den Bereich mit dem Text, den Sie in das Textfeld **Bereich** eingeben, zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f89d8-138">You also have the choice to overwrite the realm with the text you type in the **Realm** text box.</span></span>

   <span data-ttu-id="f89d8-139">Zum Beispiel könnte Contoso mehrere Teilregionen wie Europa, Asien und Nordamerika umfassen.</span><span class="sxs-lookup"><span data-stu-id="f89d8-139">For example, Contoso might have several subregions such as Europe, Asia, and North America.</span></span> <span data-ttu-id="f89d8-140">Möchte Contoso, dass dessen Benutzer in Asien die SSO-Nutzlast verwenden, erfordert die App den UPN im Format *username@asia.contoso.com*. Wenn Sie in diesem Fall **Benutzerprinzipalname** wählen, wird standardmäßig der Bereich für die einzelnen Benutzer aus AAD übernommen, der z.B. einfach *contoso.com* lauten kann. So können Sie insbesondere für Benutzer in Asien diese Nutzlast erstellen und den Bereich mit dem Wert *asia.contoso.com* überschreiben. Daraufhin wird als UPN des Endbenutzers *username@asia.contoso.com* und nicht *username@contoso.com* verwendet.</span><span class="sxs-lookup"><span data-stu-id="f89d8-140">They might want their users in Asia to use the SSO payload, and the app requires the UPN in the form *username@asia.contoso.com*. In this case, if you select **User Principle Name**, by default the realm for each user is taken from AAD that may be just *contoso.com*. So for users in Asia specially, you can create this payload and overwrite the realm with the value *asia.contoso.com*. Now the end user's UPN becomes *username@asia.contoso.com* and not *username@contoso.com*.</span></span>

- <span data-ttu-id="f89d8-141">Wenn Sie **Geräte-ID** wählen, wählt Intune automatisch die Intune-Geräte-ID aus.</span><span class="sxs-lookup"><span data-stu-id="f89d8-141">If you select **Device ID**, Intune automatically selects the Intune Device ID.</span></span>

   <span data-ttu-id="f89d8-142">Standardmäßig müssen Apps lediglich die Geräte-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="f89d8-142">By default, apps only need to use the device ID.</span></span> <span data-ttu-id="f89d8-143">Wenn Ihre App neben der Geräte-ID jedoch den Bereich verwendet, können Sie den Bereich in das Textfeld **Bereich** eingeben.</span><span class="sxs-lookup"><span data-stu-id="f89d8-143">But if your app uses the realm in addition to the device ID, you can type the realm in the **Realm** text box.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f89d8-144">Der Bereich sollte standardmäßig leer gelassen werden, wenn Sie die Geräte-ID verwenden.</span><span class="sxs-lookup"><span data-stu-id="f89d8-144">By default keep the realm empty if you use device ID.</span></span>

### <a name="url-prefixes-that-will-use-single-sign-on"></a><span data-ttu-id="f89d8-145">URL-Präfixe, die einmaliges Anmelden verwenden</span><span class="sxs-lookup"><span data-stu-id="f89d8-145">URL prefixes that will use Single Sign On</span></span>

<span data-ttu-id="f89d8-146">Geben Sie hier alle in Ihrer Organisation vorhandene URLs ein, die eine Benutzerauthentifizierung erfordern.</span><span class="sxs-lookup"><span data-stu-id="f89d8-146">Type any URLs here that exist in your organization that require user authentication.</span></span>

<span data-ttu-id="f89d8-147">Wenn ein Benutzer beispielsweise mit einer dieser Websites eine Verbindung herstellt, verwendet das iOS-Gerät die Anmeldeinformationen für einmaliges Anmelden, und der Benutzer muss keine zusätzlichen Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="f89d8-147">For example, when a user connects to any of these sites, the iOS device uses the single sign-on credentials and the user does not need to enter any additional credentials.</span></span> <span data-ttu-id="f89d8-148">Wenn Sie jedoch die mehrstufige Authentifizierung aktiviert haben, müssen Benutzer die zweite Authentifizierungsmethode anwenden.</span><span class="sxs-lookup"><span data-stu-id="f89d8-148">However, if you have multi-factor authentication enabled, users are required to enter the second authentication.</span></span>

> [!NOTE]
> <span data-ttu-id="f89d8-149">Bei diesen URLs muss es sich um ordnungsgemäß formatierte FQDNs handeln.</span><span class="sxs-lookup"><span data-stu-id="f89d8-149">These URLs must be properly formatted FQDN.</span></span> <span data-ttu-id="f89d8-150">Bei Apple müssen diese im Format `http://<yourURL.domain>` sein.</span><span class="sxs-lookup"><span data-stu-id="f89d8-150">Apple requires these to be in the form `http://<yourURL.domain>`</span></span>

<span data-ttu-id="f89d8-151">Die URL-Übereinstimmungsmuster müssen entweder mit `http://` oder `https://` beginnen.</span><span class="sxs-lookup"><span data-stu-id="f89d8-151">The URL matching patterns must begin with either `http://` or `https://`.</span></span> <span data-ttu-id="f89d8-152">Es wird ein einfacher Zeichenfolgenabgleich durchgeführt, sodass das URL-Präfix `http://www.contoso.com/` nicht mit `http://www.contoso.com:80/` übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f89d8-152">A simple string match is performed, so the URL prefix `http://www.contoso.com/` does not match `http://www.contoso.com:80/`.</span></span> <span data-ttu-id="f89d8-153">Ab iOS 9.0 kann jedoch ein einzelnes Platzhalterzeichen \* verwendet werden, um alle übereinstimmenden Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f89d8-153">With iOS 9.0 or later, however, a single wildcard \* may be used to specify all matching values.</span></span> <span data-ttu-id="f89d8-154">Beispielsweise entspricht `http://*.contoso.com/` sowohl `http://store.contoso.com/` als auch `http://www.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="f89d8-154">For example, `http://*.contoso.com/`  matches both `http://store.contoso.com/` and `http://www.contoso.com`.</span></span>
<span data-ttu-id="f89d8-155">Die Muster `http://.com` und `https://.com` stimmen mit allen HTTP- bzw. HTTPS-URLs überein.</span><span class="sxs-lookup"><span data-stu-id="f89d8-155">The patterns `http://.com` and `https://.com` match all HTTP and HTTPS URLs, respectively.</span></span>

### <a name="apps-that-will-use-single-sign-on"></a><span data-ttu-id="f89d8-156">Apps, die einmaliges Anmelden verwenden</span><span class="sxs-lookup"><span data-stu-id="f89d8-156">Apps that will use Single Sign On</span></span>

<span data-ttu-id="f89d8-157">Gibt die Apps auf dem Gerät des Endbenutzers an, die die Nutzlast zum einmaligen Anmelden verwenden</span><span class="sxs-lookup"><span data-stu-id="f89d8-157">Indicate which apps on an end user’s device that can use the Single Sign on payload.</span></span>

<span data-ttu-id="f89d8-158">Das `AppIdentifierMatches`-Array muss Zeichenfolgen enthalten, die mit App-Bündel-IDs übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="f89d8-158">The `AppIdentifierMatches` array must contain strings that match app bundle IDs.</span></span> <span data-ttu-id="f89d8-159">Bei diesen Zeichenfolgen können exakte Übereinstimmungen (z.B. `com.contoso.myapp`) oder Präfixübereinstimmungen der Bündel-ID unter Verwendung des Platzhalterzeichens \* gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="f89d8-159">These strings may be exact matches (for example: `com.contoso.myapp`) or may specify a prefix match on the bundle ID by using the \* wildcard character.</span></span> <span data-ttu-id="f89d8-160">Das Platzhalterzeichen muss nach einem Punkt (.) folgen und kann nur einmal am Ende der Zeichenfolge verwendet werden (z.B. `com.contoso.*`).</span><span class="sxs-lookup"><span data-stu-id="f89d8-160">The wildcard character must appear after a period character (.), and may appear only once, at the end of the string (for example: `com.contoso.*`).</span></span> <span data-ttu-id="f89d8-161">Wenn ein Platzhalter enthalten ist, erhält jede App, deren Bündel-ID mit dem Präfix beginnt, Zugriff auf das Konto.</span><span class="sxs-lookup"><span data-stu-id="f89d8-161">When a wildcard is included, any app whose bundle ID begins with the prefix is granted access to the account.</span></span>

<span data-ttu-id="f89d8-162">Das Feld **App-Name** wird verwendet, um einen Anzeigenamen hinzuzufügen, mit dem Sie die Bündel-ID identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="f89d8-162">The **App Name** field is used to add a user-friendly name to help you identify the bundle ID.</span></span>

### <a name="credential-renewal-certificate"></a><span data-ttu-id="f89d8-163">Zertifikat zum Erneuern der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f89d8-163">Credential renewal certificate</span></span>

<span data-ttu-id="f89d8-164">Wenn Sie Ihre Endbenutzer mit Zertifikaten (nicht mit Kennwörtern) authentifizieren, wählen Sie in diesem Feld das SCEP- oder PFX-Zertifikat aus, das Benutzern als Authentifizierungszertifikat bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f89d8-164">If you authenticate your end users with certificates (not passwords), then use this field to select the SCEP or PFX certificate that is deployed to the user as the authentication certificate.</span></span> <span data-ttu-id="f89d8-165">In der Regel handelt es sich dabei um dasselbe Zertifikat, das dem Benutzer für andere Profile wie VPN, WLAN oder E-Mail bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f89d8-165">Typically, this is the same certificate that is deployed to the user for other profiles such as VPN, WiFi, or Email.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f89d8-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f89d8-166">Next steps</span></span>

<span data-ttu-id="f89d8-167">Weitere Informationen zur Konfiguration von Gerätefeatures finden Sie unter [Konfigurieren der Einstellungen für Gerätefunktionen in Microsoft Intune](device-features-configure.md).</span><span class="sxs-lookup"><span data-stu-id="f89d8-167">For additional device feature configuration information, see [How to configure device feature settings in Microsoft Intune](device-features-configure.md).</span></span>