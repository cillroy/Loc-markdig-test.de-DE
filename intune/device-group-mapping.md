---
title: "Verwenden von Gerätekategorien in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie Gerätekategorien verwenden, die Benutzer beim Registrieren ihrer Geräte in Intune auswählen können.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7b668c37-40b9-4c69-8334-5d8344e78c24
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ddcd4639c1f5a0949be46025e16e44d0b6ac6616
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="map-device-groups"></a><span data-ttu-id="79c28-103">Zuordnen von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="79c28-103">Map device groups</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="79c28-104">Verwenden Sie die Gerätekategorien in Microsoft Intune, damit Geräte basierend auf Kategorien, die Sie definieren, automatisch Gruppen hinzugefügt werden, sodass Sie diese Geräte einfacher verwalten können.</span><span class="sxs-lookup"><span data-stu-id="79c28-104">Use Microsoft Intune device categories to automatically add devices to groups based on categories that you define, in order to make it easier for you to manage those devices.</span></span>

<span data-ttu-id="79c28-105">Gerätekategorien verwenden den folgenden Workflow:</span><span class="sxs-lookup"><span data-stu-id="79c28-105">Device categories use the following workflow:</span></span>
1. <span data-ttu-id="79c28-106">Erstellen Sie Kategorien, die Benutzer beim Registrieren ihrer Geräte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="79c28-106">Create categories that users will choose from when they enroll their device</span></span>
3. <span data-ttu-id="79c28-107">Wenn Endbenutzer von iOS- und Android-Geräten ihre Geräte registrieren, müssen sie aus der Liste der von Ihnen konfigurierten Kategorien eine Kategorie auswählen.</span><span class="sxs-lookup"><span data-stu-id="79c28-107">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="79c28-108">Um einem Windows-Gerät eine Kategorie zuzuweisen, müssen Endbenutzer die Unternehmensportal-Website verwenden (weitere Informationen dazu finden Sie in diesem Thema unter **Nach dem Konfigurieren von Gerätegruppen**).</span><span class="sxs-lookup"><span data-stu-id="79c28-108">To assign a category to a Windows device, end users must use the Company Portal website (see **After you configure device groups** in this topic for more details).</span></span>
4. <span data-ttu-id="79c28-109">Dann können Sie Richtlinien und Apps für diese Gruppen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="79c28-109">You can then deploy policies and apps to these groups.</span></span>

<span data-ttu-id="79c28-110">Sie können beliebige Gerätekategorien erstellen, z.B.:</span><span class="sxs-lookup"><span data-stu-id="79c28-110">You can create any device categories you want, for example:</span></span>
- <span data-ttu-id="79c28-111">POS-Gerät (Point of Sale)</span><span class="sxs-lookup"><span data-stu-id="79c28-111">Point of sale device</span></span>
- <span data-ttu-id="79c28-112">Demogerät</span><span class="sxs-lookup"><span data-stu-id="79c28-112">Demonstration device</span></span>
- <span data-ttu-id="79c28-113">Sales</span><span class="sxs-lookup"><span data-stu-id="79c28-113">Sales</span></span>
- <span data-ttu-id="79c28-114">Kontoführung</span><span class="sxs-lookup"><span data-stu-id="79c28-114">Accounting</span></span>
- <span data-ttu-id="79c28-115">Manager</span><span class="sxs-lookup"><span data-stu-id="79c28-115">Manager</span></span>

## <a name="how-to-configure-device-categories"></a><span data-ttu-id="79c28-116">Konfigurieren von Gerätekategorien</span><span class="sxs-lookup"><span data-stu-id="79c28-116">How to configure device categories</span></span>

### <a name="step-1---create-device-categories-in-the-intune-blade-of-the-azure-portal"></a><span data-ttu-id="79c28-117">Schritt 1: Erstellen von Gerätekategorien auf dem Blatt „Intune“ im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="79c28-117">Step 1 - Create device categories in the Intune blade of the Azure portal</span></span>
1. <span data-ttu-id="79c28-118">Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-118">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="79c28-119">Wählen Sie im Blatt **Intune** die Option **Geräteregistrierung** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-119">On the **Intune** blade, choose **Device Enrollment**.</span></span>
3. <span data-ttu-id="79c28-120">Wählen Sie im Blatt **Geräteregistrierung** die Option **Gerätekategorien** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-120">On the **Device Enrollment** blade, choose **Device Categories**.</span></span>
4. <span data-ttu-id="79c28-121">Wählen Sie auf der Seite **Gerätekategorien** die Option **Erstellen** aus, um eine neue Kategorie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="79c28-121">On the **Device Categories** page, choose **Create** to add a new category.</span></span>
5. <span data-ttu-id="79c28-122">Geben Sie auf dem nächsten Blatt einen **Namen** für die neue Kategorie und optional eine **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="79c28-122">On the next blade, enter a **Name** for the new category, and an optional **Description**.</span></span>
6. <span data-ttu-id="79c28-123">Klicken Sie auf **Erstellen**, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="79c28-123">When you are done, click **Create**.</span></span> <span data-ttu-id="79c28-124">Die gerade von Ihnen erstellte Kategorie wird in der Liste der Kategorien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79c28-124">You’ll see the category you just created in the list of categories.</span></span>

<span data-ttu-id="79c28-125">Verwenden Sie den Kategorienamen des Geräts zum Erstellen von Azure Active Directory-Sicherheitsgruppen in Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="79c28-125">You'll use the device category name when you create Azure Active Directory security groups in step 2.</span></span>

### <a name="step-2---create-azure-active-directory-security-groups"></a><span data-ttu-id="79c28-126">Schritt 2: Erstellen von Active Directory-Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="79c28-126">Step 2 - Create Azure Active Directory security groups</span></span>
<span data-ttu-id="79c28-127">In diesem Schritt erstellen Sie dynamische Gruppen im Azure-Portal auf Basis der Gerätekategorie und des Gerätekategorienamens.</span><span class="sxs-lookup"><span data-stu-id="79c28-127">In this step, you'll create dynamic groups in the Azure portal based on the device category and device category name.</span></span>

<span data-ttu-id="79c28-128">Lesen Sie das Thema [Verwenden von Attributen zum Erstellen erweiterter Regeln](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in der Dokumentation zu Azure Active Directory, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="79c28-128">To continue, refer to the topic [Using attributes to create advanced rules](https://azure.microsoft.com/documentation/articles/active-directory-accessmanagement-groups-with-advanced-rules/#using-attributes-to-create-rules-for-device-objects) in the Azure Active Directory documentation.</span></span>

<span data-ttu-id="79c28-129">Verwenden Sie die Informationen in diesem Abschnitt zum Erstellen einer Gerätegruppe mit einer erweiterten Regel mithilfe des Attributs **deviceCategory**.</span><span class="sxs-lookup"><span data-stu-id="79c28-129">Use the information in this section to create a device group with an advanced rule using the **deviceCategory** attribute.</span></span> <span data-ttu-id="79c28-130">Beispiel: (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")</span><span class="sxs-lookup"><span data-stu-id="79c28-130">For example (**device.deviceCategory -eq** "*<the device category name you got from the Azure portal>*")</span></span>

<span data-ttu-id="79c28-131">Wenn nach dem Konfigurieren von Gerätegruppen Benutzer ihre Geräte registrieren, wird ihnen eine Liste der von Ihnen konfigurierten Kategorien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79c28-131">After you configure device groups, and users enroll their device, they are presented with a list of the categories you configured.</span></span> <span data-ttu-id="79c28-132">Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät der Active Directory-Sicherheitsgruppe hinzugefügt, die der gewählten Kategorie entspricht.</span><span class="sxs-lookup"><span data-stu-id="79c28-132">After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.</span></span>

### <a name="how-to-view-the-categories-of-devices-you-manage"></a><span data-ttu-id="79c28-133">Anzeigen der Kategorien von Geräten, die Sie verwalten</span><span class="sxs-lookup"><span data-stu-id="79c28-133">How to view the categories of devices you manage</span></span>

1.  <span data-ttu-id="79c28-134">Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-134">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="79c28-135">Wählen Sie im Azure-Portal auf dem Blatt „Intune“ die Option **Geräte und Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-135">In the Intune blade of the Azure portal, choose **Devices and Groups**.</span></span>

3.  <span data-ttu-id="79c28-136">Klicken Sie unter **Verwalten** auf **Alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="79c28-136">Under **Manage**, click **All devices**.</span></span>

4.  <span data-ttu-id="79c28-137">Sehen Sie sich in der Liste der Geräte die Spalte **Kategorie** an.</span><span class="sxs-lookup"><span data-stu-id="79c28-137">In the list of devices, examine the **Category** column.</span></span>

<span data-ttu-id="79c28-138">Wenn die Spalte **Kategorie** nicht angezeigt wird, klicken Sie auf **Spalten**, wählen Sie in der Liste **Kategorie** aus, und klicken Sie dann auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="79c28-138">If the **Category** column isn’t displayed, click **Columns**, choose **Category** from the list, and then click **Apply**.</span></span>

### <a name="to-change-the-category-of-a-device"></a><span data-ttu-id="79c28-139">So ändern Sie die Kategorie eines Geräts</span><span class="sxs-lookup"><span data-stu-id="79c28-139">To change the category of a device</span></span>

1. <span data-ttu-id="79c28-140">Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-140">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="79c28-141">Wählen Sie auf dem Blatt **Intune** die Option **Geräte & Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-141">On the **Intune** blade, choose **Devices & Groups**.</span></span>
4. <span data-ttu-id="79c28-142">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Verwalten** > **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-142">On the **Devices and Groups** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="79c28-143">Wählen Sie in der Liste der Geräte das gewünschte Gerät und anschließend auf dem Blatt mit den Geräteeigenschaften **Verwalten** > **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="79c28-143">In the list of devices, choose the device you want, then, on the device properties blade, choose **Manage** > **Properties**.</span></span>
6. <span data-ttu-id="79c28-144">Auf dem nächsten Blatt können Sie die **Gerätekategorie** des ausgewählten Geräts in einen beliebigen Kategorienamen ändern, den Sie zuvor konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="79c28-144">On the next blade, you can change the **Device category** of the selected device to any of the category names you previously configured.</span></span>

## <a name="after-you-configure-device-groups"></a><span data-ttu-id="79c28-145">Nach dem Konfigurieren von Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="79c28-145">After you configure device groups</span></span>

<span data-ttu-id="79c28-146">Wenn Endbenutzer von iOS- und Android-Geräten ihre Geräte registrieren, müssen sie aus der Liste der von Ihnen konfigurierten Kategorien eine Kategorie auswählen.</span><span class="sxs-lookup"><span data-stu-id="79c28-146">When end users of iOS and Android devices enroll their device, they must choose a category from the list of categories you configured.</span></span> <span data-ttu-id="79c28-147">Nachdem sie eine Kategorie ausgewählt und die Registrierung abgeschlossen haben, wird ihr Gerät zu der Intune-Gerätegruppe oder Active Directory-Sicherheitsgruppe hinzugefügt, die der gewählten Kategorie entspricht.</span><span class="sxs-lookup"><span data-stu-id="79c28-147">After they choose a category and finish enrollment, their device is added to the Intune device group, or Active Directory security group that corresponds with the category they chose.</span></span>

<span data-ttu-id="79c28-148">Unabhängig von der Plattform können Ihre Endbenutzer nach der Registrierung des Geräts jederzeit auf „portal.manage.microsoft.com“ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="79c28-148">Regardless of platform, your end users can always go to portal.manage.microsoft.com after enrolling the device.</span></span> <span data-ttu-id="79c28-149">Weisen Sie den Benutzer dazu an, auf die Unternehmensportalwebsite zuzugreifen und zu **Meine Geräte** zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="79c28-149">Have the user access the Company Portal website and go to **My Devices**.</span></span> <span data-ttu-id="79c28-150">Er hat dann die Möglichkeit, ein auf der Seite aufgeführtes registriertes Gerät sowie eine Kategorie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="79c28-150">They can choose an enrolled device listed on the page, then select a category.</span></span>

<span data-ttu-id="79c28-151">Nach Auswahl der Kategorie wird das Gerät automatisch zur entsprechenden Gruppe hinzugefügt, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="79c28-151">After choosing a category, the device is automatically added to the corresponding group you created.</span></span> <span data-ttu-id="79c28-152">Wenn ein Gerät bereits registriert wurde, bevor Sie Kategorien konfiguriert haben, wird dem Benutzer auf der Unternehmensportal-Website eine Benachrichtigung zu dem Gerät angezeigt, und der Benutzer wird aufgefordert, beim nächsten Zugriff auf die Unternehmensportal-App über ein iOS- oder Android-Gerät eine Kategorie auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="79c28-152">If a device is already enrolled before you configure categories, the end user will see a notification about the device on the Company Portal website, and will be asked to select a category the next time they access the Company Portal app on iOS or Android.</span></span>

## <a name="further-information"></a><span data-ttu-id="79c28-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79c28-153">Further information</span></span>
- <span data-ttu-id="79c28-154">Sie können eine Gerätekategorie im Azure-Portal bearbeiten. Sie müssen dann aber manuell alle Azure Active Directory-Sicherheitsgruppen aktualisieren, die auf diese Kategorie verweisen.</span><span class="sxs-lookup"><span data-stu-id="79c28-154">You can edit a device category in the Azure Portal, but if you do this, you must manually update any Azure Active Directory Security groups that reference this category.</span></span>

- <span data-ttu-id="79c28-155">Wenn Sie eine Kategorie löschen, tragen alle Geräte, die dieser zuvor zugewiesen waren, anschließend den Kategorienamen **Nicht zugewiesen**.</span><span class="sxs-lookup"><span data-stu-id="79c28-155">If you delete a category, any devices that were assigned to it will subsequently display the category name **Unassigned**.</span></span>
