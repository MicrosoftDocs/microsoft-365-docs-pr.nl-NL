---
title: Domain-joined Windows 10 devices to be managed by Microsoft 365 for business
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Lees hoe u in Microsoft 365 enkele stappen lokale active-directory-apparaten Windows 10 kunt beveiligen.
ms.openlocfilehash: ec80159bdceffd8a13d09a297a2acc1b78c9b1b3
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636081"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="b9b31-103">Schakel domeingevoegde Windows 10 apparaten in om te worden beheerd door Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="b9b31-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="b9b31-104">Als uw organisatie on-premises Windows Server Active Directory gebruikt, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, met behoud van toegang tot on-premises resources waarvoor lokale verificatie vereist is.</span><span class="sxs-lookup"><span data-stu-id="b9b31-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="b9b31-105">Als u deze beveiliging wilt instellen, kunt u verbonden **hybride Azure AD-apparaten implementeren.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="b9b31-106">Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9b31-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

## <a name="watch-configure-hybrid-azure-active-directory-join"></a><span data-ttu-id="b9b31-107">Kijken: Hybride Azure Active Directory configureren</span><span class="sxs-lookup"><span data-stu-id="b9b31-107">Watch: Configure Hybrid Azure Active Directory join</span></span>

<span data-ttu-id="b9b31-108">In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de stappen die volgen.</span><span class="sxs-lookup"><span data-stu-id="b9b31-108">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a><span data-ttu-id="b9b31-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="b9b31-109">Before you begin</span></span>

- <span data-ttu-id="b9b31-110">Gebruikers synchroniseren met Azure AD met Azure AD Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="b9b31-110">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="b9b31-111">Voltooi Azure AD Verbinding maken organisatie-eenheid (OU) synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="b9b31-111">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="b9b31-112">Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben om Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b9b31-112">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="b9b31-113">Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="b9b31-113">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="b9b31-114">1. MDM Authority verifiëren in Intune</span><span class="sxs-lookup"><span data-stu-id="b9b31-114">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="b9b31-115">Ga naar [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en selecteer op Microsoft Intune pagina Apparaatinschrijving **en** zorg  er op de pagina Overzicht voor dat **MDM-autoriteit** **Intune is.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-115">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="b9b31-116">Als **MDM-autoriteit** **Geen** is, klikt u op **de MDM-autoriteit** om deze in te stellen **op Intune.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="b9b31-117">Als MDM-autoriteit **Microsoft Office 365 is,** gaat u naar Apparaten registreren en gebruikt u het dialoogvenster **MDM-autoriteit** toevoegen aan de rechterkant om  >   **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit** toevoegen is alleen beschikbaar als **de MDM-autoriteit** is ingesteld op Microsoft Office 365). </span><span class="sxs-lookup"><span data-stu-id="b9b31-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="b9b31-118">2. Controleren of Azure AD is ingeschakeld voor het deelnemen aan computers</span><span class="sxs-lookup"><span data-stu-id="b9b31-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="b9b31-119">Ga naar het beheercentrum bij en selecteer Azure Active Directory (selecteer Alles tonen als Azure Active Directory niet zichtbaar is) in de lijst <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Beheercentra.** </span><span class="sxs-lookup"><span data-stu-id="b9b31-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="b9b31-120">Ga in **Azure Active Directory beheercentrum** naar Azure Active Directory **,** kies **Apparaten** en vervolgens **Apparaatinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="b9b31-121">Controleren **of gebruikers kunnen deelnemen aan apparaten met Azure AD** is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="b9b31-121">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="b9b31-122">Als u alle gebruikers wilt inschakelen, stelt u alles **in.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="b9b31-123">Als u specifieke gebruikers wilt inschakelen, stelt u De optie **Geselecteerd in om** een specifieke groep gebruikers in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b9b31-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="b9b31-124">Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b9b31-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="b9b31-125">Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b9b31-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="b9b31-126">3. Controleren of Azure AD is ingeschakeld voor MDM</span><span class="sxs-lookup"><span data-stu-id="b9b31-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="b9b31-127">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer Eindpunt **managemen** t (selecteer **Alles tonen** als Endpoint Manager niet zichtbaar is) </span><span class="sxs-lookup"><span data-stu-id="b9b31-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="b9b31-128">Ga in **Microsoft Endpoint Manager beheercentrum** naar **Apparaten**  >  **Windows**  >  **Windows Automatische**  >  inschrijving.</span><span class="sxs-lookup"><span data-stu-id="b9b31-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="b9b31-129">Controleer of MDM-gebruikersbereik is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b9b31-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="b9b31-130">Als u alle computers  wilt registreren, stelt u Alles in om automatisch alle gebruikerscomputers in te schrijven die zijn verbonden met Azure AD en nieuwe computers wanneer de gebruikers een werkaccount toevoegen aan Windows.</span><span class="sxs-lookup"><span data-stu-id="b9b31-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="b9b31-131">Instellen op **Sommige** om de computers van een specifieke groep gebruikers in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="b9b31-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="b9b31-132">Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b9b31-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="b9b31-133">Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b9b31-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="b9b31-134">4. De vereiste resources maken</span><span class="sxs-lookup"><span data-stu-id="b9b31-134">4. Create the required resources</span></span> 

<span data-ttu-id="b9b31-135">Het uitvoeren van de vereiste taken voor het configureren van hybride [Azure AD-join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) die is gevonden in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="b9b31-135">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="b9b31-136">Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en groepsbeleid gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="b9b31-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="b9b31-137">U kunt deze module installeren door het volgende aan teroepen vanuit een exemplaar van PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b9b31-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="b9b31-138">U wordt aangeraden deze module te installeren op de Windows Server met Azure AD-Verbinding maken.</span><span class="sxs-lookup"><span data-stu-id="b9b31-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="b9b31-139">Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, roept u de cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) aan.</span><span class="sxs-lookup"><span data-stu-id="b9b31-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="b9b31-140">U hebt uw globale Microsoft 365 Business Premium nodig bij het uitvoeren van deze taak.</span><span class="sxs-lookup"><span data-stu-id="b9b31-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="b9b31-141">Wanneer u klaar bent om de resources te maken, roept u het volgende aan:</span><span class="sxs-lookup"><span data-stu-id="b9b31-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="b9b31-142">Met de eerste opdracht wordt een verbinding tot stand brengen met de Microsoft-cloud en wanneer u daarom wordt gevraagd, geeft u uw Microsoft 365 Business Premium globale beheerdersreferenties op.</span><span class="sxs-lookup"><span data-stu-id="b9b31-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="b9b31-143">5. Het groepsbeleid koppelen</span><span class="sxs-lookup"><span data-stu-id="b9b31-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="b9b31-144">Klik in de GPMC (Group Policy Management Console) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer Een bestaand *GPO koppelen...* in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="b9b31-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="b9b31-145">Selecteer het beleid dat is gemaakt in de bovenstaande stap en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="b9b31-146">De nieuwste beheersjablonen downloaden</span><span class="sxs-lookup"><span data-stu-id="b9b31-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="b9b31-147">Als u het beleid Automatische MDM-inschrijving inschakelen niet ziet met **standaardReferenties** voor Azure AD, is dit mogelijk omdat de ADMX niet is geïnstalleerd voor Windows 10, versie 1803 of hoger.</span><span class="sxs-lookup"><span data-stu-id="b9b31-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="b9b31-148">Als u het probleem wilt oplossen, volgt u deze stappen (Opmerking: de meest recente MDM.admx is compatibel met achteruit):</span><span class="sxs-lookup"><span data-stu-id="b9b31-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="b9b31-149">Downloaden: [Beheersjablonen (.admx) voor Windows 10 update van oktober 2020 (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="b9b31-149">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="b9b31-150">Installeer het pakket op een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="b9b31-150">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="b9b31-151">Navigeer, afhankelijk van de versie met beheersjablonen, naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="b9b31-151">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="b9b31-152">Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad **naar PolicyDefinitions.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="b9b31-153">Kopieer de **map PolicyDefinitions** naar uw SYSVOL-share, standaard op **C:\Windows\SYSVOL\domain\Policies.**</span><span class="sxs-lookup"><span data-stu-id="b9b31-153">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="b9b31-154">Als u van plan bent een centraal beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van PolicyDefinitions toe.</span><span class="sxs-lookup"><span data-stu-id="b9b31-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="b9b31-155">Als u meerdere domeincontrollers hebt, wacht u totdat SYSVOL is gerepliceerd totdat het beleid beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="b9b31-155">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="b9b31-156">Deze procedure werkt ook voor elke toekomstige versie van de beheersjablonen.</span><span class="sxs-lookup"><span data-stu-id="b9b31-156">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="b9b31-157">Op dit moment kunt u het beleid Automatische **MDM-registratie** inschakelen zien met de standaardreferenties van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b9b31-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

## <a name="related-content"></a><span data-ttu-id="b9b31-158">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b9b31-158">Related content</span></span>

<span data-ttu-id="b9b31-159">[Domeingebruikers synchroniseren met Microsoft 365](manage-domain-users.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b9b31-159">[Synchronize domain users to Microsoft 365](manage-domain-users.md) (article)</span></span>\
<span data-ttu-id="b9b31-160">[Een groep maken in het beheercentrum](../admin/create-groups/create-groups.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b9b31-160">[Create a group in the admin center](../admin/create-groups/create-groups.md) (article)</span></span>\
<span data-ttu-id="b9b31-161">[Zelfstudie: Hybride Azure Active Directory voor beheerde domeinen configureren](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b9b31-161">[Tutorial: Configure hybrid Azure Active Directory join for managed domains](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (article)</span></span>