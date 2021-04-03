---
title: Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for Business
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
description: In een paar stappen leert u hoe u Microsoft 365 kunt inschakelen om lokale Windows 10-apparaten met Active Directory te beveiligen.
ms.openlocfilehash: 8a45c6959bee368491c5c6424e3713300c443779
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580129"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="be7b1-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="be7b1-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="be7b1-104">Als uw organisatie on-premises Windows Server Active Directory gebruikt, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, met behoud van toegang tot on-premises resources waarvoor lokale verificatie vereist is.</span><span class="sxs-lookup"><span data-stu-id="be7b1-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="be7b1-105">Als u deze beveiliging wilt instellen, kunt u verbonden **hybride Azure AD-apparaten implementeren.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="be7b1-106">Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="be7b1-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="be7b1-107">In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de stappen die volgen.</span><span class="sxs-lookup"><span data-stu-id="be7b1-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="be7b1-108">Voordat u aan de slag gaat, moet u de volgende stappen volgen:</span><span class="sxs-lookup"><span data-stu-id="be7b1-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="be7b1-109">Gebruikers synchroniseren met Azure AD met Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="be7b1-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="be7b1-110">Voltooi de synchronisatie van Azure AD Connect Organizational Unit (OU).</span><span class="sxs-lookup"><span data-stu-id="be7b1-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="be7b1-111">Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben voor Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="be7b1-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="be7b1-112">Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="be7b1-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="be7b1-113">1. MDM Authority verifiëren in Intune</span><span class="sxs-lookup"><span data-stu-id="be7b1-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="be7b1-114">Ga naar [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en selecteer op de pagina Microsoft Intune de optie Apparaatinschrijving **en** zorg er op de pagina Overzicht voor dat **MDM-autoriteit** **Intune is.** </span><span class="sxs-lookup"><span data-stu-id="be7b1-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="be7b1-115">Als **MDM-autoriteit** **Geen** is, klikt u op **de MDM-autoriteit** om deze in te stellen **op Intune.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="be7b1-116">Als MDM-autoriteit **Microsoft Office 365** is, gaat u naar Apparaten registreren en gebruikt u het dialoogvenster  **MDM-autoriteit** toevoegen aan de rechterkant om  >    **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit** toevoegen is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="be7b1-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="be7b1-117">2. Controleren of Azure AD is ingeschakeld voor het deelnemen aan computers</span><span class="sxs-lookup"><span data-stu-id="be7b1-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="be7b1-118">Ga naar het beheercentrum bij en selecteer Azure Active Directory (selecteer Alles tonen als Azure Active Directory niet zichtbaar <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> is) in de **lijst Met beheercentra.** </span><span class="sxs-lookup"><span data-stu-id="be7b1-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="be7b1-119">Ga in **het Azure Active Directory-beheercentrum** naar **Azure Active Directory,** kies **Apparaten** en vervolgens **Apparaatinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="be7b1-120">Controleren **of gebruikers kunnen deelnemen aan apparaten met Azure AD** is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="be7b1-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="be7b1-121">Als u alle gebruikers wilt inschakelen, stelt u alles **in.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="be7b1-122">Als u specifieke gebruikers wilt inschakelen, stelt u De optie **Geselecteerd in om** een specifieke groep gebruikers in te stellen.</span><span class="sxs-lookup"><span data-stu-id="be7b1-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="be7b1-123">Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="be7b1-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="be7b1-124">Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.</span><span class="sxs-lookup"><span data-stu-id="be7b1-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="be7b1-125">3. Controleren of Azure AD is ingeschakeld voor MDM</span><span class="sxs-lookup"><span data-stu-id="be7b1-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="be7b1-126">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  en selecteer **Endpoint Managemen** t (selecteer **Alles tonen** **als Endpoint Manager** niet zichtbaar is)</span><span class="sxs-lookup"><span data-stu-id="be7b1-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="be7b1-127">Ga in **het Microsoft Endpoint Manager-beheercentrum** naar Automatische inschrijving **voor**  >  **Windows**  >  **Windows-apparaten**  >  .</span><span class="sxs-lookup"><span data-stu-id="be7b1-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="be7b1-128">Controleer of MDM-gebruikersbereik is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="be7b1-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="be7b1-129">Als u alle computers  wilt registreren, stelt u Alles in om automatisch alle gebruikerscomputers in te schrijven die zijn verbonden met Azure AD en nieuwe computers wanneer de gebruikers een werkaccount toevoegen aan Windows.</span><span class="sxs-lookup"><span data-stu-id="be7b1-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="be7b1-130">Instellen op **Sommige** om de computers van een specifieke groep gebruikers in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="be7b1-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="be7b1-131">Voeg de gewenste domeingebruikers die zijn gesynchroniseerd in Azure AD toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="be7b1-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="be7b1-132">Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in te stellen.</span><span class="sxs-lookup"><span data-stu-id="be7b1-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="be7b1-133">4. De vereiste resources maken</span><span class="sxs-lookup"><span data-stu-id="be7b1-133">4. Create the required resources</span></span> 

<span data-ttu-id="be7b1-134">Het uitvoeren van de vereiste taken voor het configureren van hybride [Azure AD-join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) die is gevonden in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="be7b1-134">Performing the required tasks to [configure hybrid Azure AD join](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="be7b1-135">Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en groepsbeleid gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="be7b1-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="be7b1-136">U kunt deze module installeren door het volgende aan teroepen vanuit een exemplaar van PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be7b1-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="be7b1-137">U wordt aangeraden deze module te installeren op de Windows Server met Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="be7b1-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="be7b1-138">Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, roept u de cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) aan.</span><span class="sxs-lookup"><span data-stu-id="be7b1-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="be7b1-139">U hebt uw globale beheerdersreferenties voor Microsoft 365 Business Premium nodig bij het uitvoeren van deze taak.</span><span class="sxs-lookup"><span data-stu-id="be7b1-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="be7b1-140">Wanneer u klaar bent om de resources te maken, roept u het volgende aan:</span><span class="sxs-lookup"><span data-stu-id="be7b1-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="be7b1-141">Met de eerste opdracht wordt een verbinding tot stand brengen met de Microsoft-cloud en wanneer u daarom wordt gevraagd, geeft u uw globale beheerdersreferenties van Microsoft 365 Business Premium op.</span><span class="sxs-lookup"><span data-stu-id="be7b1-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="be7b1-142">5. Het groepsbeleid koppelen</span><span class="sxs-lookup"><span data-stu-id="be7b1-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="be7b1-143">Klik in de GPMC (Group Policy Management Console) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer Een bestaand *GPO koppelen...* in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="be7b1-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="be7b1-144">Selecteer het beleid dat is gemaakt in de bovenstaande stap en klik vervolgens op **OK.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="be7b1-145">De nieuwste beheersjablonen downloaden</span><span class="sxs-lookup"><span data-stu-id="be7b1-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="be7b1-146">Als u het beleid Automatische MDM-registratie inschakelen niet ziet met behulp van **standaardReferenties** voor Azure AD, is dit mogelijk omdat de ADMX niet is geïnstalleerd voor Windows 10, versie 1803 of hoger.</span><span class="sxs-lookup"><span data-stu-id="be7b1-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="be7b1-147">Als u het probleem wilt oplossen, volgt u deze stappen (Opmerking: de meest recente MDM.admx is compatibel met achteruit):</span><span class="sxs-lookup"><span data-stu-id="be7b1-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="be7b1-148">Downloaden: [Beheersjablonen (.admx) voor Windows 10 oktober 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span><span class="sxs-lookup"><span data-stu-id="be7b1-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="be7b1-149">Installeer het pakket op een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="be7b1-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="be7b1-150">Navigeer, afhankelijk van de versie beheersjablonen, naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 oktober 2020 Update (20H2)**.</span><span class="sxs-lookup"><span data-stu-id="be7b1-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="be7b1-151">Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad **naar PolicyDefinitions.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="be7b1-152">Kopieer de **map PolicyDefinitions** naar uw SYSVOL-share, standaard op **C:\Windows\SYSVOL\domain\Policies.**</span><span class="sxs-lookup"><span data-stu-id="be7b1-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="be7b1-153">Als u van plan bent een centraal beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van PolicyDefinitions toe.</span><span class="sxs-lookup"><span data-stu-id="be7b1-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="be7b1-154">Als u meerdere domeincontrollers hebt, wacht u totdat SYSVOL is gerepliceerd totdat het beleid beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="be7b1-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="be7b1-155">Deze procedure werkt ook voor elke toekomstige versie van de beheersjablonen.</span><span class="sxs-lookup"><span data-stu-id="be7b1-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="be7b1-156">Op dit moment kunt u het beleid Automatische **MDM-registratie** inschakelen zien met de standaardreferenties van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="be7b1-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>