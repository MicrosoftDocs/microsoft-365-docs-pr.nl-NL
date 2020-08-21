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
description: Beheerders kunnen leren hoe u met de wizard Configuratie analyse beveiligingsbeleidsregels met instellingen onder de standaardbeveiliging en strikte beveiliging vooraf beveiligt.
ms.openlocfilehash: 4515efcd73d40eae93523c6ef139553420e48677
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825771"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="4ec68-103">Configuratie analyse voor beveiligingsbeleid in EOP en Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="4ec68-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="4ec68-104">De functies die in dit onderwerp worden beschreven, zijn in voorbeeld, zijn niet beschikbaar in alle organisaties en zijn onderhevig aan wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="4ec68-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="4ec68-105">Configuratie-analyse in het compliance van beveiligings & biedt een centrale locatie voor het zoeken naar en herstellen van uw beveiligingsbeleid met instellingen die onder de standaardbeveiliging en strikte bescherming van profielinstellingen in [vooraf ingesteld beveiligingsbeleid](preset-security-policies.md)bevatten.</span><span class="sxs-lookup"><span data-stu-id="4ec68-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="4ec68-106">De volgende typen beleidsregels worden geanalyseerd door de Configuration Analyzer:</span><span class="sxs-lookup"><span data-stu-id="4ec68-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="4ec68-107">**Beleid voor Exchange Online Protection (EOP)**: Dit omvat microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder postvakken van Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="4ec68-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="4ec68-108">[Anti spam beleid](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4ec68-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="4ec68-109">[Beleid voor malware van malware](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4ec68-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="4ec68-110">[EOP anti phishings beleid](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="4ec68-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="4ec68-111">**Office 365 Advanced Threat Protection (ATP)-beleidsregels**: Dit omvat organisaties met microsoft 365 E5 of Office 365 ATP-uitbreidings abonnementen:</span><span class="sxs-lookup"><span data-stu-id="4ec68-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="4ec68-112">ATP anti-phishing-beleid, waaronder:</span><span class="sxs-lookup"><span data-stu-id="4ec68-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="4ec68-113">De [instellingen voor spoofing](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het anti-phishings beleid van EOP.</span><span class="sxs-lookup"><span data-stu-id="4ec68-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="4ec68-114">Imitatie-instellingen</span><span class="sxs-lookup"><span data-stu-id="4ec68-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="4ec68-115">Geavanceerde phishingberichten</span><span class="sxs-lookup"><span data-stu-id="4ec68-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="4ec68-116">[Beleidsregels voor veilige koppelingen](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="4ec68-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="4ec68-117">[Beleidsregels voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="4ec68-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="4ec68-118">De **standaard** waarden en **strikte** beleidsinstelling waarden die worden gebruikt als basislijnen, worden beschreven in [Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="4ec68-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4ec68-119">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="4ec68-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="4ec68-120">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="4ec68-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="4ec68-121">Als u direct naar de pagina **Configuration Analyzer** wilt gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="4ec68-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="4ec68-122">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4ec68-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="4ec68-123">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="4ec68-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="4ec68-124">Als u de Configuration Analyzer wilt gebruiken **en** beveiligingsbeleidsregels wilt bijwerken, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="4ec68-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="4ec68-125">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4ec68-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="4ec68-126">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="4ec68-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="4ec68-127">Voor alleen-lezen toegang tot de configuratie analyse, moet u lid zijn van een van de volgende groepen rollen:</span><span class="sxs-lookup"><span data-stu-id="4ec68-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="4ec68-128">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="4ec68-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="4ec68-129">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="4ec68-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="4ec68-130">Werken met de functie Configuration Analyzer in het compliance van beveiligings &</span><span class="sxs-lookup"><span data-stu-id="4ec68-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="4ec68-131">Ga in het beveiligings & compliance naar **Threat management** \> **Policy** \> **configuratie analyse**beleid voor Threat Management.</span><span class="sxs-lookup"><span data-stu-id="4ec68-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![De widget configuratie analyse op de pagina beleid voor risicobeheer \>](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="4ec68-133">De configuratie analyse bestaat uit twee hoofdtabbladen:</span><span class="sxs-lookup"><span data-stu-id="4ec68-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="4ec68-134">**Instellingen en aanbevelingen**: u kunt standaard of strict selecteren en deze instellingen vergelijken met uw bestaande beveiligingsbeleidsregels.</span><span class="sxs-lookup"><span data-stu-id="4ec68-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="4ec68-135">In de resultaten kunt u de waarden van uw instellingen aanpassen, zodat ze op hetzelfde niveau als standaard of strikt worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4ec68-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="4ec68-136">Configuratie van overstappen **en geschiedenis van configuratie**overstappen: in deze weergave kunt u de wijzigingen die u hebt aangebracht in de beleidsregels bijhouden op basis van de resultaten van de Configuration Analyzer.</span><span class="sxs-lookup"><span data-stu-id="4ec68-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="4ec68-137">Tabblad instelling en aanbevelingen in de configuratie-analyse</span><span class="sxs-lookup"><span data-stu-id="4ec68-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="4ec68-138">Standaard wordt het tabblad op de vergelijking met het standaardbeveiligingsprofiel geopend.</span><span class="sxs-lookup"><span data-stu-id="4ec68-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="4ec68-139">U kunt overstappen op de vergelijking van het strikte beveiligingsprofiel door op **strikte aanbevelingen weergeven**te klikken.</span><span class="sxs-lookup"><span data-stu-id="4ec68-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="4ec68-140">Als u wilt terugkeren, selecteert u **standaard aanbevelingen weergeven**.</span><span class="sxs-lookup"><span data-stu-id="4ec68-140">To switch back, select **View Standard recommendations**.</span></span>

![De weergave van instellingen en aanbevelingen in de configuratie-analyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="4ec68-142">Standaard bevat de kolom **Beleidsgroep/naam** van gebruikersnaam een samengevouwen weergave van de verschillende typen beveiligings policies en het aantal instellingen in de beleidsregels die moeten worden verbeterd (indien aanwezig).</span><span class="sxs-lookup"><span data-stu-id="4ec68-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="4ec68-143">De typen beleidsregels zijn:</span><span class="sxs-lookup"><span data-stu-id="4ec68-143">The types of policies are:</span></span>

- <span data-ttu-id="4ec68-144">**Anti spam**</span><span class="sxs-lookup"><span data-stu-id="4ec68-144">**Anti-spam**</span></span>
- <span data-ttu-id="4ec68-145">**Anti phishing**</span><span class="sxs-lookup"><span data-stu-id="4ec68-145">**Anti-phishing**</span></span>
- <span data-ttu-id="4ec68-146">**Anti malware**</span><span class="sxs-lookup"><span data-stu-id="4ec68-146">**Anti-malware**</span></span>
- <span data-ttu-id="4ec68-147">**Veilige bijlage van ATP** (als uw abonnement de ATP omvat)</span><span class="sxs-lookup"><span data-stu-id="4ec68-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="4ec68-148">**Veilige koppelingen voor ATP** (als uw abonnement de ATP omvat)</span><span class="sxs-lookup"><span data-stu-id="4ec68-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="4ec68-149">In de standaardweergave is alles samengevouwen.</span><span class="sxs-lookup"><span data-stu-id="4ec68-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="4ec68-150">Naast elk beleid, een samenvatting van vergelijkingsresultaten van uw beleid (die u kunt wijzigen) en de instellingen in het bijbehorende beleid voor de standaard-of strikte beveiligingsprofielen (die u niet kunt wijzigen) worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="4ec68-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="4ec68-151">U ziet de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="4ec68-151">You'll see the following information:</span></span>

- <span data-ttu-id="4ec68-152">**Groen**: alle instellingen in alle bestaande beleidsregels zijn ten minste veilig als het beveiligingsprofiel waarmee u gaat vergelijken.</span><span class="sxs-lookup"><span data-stu-id="4ec68-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="4ec68-153">**Geel**: een klein aantal instellingen in het bestaande beleid is niet veilig als het beveiligingsprofiel waarmee u gaat vergelijken.</span><span class="sxs-lookup"><span data-stu-id="4ec68-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="4ec68-154">**Rood**: een groot aantal instellingen in het bestaande beleid is niet beveiligd als het beveiligingsprofiel waarmee u gaat vergelijken.</span><span class="sxs-lookup"><span data-stu-id="4ec68-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="4ec68-155">Dit kan een paar instellingen zijn voor veel beleidsregels of veel instellingen in één beleid.</span><span class="sxs-lookup"><span data-stu-id="4ec68-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="4ec68-156">Voor gunstige vergelijkingen ziet u de tekst: bij **alle instellingen volgen** de \<**Standard** or **Strict**\> **aanbevelingen**.</span><span class="sxs-lookup"><span data-stu-id="4ec68-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="4ec68-157">Anders ziet u het aantal aanbevolen instellingen dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="4ec68-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="4ec68-158">Als u **Beleidsgroep/naam**van de instelling uitvouwt, worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid weergegeven dat aandacht moet richten.</span><span class="sxs-lookup"><span data-stu-id="4ec68-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="4ec68-159">U kunt ook een specifiek type beleid uitvouwen (bijvoorbeeld **anti spam**), zodat alleen de instellingen worden weergegeven van de typen beleidsregels die uw aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="4ec68-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="4ec68-160">Als de vergelijking geen aanbevelingen oplevert voor verbetering (groen), onthult het beleid niets.</span><span class="sxs-lookup"><span data-stu-id="4ec68-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="4ec68-161">Als er sprake is van een aantal aanbevelingen voor verbetering (geel of rood), worden de instellingen die aandacht vereisen weergegeven en wordt de bijbehorende informatie getoond in de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="4ec68-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="4ec68-162">De naam van de instelling die uw aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="4ec68-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="4ec68-163">In de vorige schermafbeelding ziet u bijvoorbeeld de limiet voor **bulk mail** in een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="4ec68-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="4ec68-164">**Beleid**: de naam van het betreffende beleid dat de instelling bevat.</span><span class="sxs-lookup"><span data-stu-id="4ec68-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="4ec68-165">**Toegepast op**: het aantal gebruikers waarvoor het desbetreffende beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="4ec68-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="4ec68-166">**Huidige configuratie**: de huidige waarde van de instelling.</span><span class="sxs-lookup"><span data-stu-id="4ec68-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="4ec68-167">**Laatst gewijzigd**: de datum waarop het beleid het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="4ec68-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="4ec68-168">**Aanbevelingen**: de waarde van de instelling in het standaard-of strikte beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="4ec68-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="4ec68-169">Als u de waarde van de instelling in het beleid wilt wijzigen zodat deze overeenkomt met de aanbevolen waarde in het beveiligingsprofiel, klikt u op **aannemen**.</span><span class="sxs-lookup"><span data-stu-id="4ec68-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="4ec68-170">Als de wijziging slaagt, ziet u het volgende bericht: **aanbevelingen zijn besloten**.</span><span class="sxs-lookup"><span data-stu-id="4ec68-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="4ec68-171">Klik op **vernieuwen** om het minder aantal aanbevelingen te zien en het verwijderen van de specifieke rij voor beleidsregels/beleid van de resultaten.</span><span class="sxs-lookup"><span data-stu-id="4ec68-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="4ec68-172">Configuratie van configuratie van drijfman en historie van configuratie-analyse</span><span class="sxs-lookup"><span data-stu-id="4ec68-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="4ec68-173">Op dit tabblad kunt u de wijzigingen die u hebt aangebracht in uw aangepaste beveiligingsbeleid bijhouden op basis van de gegevens in de Security Analyzer.</span><span class="sxs-lookup"><span data-stu-id="4ec68-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="4ec68-174">Standaard wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="4ec68-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="4ec68-175">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="4ec68-175">**Last modified**</span></span>
- <span data-ttu-id="4ec68-176">**Gewijzigd door**</span><span class="sxs-lookup"><span data-stu-id="4ec68-176">**Modified by**</span></span>
- <span data-ttu-id="4ec68-177">**Naam van instelling**</span><span class="sxs-lookup"><span data-stu-id="4ec68-177">**Setting Name**</span></span>
- <span data-ttu-id="4ec68-178">**Beleid**</span><span class="sxs-lookup"><span data-stu-id="4ec68-178">**Policy**</span></span>
- <span data-ttu-id="4ec68-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="4ec68-179">**Type**</span></span>

<span data-ttu-id="4ec68-180">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="4ec68-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="4ec68-181">In de **gefilterde** flyout die wordt weergegeven, kunt u kiezen uit de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="4ec68-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="4ec68-182">**Begintijd** en **Eindtijd** (datum)</span><span class="sxs-lookup"><span data-stu-id="4ec68-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="4ec68-183">**Standaard bescherming** of **strikte bescherming**</span><span class="sxs-lookup"><span data-stu-id="4ec68-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="4ec68-184">Als u de resultaten naar een CSV-bestand wilt exporteren, klikt u op **exporteren**.</span><span class="sxs-lookup"><span data-stu-id="4ec68-184">To export the results to a .csv file, click **Export**.</span></span>

![Configuratie-analyse-en historie weergave](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
