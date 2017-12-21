---
title: "Benutzerdefinierte Intune-Profileinstellungen für Android for Work"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie benutzerdefinierte Intune-Profileinstellungen für Android for Work-Geräte erstellen.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f12d71b9477e3072b7952d3f9331ed0cefc33ac7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a><span data-ttu-id="53bd5-103">Erstellen von benutzerdefinierten Intune-Profileinstellungen für Android for Work-Geräte</span><span class="sxs-lookup"><span data-stu-id="53bd5-103">Create Intune custom profile settings for Android for Work devices</span></span>

<span data-ttu-id="53bd5-104">Weisen Sie mithilfe der benutzerdefinierten Intune-Konfigurationsrichtlinie für Android for Work die OMA-URI-Einstellungen zu, die zum Steuern von Features auf Android for Work-Geräten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="53bd5-104">Use the Intune Android for Work custom configuration policy to assign OMA-URI settings that can be used to control features on Android for Work devices.</span></span> <span data-ttu-id="53bd5-105">Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="53bd5-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="53bd5-106">Diese Funktion soll es Ihnen ermöglichen, Android-Einstellungen zuzuweisen, die nicht mit Intune-Richtlinien konfigurierbar sind.</span><span class="sxs-lookup"><span data-stu-id="53bd5-106">This capability is intended to allow you to assign Android settings that are not configurable with Intune policies.</span></span> <span data-ttu-id="53bd5-107">Intune unterstützt zurzeit eine begrenzte Anzahl von benutzerdefinierten Android-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="53bd5-107">Intune supports a limited number of Android custom policies at present.</span></span> <span data-ttu-id="53bd5-108">Mit den Beispielen in diesem Thema finden Sie heraus, welche Richtlinien Sie konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="53bd5-108">See the examples in this topic to find out which policies you can configure.</span></span>

## <a name="create-a-custom-profile"></a><span data-ttu-id="53bd5-109">Erstellen eines benutzerdefinierten Profils</span><span class="sxs-lookup"><span data-stu-id="53bd5-109">Create a custom profile</span></span>

1. <span data-ttu-id="53bd5-110">Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen](custom-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="53bd5-110">Use the instructions in [How to configure custom device settings](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="53bd5-111">Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus, um eine neue Einstellung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="53bd5-111">On the **Custom OMA-URI Settings** blade, choose **Add** to add a new setting.</span></span>
3. <span data-ttu-id="53bd5-112">Konfigurieren Sie auf dem Blatt **Zeile hinzufügen** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="53bd5-112">On the **Add Row** blade, configure the following:</span></span>
    - <span data-ttu-id="53bd5-113">**Name**: Geben Sie einen eindeutigen Namen für die benutzerdefinierten Android for Work-Einstellungen ein, damit Sie diese im Azure-Portal leichter identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="53bd5-113">**Name** - Enter a unique name for the Android for work custom settings to help you identify it in the Azure portal.</span></span>
    - <span data-ttu-id="53bd5-114">**Beschreibung**: Geben Sie eine Beschreibung mit einem Überblick über die benutzerdefinierte Android-Richtlinie sowie weitere relevante Informationen ein, die Ihnen die Suche nach der Richtlinie erleichtern.</span><span class="sxs-lookup"><span data-stu-id="53bd5-114">**Description** - Provide a description that gives an overview of the Android custom policy and other relevant information that helps you to locate it.</span></span>
    - <span data-ttu-id="53bd5-115">**OMA-URI**: Geben Sie den OMA-URI ein, für den Sie eine Einstellung bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="53bd5-115">**OMA-URI** - Enter the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="53bd5-116">**Datentyp:** Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben.</span><span class="sxs-lookup"><span data-stu-id="53bd5-116">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="53bd5-117">Wählen Sie aus folgenden Typen aus: **Zeichenfolge**, **Zeichenfolge (XML-Datei)**, **Datum und Uhrzeit**, **Ganze Zahl**, **Gleitkomma**, **Boolesch** oder **Base64 (Datei)** aus.</span><span class="sxs-lookup"><span data-stu-id="53bd5-117">Choose from **String**, **String (XML file)**, **Date and time**, **Integer**, **Floating point**, **Boolean**, or **Base64 (file)**.</span></span>
    - <span data-ttu-id="53bd5-118">**Wert**: Geben Sie den Wert an, der mit der zuvor angegebenen OMA-URI verknüpft werden soll.</span><span class="sxs-lookup"><span data-stu-id="53bd5-118">**Value** - Specify the value to associate with the OMA-URI that you specified previously.</span></span> <span data-ttu-id="53bd5-119">Mit welcher Methode Sie diesen Wert angeben, richtet sich nach dem ausgewählten Datentyp.</span><span class="sxs-lookup"><span data-stu-id="53bd5-119">The method you use to supply this value will vary according to the data type you selected.</span></span> <span data-ttu-id="53bd5-120">Beim Datentyp **Datum und Uhrzeit** beispielsweise wählen Sie den Wert aus einer Datumsauswahl aus.</span><span class="sxs-lookup"><span data-stu-id="53bd5-120">For example, if you chose **Date and time**, you'll select the value from a date picker.</span></span>
4. <span data-ttu-id="53bd5-121">Wenn Sie fertig sind, klicken Sie auf „OK“, um zu **Benutzerdefinierte OMA-URI-Einstellungen** zurückzukehren. Fügen Sie dann weitere Einstellungen hinzu, oder wählen Sie **Erstellen** aus, um das benutzerdefinierte Profil zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="53bd5-121">When you have finished, choose OK to return to the **Custom OMA-URI Settings**, and then add more settings, or choose **Create** to create the custom profile.</span></span>


## <a name="example"></a><span data-ttu-id="53bd5-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53bd5-122">Example</span></span>

<span data-ttu-id="53bd5-123">In diesem Beispiel erstellen Sie ein benutzerdefiniertes Profil, mit dem Sie festlegen können, ob Kopier- und Einfügeaktionen zwischen Arbeits- und persönlichen Apps auf verwalteten Android for Work-Geräten zulässig sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="53bd5-123">In this example, you'll create a custom profile that can be used to restrict whether copy and paste actions between work and personal apps are allowed on managed Android for Work devices.</span></span>

1. <span data-ttu-id="53bd5-124">Verwenden Sie das Verfahren in diesem Thema, um ein benutzerdefiniertes Profil für Android for Work-Geräte mit den folgenden Werten zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="53bd5-124">Use the procedure in this topic to create a custom profile for Android for Work devices using the following values:</span></span>
    - <span data-ttu-id="53bd5-125">**Name**: Geben Sie „Kopieren und Einfügen blockieren“ oder einen anderen Text Ihrer Wahl ein.</span><span class="sxs-lookup"><span data-stu-id="53bd5-125">**Name** - Enter "Block copy and paste" or text of your own choosing.</span></span>
    - <span data-ttu-id="53bd5-126">**Beschreibung**: Geben Sie „Blockiert Kopier- und Einfügevorgänge zwischen Arbeits- und persönlichen Apps“ oder einen anderen Text Ihrer Wahl ein.</span><span class="sxs-lookup"><span data-stu-id="53bd5-126">**Description** - Enter "Blocks copy/paste between work and personal apps" or text of your own choosing.</span></span>
    - <span data-ttu-id="53bd5-127">**OMA-URI**: Geben Sie **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste** ein.</span><span class="sxs-lookup"><span data-stu-id="53bd5-127">**OMA-URI** - Enter **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.</span></span>
    - <span data-ttu-id="53bd5-128">**Datentyp**: Wählen Sie **Boolesch** aus, um anzugeben, dass der Wert für diesen OMA-URI entweder **True** oder **False** ist.</span><span class="sxs-lookup"><span data-stu-id="53bd5-128">**Data type** - Select **Boolean** to indicate that the value for this OMA-URI is either **True** or **False**.</span></span>
    - <span data-ttu-id="53bd5-129">**Wert**: Wählen Sie **True**aus.</span><span class="sxs-lookup"><span data-stu-id="53bd5-129">**Value** - Select **True**.</span></span>
2. <span data-ttu-id="53bd5-130">Die Einstellung sollte in etwa wie der folgende Screenshot aussehen.</span><span class="sxs-lookup"><span data-stu-id="53bd5-130">You should end up with a setting looking similar to this image.</span></span>
<span data-ttu-id="53bd5-131">![Blockieren von Kopier- und Einfügevorgängen für Android for Work](./media/custom-policy-afw-copy-paste.png)</span><span class="sxs-lookup"><span data-stu-id="53bd5-131">![Block copy and paste for Android for Work.](./media/custom-policy-afw-copy-paste.png)</span></span>
3. <span data-ttu-id="53bd5-132">Wenn Sie dieses benutzerdefinierte Profil einem von Ihnen verwalteten Android for Work-Gerät zuweisen, werden Kopier- und Einfügeaktionen zwischen Apps im Arbeitsprofil und im persönlichen Profil blockiert.</span><span class="sxs-lookup"><span data-stu-id="53bd5-132">Now, when you assign this custom profile to Android for Work devices you manage, copy and paste will be blocked between apps in the work, and personal profiles.</span></span>