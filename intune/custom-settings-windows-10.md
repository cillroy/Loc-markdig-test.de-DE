---
title: "Benutzerdefinierte Intune-Einstellungen für Windows 10-Geräte"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Windows 10-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fa11591bf356165f57eb41db2d21b8f727e506d7
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a><span data-ttu-id="5c660-103">Benutzerdefinierte Geräteeinstellungen für Windows 10-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5c660-103">Custom device settings for Windows 10 devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

 <span data-ttu-id="5c660-104">Stellen Sie mithilfe des **benutzerdefinierten** Profils von Microsoft Intune für Windows 10 und Windows 10 Mobile OMA-URI-Einstellungen (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Geräten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="5c660-104">Use the Microsoft Intune **custom** profile for Windows 10 and Windows 10 Mobile to deploy OMA-URI (Open Mobile Alliance Uniform Resource Identifier) settings that can be used to control features on devices.</span></span> <span data-ttu-id="5c660-105">Windows 10 stellt viele CSP-Einstellungen zur Verfügung, z. B. den [Richtlinienkonfigurationsdienst-Anbieter (Policy Configuration Service Provider; Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).</span><span class="sxs-lookup"><span data-stu-id="5c660-105">Windows 10 makes many CSP settings available, for example, the [Policy Configuration Service Provider (Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).</span></span>
<span data-ttu-id="5c660-106">Wenn Sie nach einer bestimmten Einstellung suchen, beachten Sie, dass das [Geräteeinschränkungsprofil von Windows 10](device-restrictions-windows-10.md) viele Einstellungen enthält, die in Intune integriert sind und keine Angabe benutzerdefinierter Werte erfordern.</span><span class="sxs-lookup"><span data-stu-id="5c660-106">If you are looking for a particular setting, remember that the [Windows 10 device restriction profile](device-restrictions-windows-10.md) contains many settings that are built-in to Intune and do not require you to specify custom values.</span></span>

1. <span data-ttu-id="5c660-107">Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="5c660-107">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="5c660-108">Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5c660-108">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="5c660-109">Klicken Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** auf **Hinzufügen**, um einen neuen Wert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5c660-109">On the **Custom OMA-URI Settings** blade, click **Add** to add a new value.</span></span> <span data-ttu-id="5c660-110">Sie können auch auf **Exportieren** klicken, um eine Liste aller konfigurierten Werte in einer durch Trennzeichen getrennten Wertedatei (CSV) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5c660-110">You can also click **Export** to create a list of all the values you configured in a comma-separated values (.csv) file.</span></span>
4. <span data-ttu-id="5c660-111">Geben Sie für jede OMA-URI-Einstellung, die Sie hinzufügen möchten, die folgenden Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="5c660-111">For each OMA-URI setting you want to add, enter the following information.</span></span> <span data-ttu-id="5c660-112">Verwenden Sie die Liste in diesem Thema, um weitere Informationen zu den Einstellungen zu erhalten, die Sie verwenden können:</span><span class="sxs-lookup"><span data-stu-id="5c660-112">Use the list in this topic to learn about the settings you can use:</span></span>
    - <span data-ttu-id="5c660-113">**Einstellungsname** – Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="5c660-113">**Setting name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="5c660-114">**Beschreibung der Einstellung** – Geben Sie optional eine Beschreibung für die Einstellung ein.</span><span class="sxs-lookup"><span data-stu-id="5c660-114">**Setting description** - Optionally, enter a description for the setting.</span></span>
    - <span data-ttu-id="5c660-115">**Datentyp** – Wählen Sie aus:</span><span class="sxs-lookup"><span data-stu-id="5c660-115">**Data type** - Choose from:</span></span>
        - <span data-ttu-id="5c660-116">**Zeichenfolge**</span><span class="sxs-lookup"><span data-stu-id="5c660-116">**String**</span></span>
        - <span data-ttu-id="5c660-117">**Zeichenfolge (XML)**</span><span class="sxs-lookup"><span data-stu-id="5c660-117">**String (XML)**</span></span>
        - <span data-ttu-id="5c660-118">**Datum und Uhrzeit**</span><span class="sxs-lookup"><span data-stu-id="5c660-118">**Date and time**</span></span>
        - <span data-ttu-id="5c660-119">**Ganze Zahl**</span><span class="sxs-lookup"><span data-stu-id="5c660-119">**Integer**</span></span>
        - <span data-ttu-id="5c660-120">**Gleitkomma**</span><span class="sxs-lookup"><span data-stu-id="5c660-120">**Floating point**</span></span>
        - <span data-ttu-id="5c660-121">**Boolesch**</span><span class="sxs-lookup"><span data-stu-id="5c660-121">**Boolean**</span></span>
    - <span data-ttu-id="5c660-122">**OMA-URI (Groß-/Kleinschreibung beachten)** – Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c660-122">**OMA-URI (case sensitive)** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="5c660-123">**Wert** – Geben Sie den Wert an, der mit der von Ihnen eingegebenen OMA-URI verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="5c660-123">**Value** - Specify the value to associate with the OMA-URI you entered.</span></span>
5. <span data-ttu-id="5c660-124">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5c660-124">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>
<span data-ttu-id="5c660-125">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5c660-125">The profile will be created and appears on the profiles list blade.</span></span>

## <a name="example"></a><span data-ttu-id="5c660-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c660-126">Example</span></span>
<span data-ttu-id="5c660-127">Im folgenden Screenshot ist die Einstellung **Connectivity/AllowVPNOverCellular** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5c660-127">In the screenshot below, the setting **Connectivity/AllowVPNOverCellular** has been enabled.</span></span> <span data-ttu-id="5c660-128">Dadurch kann ein Windows 10-Gerät eine VPN-Verbindung über ein Mobilfunknetz öffnen.</span><span class="sxs-lookup"><span data-stu-id="5c660-128">This lets a Windows 10 device open a VPN connection when on a cellular network.</span></span>

> ![Beispiel für eine benutzerdefinierte Richtlinie mit VPN-Einstellungen](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a><span data-ttu-id="5c660-130">Suchen konfigurierbarer Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5c660-130">How to find the policies you can configure</span></span>

<span data-ttu-id="5c660-131">Eine vollständige Liste aller Konfigurationsdienstanbieter (CSP), die von Windows 10 unterstützt werden, finden Sie in der [Konfigurationsdienstanbieter-Referenz](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in der Windows-Dokumentationsbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5c660-131">You’ll find a complete list of all configuration service providers (CSPs) that Windows 10 supports in the [Configuration service provider reference](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in the Windows documentation library.</span></span>

<span data-ttu-id="5c660-132">Nicht alle Einstellungen sind mit allen Windows 10-Versionen kompatibel.</span><span class="sxs-lookup"><span data-stu-id="5c660-132">Not all settings are compatible with all Windows 10 versions.</span></span> <span data-ttu-id="5c660-133">Die Tabelle im Windows-Abschnitt enthält entsprechende Informationen, welche Versionen für die einzelnen Konfigurationsdienstanbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="5c660-133">The table in the Windows topic tells you which versions are supported for each CSP.</span></span>

<span data-ttu-id="5c660-134">Darüber hinaus unterstützt Intune nicht alle Einstellungen, die in diesem Abschnitt aufgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5c660-134">Additionally, Intune does not support all of the settings listed in the topic.</span></span> <span data-ttu-id="5c660-135">Öffnen Sie den Abschnitt für die jeweilige Einstellung, um herauszufinden, ob die gewünschte Einstellung von Intune unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="5c660-135">To find out if Intune supports the setting you want, open the topic for that setting.</span></span> <span data-ttu-id="5c660-136">Jede Einstellungsseite zeigt ihren unterstützten Vorgang an.</span><span class="sxs-lookup"><span data-stu-id="5c660-136">Each setting page shows it’s supported operation.</span></span> <span data-ttu-id="5c660-137">Damit die Einstellung mit Intune funktioniert, muss sie die Vorgänge **Hinzufügen** oder **Ersetzen** unterstützen.</span><span class="sxs-lookup"><span data-stu-id="5c660-137">To work with Intune, the setting must support the **Add** or **Replace** operations.</span></span>


