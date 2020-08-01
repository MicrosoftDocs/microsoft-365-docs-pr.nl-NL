---
title: Configuratieanalyzer voor beveiligingsbeleid
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze de configuratieanalyzer kunnen gebruiken om beveiligingsbeleid te vinden en vast te stellen dat instellingen bevat die lager zijn dan het beveiligingsbeleid voor standaardbescherming en strikte beveiliging.
ms.openlocfilehash: 259d498646ecf893a57a608a37e3b771083716cc
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533968"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a><span data-ttu-id="b01e3-103">Configuratieanalyzer voor beveiligingsbeleid in EOP en Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="b01e3-103">Configuration analyzer for protection policies in EOP and Office 365 ATP</span></span>

> [!NOTE]
> <span data-ttu-id="b01e3-104">De functies die in dit onderwerp worden beschreven, staan in Voorbeeld, zijn niet beschikbaar in alle organisaties en kunnen worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="b01e3-104">The features described in this topic are in Preview, aren't available in all organizations, and are subject to change.</span></span>

<span data-ttu-id="b01e3-105">Configuratieanalyzer in het Security & Compliance center biedt een centrale locatie voor het vinden en repareren van een van uw beveiligingsbeleid dat instellingen bevat die lager zijn dan de instellingen voor standaardbeveiliging en strikt beveiligingsprofiel in [vooraf ingestelde beveiligingsbeleid.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="b01e3-105">Configuration analyzer in the Security & Compliance center provides a central location to find and fix any of your security policies that contain settings that are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="b01e3-106">De volgende typen beleidsregels worden geanalyseerd door de configuratieanalyzer:</span><span class="sxs-lookup"><span data-stu-id="b01e3-106">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="b01e3-107">**EOP-beleid (Exchange Online Protection):** Dit omvat Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder Exchange Online-postvakken:</span><span class="sxs-lookup"><span data-stu-id="b01e3-107">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>
  
  - <span data-ttu-id="b01e3-108">[Anti-spam beleid](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b01e3-108">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="b01e3-109">[Anti-malware beleid](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="b01e3-109">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="b01e3-110">[EOP Anti-phishing beleid](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="b01e3-110">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="b01e3-111">**Atp-beleid (Advanced Threat Protection) van Office 365:** dit geldt ook voor organisaties met Microsoft 365 E5- of Office 365 ATP-invoegabonnementen:</span><span class="sxs-lookup"><span data-stu-id="b01e3-111">**Office 365 Advanced Threat Protection (ATP) policies**: This includes organizations with Microsoft 365 E5 or Office 365 ATP add-on subscriptions:</span></span>

  - <span data-ttu-id="b01e3-112">ATP anti-phishing beleid, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b01e3-112">ATP anti-phishing policies, which include:</span></span>

    - <span data-ttu-id="b01e3-113">Dezelfde [spoofinstellingen](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het EOP-anti-phishingbeleid.</span><span class="sxs-lookup"><span data-stu-id="b01e3-113">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="b01e3-114">Imitatie-instellingen</span><span class="sxs-lookup"><span data-stu-id="b01e3-114">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [<span data-ttu-id="b01e3-115">Geavanceerde phishingdrempels</span><span class="sxs-lookup"><span data-stu-id="b01e3-115">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - <span data-ttu-id="b01e3-116">[Beleid voor veilige links](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="b01e3-116">[Safe Links policies](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users).</span></span>

  - <span data-ttu-id="b01e3-117">[Beleid voor veilige bijlagen](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span><span class="sxs-lookup"><span data-stu-id="b01e3-117">[Safe Attachments policies](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).</span></span>

<span data-ttu-id="b01e3-118">De **standaard-** en **strikte** beleidsinstellingswaarden die worden gebruikt als basislijnen, worden beschreven in [aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging](recommended-settings-for-eop-and-office365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="b01e3-118">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Office 365 ATP security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b01e3-119">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="b01e3-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b01e3-120">U opent het Beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b01e3-120">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="b01e3-121">Als u rechtstreeks naar de pagina **Configuratieanalyse wilt** gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="b01e3-121">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="b01e3-122">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b01e3-122">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="b01e3-123">U moet beschikken over bepaalde machtigingen om de procedures in dit onderwerp te kunnen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="b01e3-123">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="b01e3-124">Als u de configuratieanalyzer wilt gebruiken **en** het beveiligingsbeleid wilt bijsy-updaten, moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="b01e3-124">To use the configuration analyzer **and** make updates to security policies, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b01e3-125">**Organisatiebeheer** of **Beveiligingsbeheerder** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b01e3-125">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b01e3-126">**Organisatiebeheer** of **Hygiënebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b01e3-126">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="b01e3-127">Voor alleen-lezen toegang tot de configuratieanalyzer moet u lid zijn van een van de volgende rolgroepen:</span><span class="sxs-lookup"><span data-stu-id="b01e3-127">For read-only access to the configuration analyzer, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="b01e3-128">**Beveiligingslezer** in het [Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b01e3-128">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="b01e3-129">**Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="b01e3-129">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="b01e3-130">De configuratieanalyzer gebruiken in het Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="b01e3-130">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="b01e3-131">Ga in het Security & Compliance Center naar **Threat management** \> **Policy** \> **Configuration analyzer**.</span><span class="sxs-lookup"><span data-stu-id="b01e3-131">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget Configuratieanalyzer op de \> pagina Bedreigingsbeheerbeleid](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="b01e3-133">De configuratieanalyzer heeft twee hoofdtabbladen:</span><span class="sxs-lookup"><span data-stu-id="b01e3-133">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="b01e3-134">**Instellingen en aanbevelingen**: u kiest Standaard of Streng en vergelijkt deze instellingen met uw bestaande beveiligingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="b01e3-134">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="b01e3-135">In de resultaten u de waarden van uw instellingen aanpassen om ze op hetzelfde niveau te brengen als Standaard of Streng.</span><span class="sxs-lookup"><span data-stu-id="b01e3-135">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="b01e3-136">**Analyse en geschiedenis van configuratiedrift:** met deze weergave u de wijzigingen bijhouden die u in uw beleid hebt aangebracht op basis van de resultaten van de configuratieanalyzer in de loop van de tijd.</span><span class="sxs-lookup"><span data-stu-id="b01e3-136">**Configuration drift analysis and history**: This view allows to track the changes that you've made to your policies based on the results of the configuration analyzer over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="b01e3-137">Tabblad Instelling en aanbevelingen in de configuratieanalyzer</span><span class="sxs-lookup"><span data-stu-id="b01e3-137">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="b01e3-138">Standaard wordt het tabblad geopend op de vergelijking met het standaardbeveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="b01e3-138">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="b01e3-139">U overschakelen naar de vergelijking van het strikt beschermingsprofiel door op **Strikte aanbevelingen weergeven**te klikken.</span><span class="sxs-lookup"><span data-stu-id="b01e3-139">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="b01e3-140">Als u terug wilt schakelen, selecteert u **Standaardaanbevelingen weergeven**.</span><span class="sxs-lookup"><span data-stu-id="b01e3-140">To switch back, select **View Standard recommendations**.</span></span>

![Weergave Instellingen en aanbevelingen in de configuratieanalyseree](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="b01e3-142">Standaard bevat de **kolom Beleidsgroep/instellingsnaam** een samengevouwen weergave van de verschillende typen beveiligingspolitie en het aantal instellingen in het beleid dat moet worden verbeterd (indien van toepassing).</span><span class="sxs-lookup"><span data-stu-id="b01e3-142">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security polices and the number of settings in those policies that need improvement (if any).</span></span> <span data-ttu-id="b01e3-143">De soorten beleid zijn:</span><span class="sxs-lookup"><span data-stu-id="b01e3-143">The types of policies are:</span></span>

- <span data-ttu-id="b01e3-144">**Anti-spam**</span><span class="sxs-lookup"><span data-stu-id="b01e3-144">**Anti-spam**</span></span>
- <span data-ttu-id="b01e3-145">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="b01e3-145">**Anti-phishing**</span></span>
- <span data-ttu-id="b01e3-146">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="b01e3-146">**Anti-malware**</span></span>
- <span data-ttu-id="b01e3-147">**ATP Safe Attachments** (als uw abonnement ATP bevat)</span><span class="sxs-lookup"><span data-stu-id="b01e3-147">**ATP Safe Attachments** (if your subscription includes ATP)</span></span>
- <span data-ttu-id="b01e3-148">**ATP Safe Links** (als uw abonnement ATP bevat)</span><span class="sxs-lookup"><span data-stu-id="b01e3-148">**ATP Safe Links** (if your subscription includes ATP)</span></span>

<span data-ttu-id="b01e3-149">In de standaardweergave is alles samengevouwen.</span><span class="sxs-lookup"><span data-stu-id="b01e3-149">In the default view, everything is collapsed.</span></span> <span data-ttu-id="b01e3-150">Naast elk beleid worden een overzicht weergegeven van de vergelijkingsresultaten van uw beleid (die u wijzigen) en de instellingen in het bijbehorende beleid voor de standaard- of strikte beveiligingsprofielen (die u niet wijzigen).</span><span class="sxs-lookup"><span data-stu-id="b01e3-150">Next to each policy, a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify) are displayed.</span></span> <span data-ttu-id="b01e3-151">U ziet de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="b01e3-151">You'll see the following information:</span></span>

- <span data-ttu-id="b01e3-152">**Groen:** Alle instellingen in alle bestaande beleidsregels zijn minstens zo veilig als het beveiligingsprofiel waarmee u het vergelijkt.</span><span class="sxs-lookup"><span data-stu-id="b01e3-152">**Green**: All settings in all existing policies are at least as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="b01e3-153">**Amber:** Een klein aantal instellingen in het bestaande beleid zijn niet zo veilig als het beveiligingsprofiel waarmee u zich ver vergeleek.</span><span class="sxs-lookup"><span data-stu-id="b01e3-153">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span>
- <span data-ttu-id="b01e3-154">**Rood:** Een aanzienlijk aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel waarmee u zich ver vergeleek.</span><span class="sxs-lookup"><span data-stu-id="b01e3-154">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile that you're comparing to.</span></span> <span data-ttu-id="b01e3-155">Dit kunnen een paar instellingen in veel beleidsregels of veel instellingen in een beleid.</span><span class="sxs-lookup"><span data-stu-id="b01e3-155">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="b01e3-156">Voor gunstige vergelijkingen ziet u de tekst: **Alle instellingen volgen** \<**Standard** or **Strict**\> **aanbevelingen.**</span><span class="sxs-lookup"><span data-stu-id="b01e3-156">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="b01e3-157">Anders ziet u het aantal aanbevolen instellingen dat moet worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="b01e3-157">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="b01e3-158">Als u **de naam van de beleidsgroep/-instelling uitbreidt,** worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid die aandacht vereisen, weergegeven.</span><span class="sxs-lookup"><span data-stu-id="b01e3-158">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="b01e3-159">U ook een specifiek type beleid (bijvoorbeeld **antispam)** uitbreiden om alleen die instellingen te zien in dat soort beleidsregels waarvoor uw aandacht vereist is.</span><span class="sxs-lookup"><span data-stu-id="b01e3-159">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="b01e3-160">Als de vergelijking geen aanbevelingen voor verbetering (groen) heeft, onthult het uitbreiden van het beleid niets.</span><span class="sxs-lookup"><span data-stu-id="b01e3-160">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="b01e3-161">Als er een aantal aanbevelingen voor verbetering (amber of rood), de instellingen die aandacht vereisen worden onthuld, en de bijbehorende informatie wordt onthuld in de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="b01e3-161">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="b01e3-162">De naam van de instelling die uw aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="b01e3-162">The name of the setting that requires your attention.</span></span> <span data-ttu-id="b01e3-163">In de vorige schermafbeelding is het bijvoorbeeld de **drempel voor bulke-mail** in een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="b01e3-163">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="b01e3-164">**Beleid**: de naam van het betreffende beleid dat de instelling bevat.</span><span class="sxs-lookup"><span data-stu-id="b01e3-164">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="b01e3-165">**Toegepast op**: Het aantal gebruikers waarop het betreffende beleid wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="b01e3-165">**Applied to**: The number of user that the affected policies are applied to.</span></span>

- <span data-ttu-id="b01e3-166">**Huidige configuratie**: de huidige waarde van de instelling.</span><span class="sxs-lookup"><span data-stu-id="b01e3-166">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="b01e3-167">**Laatst gewijzigd**: De datum waarop het beleid voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="b01e3-167">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="b01e3-168">**Aanbevelingen**: De waarde van de instelling in het standaard- of strikt beschermingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="b01e3-168">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="b01e3-169">Als u de waarde van de instelling in uw beleid wilt wijzigen die overeenkomt met de aanbevolen waarde in het beveiligingsprofiel, klikt u op **Adopteren**.</span><span class="sxs-lookup"><span data-stu-id="b01e3-169">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="b01e3-170">Als de wijziging is geslaagd, ziet u het bericht: **Aanbevelingen die zijn aangenomen.**</span><span class="sxs-lookup"><span data-stu-id="b01e3-170">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="b01e3-171">Klik **op Vernieuwen** om het verminderde aantal aanbevelingen en het verwijderen van de specifieke instellings-/beleidsrij uit de resultaten te bekijken.</span><span class="sxs-lookup"><span data-stu-id="b01e3-171">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="b01e3-172">Tabblad Configuratiedriftanalyse en geschiedenis in de configuratieanalyzer</span><span class="sxs-lookup"><span data-stu-id="b01e3-172">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="b01e3-173">Met dit tabblad u de wijzigingen bijhouden die u hebt aangebracht in uw aangepaste beveiligingsbeleid op basis van de informatie in de beveiligingsanalyseer.</span><span class="sxs-lookup"><span data-stu-id="b01e3-173">This tab allows you to track the changes that you've made to your custom security policies based on the information in the security analyzer.</span></span> <span data-ttu-id="b01e3-174">Standaard worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="b01e3-174">By default, the following information is displayed:</span></span>

- <span data-ttu-id="b01e3-175">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="b01e3-175">**Last modified**</span></span>
- <span data-ttu-id="b01e3-176">**Gewijzigd door**</span><span class="sxs-lookup"><span data-stu-id="b01e3-176">**Modified by**</span></span>
- <span data-ttu-id="b01e3-177">**Naam instellen**</span><span class="sxs-lookup"><span data-stu-id="b01e3-177">**Setting Name**</span></span>
- <span data-ttu-id="b01e3-178">**Beleid**</span><span class="sxs-lookup"><span data-stu-id="b01e3-178">**Policy**</span></span>
- <span data-ttu-id="b01e3-179">**Type**</span><span class="sxs-lookup"><span data-stu-id="b01e3-179">**Type**</span></span>

<span data-ttu-id="b01e3-180">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="b01e3-180">To filter the results, click **Filter**.</span></span> <span data-ttu-id="b01e3-181">In de flyout **Filters** die wordt weergegeven, u kiezen uit de volgende filters:</span><span class="sxs-lookup"><span data-stu-id="b01e3-181">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="b01e3-182">**Begintijd** en **eindtijd** (datum)</span><span class="sxs-lookup"><span data-stu-id="b01e3-182">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="b01e3-183">**Standaardbescherming** of **strikte bescherming**</span><span class="sxs-lookup"><span data-stu-id="b01e3-183">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="b01e3-184">Als u de resultaten wilt exporteren naar een CSV-bestand, klikt u op **Exporteren**.</span><span class="sxs-lookup"><span data-stu-id="b01e3-184">To export the results to a .csv file, click **Export**.</span></span>

![Configuratiedriftanalyse en geschiedenisweergave in de configuratieanalyzer](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
