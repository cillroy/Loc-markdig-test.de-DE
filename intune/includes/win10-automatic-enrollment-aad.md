## <a name="enable-windows-10-automatic-enrollment"></a><span data-ttu-id="13057-101">Aktivieren der automatischen Registrierung von Windows 10</span><span class="sxs-lookup"><span data-stu-id="13057-101">Enable Windows 10 automatic enrollment</span></span>

<span data-ttu-id="13057-102">Durch die automatische Registrierung können Benutzer ihre Windows 10-Geräte in Intune registrieren.</span><span class="sxs-lookup"><span data-stu-id="13057-102">Automatic enrollment lets users enroll their Windows 10 devices in Intune.</span></span> <span data-ttu-id="13057-103">Benutzer müssen für die Registrierung ihr Geschäftskonto ihrem persönlichen Gerät hinzufügen oder firmeneigene Geräte mit Azure Active Directory verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="13057-103">To enroll, users add their work account to their personally owned devices or join corporate-owned devices to Azure Active Directory.</span></span> <span data-ttu-id="13057-104">Im Hintergrund registriert sich das Gerät und tritt Azure Active Directory bei.</span><span class="sxs-lookup"><span data-stu-id="13057-104">In the background, the device registers and joins Azure Active Directory.</span></span> <span data-ttu-id="13057-105">Nach der Registrierung wird das Gerät mit Intune verwaltet.</span><span class="sxs-lookup"><span data-stu-id="13057-105">Once registered, the device is managed with Intune.</span></span>

<span data-ttu-id="13057-106">**Voraussetzungen**</span><span class="sxs-lookup"><span data-stu-id="13057-106">**Prerequisites**</span></span>
- <span data-ttu-id="13057-107">Azure Active Directory Premium-Abonnement ([Testabonnement](http://go.microsoft.com/fwlink/?LinkID=816845))</span><span class="sxs-lookup"><span data-stu-id="13057-107">Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))</span></span>
- <span data-ttu-id="13057-108">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="13057-108">Microsoft Intune subscription</span></span>


### <a name="configure-automatic-mdm-enrollment"></a><span data-ttu-id="13057-109">Konfigurieren der automatischen MDM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="13057-109">Configure automatic MDM enrollment</span></span>

1. <span data-ttu-id="13057-110">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an, und klicken Sie auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="13057-110">Sign in to the [Azure portal](https://portal.azure.com), and select **Azure Active Directory**.</span></span>

   ![Screenshot des Azure-Portals](../media/auto-enroll-azure-main.png)

2. <span data-ttu-id="13057-112">Wählen Sie **Mobilität (MDM und MAM)** aus.</span><span class="sxs-lookup"><span data-stu-id="13057-112">Select **Mobility (MDM and MAM)**.</span></span>

   ![Screenshot des Azure-Portals](../media/auto-enroll-mdm.png)

3. <span data-ttu-id="13057-114">Wählen Sie **Microsoft Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="13057-114">Select **Microsoft Intune**.</span></span>

   ![Screenshot des Azure-Portals](../media/auto-enroll-intune.png)

4. <span data-ttu-id="13057-116">Konfigurieren Sie den **MDM-Benutzerbereich**.</span><span class="sxs-lookup"><span data-stu-id="13057-116">Configure **MDM User scope**.</span></span> <span data-ttu-id="13057-117">Geben Sie an, welche Geräte von Benutzern von Microsoft Intune verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="13057-117">Specify which users’ devices should be managed by Microsoft Intune.</span></span> <span data-ttu-id="13057-118">Diese Windows 10-Geräte können sich automatisch für die Verwaltung mit Microsoft Intune registrieren.</span><span class="sxs-lookup"><span data-stu-id="13057-118">These Windows 10 devices can automatically enroll for management with Microsoft Intune.</span></span>

   - <span data-ttu-id="13057-119">**Keine**: Automatische MDM-Registrierung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="13057-119">**None** - MDM automatic enrollment disabled</span></span>
   - <span data-ttu-id="13057-120">**Einige**: Wählen Sie die **Gruppen** aus, die ihre Windows 10-Geräte automatisch registrieren können.</span><span class="sxs-lookup"><span data-stu-id="13057-120">**Some** - Select the **Groups** that can automatically enroll their Windows 10 devices</span></span>
   - <span data-ttu-id="13057-121">**Alle**: Alle Benutzer können ihre Windows 10-Geräte automatisch registrieren.</span><span class="sxs-lookup"><span data-stu-id="13057-121">**All** - All users can automatically enroll their Windows 10 devices</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="13057-122">Wenn der **MAM-Benutzerbereich** und die automatische MDM-Registrierung (**MDM-Benutzerbereich**) für eine Gruppe aktiviert sind, wird nur MAM aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13057-122">If both **MAM user scope** and automatic MDM enrollment (**MDM user scope**) are enabled for a group, only MAM is enabled.</span></span> <span data-ttu-id="13057-123">Nur MAM wird für Benutzer in dieser Gruppe hinzugefügt, wenn ihr persönliches Gerät dem Arbeitsplatz beitritt.</span><span class="sxs-lookup"><span data-stu-id="13057-123">Only MAM is added for users in that group when they workplace join personal device.</span></span> <span data-ttu-id="13057-124">Geräte werden nicht automatisch in MDM registriert.</span><span class="sxs-lookup"><span data-stu-id="13057-124">Devices are not automatically MDM enrolled.</span></span>

   ![Screenshot des Azure-Portals](../media/auto-enroll-scope.png)

5. <span data-ttu-id="13057-126">Verwenden Sie die Standardwerte für die folgenden URLs:</span><span class="sxs-lookup"><span data-stu-id="13057-126">Use the default values for the following URLs:</span></span>
    - <span data-ttu-id="13057-127">**URL für MDM-Nutzungsbedingungen**</span><span class="sxs-lookup"><span data-stu-id="13057-127">**MDM Terms of use URL**</span></span>
    - <span data-ttu-id="13057-128">**URL für MDM-Ermittlung**</span><span class="sxs-lookup"><span data-stu-id="13057-128">**MDM Discovery URL**</span></span>
    - <span data-ttu-id="13057-129">**MDM Compliance-URL**</span><span class="sxs-lookup"><span data-stu-id="13057-129">**MDM Compliance URL**</span></span>

6. <span data-ttu-id="13057-130">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="13057-130">Select **Save**.</span></span>

<span data-ttu-id="13057-131">Standardmäßig ist die zweistufige Authentifizierung für den Dienst nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="13057-131">By default, two-factor authentication is not enabled for the service.</span></span> <span data-ttu-id="13057-132">Die zweistufige Authentifizierung wird jedoch empfohlen, wenn Sie ein Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="13057-132">However, two-factor authentication is recommended when registering a device.</span></span> <span data-ttu-id="13057-133">Für die zweistufige Authentifizierung müssen Sie einen Anbieter für die zweistufige Authentifizierung in Azure AD konfigurieren. Außerdem müssen Sie Ihre Benutzerkonten für die mehrstufige Authentifizierung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="13057-133">To enable two-factor authentication, configure a two-factor authentication provider in Azure AD and configure your user accounts for multi-factor authentication.</span></span> <span data-ttu-id="13057-134">Weitere Informationen finden Sie unter [Erste Schritte mit Azure Multi-Factor Authentication-Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span><span class="sxs-lookup"><span data-stu-id="13057-134">See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>
