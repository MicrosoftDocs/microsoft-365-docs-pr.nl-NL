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
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564930"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a><span data-ttu-id="0899f-103">Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="0899f-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium</span></span>

<span data-ttu-id="0899f-104">Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.</span><span class="sxs-lookup"><span data-stu-id="0899f-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business Premium to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span>
<span data-ttu-id="0899f-105">Als u deze beveiliging wilt instellen, u **hybride azure ad-apparaten**implementeren.</span><span class="sxs-lookup"><span data-stu-id="0899f-105">To set up this protection, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="0899f-106">Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0899f-106">These devices are joined to both your on-premises Active Directory and your Azure Active Directory.</span></span>

<span data-ttu-id="0899f-107">In deze video worden de stappen beschreven voor het instellen van dit voor het meest voorkomende scenario, dat ook wordt beschreven in de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="0899f-107">This video describes the steps for how to set this up for the most common scenario, which is also detailed in the steps that follow.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a><span data-ttu-id="0899f-108">Voordat u aan de slag gaat, moet u de volgende stappen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0899f-108">Before you get started, make sure you complete these steps:</span></span>
- <span data-ttu-id="0899f-109">Gebruikers synchroniseren met Azure AD met Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0899f-109">Synchronize users to Azure AD with Azure AD Connect.</span></span>
- <span data-ttu-id="0899f-110">Volledige Azure AD Connect Organizational Unit (OU) synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="0899f-110">Complete Azure AD Connect Organizational Unit (OU) sync.</span></span>
- <span data-ttu-id="0899f-111">Zorg ervoor dat alle domeingebruikers die u synchroniseert licenties hebben voor Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0899f-111">Make sure all the domain users you sync have licenses to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="0899f-112">Zie [Domeingebruikers synchroniseren met Microsoft](manage-domain-users.md) voor de stappen.</span><span class="sxs-lookup"><span data-stu-id="0899f-112">See [Synchronize domain users to Microsoft](manage-domain-users.md) for the steps.</span></span>

## <a name="1-verify-mdm-authority-in-intune"></a><span data-ttu-id="0899f-113">1. MDM-autoriteit in Intune verifiëren</span><span class="sxs-lookup"><span data-stu-id="0899f-113">1. Verify MDM Authority in Intune</span></span>

<span data-ttu-id="0899f-114">Ga naar portal.azure.com en zoek bovenaan de pagina naar Intune.</span><span class="sxs-lookup"><span data-stu-id="0899f-114">Go to portal.azure.com and on the top of the page search for Intune.</span></span>
<span data-ttu-id="0899f-115">Selecteer op de pagina Microsoft Intune de optie **Apparaatinschrijving** en controleer op de pagina **Overzicht** of **de MDM-autoriteit** **Intune**is.</span><span class="sxs-lookup"><span data-stu-id="0899f-115">On the Microsoft Intune page, select **Device enrollment** and on the **Overview** page make sure **MDM authority** is **Intune**.</span></span>

- <span data-ttu-id="0899f-116">Als **MDM-autoriteit** **geen**is, klikt u op de **MDM-autoriteit** om deze in te stellen op **Intune**.</span><span class="sxs-lookup"><span data-stu-id="0899f-116">If **MDM authority** is **None**, click the **MDM authority** to set it to **Intune**.</span></span>
- <span data-ttu-id="0899f-117">Als **MDM-autoriteit** **Microsoft Office 365**is, ga dan naar **Apparaten**Inschrijven  >  **en** gebruik het dialoogvenster **MDM-autoriteit toevoegen** aan het recht om **Intune MDM-autoriteit** toe te voegen (het dialoogvenster **MDM-autoriteit toevoegen** is alleen beschikbaar als de **MDM-autoriteit** is ingesteld op Microsoft Office 365).</span><span class="sxs-lookup"><span data-stu-id="0899f-117">If **MDM authority** is **Microsoft Office 365**,go to **Devices** > **Enroll devices** and use the **Add MDM authority** dialog on the right to add **Intune MDM** authority (the **Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).</span></span>

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a><span data-ttu-id="0899f-118">2. Controleren of Azure AD is ingeschakeld voor het samenvoegen van computers</span><span class="sxs-lookup"><span data-stu-id="0899f-118">2. Verify Azure AD is enabled for joining computers</span></span>

- <span data-ttu-id="0899f-119">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer Azure Active **Directory** (selecteer Alles weergeven als Azure Active Directory niet zichtbaar is) in de lijst **Met beheercentra.**</span><span class="sxs-lookup"><span data-stu-id="0899f-119">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select **Azure Active Directory** (select Show all if Azure Active Directory is not visible) in the **Admin centers** list.</span></span> 
- <span data-ttu-id="0899f-120">Kies **apparaten** en vervolgens **apparaatinstellingen** **in** het Azure **Active Directory-beheercentrum**.</span><span class="sxs-lookup"><span data-stu-id="0899f-120">In the **Azure Active Directory admin center**, go to **Azure Active Directory** , choose **Devices** and then **Device settings**.</span></span>
- <span data-ttu-id="0899f-121">Controleren**of gebruikers apparaten kunnen koppelen aan Azure AD** is ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="0899f-121">Verify**Users may join devices to Azure AD** is enabled</span></span> 
    1. <span data-ttu-id="0899f-122">Als u alle gebruikers wilt inschakelen, stelt u in op **Alles**.</span><span class="sxs-lookup"><span data-stu-id="0899f-122">To enable all users, set to **All**.</span></span>
    2. <span data-ttu-id="0899f-123">Als u specifieke gebruikers wilt inschakelen, stelt u deze in **op Geselecteerd** om een specifieke groep gebruikers in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0899f-123">To enable specific users, set to **Selected** to enable a specific group of users.</span></span>
        - <span data-ttu-id="0899f-124">Voeg de gewenste domeingebruikers toe die in Azure AD zijn gesynchroniseerd aan een [beveiligingsgroep](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0899f-124">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        - <span data-ttu-id="0899f-125">Kies **Groepen selecteren** om de mdm-gebruikersbereik voor die beveiligingsgroep in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0899f-125">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a><span data-ttu-id="0899f-126">3. Controleren of Azure AD is ingeschakeld voor MDM</span><span class="sxs-lookup"><span data-stu-id="0899f-126">3. Verify Azure AD is enabled for MDM</span></span>

- <span data-ttu-id="0899f-127">Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> en selecteer **Eindpunt managemen**t (selecteer **Alles weergeven** als **Eindpuntbeheer** niet zichtbaar is)</span><span class="sxs-lookup"><span data-stu-id="0899f-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  and select select **Endpoint Managemen**t (select **Show all** if **Endpoint Manager** is not visible)</span></span>
- <span data-ttu-id="0899f-128">Ga in het **Microsoft Endpoint Manager-beheercentrum**naar **Automatische**inschrijving voor  >  **Windows**  >  **Windows Windows-inschrijving**  >  **Automatic Enrollment**.</span><span class="sxs-lookup"><span data-stu-id="0899f-128">In the **Microsoft Endpoint Manager admin center**, go to **Devices** > **Windows** > **Windows Enrollment** > **Automatic Enrollment**.</span></span>
- <span data-ttu-id="0899f-129">Controleer of het gebruikersbereik van MDM is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0899f-129">Verify MDM user scope is enabled.</span></span>

    1. <span data-ttu-id="0899f-130">Als u alle computers wilt inschrijven, stelt u in **op Alles** om alle gebruikerscomputers die zijn aangesloten bij Azure AD en nieuwe computers automatisch in te schrijven wanneer de gebruikers een werkaccount aan Windows toevoegen.</span><span class="sxs-lookup"><span data-stu-id="0899f-130">To enroll all computers, set to **All** to automatically enroll all user computers that are joined to Azure AD and new computers  when the users add a work account to Windows.</span></span>
    2. <span data-ttu-id="0899f-131">Stel in **op Sommige** om de computers van een specifieke groep gebruikers in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="0899f-131">Set to **Some** to enroll the computers of a specific group of users.</span></span>
        -  <span data-ttu-id="0899f-132">Voeg de gewenste domeingebruikers toe die in Azure AD zijn gesynchroniseerd aan een [beveiligingsgroep](../admin/create-groups/create-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0899f-132">Add the desired domain users synced in Azure AD to a [security group](../admin/create-groups/create-groups.md).</span></span>
        -  <span data-ttu-id="0899f-133">Kies **Groepen selecteren** om de mdm-gebruikersbereik voor die beveiligingsgroep in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="0899f-133">Choose **Select groups** to enable MDM user scope for that security group.</span></span>

## <a name="4-set-up-service-connection-point-scp"></a><span data-ttu-id="0899f-134">4. Service-verbindingspunt instellen (SCP)</span><span class="sxs-lookup"><span data-stu-id="0899f-134">4. Set up Service connection point (SCP)</span></span>

<span data-ttu-id="0899f-135">Deze stappen worden vereenvoudigd door [hybride azure AD join te configureren.](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)</span><span class="sxs-lookup"><span data-stu-id="0899f-135">These steps are simplified from [configure hybrid azure AD join](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join).</span></span> <span data-ttu-id="0899f-136">Als u de stappen wilt uitvoeren die u azure AD Connect en uw algemene beheerderswachtwoorden van Microsoft 365 Business Premium en Active Directory-beheerders moet gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0899f-136">To complete the steps you need to use Azure AD Connect and your Microsoft 365 Business Premium global admin and Active Directory admin passwords.</span></span>

1.  <span data-ttu-id="0899f-137">Start Azure AD Connect en selecteer **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="0899f-137">Start Azure AD Connect, and then select **Configure**.</span></span>
2.  <span data-ttu-id="0899f-138">Selecteer op de pagina **Extra taken** de optie **Apparaatopties configureren**en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0899f-138">On the **Additional tasks**  page, select **Configure device options**, and then select **Next**.</span></span>
3.  <span data-ttu-id="0899f-139">Selecteer **Volgende**op de pagina **Overzicht.**</span><span class="sxs-lookup"><span data-stu-id="0899f-139">On the **Overview** page, select **Next**.</span></span>
4.  <span data-ttu-id="0899f-140">Voer **op** de pagina Verbinding maken met Azure AD de referenties in van een globale beheerder voor Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0899f-140">On the **Connect to Azure AD** page, enter the credentials of a global administrator for Microsoft 365 Business Premium.</span></span>
5.  <span data-ttu-id="0899f-141">Selecteer op de pagina **Apparaatopties** de optie **Hybride Azure AD join configureren**en selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0899f-141">On the **Device options** page, select **Configure Hybrid Azure AD join**, and then select **Next**.</span></span>
6.  <span data-ttu-id="0899f-142">Voer op de **SCP-pagina** voor elk forest waar u Azure AD Connect wilt configureren van het SCP de volgende stappen uit en selecteer **Volgende:**</span><span class="sxs-lookup"><span data-stu-id="0899f-142">On the **SCP** page, for each forest where you want Azure AD Connect to configure the SCP, complete the following steps, and then select **Next**:</span></span>
    - <span data-ttu-id="0899f-143">Schakel het vakje naast de bosnaam in.</span><span class="sxs-lookup"><span data-stu-id="0899f-143">Check the box beside the forest name.</span></span> <span data-ttu-id="0899f-144">Het forest moet uw AD-domeinnaam zijn.</span><span class="sxs-lookup"><span data-stu-id="0899f-144">The forest should be your AD domain name.</span></span>
    - <span data-ttu-id="0899f-145">Open onder de kolom **Verificatieservice** de vervolgkeuzelijst en selecteer overeenkomende domeinnaam (er mag slechts één optie zijn).</span><span class="sxs-lookup"><span data-stu-id="0899f-145">Under the **Authentication Service** column, open the dropdown and select matching domain name (there should only be one only option).</span></span>
    - <span data-ttu-id="0899f-146">Selecteer **Toevoegen** om de domeinbeheerdersreferenties in te voeren.</span><span class="sxs-lookup"><span data-stu-id="0899f-146">Select **Add** to enter the domain administrator credentials.</span></span>  
7.  <span data-ttu-id="0899f-147">Selecteer alleen op de pagina **Apparatenbesturingssystemen** windows 10 of hoger apparaten die zijn aangesloten bij het domein.</span><span class="sxs-lookup"><span data-stu-id="0899f-147">On the **Device operating systems** page, select Windows 10 or later domain-joined devices only.</span></span>
8.  <span data-ttu-id="0899f-148">Selecteer Op de pagina **Klaar om te configureren** de optie **Configureren**.</span><span class="sxs-lookup"><span data-stu-id="0899f-148">On the **Ready to configure** page, select **Configure**.</span></span>
9.  <span data-ttu-id="0899f-149">Selecteer **op** de pagina Configuratie voltooid de optie **Afsluiten**.</span><span class="sxs-lookup"><span data-stu-id="0899f-149">On the **Configuration complete** page, select **Exit**.</span></span>


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a><span data-ttu-id="0899f-150">5. Maak een GPO voor Intune Enrollment – ADMX-methode</span><span class="sxs-lookup"><span data-stu-id="0899f-150">5. Create a GPO for Intune Enrollment – ADMX method</span></span>

<span data-ttu-id="0899f-151">Gebruiken. ADMX-sjabloonbestand.</span><span class="sxs-lookup"><span data-stu-id="0899f-151">Use .ADMX template file.</span></span>

1.  <span data-ttu-id="0899f-152">Meld u aan bij de **Server Manager**AD-server, zoek en open  >  **groepsbeleidsbeheer voor serverbeheerprogramma's**  >  **Group Policy Management**.</span><span class="sxs-lookup"><span data-stu-id="0899f-152">Log on to AD server, search and open **Server Manager** > **Tools** > **Group Policy Management**.</span></span>
2.  <span data-ttu-id="0899f-153">Selecteer uw domeinnaam onder Domeinen en klik met de rechtermuisknop op **Groepsbeleidsobjecten** om **Nieuw**te selecteren. **Domains**</span><span class="sxs-lookup"><span data-stu-id="0899f-153">Select your domain name under **Domains** and right-click **Group Policy Objects** to select **New**.</span></span>
3.  <span data-ttu-id="0899f-154">Geef de nieuwe GPO een naam, bijvoorbeeld "*Cloud_Enrollment*" en selecteer vervolgens **OK**.</span><span class="sxs-lookup"><span data-stu-id="0899f-154">Give the new GPO an name, for example “*Cloud_Enrollment*” and then select **OK**.</span></span>
4.  <span data-ttu-id="0899f-155">Klik met de rechtermuisknop op het nieuwe GPO onder **Groepsbeleidsobjecten** en selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0899f-155">Right-click the new GPO under **Group Policy Objects** and select **Edit**.</span></span>
5.  <span data-ttu-id="0899f-156">Ga in de **editor voor groepsbeleidsbeheer**naar Beheersjablonen voor **Computer Configuration**  >  **Policies**  >  **computerconfiguratiebeleid**  >  **Windows Components**  >  **MDM**.</span><span class="sxs-lookup"><span data-stu-id="0899f-156">In the **Group Policy Management Editor**, go to **Computer Configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDM**.</span></span>
6. <span data-ttu-id="0899f-157">Klik met de rechtermuisknop op **Automatische MDM-inschrijving inschakelen met standaard Azure AD-referenties** en selecteer **Ingeschakeld OK**  >  **OK**.</span><span class="sxs-lookup"><span data-stu-id="0899f-157">Right-click **Enable automatic MDM enrollment using default Azure AD credentials** and then select **Enabled** > **OK**.</span></span> <span data-ttu-id="0899f-158">Sluit het editorvenster.</span><span class="sxs-lookup"><span data-stu-id="0899f-158">Close the editor window.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0899f-159">Zie De [nieuwste beheersjablonen](#get-the-latest-administrative-templates)ophalen als u het beleid **Automatische MDM-inschrijving**inschakelen niet ziet.</span><span class="sxs-lookup"><span data-stu-id="0899f-159">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, see [Get the latest Administrative Templates](#get-the-latest-administrative-templates).</span></span>

## <a name="6-deploy-the-group-policy"></a><span data-ttu-id="0899f-160">6. Het groepsbeleid implementeren</span><span class="sxs-lookup"><span data-stu-id="0899f-160">6. Deploy the Group Policy</span></span>

1.  <span data-ttu-id="0899f-161">Selecteer in Serverbeheer onder Domeinen > **groepsbeleidsobjecten** de GPO uit stap 3 hierboven, bijvoorbeeld 'Cloud_Enrollment'.</span><span class="sxs-lookup"><span data-stu-id="0899f-161">In the Server Manager, under **Domains** > Group Policy objects, select the GPO from Step 3 above, for example “Cloud_Enrollment”.</span></span>
2.  <span data-ttu-id="0899f-162">Selecteer het tabblad **Bereik** voor uw GPO.</span><span class="sxs-lookup"><span data-stu-id="0899f-162">Select the **Scope** tab for your GPO.</span></span>
3.  <span data-ttu-id="0899f-163">Klik op het tabblad Bereik van GPO met de rechtermuisknop op de koppeling naar het domein onder **Koppelingen**.</span><span class="sxs-lookup"><span data-stu-id="0899f-163">In the GPO’s Scope tab, right-click the link to the domain under **Links**.</span></span>
4.  <span data-ttu-id="0899f-164">Selecteer **Afgedwongen** om de GPO te implementeren en **vervolgens OK** in het bevestigingsscherm.</span><span class="sxs-lookup"><span data-stu-id="0899f-164">Select **Enforced** to deploy the GPO and then **OK** in the confirmation screen.</span></span>

## <a name="get-the-latest-administrative-templates"></a><span data-ttu-id="0899f-165">De nieuwste beheersjablonen ophalen</span><span class="sxs-lookup"><span data-stu-id="0899f-165">Get the latest Administrative Templates</span></span>

<span data-ttu-id="0899f-166">Als u het beleid Automatische MDM-inschrijving inschakelen niet ziet **met standaard Azure AD-referenties,** kan dit zijn omdat u de ADMX niet hebt geïnstalleerd voor Windows 10, versie 1803, versie 1809 of versie 1903.</span><span class="sxs-lookup"><span data-stu-id="0899f-166">If you do not see the policy **Enable automatic MDM enrollment using default Azure AD credentials**, it may be because you don’t have the ADMX installed for Windows 10, version 1803, version 1809, or version 1903.</span></span> <span data-ttu-id="0899f-167">Voer de volgende stappen uit (Opmerking: de nieuwste MDM.admx is backwards compatible):</span><span class="sxs-lookup"><span data-stu-id="0899f-167">To fix the issue, follow these steps (Note: the latest MDM.admx is backwards compatible):</span></span>

1.  <span data-ttu-id="0899f-168">Download: [Beheersjablonen (.admx) voor Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span><span class="sxs-lookup"><span data-stu-id="0899f-168">Download: [Administrative Templates (.admx) for Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).</span></span>
2.  <span data-ttu-id="0899f-169">Installeer het pakket op de primaire domeincontroller (PDC).</span><span class="sxs-lookup"><span data-stu-id="0899f-169">Install the package on the Primary Domain Controller (PDC).</span></span>
3.  <span data-ttu-id="0899f-170">Navigeren, afhankelijk van de versie naar de map: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span><span class="sxs-lookup"><span data-stu-id="0899f-170">Navigate, depending on the version to the folder: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.</span></span>
4.  <span data-ttu-id="0899f-171">Wijzig de naam van de map **Beleidsdefinities** in het bovenstaande pad naar **Beleidsdefinities**.</span><span class="sxs-lookup"><span data-stu-id="0899f-171">Rename the **Policy Definitions** folder in the above path to **PolicyDefinitions**.</span></span>
5.  <span data-ttu-id="0899f-172">Map **Beleidsdefinities** kopiëren naar **C:\Windows\SYSVOL\domain\Policies**.</span><span class="sxs-lookup"><span data-stu-id="0899f-172">Copy **PolicyDefinitions** folder to **C:\Windows\SYSVOL\domain\Policies**.</span></span> 
    -   <span data-ttu-id="0899f-173">Als u van plan bent een centrale beleidsopslag voor uw hele domein te gebruiken, voegt u daar de inhoud van Beleidsdefinities toe.</span><span class="sxs-lookup"><span data-stu-id="0899f-173">If you plan to use a central policy store for your entire domain, add the contents of PolicyDefinitions there.</span></span>
6.  <span data-ttu-id="0899f-174">Start de primaire domeincontroller opnieuw om het beleid beschikbaar te maken.</span><span class="sxs-lookup"><span data-stu-id="0899f-174">Restart the Primary Domain Controller for the policy to be available.</span></span> <span data-ttu-id="0899f-175">Deze procedure zal ook werken voor elke toekomstige versie.</span><span class="sxs-lookup"><span data-stu-id="0899f-175">This procedure will work for any future version as well.</span></span>

<span data-ttu-id="0899f-176">Op dit punt moet u het beleid **Automatische MDM-inschrijving inschakelen** kunnen zien met standaard Azure AD-referenties beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="0899f-176">At this point you should be able to see the policy **Enable automatic MDM enrollment using default Azure AD credentials** available.</span></span>

