---
title: Instellen dat aan een domein verbonden Windows 10-apparaten kunnen worden beheerd door Microsoft 365 voor Bedrijven
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Leer in slechts een paar stappen hoe u Microsoft 365 inschakelen om lokale Windows 10-apparaten die lid zijn van Active Directory te beveiligen.
ms.openlocfilehash: 0b597110447272be128bfe1866234ac25a8e67e6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407073"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="57e27-103">Instellen dat aan een domein verbonden Windows 10-apparaten kunnen worden beheerd door Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="57e27-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="57e27-104">Als uw organisatie on-premises gebruikmaakt van Windows Server Active Directory, kunt u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist.</span><span class="sxs-lookup"><span data-stu-id="57e27-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="57e27-105">Om deze beveiliging in te stellen, kunt u apparaten implementeren die lid zijn van **Hybride Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="57e27-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="57e27-106">Deze apparaten zijn verbonden met uw on-premises Active Directory en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="57e27-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="57e27-107">In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario. Dit wordt ook beschreven in de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="57e27-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="57e27-108">Zorg ervoor dat u deze stappen voltooit voordat u aan de slag gaat:</span><span class="sxs-lookup"><span data-stu-id="57e27-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="57e27-109">Gebruikers synchroniseren met Azure AD met Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="57e27-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="57e27-110">Voltooi de synchronisatie van de organisatie-eenheid (OU) van Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="57e27-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="57e27-111">Zorg ervoor dat alle domeingebruikers die u synchroniseert, een licentie hebben voor Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="57e27-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="57e27-112">Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="57e27-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="57e27-113">1. MDM Authority in Intune verifiëren</span><span class="sxs-lookup"><span data-stu-id="57e27-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="57e27-114">Ga naar [Eindpuntenbeheer](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) en selecteer op de pagina Microsoft Intune  apparaatinschrijving en ga naar de pagina Overzicht en zorg ervoor dat **MDM-autoriteit** **Intune** is.</span><span class="sxs-lookup"><span data-stu-id="57e27-114">Go to [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) and on the Microsoft Intune page, select **Device enrollment**, then on the **Overview** page, make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="57e27-115">Als **MDM-autoriteit** **Geen** is, klikt u op de **MDM-instantie** om deze in te stellen **op Intune.**</span><span class="sxs-lookup"><span data-stu-id="57e27-115">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="57e27-116">Als **MDM-autoriteit** **Microsoft Office 365** is, gaat u naar Apparaten registreren en gebruikt u het dialoogvenster MDM-autoriteit toevoegen aan de rechterkant om   >   **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit** toevoegen is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365). </span><span class="sxs-lookup"><span data-stu-id="57e27-116">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="57e27-117">2. Controleren of Azure AD is ingeschakeld voor het deelnemen aan computers</span><span class="sxs-lookup"><span data-stu-id="57e27-117">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="57e27-118">Ga naar het beheercentrum en selecteer Azure Active Directory (selecteer Alles tonen als Azure Active Directory niet zichtbaar is) in de lijst <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **met beheercentra.** </span><span class="sxs-lookup"><span data-stu-id="57e27-118">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="57e27-119">Ga in **het Azure Active Directory-beheercentrum** naar **Azure Active Directory,** kies **Apparaten en** vervolgens **Apparaatinstellingen.**</span><span class="sxs-lookup"><span data-stu-id="57e27-119">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="57e27-120">Controleren **of Gebruikers apparaten kunnen deelnemen aan Azure AD** is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="57e27-120">Verify **Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="57e27-121">Als u alle gebruikers wilt inschakelen, stelt u alles **in.**</span><span class="sxs-lookup"><span data-stu-id="57e27-121">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="57e27-122">Als u specifieke gebruikers wilt inschakelen, stelt **u deze** optie in op Geselecteerd om een specifieke groep gebruikers in teschakelen.</span><span class="sxs-lookup"><span data-stu-id="57e27-122">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="57e27-123">Voeg het gewenste domein dat gebruikers in Azure AD hebben gesynchroniseerd toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="57e27-123">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="57e27-124">Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in teschakelen.</span><span class="sxs-lookup"><span data-stu-id="57e27-124">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="57e27-125">3. Controleer of Azure AD is ingeschakeld voor MDM</span><span class="sxs-lookup"><span data-stu-id="57e27-125">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="57e27-126">Ga naar het beheercentrum en selecteer Eindpunt beheren t (selecteer Alles tonen als <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Eindpuntbeheer** niet zichtbaar is) </span><span class="sxs-lookup"><span data-stu-id="57e27-126">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen** t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="57e27-127">Ga in **het beheercentrum van Microsoft Endpoint Manager** naar **Automatische** inschrijving van  >    >    >  **Windows-apparaten.**</span><span class="sxs-lookup"><span data-stu-id="57e27-127">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="57e27-128">Controleer of het gebruikersbereik van MDM is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="57e27-128">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="57e27-129">Als u alle computers  wilt registreren, stelt u Alles in om automatisch alle gebruikerscomputers te registreren die zijn aangesloten op Azure AD en nieuwe computers wanneer gebruikers een werkaccount toevoegen aan Windows.</span><span class="sxs-lookup"><span data-stu-id="57e27-129">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="57e27-130">Stel in **op Sommige** om de computers van een specifieke groep gebruikers in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="57e27-130">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="57e27-131">Voeg het gewenste domein dat gebruikers in Azure AD hebben gesynchroniseerd toe aan een [beveiligingsgroep.](../admin/create-groups/create-groups.md)</span><span class="sxs-lookup"><span data-stu-id="57e27-131">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="57e27-132">Kies **Groepen selecteren om** het MDM-gebruikersbereik voor die beveiligingsgroep in teschakelen.</span><span class="sxs-lookup"><span data-stu-id="57e27-132">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="57e27-133">4. De vereiste resources maken</span><span class="sxs-lookup"><span data-stu-id="57e27-133">4. Create the required resources</span></span> 

<span data-ttu-id="57e27-134">Het uitvoeren van de vereiste taken voor het configureren van hybride [Azure AD-join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) die beschikbaar is in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-module.</span><span class="sxs-lookup"><span data-stu-id="57e27-134">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="57e27-135">Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en het groepsbeleid gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="57e27-135">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="57e27-136">U kunt deze module installeren door het volgende in te stemmen vanuit een exemplaar van PowerShell:</span><span class="sxs-lookup"><span data-stu-id="57e27-136">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="57e27-137">U wordt aangeraden deze module te installeren op de Windows-server met Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="57e27-137">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="57e27-138">Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, wordt de cmdlet  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) aanroepen.</span><span class="sxs-lookup"><span data-stu-id="57e27-138">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="57e27-139">U hebt uw globale beheerdersreferenties voor Microsoft 365 Business Premium nodig wanneer u deze taak wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="57e27-139">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="57e27-140">Wanneer u klaar bent om de bronnen te maken, kunt u het volgende aanroepen:</span><span class="sxs-lookup"><span data-stu-id="57e27-140">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="57e27-141">Met de eerste opdracht wordt een verbinding tot stand brengen met de Microsoft-cloud en wanneer u daarom wordt gevraagd, geeft u uw globale beheerdersreferenties voor Microsoft 365 Business Premium op.</span><span class="sxs-lookup"><span data-stu-id="57e27-141">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="57e27-142">5. Het groepsbeleid koppelen</span><span class="sxs-lookup"><span data-stu-id="57e27-142">5. Link the Group Policy</span></span>

1. <span data-ttu-id="57e27-143">Klik in de GPMC (Group Policy Management Console) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer Een bestaand groepsbeleidsteam *koppelen...* in het snelmenu.</span><span class="sxs-lookup"><span data-stu-id="57e27-143">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="57e27-144">Selecteer het beleid dat in de bovenstaande stap is gemaakt en klik op **OK.**</span><span class="sxs-lookup"><span data-stu-id="57e27-144">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="57e27-145">De nieuwste beheersjablonen downloaden</span><span class="sxs-lookup"><span data-stu-id="57e27-145">Get the latest Administrative Templates</span></span>

<span data-ttu-id="57e27-146">Als u het beleid Automatische **MDM-inschrijving** inschakelen met standaard Azure AD-referenties niet ziet, hebt u de ADMX mogelijk niet geïnstalleerd voor Windows 10, versie 1803 of hoger.</span><span class="sxs-lookup"><span data-stu-id="57e27-146">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, or later.</span></span> <span data-ttu-id="57e27-147">Volg deze stappen om het probleem op te lossen (opmerking: de nieuwste MDM.admx is compatibel met de terugwaartse versie):</span><span class="sxs-lookup"><span data-stu-id="57e27-147">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="57e27-148">Downloaden: [Beheersjablonen (.admx) voor Windows 10 update van oktober 2020 (20H2).](https://www.microsoft.com/download/102157)</span><span class="sxs-lookup"><span data-stu-id="57e27-148">Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).</span></span>
2.  <span data-ttu-id="57e27-149">Installeer het pakket op een domeincontroller.</span><span class="sxs-lookup"><span data-stu-id="57e27-149">Install the package on a Domain Controller.</span></span>
3.  <span data-ttu-id="57e27-150">Navigeer, afhankelijk van de versie met beheersjablonen, naar de map: **C:\Program Files (x86)\Microsoft-groepsbeleid\Windows 10 update van oktober 2020 (20H2).**</span><span class="sxs-lookup"><span data-stu-id="57e27-150">Navigate, depending on the Administrative Templates version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.</span></span>
4.  <span data-ttu-id="57e27-151">Wijzig de naam **van de** map Beleidsdefinities in het bovenstaande pad **naar PolicyDefinitions.**</span><span class="sxs-lookup"><span data-stu-id="57e27-151">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="57e27-152">Kopieer de **map PolicyDefinitions** naar uw SYSVOL-share, standaard op **C:\Windows\SYSVOL\domain\Policies.**</span><span class="sxs-lookup"><span data-stu-id="57e27-152">Copy the **PolicyDefinitions** folder to your SYSVOL share, by default located at **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="57e27-153">Als u van plan bent om een centraal beleidsopslag te gebruiken voor uw hele domein, voegt u de inhoud van PolicyDefinitions daar toe.</span><span class="sxs-lookup"><span data-stu-id="57e27-153">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="57e27-154">Als u meerdere domeincontrollers hebt, wacht u totdat SYSVOL is gerepliceerd voordat het beleid beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="57e27-154">In case you have several Domain Controllers, wait for SYSVOL to replicate for the policies to be available.</span></span> <span data-ttu-id="57e27-155">Deze procedure werkt ook voor elke toekomstige versie van de beheersjablonen.</span><span class="sxs-lookup"><span data-stu-id="57e27-155">This procedure will work for any future version of the Administrative Templates as well.</span></span>

<span data-ttu-id="57e27-156">Nu moet u het beleid Automatische MDM-inschrijving inschakelen met beschikbare **Standaard Azure AD-referenties kunnen** zien.</span><span class="sxs-lookup"><span data-stu-id="57e27-156">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
