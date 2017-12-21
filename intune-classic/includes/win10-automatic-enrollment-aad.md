## <a name="enable-windows-10-automatic-enrollment"></a><span data-ttu-id="87959-101">Aktivieren der automatischen Registrierung von Windows 10</span><span class="sxs-lookup"><span data-stu-id="87959-101">Enable Windows 10 automatic enrollment</span></span>

<span data-ttu-id="87959-102">Mit der Funktion der automatischen Registrierung können Benutzer ihre Windows 10-Geräte bei Intune registrieren, wenn sie ihr Arbeitskonto auf Geräten hinzufügen, die ihnen privat gehören, oder wenn sie ihre unternehmenseigenen Geräte in Ihr Azure Active Directory einbinden.</span><span class="sxs-lookup"><span data-stu-id="87959-102">Automatic enrollment lets users enroll their Windows 10 devices in Intune when adding their work account to their personally-owned devices or joining their corporate-owned devices to your Azure Active Directory.</span></span> <span data-ttu-id="87959-103">Im Hintergrund registriert sich das Gerät des Benutzers und tritt Azure Active Directory bei.</span><span class="sxs-lookup"><span data-stu-id="87959-103">In the background, the user's device registers and joins Azure Active Directory.</span></span> <span data-ttu-id="87959-104">Nach der Registrierung wird das Gerät mit Intune verwaltet.</span><span class="sxs-lookup"><span data-stu-id="87959-104">Once registered, the device is managed with Intune.</span></span>

<span data-ttu-id="87959-105">**Voraussetzungen**</span><span class="sxs-lookup"><span data-stu-id="87959-105">**Prerequisites**</span></span>
- <span data-ttu-id="87959-106">Azure Active Directory Premium-Abonnement ([Testabonnement](http://go.microsoft.com/fwlink/?LinkID=816845))</span><span class="sxs-lookup"><span data-stu-id="87959-106">Azure Active Directory Premium subscription ([trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845))</span></span>
- <span data-ttu-id="87959-107">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="87959-107">Microsoft Intune subscription</span></span>


### <a name="configure-automatic-mdm-enrollment"></a><span data-ttu-id="87959-108">Konfigurieren der automatischen MDM-Registrierung</span><span class="sxs-lookup"><span data-stu-id="87959-108">Configure automatic MDM enrollment</span></span>

1. <span data-ttu-id="87959-109">Melden Sie sich im [Azure-Verwaltungsportal](https://portal.azure.com) (https://manage.windowsazure.com) an, und wählen Sie **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="87959-109">Sign in to the [Azure management portal](https://portal.azure.com) (https://manage.windowsazure.com), and select **Azure Active Directory**.</span></span>

  ![Screenshot des Azure-Portals](../media/auto-enroll-azure-main.png)

2. <span data-ttu-id="87959-111">Wählen Sie **Mobilität (MDM und MAM)** aus.</span><span class="sxs-lookup"><span data-stu-id="87959-111">Select **Mobility (MDM and MAM)**.</span></span>

  ![Screenshot des Azure-Portals](../media/auto-enroll-mdm.png)

3. <span data-ttu-id="87959-113">Wählen Sie **Microsoft Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="87959-113">Select **Microsoft Intune**.</span></span>

  ![Screenshot des Azure-Portals](../media/auto-enroll-intune.png)

4. <span data-ttu-id="87959-115">Konfigurieren Sie den **MDM-Benutzerbereich**.</span><span class="sxs-lookup"><span data-stu-id="87959-115">Configure **MDM User scope**.</span></span> <span data-ttu-id="87959-116">Geben Sie an, welche Geräte von Benutzern von Microsoft Intune verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="87959-116">Specify which users’ devices should be managed by Microsoft Intune.</span></span> <span data-ttu-id="87959-117">Die Windows 10-Geräte dieser Benutzer werden automatisch für die Verwaltung mit Microsoft Intune registriert.</span><span class="sxs-lookup"><span data-stu-id="87959-117">These users’ Windows 10 devices will be automatically enrolled for management with Microsoft Intune.</span></span>

  - <span data-ttu-id="87959-118">**Keine**</span><span class="sxs-lookup"><span data-stu-id="87959-118">**None**</span></span>
  - <span data-ttu-id="87959-119">**Einige**</span><span class="sxs-lookup"><span data-stu-id="87959-119">**Some**</span></span>
  - <span data-ttu-id="87959-120">**Alle**</span><span class="sxs-lookup"><span data-stu-id="87959-120">**All**</span></span>

 ![Screenshot des Azure-Portals](../media/auto-enroll-scope.png)

5. <span data-ttu-id="87959-122">Verwenden Sie die Standardwerte für die folgenden URLs:</span><span class="sxs-lookup"><span data-stu-id="87959-122">Use the default values for the following URLs:</span></span>
  - <span data-ttu-id="87959-123">**URL für MDM-Nutzungsbedingungen**</span><span class="sxs-lookup"><span data-stu-id="87959-123">**MDM Terms of use URL**</span></span>
  - <span data-ttu-id="87959-124">**URL für MDM-Ermittlung**</span><span class="sxs-lookup"><span data-stu-id="87959-124">**MDM Discovery URL**</span></span>
  - <span data-ttu-id="87959-125">**MDM Compliance-URL**</span><span class="sxs-lookup"><span data-stu-id="87959-125">**MDM Compliance URL**</span></span>

6. <span data-ttu-id="87959-126">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="87959-126">Select **Save**.</span></span>

<span data-ttu-id="87959-127">Standardmäßig ist die zweistufige Authentifizierung für den Dienst nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="87959-127">By default, two-factor authentication is not enabled for the service.</span></span> <span data-ttu-id="87959-128">Die zweistufige Authentifizierung wird jedoch empfohlen, wenn Sie ein Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="87959-128">However, two-factor authentication is recommended when registering a device.</span></span> <span data-ttu-id="87959-129">Bevor die zweistufige Authentifizierung für diesen Dienst erforderlich ist, müssen Sie einen Anbieter für die zweistufige Authentifizierung in Azure Active Directory und Ihre Benutzerkonten konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="87959-129">Before requiring two-factor authentication for this service, you must configure a two-factor authentication provider in Azure Active Directory and configure your user accounts for multi-factor authentication.</span></span> <span data-ttu-id="87959-130">Weitere Informationen finden Sie unter [Erste Schritte mit Azure Multi-Factor Authentication-Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span><span class="sxs-lookup"><span data-stu-id="87959-130">See [Getting started with the Azure Multi-Factor Authentication Server](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud).</span></span>
