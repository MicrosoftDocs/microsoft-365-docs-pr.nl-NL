---
title: Configuratieanalyse voor beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over het gebruik van de configuratieanalyse om beveiligingsbeleid te zoeken en op te lossen dat zich onder het standaardbeveiligingsbeleid en het vooraf ingestelde beveiligingsbeleid voor strikte beveiliging kunt vinden en oplossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0d2ad1449730f392adc27c8ed2a8fc8e9ecc7a04
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789298"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="564ae-103">Configuratieanalyse voor beveiligingsbeleid in EOP en Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="564ae-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="564ae-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="564ae-104">**Applies to**</span></span>
- [<span data-ttu-id="564ae-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="564ae-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="564ae-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="564ae-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="564ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="564ae-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="564ae-108">Configuratieanalyse in het Microsoft 365-beveiligingscentrum biedt een centrale locatie om beveiligingsbeleid te zoeken en op te lossen waarbij de instellingen zich onder de instellingen Standaardbeveiligings- en Strikt beveiligingsprofiel bevinden in vooraf ingestelde [beveiligingsbeleidsregels.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="564ae-108">Configuration analyzer in the Microsoft 365 security center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="564ae-109">De volgende typen beleid worden geanalyseerd door de configuratieanalyse:</span><span class="sxs-lookup"><span data-stu-id="564ae-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="564ae-110">**Exchange Online Protection (EOP)-beleid**: Dit geldt Microsoft 365 organisaties met Exchange Online postvakken en zelfstandige EOP-organisaties zonder Exchange Online postvakken:</span><span class="sxs-lookup"><span data-stu-id="564ae-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="564ae-111">[Antispambeleid.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="564ae-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="564ae-112">[Anti-malwarebeleid.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="564ae-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="564ae-113">[EOP-anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="564ae-113">[EOP anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="564ae-114">**Microsoft Defender voor Office 365** beleid: Dit geldt ook voor organisaties met Microsoft 365 E5 of Defender voor Office 365-invoegabonnementen:</span><span class="sxs-lookup"><span data-stu-id="564ae-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="564ae-115">Anti-phishingbeleid in Microsoft Defender voor Office 365, waaronder:</span><span class="sxs-lookup"><span data-stu-id="564ae-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>
    - <span data-ttu-id="564ae-116">Dezelfde [spoofinstellingen die](set-up-anti-phishing-policies.md#spoof-settings) beschikbaar zijn in het anti-phishingbeleid van EOP.</span><span class="sxs-lookup"><span data-stu-id="564ae-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="564ae-117">Instellingen voor imitatie</span><span class="sxs-lookup"><span data-stu-id="564ae-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="564ae-118">Geavanceerde phishingdrempels</span><span class="sxs-lookup"><span data-stu-id="564ae-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - <span data-ttu-id="564ae-119">[Safe koppelingenbeleid](set-up-safe-links-policies.md).</span><span class="sxs-lookup"><span data-stu-id="564ae-119">[Safe Links policies](set-up-safe-links-policies.md).</span></span>
  - <span data-ttu-id="564ae-120">[Safe bijlagenbeleid](set-up-safe-attachments-policies.md).</span><span class="sxs-lookup"><span data-stu-id="564ae-120">[Safe Attachments policies](set-up-safe-attachments-policies.md).</span></span>

<span data-ttu-id="564ae-121">De **waarden standaard** en **strikt** beleid die als basislijnen worden gebruikt, worden beschreven in aanbevolen instellingen voor EOP en Microsoft Defender voor [Office 365 beveiliging.](recommended-settings-for-eop-and-office365.md)</span><span class="sxs-lookup"><span data-stu-id="564ae-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="564ae-122">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="564ae-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="564ae-123">U opent het beveiligingscentrum in <https://security.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="564ae-123">You open the security center at <https://security.microsoft.com>.</span></span> <span data-ttu-id="564ae-124">Als u rechtstreeks naar de **pagina Configuratieanalyse wilt** gaan, gebruikt u <https://security.microsoft.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="564ae-124">To go directly to the **Configuration analyzer** page, use <https://security.microsoft.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="564ae-125">Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="564ae-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="564ae-126">U moet machtigingen krijgen toegewezen in het beveiligingscentrum voordat u de procedures in dit artikel kunt uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="564ae-126">You need to be assigned permissions in the security center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="564ae-127">Als u de configuratieanalyse wilt gebruiken **en** updates voor beveiligingsbeleid wilt uitvoeren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="564ae-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="564ae-128">Voor alleen-lezen toegang tot de configuratieanalyse moet u lid zijn van de rollengroepen **Globale** lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="564ae-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="564ae-129">Zie Machtigingen in het Microsoft 365 [beveiligingscentrum voor meer informatie.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="564ae-129">For more information, see [Permissions in the Microsoft 365 security center](permissions-microsoft-365-security-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="564ae-130">Gebruikers toevoegen aan de bijbehorende Azure Active Directory geeft gebruikers de vereiste machtigingen in het beveiligingscentrum en _machtigingen_ voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="564ae-130">Adding users to the corresponding Azure Active Directory role gives users the required permissions in the security center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="564ae-131">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="564ae-131">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  >
  > - <span data-ttu-id="564ae-132">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="564ae-132">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security-center"></a><span data-ttu-id="564ae-133">De configuratieanalyse gebruiken in het beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="564ae-133">Use the configuration analyzer in the security center</span></span>

<span data-ttu-id="564ae-134">Ga in het beveiligingscentrum naar De sectie **Configuratieanalyse** van & e-mailbeleid & regels \>  \> **Beleidsregels** \>  \> met sjabloon .</span><span class="sxs-lookup"><span data-stu-id="564ae-134">In the security center, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Templated policies** section \> **Configuration analyzer**.</span></span>

<span data-ttu-id="564ae-135">De configuratieanalyse heeft twee hoofdtabbladen:</span><span class="sxs-lookup"><span data-stu-id="564ae-135">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="564ae-136">**Instellingen en aanbevelingen:** U kiest  **Standaard** of Strikt en vergelijkt deze instellingen met uw bestaande beveiligingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="564ae-136">**Settings and recommendations**: You pick **Standard** or **Strict** and compare those settings to your existing security policies.</span></span> <span data-ttu-id="564ae-137">In de resultaten kunt u de waarden van uw instellingen aanpassen om deze op hetzelfde niveau te brengen als Standaard of Strikt.</span><span class="sxs-lookup"><span data-stu-id="564ae-137">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>
- <span data-ttu-id="564ae-138">**Configuratiedriftanalyse en -geschiedenis:** met deze weergave kunt u beleidswijzigingen in de tijd bijhouden.</span><span class="sxs-lookup"><span data-stu-id="564ae-138">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="564ae-139">Tabblad Instellingen en aanbevelingen in de configuratieanalyse</span><span class="sxs-lookup"><span data-stu-id="564ae-139">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="564ae-140">Standaard wordt het tabblad geopend in de vergelijking met het standaardbeveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="564ae-140">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="564ae-141">U kunt overschakelen naar de vergelijking van het strikte beveiligingsprofiel door **Strikte aanbevelingen weergeven te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="564ae-141">You can switch to the comparison of the Strict protection profile by selecting **View Strict recommendations**.</span></span> <span data-ttu-id="564ae-142">Als u wilt teruggaan, **selecteert u Standaardaanbevelingen weergeven.**</span><span class="sxs-lookup"><span data-stu-id="564ae-142">To switch back, select **View Standard recommendations**.</span></span>

![Instellingen en aanbevelingen weergeven in de configuratieanalyse](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="564ae-144">Standaard bevat de kolom **Beleidsgroep/instellingsnaam** een samengevouwen weergave van de verschillende typen beveiligingsbeleid en het aantal instellingen dat moet worden verbeterd (indien van beide).</span><span class="sxs-lookup"><span data-stu-id="564ae-144">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="564ae-145">De typen beleidsregels zijn:</span><span class="sxs-lookup"><span data-stu-id="564ae-145">The types of policies are:</span></span>

- <span data-ttu-id="564ae-146">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="564ae-146">**Anti-spam**</span></span>
- <span data-ttu-id="564ae-147">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="564ae-147">**Anti-phishing**</span></span>
- <span data-ttu-id="564ae-148">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="564ae-148">**Anti-malware**</span></span>
- <span data-ttu-id="564ae-149">**Safe bijlagen** (als uw abonnement Microsoft Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="564ae-149">**Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="564ae-150">**Safe Koppelingen** (als uw abonnement Microsoft Defender voor Office 365)</span><span class="sxs-lookup"><span data-stu-id="564ae-150">**Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="564ae-151">In de standaardweergave wordt alles samengevouwen.</span><span class="sxs-lookup"><span data-stu-id="564ae-151">In the default view, everything is collapsed.</span></span> <span data-ttu-id="564ae-152">Naast elk beleid ziet u een overzicht van de vergelijkingsresultaten van uw beleid (dat u kunt wijzigen) en de instellingen in het bijbehorende beleid voor de standaard- of strikte beveiligingsprofielen (die u niet kunt wijzigen).</span><span class="sxs-lookup"><span data-stu-id="564ae-152">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="564ae-153">U ziet de volgende informatie voor het beveiligingsprofiel dat u vergelijkt met:</span><span class="sxs-lookup"><span data-stu-id="564ae-153">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="564ae-154">**Groen:** Alle instellingen in alle bestaande beleidsregels zijn ten minste even veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="564ae-154">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="564ae-155">**Oranje:** Een klein aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="564ae-155">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="564ae-156">**Rood:** Een aanzienlijk aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="564ae-156">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="564ae-157">Dit kunnen enkele instellingen zijn in veel beleidsregels of veel instellingen in één beleid.</span><span class="sxs-lookup"><span data-stu-id="564ae-157">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="564ae-158">Voor gunstige vergelijkingen ziet u de tekst: **Alle instellingen volgen** \<**Standard** or **Strict**\> **aanbevelingen.**</span><span class="sxs-lookup"><span data-stu-id="564ae-158">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="564ae-159">Anders ziet u het aantal aanbevolen instellingen dat u wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="564ae-159">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="564ae-160">Als u de **naam van de groep Beleid/instelling** uitv vouwt, worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid die aandacht vereisen, openbaar.</span><span class="sxs-lookup"><span data-stu-id="564ae-160">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="564ae-161">U kunt ook een specifiek type beleid (bijvoorbeeld **Antispam)** uitbreiden om alleen die instellingen weer te geven in de beleidtypen die uw aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="564ae-161">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="564ae-162">Als de vergelijking geen aanbevelingen voor verbetering (groen) heeft, laat het uitbreiden van het beleid niets zien.</span><span class="sxs-lookup"><span data-stu-id="564ae-162">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="564ae-163">Als er een aantal aanbevelingen voor verbetering (oranje of rood) zijn, worden de instellingen die aandacht vereisen, onthuld en worden de bijbehorende informatie in de volgende kolommen aan het licht komen:</span><span class="sxs-lookup"><span data-stu-id="564ae-163">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="564ae-164">**Naam van beleidsgroep/instelling:** de naam van de instelling die uw aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="564ae-164">**Policy group/setting name**: The name of the setting that requires your attention.</span></span> <span data-ttu-id="564ae-165">In de vorige schermafbeelding zijn het bijvoorbeeld de instellingen in het standaardbeleid voor spam.</span><span class="sxs-lookup"><span data-stu-id="564ae-165">For example, in the previous screenshot, it's the settings in the default anti-spam policy.</span></span>
- <span data-ttu-id="564ae-166">**Beleid:** de naam van het betreffende beleid dat de instelling bevat.</span><span class="sxs-lookup"><span data-stu-id="564ae-166">**Policy**: The name of the affected policy that contains the setting.</span></span>
- <span data-ttu-id="564ae-167">**Toegepast op**: Het aantal gebruikers waar het betreffende beleid op wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="564ae-167">**Applied to**: The number of users that the affected policies are applied to.</span></span>
- <span data-ttu-id="564ae-168">**Huidige configuratie:** de huidige waarde van de instelling.</span><span class="sxs-lookup"><span data-stu-id="564ae-168">**Current configuration**: The current value of the setting.</span></span> <span data-ttu-id="564ae-169">Voor het standaardbeleid van dat type dat van toepassing is op alle geadresseerden, is deze waarde leeg.</span><span class="sxs-lookup"><span data-stu-id="564ae-169">For the default policy of that type that applies to all recipients, this value is blank.</span></span>
- <span data-ttu-id="564ae-170">**Laatst gewijzigd:** de datum waarop het beleid voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="564ae-170">**Last modified**: The date that the policy was last modified.</span></span>
- <span data-ttu-id="564ae-171">**Aanbevelingen:** De waarde van de instelling in het beveiligingsprofiel Standaard of Strikt.</span><span class="sxs-lookup"><span data-stu-id="564ae-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="564ae-172">Als u de waarde van de instelling in uw beleid wilt wijzigen op de aanbevolen waarde in het beveiligingsprofiel, klikt u op **Goedkeuren.**</span><span class="sxs-lookup"><span data-stu-id="564ae-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="564ae-173">Als de wijziging is gelukt, ziet u het bericht: **Aanbevelingen is goedgekeurd.**</span><span class="sxs-lookup"><span data-stu-id="564ae-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="564ae-174">Klik **op** Vernieuwen om het beperkte aantal aanbevelingen weer te geven en de specifieke rij met instellingen/beleid uit de resultaten te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="564ae-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="564ae-175">Tabblad Configuratiedriftanalyse en -geschiedenis in de configuratieanalyse</span><span class="sxs-lookup"><span data-stu-id="564ae-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="564ae-176">Op dit tabblad kunt u de wijzigingen bijhouden die u hebt aangebracht in uw aangepaste beveiligingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="564ae-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="564ae-177">Standaard worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="564ae-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="564ae-178">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="564ae-178">**Last modified**</span></span>
- <span data-ttu-id="564ae-179">**Gewijzigd door**</span><span class="sxs-lookup"><span data-stu-id="564ae-179">**Modified by**</span></span>
- <span data-ttu-id="564ae-180">**Naam instellen**</span><span class="sxs-lookup"><span data-stu-id="564ae-180">**Setting Name**</span></span>
- <span data-ttu-id="564ae-181">**Beleid**</span><span class="sxs-lookup"><span data-stu-id="564ae-181">**Policy**</span></span>
- <span data-ttu-id="564ae-182">**Type**</span><span class="sxs-lookup"><span data-stu-id="564ae-182">**Type**</span></span>
- <span data-ttu-id="564ae-183">**Configuratiewijziging**</span><span class="sxs-lookup"><span data-stu-id="564ae-183">**Configuration change**</span></span>
- <span data-ttu-id="564ae-184">**Configuratiedrift:** De waarde **Verhogen** of **Verlagen**.</span><span class="sxs-lookup"><span data-stu-id="564ae-184">**Configuration drift**: The value **Increase** or **Decrease**.</span></span>

<span data-ttu-id="564ae-185">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="564ae-185">To filter the results, click **Filter**.</span></span> <span data-ttu-id="564ae-186">In het **flyout** Filters dat wordt weergegeven, kunt u kiezen uit de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="564ae-186">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="564ae-187">**Begintijd** **en eindtijd** (datum)</span><span class="sxs-lookup"><span data-stu-id="564ae-187">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="564ae-188">**Standaardbeveiliging** of **Strikte beveiliging**</span><span class="sxs-lookup"><span data-stu-id="564ae-188">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="564ae-189">Als u de resultaten wilt exporteren naar een .csv bestand, klikt u op **Exporteren.**</span><span class="sxs-lookup"><span data-stu-id="564ae-189">To export the results to a .csv file, click **Export**.</span></span>

![Configuratiedriftanalyse en geschiedenisweergave in configuratieanalyse](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
