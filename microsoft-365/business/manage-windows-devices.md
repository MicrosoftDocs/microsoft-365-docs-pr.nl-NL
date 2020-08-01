---
title: Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 voor bedrijven
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
description: Meer informatie over het inschakelen van Microsoft 365 om lokale Windows 10-apparaten met Actieve Directory in slechts een paar stappen te beschermen.
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533780"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="c3432-103">Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c3432-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="c3432-104">Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.</span><span class="sxs-lookup"><span data-stu-id="c3432-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="c3432-105">Als u deze beveiliging wilt instellen, u **hybride azure ad-apparaten**implementeren.</span><span class="sxs-lookup"><span data-stu-id="c3432-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="c3432-106">Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3432-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="c3432-107">In deze video worden de stappen beschreven voor het instellen van dit voor het meest voorkomende scenario, dat ook wordt beschreven in de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="c3432-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="c3432-108">Voordat u aan de slag gaat, moet u de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="c3432-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="c3432-109">Gebruikers synchroniseren met Azure AD met Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="c3432-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="c3432-110">Volledige Azure AD Connect Organizational Unit (OU) synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="c3432-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="c3432-111">Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben voor Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="c3432-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="c3432-112">Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="c3432-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="c3432-113">1. MDM-autoriteit in Intune verifiëren</span><span class="sxs-lookup"><span data-stu-id="c3432-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="c3432-114">Ga naar portal.azure.com en zoek bovenaan de pagina naar Intune.</span><span class="sxs-lookup"><span data-stu-id="c3432-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="c3432-115">Selecteer op de pagina Microsoft Intune de optie **Apparaatinschrijving** en controleer op de pagina **Overzicht** of **de MDM-autoriteit** **Intune**is.</span><span class="sxs-lookup"><span data-stu-id="c3432-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="c3432-116">Als **MDM-autoriteit** **geen**is, klikt u op de **MDM-autoriteit** om deze in te stellen op **Intune**.</span><span class="sxs-lookup"><span data-stu-id="c3432-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="c3432-117">Als **MDM-autoriteit** **Microsoft Office 365**is, ga dan naar **Apparaten**Inschrijven  >  **en** gebruik het dialoogvenster **MDM-autoriteit toevoegen** aan het recht om **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit toevoegen** is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="c3432-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="c3432-118">2. Controleren of Azure AD is ingeschakeld voor het samenvoegen van computers</span><span class="sxs-lookup"><span data-stu-id="c3432-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="c3432-119">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer Azure Active **Directory** (selecteer Alles weergeven als Azure Active Directory niet zichtbaar is) in de lijst **Met beheercentra.**</span><span class="sxs-lookup"><span data-stu-id="c3432-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="c3432-120">Kies **apparaten** en vervolgens **apparaatinstellingen** **in** het Azure **Active Directory-beheercentrum**.</span><span class="sxs-lookup"><span data-stu-id="c3432-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="c3432-121">Controleren**of gebruikers apparaten kunnen koppelen aan Azure AD** is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="c3432-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="c3432-122">Als u alle gebruikers wilt inschakelen, stelt u in op **Alles**.</span><span class="sxs-lookup"><span data-stu-id="c3432-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="c3432-123">Als u specifieke gebruikers wilt inschakelen, stelt u deze in **op Geselecteerd** om een specifieke groep gebruikers in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="c3432-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="c3432-124">Voeg de gewenste domeingebruikers toe die in Azure AD zijn gesynchroniseerd aan een [beveiligingsgroep](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c3432-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="c3432-125">Kies **Groepen selecteren** om de mdm-gebruikersbereik voor die beveiligingsgroep in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="c3432-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="c3432-126">3. Controleren of Azure AD is ingeschakeld voor MDM</span><span class="sxs-lookup"><span data-stu-id="c3432-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="c3432-127">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer **Eindpunt managemen**t (selecteer **Alles weergeven** als **Eindpuntbeheer** niet zichtbaar is)</span><span class="sxs-lookup"><span data-stu-id="c3432-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="c3432-128">Ga in het **Microsoft Endpoint Manager-beheercentrum**naar **Automatische**inschrijving voor  >  **Windows**  >  **Windows Windows-inschrijving**  >  **Automatic Enrollment**.</span><span class="sxs-lookup"><span data-stu-id="c3432-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="c3432-129">Controleer of het gebruikersbereik van MDM is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c3432-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="c3432-130">Als u alle computers wilt inschrijven, stelt u in **op Alles** om alle gebruikerscomputers die zijn aangesloten bij Azure AD en nieuwe computers automatisch in te schrijven wanneer de gebruikers een werkaccount aan Windows toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c3432-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="c3432-131">Stel in **op Sommige** om de computers van een specifieke groep gebruikers in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="c3432-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="c3432-132">Voeg de gewenste domeingebruikers toe die in Azure AD zijn gesynchroniseerd aan een [beveiligingsgroep](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="c3432-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="c3432-133">Kies **Groepen selecteren** om de mdm-gebruikersbereik voor die beveiligingsgroep in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="c3432-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-create-the-required-resources"></a><span data-ttu-id="c3432-134">4. Maak de benodigde resources</span><span class="sxs-lookup"><span data-stu-id="c3432-134">4. Create the required resources</span></span> 

<span data-ttu-id="c3432-135">Het uitvoeren van de vereiste taken voor [het configureren van hybride Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) is vereenvoudigd door het gebruik van de [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet gevonden in de [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span><span class="sxs-lookup"><span data-stu-id="c3432-135">Performing the required tasks to [configure hybrid Azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) has been simplified through the use of the [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet found in the [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell module.</span></span> <span data-ttu-id="c3432-136">Wanneer u deze cmdlet aanroept, wordt het vereiste serviceverbindingspunt en groepsbeleid gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="c3432-136">When you invoke this cmdlet it will create and configure the required service connection point and group policy.</span></span>

<span data-ttu-id="c3432-137">U deze module installeren door een beroep te doen op het volgende van een exemplaar van PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c3432-137">You can install this module by invoking the following from an instance of PowerShell:</span></span>

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> <span data-ttu-id="c3432-138">Het wordt aanbevolen deze module te installeren op de Windows Server waarop Azure AD Connect wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="c3432-138">It is recommended that you install this module on the Windows Server running Azure AD Connect.</span></span>

<span data-ttu-id="c3432-139">Als u het vereiste serviceverbindingspunt en groepsbeleid wilt maken, wordt u een beroep doen op de cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md)</span><span class="sxs-lookup"><span data-stu-id="c3432-139">To create the required service connection point and group policy, you will invoke the  [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) cmdlet.</span></span> <span data-ttu-id="c3432-140">U hebt uw algemene beheerdersreferenties van Microsoft 365 Business Premium nodig bij het uitvoeren van deze taak.</span><span class="sxs-lookup"><span data-stu-id="c3432-140">You will need your Microsoft 365 Business Premium global admin credentials when performing this task.</span></span> <span data-ttu-id="c3432-141">Wanneer u klaar bent om de resources te maken, roept u het volgende aan:</span><span class="sxs-lookup"><span data-stu-id="c3432-141">When you are ready to create the resources, invoke the following:</span></span>

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

<span data-ttu-id="c3432-142">Met de eerste opdracht wordt een verbinding tot stand gebracht met de Microsoft-cloud en wanneer u wordt gevraagd, geeft u uw globale beheerdersreferenties van Microsoft 365 Business Premium op.</span><span class="sxs-lookup"><span data-stu-id="c3432-142">The first command will establish a connection with the Microsoft cloud, and when you are prompted, specify your Microsoft 365 Business Premium global admin credentials.</span></span>

## <a name="5-link-the-group-policy"></a><span data-ttu-id="c3432-143">5. Koppeling van het groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="c3432-143">5. Link the Group Policy</span></span>

1. <span data-ttu-id="c3432-144">Klik in de Groepsbeleidsbeheerconsole (GPMC) met de rechtermuisknop op de locatie waar u het beleid wilt koppelen en selecteer *Een bestaande GPO koppelen...* in het contextmenu.</span><span class="sxs-lookup"><span data-stu-id="c3432-144">In the Group Policy Management Console (GPMC), right-click on the location where you want to link the policy and select *Link an existing GPO...* from the context menu.</span></span>
2. <span data-ttu-id="c3432-145">Selecteer het beleid dat in de bovenstaande stap is gemaakt en klik op **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3432-145">Select the policy created in the above step, then click **OK**.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="c3432-146">De nieuwste beheersjablonen ophalen</span><span class="sxs-lookup"><span data-stu-id="c3432-146">Get the latest Administrative Templates</span></span>

<span data-ttu-id="c3432-147">Als u het beleid Automatische MDM-inschrijving inschakelen niet ziet **met standaard Azure AD-referenties,** kan dit zijn omdat u de ADMX niet hebt geïnstalleerd voor Windows 10, versie 1803, versie 1809 of versie 1903.</span><span class="sxs-lookup"><span data-stu-id="c3432-147">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="c3432-148">Voer de volgende stappen uit (Opmerking: de nieuwste MDM.admx is backwards compatible):</span><span class="sxs-lookup"><span data-stu-id="c3432-148">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="c3432-149">Download: [Beheersjablonen (.admx) voor Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="c3432-149">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="c3432-150">Installeer het pakket op de primaire domeincontroller (PDC).</span><span class="sxs-lookup"><span data-stu-id="c3432-150">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="c3432-151">Navigeren, afhankelijk van de versie naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="c3432-151">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="c3432-152">Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad naar **Beleidsdefinities**.</span><span class="sxs-lookup"><span data-stu-id="c3432-152">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="c3432-153">Map **Beleidsdefinities** kopiëren naar **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="c3432-153">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="c3432-154">Als u van plan bent een centrale beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van Beleidsdefinities toe.</span><span class="sxs-lookup"><span data-stu-id="c3432-154">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="c3432-155">Start de primaire domeincontroller opnieuw om het beleid beschikbaar te maken.</span><span class="sxs-lookup"><span data-stu-id="c3432-155">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="c3432-156">Deze procedure zal ook werken voor elke toekomstige versie.</span><span class="sxs-lookup"><span data-stu-id="c3432-156">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="c3432-157">Op dit punt moet u het beleid **Automatische MDM-inschrijving inschakelen** kunnen zien met standaard Azure AD-referenties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c3432-157">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>
