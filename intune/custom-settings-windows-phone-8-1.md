---
title: "Benutzerdefinierte Intune-Einstellungen für Windows Phone 8.1-Geräte"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Windows Phone 8.1-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 21c55041-3821-4a62-9f85-855b97dba269
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a2ff0db3aebf2e043e137c96ce1bc6e73ff2f42a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-windows-phone-81-devices-in-microsoft-intune"></a><span data-ttu-id="5b459-103">Benutzerdefinierte Einstellungen für Windows Phone 8.1-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5b459-103">Custom settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="5b459-104">Weisen Sie mithilfe des **benutzerdefinierten** Profils für Windows Phone 8.1 von Microsoft Intune die OMA-URI-Einstellungen zu, um Features auf Windows Phone 8.1-Geräten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="5b459-104">Use the Microsoft Intune Windows Phone 8.1 **Custom** profile to assign OMA-URI settings that can be used to control features on Windows Phone 8.1 devices.</span></span> <span data-ttu-id="5b459-105">Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="5b459-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="5b459-106">Diese Funktion soll es Ihnen ermöglichen, Einstellungen zuzuweisen, die nicht mit anderen Intune-Richtlinien konfigurierbar sind.</span><span class="sxs-lookup"><span data-stu-id="5b459-106">This capability is intended to allow you to assign settings that are not configurable with other Intune policies.</span></span>

## <a name="custom-policy-settings-for-windows-phone-81-devices"></a><span data-ttu-id="5b459-107">Benutzerdefinierte Richtlinieneinstellungen für Windows Phone 8.1-Geräte</span><span class="sxs-lookup"><span data-stu-id="5b459-107">Custom policy settings for Windows Phone 8.1 devices</span></span>

1. <span data-ttu-id="5b459-108">Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="5b459-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="5b459-109">Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5b459-109">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="5b459-110">Konfigurieren Sie auf dem Blatt **Zeile hinzufügen** die folgenden Werte für jede Einstellung:</span><span class="sxs-lookup"><span data-stu-id="5b459-110">On the **Add Row** blade, configure the following values for each setting:</span></span>
    - <span data-ttu-id="5b459-111">**Name:** Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="5b459-111">**Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="5b459-112">**Beschreibung:** Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.</span><span class="sxs-lookup"><span data-stu-id="5b459-112">**Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.</span></span>
    - <span data-ttu-id="5b459-113">**OMA-URI:** Geben Sie den OMA-URI an, für den Sie eine Einstellung bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="5b459-113">**OMA-URI** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="5b459-114">**Datentyp:** Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben.</span><span class="sxs-lookup"><span data-stu-id="5b459-114">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="5b459-115">Wählen Sie aus **Zeichenfolge**, **Datum und Uhrzeit**, **Ganze Zahl**, **Gleitkomma** oder **Boolesch** aus.</span><span class="sxs-lookup"><span data-stu-id="5b459-115">Choose from **String**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.</span></span>
    - <span data-ttu-id="5b459-116">**Wert:** Geben Sie den gewünschten Wert an, der dem von Ihnen eingegebenen OMA-URI zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b459-116">**Value** - Enter the value you want to associate with the OMA-URI you entered.</span></span>

4. <span data-ttu-id="5b459-117">Klicken Sie abschließend auf **OK**, und fahren Sie bei Bedarf mit dem Hinzufügen weiterer Einstellungen fort.</span><span class="sxs-lookup"><span data-stu-id="5b459-117">Click **OK** once you are done, then continue to add more settings as required.</span></span>
