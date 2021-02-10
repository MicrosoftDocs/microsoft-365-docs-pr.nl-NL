---
title: Configuration Analyzer voor beveiligingsbeleid
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
description: Beheerders kunnen informatie krijgen over het gebruik van configuration analyzer om beveiligingsbeleid te vinden en op te lossen dat zich onder het standaardbeveiligingsbeleid en het vooraf ingestelde beveiligingsbeleid voor strikte beveiliging vindt.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a78452cb3a7e4cb65c72d98b9322f217309a6d6f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165905"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a><span data-ttu-id="cd4f4-103">Configuration analyzer voor beveiligingsbeleid in EOP en Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cd4f4-103">Configuration analyzer for protection policies in EOP and Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="cd4f4-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-104">**Applies to**</span></span>
- [<span data-ttu-id="cd4f4-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cd4f4-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="cd4f4-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cd4f4-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="cd4f4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd4f4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="cd4f4-108">Configuratieanalyse in het beveiligings- & Compliancecentrum biedt een centrale locatie voor het zoeken en herstellen van beveiligingsbeleid waarin de instellingen onder de instellingen Standaardbeveiliging en Strikt beveiligingsprofiel in vooraf ingestelde beveiligingsbeleidsregels [staan.](preset-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-108">Configuration analyzer in the Security & Compliance center provides a central location to find and fix security policies where the settings are below the Standard protection and Strict protection profile settings in [preset security policies](preset-security-policies.md).</span></span>

<span data-ttu-id="cd4f4-109">De volgende soorten beleidsregels worden geanalyseerd met de configuration analyzer:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-109">The following types of policies are analyzed by the configuration analyzer:</span></span>

- <span data-ttu-id="cd4f4-110">**Beleidsregels voor Exchange Online Protection (EOP:** Dit geldt ook voor Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties zonder Exchange Online-postvakken:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-110">**Exchange Online Protection (EOP) policies**: This includes Microsoft 365 organizations with Exchange Online mailboxes and standalone EOP organizations without Exchange Online mailboxes:</span></span>

  - <span data-ttu-id="cd4f4-111">[Antispambeleid.](configure-your-spam-filter-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-111">[Anti-spam policies](configure-your-spam-filter-policies.md).</span></span>
  - <span data-ttu-id="cd4f4-112">[Anti-malwarebeleid.](configure-anti-malware-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-112">[Anti-malware policies](configure-anti-malware-policies.md).</span></span>
  - <span data-ttu-id="cd4f4-113">[EOP Anti-phishingbeleid.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-113">[EOP Anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="cd4f4-114">Beleid van Microsoft Defender voor **Office 365:** dit geldt ook voor organisaties met Microsoft 365 E5- of Defender voor Office 365-abonnementen voor invoegabonnementen:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-114">**Microsoft Defender for Office 365 policies**: This includes organizations with Microsoft 365 E5 or Defender for Office 365 add-on subscriptions:</span></span>

  - <span data-ttu-id="cd4f4-115">Anti-phishingbeleid in Microsoft Defender voor Office 365, waaronder:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-115">Anti-phishing policies in Microsoft Defender for Office 365, which include:</span></span>

    - <span data-ttu-id="cd4f4-116">Dezelfde [spoof-instellingen](set-up-anti-phishing-policies.md#spoof-settings) die beschikbaar zijn in het anti-phishingbeleid van EOP.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-116">The same [spoof settings](set-up-anti-phishing-policies.md#spoof-settings) that are available in the EOP anti-phishing policies.</span></span>
    - [<span data-ttu-id="cd4f4-117">Imitatie-instellingen</span><span class="sxs-lookup"><span data-stu-id="cd4f4-117">Impersonation settings</span></span>](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [<span data-ttu-id="cd4f4-118">Geavanceerde drempelwaarden voor phishing</span><span class="sxs-lookup"><span data-stu-id="cd4f4-118">Advanced phishing thresholds</span></span>](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - <span data-ttu-id="cd4f4-119">[Beleid voor veilige koppelingen.](set-up-atp-safe-links-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-119">[Safe Links policies](set-up-atp-safe-links-policies.md).</span></span>

  - <span data-ttu-id="cd4f4-120">[Beleid voor veilige bijlagen.](set-up-atp-safe-attachments-policies.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-120">[Safe Attachments policies](set-up-atp-safe-attachments-policies.md).</span></span>

<span data-ttu-id="cd4f4-121">De  waarden **voor** de beleidsinstelling Standaard en Strikt die als basislijnen worden gebruikt, worden beschreven in aanbevolen instellingen voor de beveiliging van EOP en Microsoft Defender voor [Office 365.](recommended-settings-for-eop-and-office365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-121">The **Standard** and **Strict** policy setting values that are used as baselines are described in [Recommended settings for EOP and Microsoft Defender for Office 365 security](recommended-settings-for-eop-and-office365-atp.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="cd4f4-122">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="cd4f4-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="cd4f4-123">U opent het beveiligings- en compliancecentrum in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-123">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="cd4f4-124">Als u rechtstreeks naar de **pagina Configuration analyzer wilt** gaan, gebruikt u <https://protection.office.com/configurationAnalyzer> .</span><span class="sxs-lookup"><span data-stu-id="cd4f4-124">To go directly to the **Configuration analyzer** page, use <https://protection.office.com/configurationAnalyzer>.</span></span>

- <span data-ttu-id="cd4f4-125">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="cd4f4-126">Je moet beschikken over toegewezen machtigingen voor het uitvoeren van de procedures in dit onderwerp:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-126">You need to be assigned permissions in the Security & Compliance Center before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="cd4f4-127">Als u de configuration **analyzer** wilt gebruiken en beveiligingsbeleid wilt verbeteren, moet u lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-127">To use the configuration analyzer **and** make updates to security policies, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="cd4f4-128">Voor alleen-lezen toegang tot de configuration analyzer moet  u lid zijn van de rollengroepen Globale lezer of **Beveiligingslezer.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-128">For read-only access to the configuration analyzer, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="cd4f4-129">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-129">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

  > [!NOTE]
  >  
  > - <span data-ttu-id="cd4f4-130">Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-130">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions in the Security & Compliance Center _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="cd4f4-131">Zie[Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-131">For more information, see [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>
  > 
  > - <span data-ttu-id="cd4f4-132">De functiegroep **Alleen-lezen organisatiebeheer** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) geeft ook alleen-lezentoegang tot deze functie.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-132">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a><span data-ttu-id="cd4f4-133">De configuration analyzer gebruiken in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="cd4f4-133">Use the configuration analyzer in the Security & Compliance Center</span></span>

<span data-ttu-id="cd4f4-134">Ga in het & Compliancecentrum naar **Threat Management** \> **Policy** Configuration \> **analyzer.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Configuration analyzer**.</span></span>

![Widget Configuration analyzer op de pagina \> Risicobeheerbeleid](../../media/configuration-analyzer-widget.png)

<span data-ttu-id="cd4f4-136">De configuration analyzer heeft twee hoofdtabbladen:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-136">The configuration analyzer has two main tabs:</span></span>

- <span data-ttu-id="cd4f4-137">**Instellingen en aanbevelingen: u** kiest Standaard of Strikt en vergelijkt deze instellingen met uw bestaande beveiligingsbeleid.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-137">**Settings and recommendations**: You pick Standard or Strict and compare those settings to your existing security policies.</span></span> <span data-ttu-id="cd4f4-138">In de resultaten kunt u de waarden van uw instellingen aanpassen om ze naar hetzelfde niveau als Standaard of Strikt te brengen.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-138">In the results, you can adjust the values of your settings to bring them up to the same level as Standard or Strict.</span></span>

- <span data-ttu-id="cd4f4-139">**Configuratieanalyse en geschiedenis:** in deze weergave kunt u beleidswijzigingen in de tijd bijhouden.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-139">**Configuration drift analysis and history**: This view allows you to track policy changes over time.</span></span>

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a><span data-ttu-id="cd4f4-140">Tabblad Instellingen en aanbevelingen in de configuration analyzer</span><span class="sxs-lookup"><span data-stu-id="cd4f4-140">Setting and recommendations tab in the configuration analyzer</span></span>

<span data-ttu-id="cd4f4-141">Standaard wordt het tabblad geopend in de vergelijking met het standaardbeveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-141">By default, the tab opens on the comparison to the Standard protection profile.</span></span> <span data-ttu-id="cd4f4-142">U kunt overschakelen naar de vergelijking van het profiel Voor strikte beveiliging door te klikken op **Strikte aanbevelingen weergeven.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-142">You can switch to the comparison of the Strict protection profile by clicking **View Strict recommendations**.</span></span> <span data-ttu-id="cd4f4-143">Als u wilt teruggaan, **selecteert u Standaardaanbevelingen weergeven.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-143">To switch back, select **View Standard recommendations**.</span></span>

![Weergave Instellingen en aanbevelingen in Configuration analyzer](../../media/configuration-analyzer-settings-and-recommendations-view.png)

<span data-ttu-id="cd4f4-145">Standaard bevat de kolom Beleid **groep/instellingsnaam** een samengevouwen weergave van de verschillende typen beveiligingsbeleidsregels en het aantal instellingen dat moet worden verbeterd (indien van beide).</span><span class="sxs-lookup"><span data-stu-id="cd4f4-145">By default, the **Policy group/setting name** column contains a collapsed view of the different types of security policies and the number of settings that need improvement (if any).</span></span> <span data-ttu-id="cd4f4-146">De soorten beleidsregels zijn:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-146">The types of policies are:</span></span>

- <span data-ttu-id="cd4f4-147">**Antispam**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-147">**Anti-spam**</span></span>
- <span data-ttu-id="cd4f4-148">**Anti-phishing**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-148">**Anti-phishing**</span></span>
- <span data-ttu-id="cd4f4-149">**Anti-malware**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-149">**Anti-malware**</span></span>
- <span data-ttu-id="cd4f4-150">**Veilige bijlagen met ATP** (als Uw abonnement Microsoft Defender voor Office 365 omvat)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-150">**ATP Safe Attachments** (if your subscription includes Microsoft Defender for Office 365)</span></span>
- <span data-ttu-id="cd4f4-151">**Veilige koppelingen met ATP** (als Uw abonnement Microsoft Defender voor Office 365 omvat)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-151">**ATP Safe Links** (if your subscription includes Microsoft Defender for Office 365)</span></span>

<span data-ttu-id="cd4f4-152">In de standaardweergave is alles samengevouwen.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-152">In the default view, everything is collapsed.</span></span> <span data-ttu-id="cd4f4-153">Naast elk beleid ziet u een overzicht van de vergelijkingsresultaten van uw beleid (dat u kunt wijzigen) en de instellingen in het bijbehorende beleid voor de standaard- of strikte beveiligingsprofielen (die u niet kunt wijzigen).</span><span class="sxs-lookup"><span data-stu-id="cd4f4-153">Next to each policy, there's a summary of comparison results from your policies (which you can modify) and the settings in the corresponding policies for the Standard or Strict protection profiles (which you can't modify).</span></span> <span data-ttu-id="cd4f4-154">U ziet de volgende informatie voor het beveiligingsprofiel dat u wilt vergelijken met:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-154">You'll see the following information for the protection profile that you're comparing to:</span></span>

- <span data-ttu-id="cd4f4-155">**Groen:** alle instellingen in alle bestaande beleidsregels zijn ten minste even veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-155">**Green**: All settings in all existing policies are at least as secure as the protection profile.</span></span>
- <span data-ttu-id="cd4f4-156">**Oranje:** een klein aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-156">**Amber**: A small number of settings in the existing policies are not as secure as the protection profile.</span></span>
- <span data-ttu-id="cd4f4-157">**Rood:** een aanzienlijk aantal instellingen in het bestaande beleid is niet zo veilig als het beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-157">**Red**: A significant number of settings in the existing policies are not as secure as the protection profile.</span></span> <span data-ttu-id="cd4f4-158">Dit kunnen enkele instellingen in veel beleidsregels of veel instellingen in één beleid zijn.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-158">This could be a few settings in many policies or many settings in one policy.</span></span>

<span data-ttu-id="cd4f4-159">Voor vergelijkingen ziet u de tekst: **Alle instellingen volgen** \<**Standard** or **Strict**\> **aanbevelingen.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-159">For favorable comparisons, you'll see the text: **All settings follow** \<**Standard** or **Strict**\> **recommendations**.</span></span> <span data-ttu-id="cd4f4-160">Anders ziet u het aantal aanbevolen instellingen dat u kunt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-160">Otherwise, you'll see the number of recommended settings to change.</span></span>

<span data-ttu-id="cd4f4-161">Als u de naam **van de beleidsgroep/instelling** uitbreidt, worden alle beleidsregels en de bijbehorende instellingen in elk specifiek beleid die aandacht nodig hebben, bekend.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-161">If you expand **Policy group/setting name**, all of the policies and the associated settings in each specific policy that require attention are revealed.</span></span> <span data-ttu-id="cd4f4-162">Of u kunt een specifiek type beleid (bijvoorbeeld **antispambeleid)** uitbreiden om alleen die instellingen te zien in die soorten beleidsregels die uw aandacht vereisen.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-162">Or, you can expand a specific type of policy (for example, **Anti-spam**) to see just those settings in those types of policies that require your attention.</span></span>

<span data-ttu-id="cd4f4-163">Als de vergelijking geen aanbevelingen voor verbetering (groen) heeft, wordt er niets gevonden als u het beleid uitbreidt.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-163">If the comparison has no recommendations for improvement (green), expanding the policy reveals nothing.</span></span> <span data-ttu-id="cd4f4-164">Als er een aantal aanbevelingen voor verbetering (oranje of rood) is, worden de instellingen die aandacht nodig hebben, bekend en corresponderende informatie in de volgende kolommen:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-164">If there are any number of recommendations for improvement (amber or red), the settings that require attention are revealed, and corresponding information is revealed in the following columns:</span></span>

- <span data-ttu-id="cd4f4-165">De naam van de instelling die uw aandacht vereist.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-165">The name of the setting that requires your attention.</span></span> <span data-ttu-id="cd4f4-166">In de vorige schermafbeelding is dit bijvoorbeeld de drempelwaarde voor bulkmail **in** een antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-166">For example, in the previous screenshot, it's the **Bulk email threshold** in an anti-spam policy.</span></span>

- <span data-ttu-id="cd4f4-167">**Beleid:** de naam van het betreffende beleid dat de instelling bevat.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-167">**Policy**: The name of the affected policy that contains the setting.</span></span>

- <span data-ttu-id="cd4f4-168">**Toegepast op:** het aantal gebruikers op hoeveel van de betreffende beleidsregels wordt toegepast.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-168">**Applied to**: The number of users that the affected policies are applied to.</span></span>

- <span data-ttu-id="cd4f4-169">**Huidige configuratie:** de huidige waarde van de instelling.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-169">**Current configuration**: The current value of the setting.</span></span>

- <span data-ttu-id="cd4f4-170">**Laatst gewijzigd:** de datum waarop het beleid voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-170">**Last modified**: The date that the policy was last modified.</span></span>

- <span data-ttu-id="cd4f4-171">**Aanbevelingen:** de waarde van de instelling in het standaard- of strikt beveiligingsprofiel.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-171">**Recommendations**: The value of the setting in the Standard or Strict protection profile.</span></span> <span data-ttu-id="cd4f4-172">Als u de waarde van de instelling in uw beleid wilt wijzigen om deze overeen te laten komen met de aanbevolen waarde in het beveiligingsprofiel, klikt u op **Goedkeuren.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-172">To change the value of the setting in your policy to match the recommended value in the protection profile, click **Adopt**.</span></span> <span data-ttu-id="cd4f4-173">Als de wijziging is geslaagd, ziet u het bericht: **Aanbevelingen zijn aangenomen.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-173">If the change is successful, you'll see the message: **Recommendations successfully adopted**.</span></span> <span data-ttu-id="cd4f4-174">Klik **op** Vernieuwen om het beperkte aantal aanbevelingen en het verwijderen van de specifieke instelling/beleidsrij uit de resultaten te zien.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-174">Click **Refresh** to see the reduced number of recommendations, and the removal of the specific setting/policy row from the results.</span></span>

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a><span data-ttu-id="cd4f4-175">Het tabblad Configuratieanalyse en Geschiedenis in de configuration analyzer</span><span class="sxs-lookup"><span data-stu-id="cd4f4-175">Configuration drift analysis and history tab in the configuration analyzer</span></span>

<span data-ttu-id="cd4f4-176">Op dit tabblad kunt u de wijzigingen bijhouden die u in uw aangepaste beveiligingsbeleid hebt aangebracht.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-176">This tab allows you to track the changes that you've made to your custom security policies.</span></span> <span data-ttu-id="cd4f4-177">Standaard wordt de volgende informatie weergegeven:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-177">By default, the following information is displayed:</span></span>

- <span data-ttu-id="cd4f4-178">**Laatst gewijzigd**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-178">**Last modified**</span></span>
- <span data-ttu-id="cd4f4-179">**Gewijzigd door**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-179">**Modified by**</span></span>
- <span data-ttu-id="cd4f4-180">**Naam van instelling**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-180">**Setting Name**</span></span>
- <span data-ttu-id="cd4f4-181">**Beleid**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-181">**Policy**</span></span>
- <span data-ttu-id="cd4f4-182">**Type**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-182">**Type**</span></span>

<span data-ttu-id="cd4f4-183">Klik op **Filter** om de resultaten te filteren.</span><span class="sxs-lookup"><span data-stu-id="cd4f4-183">To filter the results, click **Filter**.</span></span> <span data-ttu-id="cd4f4-184">In de **flyout** Filters die wordt weergegeven, kunt u een van de volgende filters selecteren:</span><span class="sxs-lookup"><span data-stu-id="cd4f4-184">In the **Filters** flyout that appears, you can select from the following filters:</span></span>

- <span data-ttu-id="cd4f4-185">**Begintijd** en **eindtijd** (datum)</span><span class="sxs-lookup"><span data-stu-id="cd4f4-185">**Start time** and **End time** (date)</span></span>
- <span data-ttu-id="cd4f4-186">**Standaardbeveiliging** of **strikte beveiliging**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-186">**Standard protection** or **Strict protection**</span></span>

<span data-ttu-id="cd4f4-187">Als u de resultaten naar een CSV-bestand wilt exporteren, klikt u op **Exporteren.**</span><span class="sxs-lookup"><span data-stu-id="cd4f4-187">To export the results to a .csv file, click **Export**.</span></span>

![Configuratieanalyse en geschiedenisweergave in Configuration Analyzer](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
