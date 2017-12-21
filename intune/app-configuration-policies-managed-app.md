---
title: "Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung verwenden."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E61C1618-79D0-41A1-B61F-4123FB6672FC
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b4ccc107521ae7f199ad2b37b86b573995e83c4d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="add-app-configuration-policies-for-managed-apps-without-device-enrollment"></a><span data-ttu-id="71982-103">Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="71982-103">Add app configuration policies for managed apps without device enrollment</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="71982-104">Sie können App-Konfigurationsrichtlinien mit verwalteten Apps, die das Intune App-SDK unterstützen, sogar auf nicht registrierten Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="71982-104">You can use app configuration policies with managed apps that support the Intune App SDK, even on devices that are not enrolled.</span></span> 

1. <span data-ttu-id="71982-105">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="71982-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="71982-106">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="71982-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="71982-107">Wählen Sie die Workload **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="71982-107">Choose the **Mobile apps** workload.</span></span>
4. <span data-ttu-id="71982-108">Wählen Sie in der Gruppe **Verwalten** **App-Konfigurationsrichtlinien** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="71982-108">Choose **App configuration policies** in the **Manage** group, and then choose **Add**.</span></span>
5. <span data-ttu-id="71982-109">Legen Sie die folgenden Details fest:</span><span class="sxs-lookup"><span data-stu-id="71982-109">Set the following details:</span></span>
    - <span data-ttu-id="71982-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="71982-110">**Name**</span></span>  
      <span data-ttu-id="71982-111">Der Name des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="71982-111">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="71982-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="71982-112">**Description**</span></span>  
      <span data-ttu-id="71982-113">Die Beschreibung des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="71982-113">The  description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="71982-114">**Geräteregistrierungstyp**</span><span class="sxs-lookup"><span data-stu-id="71982-114">**Device enrollment type**</span></span>  
      <span data-ttu-id="71982-115">Klicken Sie auf **Apps verwalten**.</span><span class="sxs-lookup"><span data-stu-id="71982-115">Choose **Manage apps**.</span></span>
6. <span data-ttu-id="71982-116">Klicken Sie auf **Zugeordnete App**, um die App auszuwählen, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="71982-116">Select **Associated app** to choose the app that you are going to configure.</span></span> <span data-ttu-id="71982-117">Wählen Sie die App aus der Liste der Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="71982-117">Select the app from the list of apps that you have approved and synchronized with Intune.</span></span>
7. <span data-ttu-id="71982-118">Geben Sie für jede von der App unterstützte Konfigurationseinstellung den **Namen** und den **Wert** ein, und wählen Sie die Auslassungspunkte (**…**) aus.</span><span class="sxs-lookup"><span data-stu-id="71982-118">For each configuration setting that the app supports, type the **Name** and **Value**, and choose the ellipsis (**…**).</span></span>  
    <span data-ttu-id="71982-119">Wählen Sie zum Löschen einer Konfiguration die Auslassungspunkte (**...**) und dann auf **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="71982-119">To delete a configuration, choose the ellipsis (**…**) and select **Delete**.</span></span>  
    <span data-ttu-id="71982-120">Für das Intune App SDK aktivierte Apps unterstützen Konfigurationen in Schlüssel-Wert-Paaren.</span><span class="sxs-lookup"><span data-stu-id="71982-120">Intune App SDK-enabled apps support configurations in key/value pairs.</span></span> <span data-ttu-id="71982-121">Weitere Informationen zu den unterstützten Schlüssel-Wert-Konfigurationen finden Sie in der Dokumentation zu den einzelnen Apps.</span><span class="sxs-lookup"><span data-stu-id="71982-121">To learn more about which key-value configurations are supported, consult the documentation for each app.</span></span>  
    <span data-ttu-id="71982-122">Zusätzlich können Sie Tokens verwenden, die dynamisch mit den Daten aufgefüllt werden, die von der App generiert werden.</span><span class="sxs-lookup"><span data-stu-id="71982-122">In addition, you can use tokens that will be dynamically populated with data generated by the application.</span></span>

## <a name="configuration-values-for-using-tokens"></a><span data-ttu-id="71982-123">Konfigurationswerte für das Verwenden von Token</span><span class="sxs-lookup"><span data-stu-id="71982-123">Configuration values for using tokens</span></span>

<span data-ttu-id="71982-124">Intune kann bestimmte Token generieren und sie an die verwaltete Anwendung senden.</span><span class="sxs-lookup"><span data-stu-id="71982-124">Intune can generate certain tokens and send them to the managed application.</span></span> <span data-ttu-id="71982-125">Wenn Ihre App-Konfiguration beispielsweise eine E-Mail-Einstellung verwenden kann, können Sie mithilfe eines Tokens dynamische E-Mail hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="71982-125">For example, if your app configuration can use an email setting, you can add a dynamic email by using a token.</span></span> <span data-ttu-id="71982-126">Geben Sie den Namen, der von der App erwartet wird, in das Feld **Name** und anschließend `\{\{mail\}\}` in das Feld **Wert** ein.</span><span class="sxs-lookup"><span data-stu-id="71982-126">Type the name expected by the app in the **Name** field, and then type `\{\{mail\}\}` in the **Value** field.</span></span>

<span data-ttu-id="71982-127">Intune unterstützt folgende Tokentypen in den Konfigurationseinstellungen:</span><span class="sxs-lookup"><span data-stu-id="71982-127">Intune supports the following token types in the configuration settings:</span></span>

- <span data-ttu-id="71982-128">\{\{userPrincipalName\}\}: z.B.**John@contoso.com**</span><span class="sxs-lookup"><span data-stu-id="71982-128">\{\{userprincipalname\}\}—for example, **John@contoso.com**</span></span>
- <span data-ttu-id="71982-129">\{\{Mail\}\}: z.B.**John@contoso.com**</span><span class="sxs-lookup"><span data-stu-id="71982-129">\{\{mail\}\}—for example, **John@contoso.com**</span></span>
- <span data-ttu-id="71982-130">\{\{partialupn\}\}: z.B. **John**</span><span class="sxs-lookup"><span data-stu-id="71982-130">\{\{partialupn\}\}—for example, **John**</span></span>
- <span data-ttu-id="71982-131">\{\{accountid\}\}: z.B. **fc0dc142-71d8-4b12-bbea-bae2a8514c81**</span><span class="sxs-lookup"><span data-stu-id="71982-131">\{\{accountid\}\}—for example, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**</span></span>
- <span data-ttu-id="71982-132">\{\{userid\}\}: z.B. **3ec2c00f-b125-4519-acf0-302ac3761822**</span><span class="sxs-lookup"><span data-stu-id="71982-132">\{\{userid\}\}—for example, **3ec2c00f-b125-4519-acf0-302ac3761822**</span></span>
- <span data-ttu-id="71982-133">\{\{username\}\}: z.B. **John Doe**</span><span class="sxs-lookup"><span data-stu-id="71982-133">\{\{username\}\}—for example, **John Doe**</span></span>
- <span data-ttu-id="71982-134">\{\{PrimarySMTPAddress\}\}. z.B.**testuser@ad.domain.com**</span><span class="sxs-lookup"><span data-stu-id="71982-134">\{\{PrimarySMTPAddress\}\}—for example, **testuser@ad.domain.com**</span></span> 


> [!Note]  
> <span data-ttu-id="71982-135">Die Zeichen \{\{ und \}\} werden nur von Tokentypen verwendet und dürfen nicht für andere Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="71982-135">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <a name="next-steps"></a><span data-ttu-id="71982-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="71982-136">Next steps</span></span>

<span data-ttu-id="71982-137">Fahren Sie wie gewöhnlich mit dem [Zuweisen](apps-deploy.md) und [Überwachen](apps-monitor.md) der App fort.</span><span class="sxs-lookup"><span data-stu-id="71982-137">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>