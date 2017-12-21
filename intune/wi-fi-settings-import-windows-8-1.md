---
title: "Importieren von WLAN-Einstellungen für Windows 8.1 und höher"
titleSuffix: Azure portal
description: Informationen zum Importieren von WLAN-Einstellungen von Windows in ein Intune-WLAN-Profil
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8713b310d481caa3152961b19a7601b938bcfc10
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a><span data-ttu-id="45378-103">Importieren von WLAN-Einstellungen für Geräte mit Windows 8.1 und höher in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="45378-103">How to import Wi-Fi settings for Windows 8.1 and later devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="45378-104">Sie können für Windows 8.1, Windows 10 Desktop oder Windows 10 Mobile ein WLAN-Konfigurationsprofil importieren, das zuvor in eine Datei exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="45378-104">For devices that run Windows 8.1 or Windows 10 desktop or mobile, you can import a Wi-Fi configuration profile that was previously exported to a file.</span></span>

## <a name="export-wi-fi-settings-from-a-windows-device"></a><span data-ttu-id="45378-105">Exportieren von WLAN-Einstellungen von einem Windows-Gerät</span><span class="sxs-lookup"><span data-stu-id="45378-105">Export Wi-Fi settings from a Windows device</span></span>

<span data-ttu-id="45378-106">In Windows können Sie WLAN-Profile mit dem Hilfsprogramm **netsh wlan** in eine XML-Datei exportieren, die von Intune gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="45378-106">In Windows, use the **netsh wlan** utility to export an existing Wi-Fi profile to an XML file readable by Intune.</span></span> <span data-ttu-id="45378-107">Führen Sie auf einem Windows-Computer, auf dem das erforderliche WLAN-Profil bereits installiert ist, das folgende Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="45378-107">On a Windows computer that already has the required WiFi profile installed, follow this following procedure.</span></span>
1. <span data-ttu-id="45378-108">Erstellen Sie einen lokalen Ordner für die exportierten WLAN-Profile, z.B. **C:\WiFi**.</span><span class="sxs-lookup"><span data-stu-id="45378-108">Create a local folder for the exported W-Fi- profiles, such as **c:\WiFi**.</span></span>
1. <span data-ttu-id="45378-109">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="45378-109">Open up a Command Prompt as an administrator.</span></span>
1. <span data-ttu-id="45378-110">Führen Sie den Befehl **netsh wlan show profiles** aus, und notieren Sie den Namen des Profils, das Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="45378-110">Run the command **netsh wlan show profiles**, and note the name of the profile you'd like to export.</span></span> <span data-ttu-id="45378-111">In diesem Beispiel lautet der Profilname **WiFiName**.</span><span class="sxs-lookup"><span data-stu-id="45378-111">In this example, the profile name is **WiFiName**.</span></span>
1. <span data-ttu-id="45378-112">Führen Sie diesen Befehl aus: **netsh wlan export profile name="Profilname" folder=c:\Wifi**. Dadurch wird ein WLAN-Profil namens **Wi-Fi-WiFiName.xml** im Zielordner erstellt.</span><span class="sxs-lookup"><span data-stu-id="45378-112">Run this command: **netsh wlan export profile name="ProfileName" folder=c:\Wifi**.This will create a Wi-Fi profile file named **Wi-Fi-WiFiName.xml** in your target folder.</span></span>

## <a name="import-the-wi-fi-settings-into-intune"></a><span data-ttu-id="45378-113">Importieren der WLAN-Einstellungen in Intune</span><span class="sxs-lookup"><span data-stu-id="45378-113">Import the Wi-Fi settings into Intune</span></span>

1. <span data-ttu-id="45378-114">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="45378-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="45378-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="45378-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="45378-116">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="45378-116">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="45378-117">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="45378-117">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="45378-118">Klicken Sie auf dem Blatt „Profile“ auf **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="45378-118">On the profiles blade, click **Create Profile**.</span></span>
4. <span data-ttu-id="45378-119">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.</span><span class="sxs-lookup"><span data-stu-id="45378-119">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="45378-120">Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 8.1 und höher** aus.</span><span class="sxs-lookup"><span data-stu-id="45378-120">From the **Platform** drop-down list, choose **Windows 8.1 and later**.</span></span>
6. <span data-ttu-id="45378-121">Wählen Sie in der Dropdownliste **Profiltyp** die Option **WLAN (Import)** aus.</span><span class="sxs-lookup"><span data-stu-id="45378-121">From the **Profile** type drop-down list, choose **Wi-Fi import**.</span></span>
7. <span data-ttu-id="45378-122">Konfigurieren Sie auf dem Blatt **Basis-WLAN** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="45378-122">On the **Wi-Fi Basic** blade, configure the following:</span></span>
    - <span data-ttu-id="45378-123">**Verbindungsname:** Geben Sie den Namen der WLAN-Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="45378-123">**Connection name** Enter the name of the Wi-Fi connection.</span></span> <span data-ttu-id="45378-124">Dieser Name wird beim Durchsuchen der verfügbaren WLAN-Netzwerke für Endbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45378-124">This name will be displayed to end users when they browse available Wi-Fi networks.</span></span>
    - <span data-ttu-id="45378-125">**Profil-XML:** Klicken Sie auf die Schaltfläche „Durchsuchen“, und wählen Sie die XML-Datei mit den WLAN-Profileinstellungen aus, die Sie in Intune importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="45378-125">**Profile XML** Click the browse button to select the XML file containing the Wi-Fi profile settings that you want to import into Intune.</span></span>
    - <span data-ttu-id="45378-126">**Dateiinhalt:** Zeigt den XML-Code des ausgewählte Konfigurationsprofils an.</span><span class="sxs-lookup"><span data-stu-id="45378-126">**File contents** Displays the XML code for the configuration profile you selected.</span></span>
8. <span data-ttu-id="45378-127">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="45378-127">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="45378-128">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45378-128">The profile will be created and appears on the profiles list blade.</span></span>
