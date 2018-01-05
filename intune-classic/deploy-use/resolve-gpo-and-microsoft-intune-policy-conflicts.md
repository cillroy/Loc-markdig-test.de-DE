---
title: "Lösen von Konflikten mit Gruppenrichtlinienobjekten und Intune-Richtlinien"
description: "Informationen zum Lösen von Konflikten zwischen Gruppenrichtlinie und Intune-Konfigurationsrichtlinien."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fcad94039722beb7d71f9d8cf7e0db2453b2a260
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="resolve-group-policy-objects-gpo-and-microsoft-intune-policy-conflicts"></a><span data-ttu-id="f904e-103">Lösen von Konflikten mit Gruppenrichtlinienobjekten und Microsoft Intune-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="f904e-103">Resolve Group Policy Objects (GPO) and Microsoft Intune policy conflicts</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f904e-104">In Intune können Sie Richtlinien zum Verwalten der Einstellungen auf Windows-PCs verwenden.</span><span class="sxs-lookup"><span data-stu-id="f904e-104">Intune uses policies that help you manage settings on Windows PCs.</span></span> <span data-ttu-id="f904e-105">Beispielsweise können Sie eine Richtlinie verwenden, um Einstellungen für die Windows-Firewall auf PCs zu steuern.</span><span class="sxs-lookup"><span data-stu-id="f904e-105">For example, you can use a policy to control settings for the Windows Firewall on PCs.</span></span> <span data-ttu-id="f904e-106">Viele Intune-Einstellungen sind mit Einstellungen vergleichbar, die Sie mit Windows-Gruppenrichtlinien konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="f904e-106">Many Intune settings are similar to settings that you might configure with Windows Group Policy.</span></span> <span data-ttu-id="f904e-107">Es ist allerdings manchmal möglich, dass die beiden Methoden miteinander in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="f904e-107">However, it is possible that, at times, the two methods might conflict with each another.</span></span>

<span data-ttu-id="f904e-108">Wenn Konflikte auftreten, hat die Gruppenrichtlinie auf Domänenebene Vorrang vor der Intune-Richtlinie, sofern die Anmeldung des PCs bei der Domäne möglich ist.</span><span class="sxs-lookup"><span data-stu-id="f904e-108">When conflicts happen, domain-level Group Policy takes precedence over Intune policy, unless the PC can’t sign in to the domain.</span></span> <span data-ttu-id="f904e-109">In diesem Fall wird die Intune-Richtlinie auf den Client-PC angewendet.</span><span class="sxs-lookup"><span data-stu-id="f904e-109">In this case, Intune policy is applied to the client PC.</span></span>

## <a name="what-to-do-if-you-are-using-group-policy"></a><span data-ttu-id="f904e-110">Vorgehensweise bei Verwendung von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f904e-110">What to do if you are using Group Policy</span></span>
<span data-ttu-id="f904e-111">Stellen Sie sicher, dass Richtlinien, die Sie anwenden, nicht von Gruppenrichtlinien verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f904e-111">Make sure that policies that you apply are not being managed by Group Policy.</span></span> <span data-ttu-id="f904e-112">Zum Vermeiden von Konflikten können Sie eine oder mehrere der folgenden Methoden verwenden:</span><span class="sxs-lookup"><span data-stu-id="f904e-112">To help prevent conflicts, you can use one or more of the following methods:</span></span>

-   <span data-ttu-id="f904e-113">Verschieben Sie Ihre PCs in eine Active Directory-Organisationseinheit (OU), auf die keine Gruppenrichtlinieneinstellungen angewendet werden, bevor Sie den Intune-Client installieren.</span><span class="sxs-lookup"><span data-stu-id="f904e-113">Move your PCs to an Active Directory organizational unit (OU) that does not have Group Policy settings applied before you install the Intune client.</span></span> <span data-ttu-id="f904e-114">Sie können bei OUs mit PCs, die in Intune registriert sind und auf die Sie die Gruppenrichtlinieneinstellungen nicht anwenden möchten, auch die Vererbung der Gruppenrichtlinie deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f904e-114">You can also block Group Policy inheritance on OUs that contain PCs enrolled in Intune to which you do not want to apply Group Policy settings.</span></span>

-   <span data-ttu-id="f904e-115">Verwenden Sie einen Sicherheitsgruppenfilter, um Gruppenrichtlinienobjekte auf PCs zu beschränken, die nicht mit Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f904e-115">Use a security group filter to restrict GPOs only to PCs that are not managed by Intune.</span></span>

-   <span data-ttu-id="f904e-116">Deaktivieren oder entfernen Sie Gruppenrichtlinienobjekte, die mit den Intune-Richtlinien in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="f904e-116">Disable or remove the Group Policy Objects that conflict with the Intune policies.</span></span>

<span data-ttu-id="f904e-117">Weitere Informationen zu Active Directory und Windows-Gruppenrichtlinien finden Sie in Ihrer Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f904e-117">For more information about Active Directory and Windows Group Policy, see your Windows Server Documentation.</span></span>

## <a name="how-to-filter-existing-gpos-to-avoid-conflicts-with-intune-policy"></a><span data-ttu-id="f904e-118">Filtern vorhandener Gruppenrichtlinienobjekte, um Konflikte mit Intune-Richtlinien zu vermeiden</span><span class="sxs-lookup"><span data-stu-id="f904e-118">How to filter existing GPOs to avoid conflicts with Intune policy</span></span>
<span data-ttu-id="f904e-119">Wenn Sie Gruppenrichtlinienobjekte ermittelt haben, deren Einstellungen in Konflikt mit Intune-Richtlinien stehen, können Sie Sicherheitsgruppenfilter verwenden, um diese Gruppenrichtlinienobjekte auf PCs zu beschränken, die nicht mit Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f904e-119">If you have identified GPOs whose settings conflict with Intune policies, you can use security group filters to restrict those GPOs only to PCs that are not managed by Intune.</span></span>

<!--- ### Use WMI filters
WMI filters selectively apply GPOs to computers that satisfy the conditions of a query. To apply a WMI filter, deploy a WMI class instance to all PCs in the enterprise before you enroll any PCs in the Intune service.

#### To apply WMI filters to a GPO

1.  Create a management object file by copying and pasting the following into a text file, and then saving it to a convenient location as **WIT.mof**. The file contains the WMI class instance that you deploy to PCs that you want to enroll in the Intune service.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Use either a startup script or Group Policy to deploy the file. The following is the deployment command for the startup script. The WMI class instance must be deployed before you enroll client PCs in the Intune service.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;path to MOF file&gt;\wit.mof**

3.  Run either of the following commands to create the WMI filters, depending on whether the GPO you want to filter applies to PCs that are managed by using Intune or to PCs that are not managed by using Intune.

    -   For GPOs that apply to PCs that are not managed by using Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   For GPOs that apply to PCs that are managed by Intune, use the following:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Edit the GPO in the Group Policy Management console to apply the WMI filter that you created in the previous step.

    -   For GPOs that should apply only to PCs that you want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=1**.

    -   For GPOs that should apply only to PCs that you do not want to manage by using Intune, apply the filter **WindowsIntunePolicyEnabled=0**.

For more information about how to apply WMI filters in Group Policy, see the blog post [Security Filtering, WMI Filtering, and Item-level Targeting in Group Policy Preferences](http://go.microsoft.com/fwlink/?LinkId=177883). --->


<span data-ttu-id="f904e-120">Sie können GPOs auf nur die Sicherheitsgruppen anwenden, die im Bereich **Sicherheitsfilterung** der Gruppenrichtlinien-Verwaltungskonsole für ein ausgewähltes GPO festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="f904e-120">You can apply GPOs to only those security groups that are specified in the **Security Filtering** area of the Group Policy Management console for a selected GPO.</span></span> <span data-ttu-id="f904e-121">Standardmäßig gelten Gruppenrichtlinienobjekte für *Authentifizierte Benutzer*.</span><span class="sxs-lookup"><span data-stu-id="f904e-121">By default, GPOs apply to *Authenticated Users*.</span></span>

-   <span data-ttu-id="f904e-122">Erstellen Sie im Snap-In **Active Directory-Benutzer und -Computer** eine neue Sicherheitsgruppe, die Computer und Benutzerkonten enthält, die nicht über Intune verwaltet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f904e-122">In the **Active Directory Users and Computers** snap-in, create a new security group that contains computers and user accounts that you do not want Intune to manage.</span></span> <span data-ttu-id="f904e-123">Nennen Sie die Gruppe z. B. *Nicht in Microsoft Intune*.</span><span class="sxs-lookup"><span data-stu-id="f904e-123">For example, you might name the group *Not In Microsoft Intune*.</span></span>

-   <span data-ttu-id="f904e-124">Klicken Sie auf der Registerkarte **Delegierung** in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die neue Sicherheitsgruppe, um den Benutzern und Computern in der Sicherheitsgruppe die geeigneten Berechtigungen **Lesen** und **Gruppenrichtlinie übernehmen** zu delegieren.</span><span class="sxs-lookup"><span data-stu-id="f904e-124">In the Group Policy Management console, on the **Delegation** tab for the selected GPO, right-click the new security group to delegate appropriate **Read** and **Apply Group Policy** permissions to both users and computers in the security group.</span></span> <span data-ttu-id="f904e-125">(Die Berechtigungen**Gruppenrichtlinie übernehmen** befinden sich im Dialogfeld **Erweitert** .)</span><span class="sxs-lookup"><span data-stu-id="f904e-125">(**Apply Group Policy** permissions are available on the **Advanced** dialog box.)</span></span>

-   <span data-ttu-id="f904e-126">Wenden Sie dann den neuen Sicherheits-Gruppenfilter auf ein ausgewähltes Gruppenrichtlinienobjekt an, und entfernen Sie den Standardfilter **Authentifizierte Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="f904e-126">Then, apply the new security group filter to a selected GPO, and remove the **Authenticated Users** default filter.</span></span>

<span data-ttu-id="f904e-127">Die neue Sicherheitsgruppe muss in den Intune-Dienständerungen als Registrierung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f904e-127">The new security group must be maintained as enrollment in the Intune service changes.</span></span>

### <a name="see-also"></a><span data-ttu-id="f904e-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f904e-128">See also</span></span>
[<span data-ttu-id="f904e-129">Verwalten von Windows-PCs mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f904e-129">Manage Windows PCs with Microsoft Intune</span></span>](manage-windows-pcs-with-microsoft-intune.md)
