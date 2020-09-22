---
title: Configuratie analyse voor beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe u met de wizard Configuratie analyse beveiligingsbeleid onder de standaardbeveiliging en strikte beveiligings beleidsregels voor beveiliging kunt vinden en oplossen.
ms.openlocfilehash: d2d37d937f42587ad99e4145d3a9f9fbc6a5a0f4
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203429"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="1f48e-103">Configuratie analyse voor beveiligingsbeleid in EOP en Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1f48e-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="1f48e-104">De functies die in dit onderwerp worden beschreven, zijn in voorbeeld, zijn niet beschikbaar in alle organisaties en zijn onderhevig aan wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="1f48e-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span> <span data-ttu-id="1f48e-105">Voor informatie over de release planning raadpleegt u het [Microsoft 365-wegwijzer](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span><span class="sxs-lookup"><span data-stu-id="1f48e-105">For information about the release schedule, check out the [Microsoft 365 roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).</span></span>

<span data-ttu-id="1f48e-106">Configuratie-analyse in het compliance van beveiligings & biedt een centrale locatie voor het zoeken naar en herstellen van beveiligingsbeleid waarbij de instellingen onder de standaardbeveiliging en strikte bescherming van profielinstellingen in [vooraf ingesteld beveiligingsbeleid](preset-security-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1f48e-106">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="1f48e-107">De volgende typen beleidsregels worden geanalyseerd door de Configuration Analyzer:</span><span class="sxs-lookup"><span data-stu-id="1f48e-107">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="1f48e-108">**Beleid voor Exchange Online Protection (EOP)**: Dit omvat microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder postvakken van Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="1f48e-108">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="1f48e-109">[Anti spam beleid](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1f48e-109">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="1f48e-110">[Beleid voor malware van malware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="1f48e-110">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="1f48e-111">[EOP anti phishings beleid](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="1f48e-111">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="1f48e-112">**Office 365 Advanced Threat Protection (ATP)-beleidsregels**: Dit omvat organisaties met microsoft 365 E5 of Office 365 ATP-uitbreidings abonnementen:</span><span class="sxs-lookup"><span data-stu-id="1f48e-112">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="1f48e-113">ATP anti-phishing-beleid, waaronder:</span><span class="sxs-lookup"><span data-stu-id="1f48e-113">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="1f48e-114">De [instellingen voor spoofing](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het anti-phishings beleid van EOP.</span><span class="sxs-lookup"><span data-stu-id="1f48e-114">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="1f48e-115">Imitatie-instellingen</span><span class="sxs-lookup"><span data-stu-id="1f48e-115">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="1f48e-116">Geavanceerde phishingberichten</span><span class="sxs-lookup"><span data-stu-id="1f48e-116">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="1f48e-117">[Beleidsregels voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="1f48e-117">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="1f48e-118">[Beleidsregels voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="1f48e-118">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="1f48e-119">De **standaard** waarden en **strikte** beleidsinstelling waarden die worden gebruikt als basislijnen, worden beschreven in [Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="1f48e-119">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1f48e-120">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="1f48e-120">What do you need to know before you begin?</span></span>

- <span data-ttu-id="1f48e-121">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="1f48e-121">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="1f48e-122">Als u direct naar de pagina **Configuration Analyzer** wilt gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="1f48e-122">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="1f48e-123">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f48e-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="1f48e-124">U moet machtigingen zijn toegewezen voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="1f48e-124">You need to be assigned permissions before you can do the procedures in this article:</span></span>

  - <span data-ttu-id="1f48e-125">Als u de Configuration Analyzer wilt gebruiken **en** beveiligingsbeleidsregels wilt bijwerken, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="1f48e-125">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1f48e-126">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1f48e-126">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1f48e-127">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1f48e-127">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="1f48e-128">Voor alleen-lezen toegang tot de configuratie analyse, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="1f48e-128">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="1f48e-129">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="1f48e-129">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="1f48e-130">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="1f48e-130">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="1f48e-131">Werken met de functie Configuration Analyzer in het compliance van beveiligings &</span><span class="sxs-lookup"><span data-stu-id="1f48e-131">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="1f48e-132">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **configuratie analyse**beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="1f48e-132">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![De widget configuratie analyse op de pagina beleid voor risicobeheer \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="1f48e-134">De configuratie analyse bestaat uit twee hoofdtabbladen:</span><span class="sxs-lookup"><span data-stu-id="1f48e-134">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="1f48e-135">**Instellingen en aanbevelingen**: u kunt standaard of strict selecteren en deze instellingen vergelijken met uw bestaande beveiligingsbeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="1f48e-135">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="1f48e-136">In de resultaten kunt u de waarden van uw instellingen aanpassen, zodat ze op hetzelfde niveau als standaard of strikt worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1f48e-136">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="1f48e-137">Configuratie van de overstappen **en geschiedenis**van de configuratie van de overstappen, zodat u de beleidswijzigingen in de tijd kunt bijhouden.</span><span class="sxs-lookup"><span data-stu-id="1f48e-137">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="1f48e-138">Tabblad instelling en aanbevelingen in de configuratie-analyse</span><span class="sxs-lookup"><span data-stu-id="1f48e-138">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="1f48e-139">Standaard wordt het tabblad op de vergelijking met het standaardbeveiligingsprofiel geopend.</span><span class="sxs-lookup"><span data-stu-id="1f48e-139">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="1f48e-140">U kunt overstappen op de vergelijking van het strikte beveiligingsprofiel door op **strikte aanbevelingen weergeven**te klikken.</span><span class="sxs-lookup"><span data-stu-id="1f48e-140">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="1f48e-141">Als u wilt terugkeren, selecteert u **standaard aanbevelingen weergeven**.</span><span class="sxs-lookup"><span data-stu-id="1f48e-141">To switch back, select **View Standard recommendations**.</span></span>

![De weergave van instellingen en aanbevelingen in de configuratie-analyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="1f48e-143">De kolom **Beleidsgroep/naam van instelling** bevat standaard een samengevouwen weergave van de verschillende typen beveiligingsbeleidsregels en het aantal instellingen dat moet worden verbeterd (indien van toepassing).</span><span class="sxs-lookup"><span data-stu-id="1f48e-143">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="1f48e-144">De typen beleidsregels zijn:</span><span class="sxs-lookup"><span data-stu-id="1f48e-144">The types of policies are:</span></span>

- <span data-ttu-id="1f48e-145">**Anti spam**</span><span class="sxs-lookup"><span data-stu-id="1f48e-145">**Anti-spam**</span></span>
- <span data-ttu-id="1f48e-146">**Anti phishing**</span><span class="sxs-lookup"><span data-stu-id="1f48e-146">**Anti-phishing**</span></span>
- <span data-ttu-id="1f48e-147">**Anti malware**</span><span class="sxs-lookup"><span data-stu-id="1f48e-147">**Anti-malware**</span></span>
- <span data-ttu-id="1f48e-148">**Veilige bijlage van ATP** (als uw abonnement de ATP omvat)</span><span class="sxs-lookup"><span data-stu-id="1f48e-148">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="1f48e-149">**Veilige koppelingen voor ATP** (als uw abonnement de ATP omvat)</span><span class="sxs-lookup"><span data-stu-id="1f48e-149">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="1f48e-150">In de standaardweergave is alles samengevouwen.</span><span class="sxs-lookup"><span data-stu-id="1f48e-150">In the default view, everything is collapsed.</span></span> <span data-ttu-id="1f48e-151">Naast elk beleid bevindt zich een samenvatting van vergelijkingsresultaten van uw beleid (die u kunt wijzigen) en de instellingen in het bijbehorende beleid voor de standaard-of strikte beveiligingsprofielen (die u niet kunt wijzigen).</span><span class="sxs-lookup"><span data-stu-id="1f48e-151">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="1f48e-152">U ziet de volgende informatie voor het beveiligingsprofiel waarmee u een vergelijking maakt:</span><span class="sxs-lookup"><span data-stu-id="1f48e-152">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="1f48e-153">**Groen**: alle instellingen in alle bestaande beleidsregels zijn ten minste veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="1f48e-153">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="1f48e-154">**Geel**: een klein aantal instellingen in het bestaande beleid is niet veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="1f48e-154">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="1f48e-155">**Rood**: een groot aantal instellingen in het bestaande beleid is niet veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="1f48e-155">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="1f48e-156">Dit kan een paar instellingen zijn voor veel beleidsregels of veel instellingen in één beleid.</span><span class="sxs-lookup"><span data-stu-id="1f48e-156">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="1f48e-157">Voor gunstige vergelijkingen ziet u de tekst: bij **alle instellingen volgen** de \<**Standard** or **Strict**\> **aanbevelingen**.</span><span class="sxs-lookup"><span data-stu-id="1f48e-157">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="1f48e-158">Anders ziet u het aantal aanbevolen instellingen dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="1f48e-158">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="1f48e-159">Als u **Beleidsgroep/naam**van de instelling uitvouwt, worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid weergegeven dat aandacht moet richten.</span><span class="sxs-lookup"><span data-stu-id="1f48e-159">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="1f48e-160">U kunt ook een specifiek type beleid uitvouwen (bijvoorbeeld **anti spam**), zodat alleen de instellingen worden weergegeven van de typen beleidsregels die uw aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="1f48e-160">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="1f48e-161">Als de vergelijking geen aanbevelingen oplevert voor verbetering (groen), onthult het beleid niets.</span><span class="sxs-lookup"><span data-stu-id="1f48e-161">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="1f48e-162">Als er sprake is van een aantal aanbevelingen voor verbetering (geel of rood), worden de instellingen die aandacht vereisen weergegeven en wordt de bijbehorende informatie getoond in de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="1f48e-162">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="1f48e-163">De naam van de instelling die uw aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="1f48e-163">The name of the setting that requires your attention.</span></span> <span data-ttu-id="1f48e-164">In de vorige schermafbeelding ziet u bijvoorbeeld de limiet voor **bulk mail** in een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="1f48e-164">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="1f48e-165">**Beleid**: de naam van het betreffende beleid dat de instelling bevat.</span><span class="sxs-lookup"><span data-stu-id="1f48e-165">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="1f48e-166">**Toepassen op**: het aantal gebruikers waarop het desbetreffende beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="1f48e-166">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="1f48e-167">**Huidige configuratie**: de huidige waarde van de instelling.</span><span class="sxs-lookup"><span data-stu-id="1f48e-167">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="1f48e-168">**Laatst gewijzigd**: de datum waarop het beleid het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1f48e-168">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="1f48e-169">**Aanbevelingen**: de waarde van de instelling in het standaard-of strikte beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="1f48e-169">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="1f48e-170">Als u de waarde van de instelling in het beleid wilt wijzigen zodat deze overeenkomt met de aanbevolen waarde in het beveiligingsprofiel, klikt u op **aannemen**.</span><span class="sxs-lookup"><span data-stu-id="1f48e-170">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="1f48e-171">Als de wijziging slaagt, ziet u het volgende bericht: **aanbevelingen zijn besloten**.</span><span class="sxs-lookup"><span data-stu-id="1f48e-171">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="1f48e-172">Klik op **vernieuwen** om het minder aantal aanbevelingen te zien en het verwijderen van de specifieke rij voor beleidsregels/beleid van de resultaten.</span><span class="sxs-lookup"><span data-stu-id="1f48e-172">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="1f48e-173">Configuratie van configuratie van drijfman en historie van configuratie-analyse</span><span class="sxs-lookup"><span data-stu-id="1f48e-173">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="1f48e-174">Op dit tabblad kunt u de wijzigingen bijhouden die u in uw aangepaste beveiligingsbeleid hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="1f48e-174">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="1f48e-175">Standaard wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="1f48e-175">By default, the following information is displayed:</span></span>

- <span data-ttu-id="1f48e-176">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="1f48e-176">**Last modified**</span></span>
- <span data-ttu-id="1f48e-177">**Gewijzigd door**</span><span class="sxs-lookup"><span data-stu-id="1f48e-177">**Modified by**</span></span>
- <span data-ttu-id="1f48e-178">**Naam van instelling**</span><span class="sxs-lookup"><span data-stu-id="1f48e-178">**Setting Name**</span></span>
- <span data-ttu-id="1f48e-179">**Beleid**</span><span class="sxs-lookup"><span data-stu-id="1f48e-179">**Policy**</span></span>
- <span data-ttu-id="1f48e-180">**Type**</span><span class="sxs-lookup"><span data-stu-id="1f48e-180">**Type**</span></span>

<span data-ttu-id="1f48e-181">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="1f48e-181">To filter the results, click **Filter**.</span></span> <span data-ttu-id="1f48e-182">In de **gefilterde** flyout die wordt weergegeven, kunt u kiezen uit de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="1f48e-182">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="1f48e-183">**Begintijd** en **Eindtijd** (datum)</span><span class="sxs-lookup"><span data-stu-id="1f48e-183">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="1f48e-184">**Standaard bescherming** of **strikte bescherming**</span><span class="sxs-lookup"><span data-stu-id="1f48e-184">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="1f48e-185">Als u de resultaten naar een CSV-bestand wilt exporteren, klikt u op **exporteren**.</span><span class="sxs-lookup"><span data-stu-id="1f48e-185">To export the results to a .csv file, click **Export**.</span></span>

![Configuratie-analyse-en historie weergave](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
