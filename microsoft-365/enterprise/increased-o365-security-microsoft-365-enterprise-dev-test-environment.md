---
title: Verbeterde Microsoft 365-beveiliging voor uw Microsoft 365 Enterprise-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Gebruik deze Test Lab-handleiding om extra Microsoft 365-beveiligingsinstellingen in te schakelen in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: 53205f0626ce55c5a9627339f3631964e3374a19
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631667"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2b1f7-103">Verbeterde Microsoft 365-beveiliging voor uw Microsoft 365 Enterprise-testomgeving</span><span class="sxs-lookup"><span data-stu-id="2b1f7-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2b1f7-104">*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*</span><span class="sxs-lookup"><span data-stu-id="2b1f7-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="2b1f7-105">Met de instructies in dit artikel configureert u extra Microsoft 365-instellingen om de beveiliging in uw Microsoft 365 Enterprise-testomgeving te verhogen.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2b1f7-107">Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2b1f7-108">Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen</span><span class="sxs-lookup"><span data-stu-id="2b1f7-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2b1f7-109">Als u alleen de verbeterde Microsoft 365-beveiliging op een lichtgewicht manier wilt configureren met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="2b1f7-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2b1f7-110">Als u de verbeterde Microsoft 365-beveiliging in een gesimuleerde onderneming wilt configureren, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="2b1f7-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b1f7-111">Testen verhoogde Microsoft 365-beveiliging vereist geen gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met internet en directorysynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="2b1f7-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="2b1f7-112">Het wordt hier als optie verstrekt, zodat u geautomatiseerde licenties en groepslidmaatschap testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="2b1f7-113">Fase 2: Verbeterde Microsoft 365-beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="2b1f7-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="2b1f7-114">In deze fase schakelt u meer Microsoft 365-beveiliging in voor uw Microsoft 365 Enterprise-testomgeving.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="2b1f7-115">Zie [Uw tenant configureren voor meer beveiliging voor](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)meer informatie en instellingen.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="2b1f7-116">SharePoint Online configureren om apps te blokkeren die geen moderne verificatie ondersteunen</span><span class="sxs-lookup"><span data-stu-id="2b1f7-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="2b1f7-117">Apps die geen moderne verificatie ondersteunen, kunnen geen [identiteits- en apparaattoegangsconfiguraties](microsoft-365-policies-configurations.md) op deze apps toepassen, wat een belangrijk element is van het beveiligen van uw Microsoft 365-abonnement en de digitale elementen ervan.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="2b1f7-118">Ga naar het Microsoft 365-beheercentrum ( )[https://portal.microsoft.com](https://portal.microsoft.com)en meld u aan bij uw Microsoft 365-testlababonnement met uw wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="2b1f7-119">Als u de lichtgewicht Microsoft 365-testomgeving gebruikt, meldt u zich aan vanaf uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="2b1f7-120">Als u de gesimuleerde Microsoft 365-testomgeving voor ondernemingen gebruikt, gebruikt u de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele client1-machine en meldt u zich aan vanuit CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="2b1f7-121">Klik op het nieuwe tabblad **Microsoft 365-beheercentrum** onder **Beheercentra** in het linkernavigatiedeelvenster op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="2b1f7-122">Klik op het nieuwe tabblad **SharePoint-beheercentrum** op **Beleid > Toegangsbeheer**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="2b1f7-123">Klik op **Apps die geen moderne verificatie ondersteunen,** selecteer Toegang **blokkeren**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="2b1f7-124">Geavanceerde bescherming tegen bedreigingen inschakelen voor SharePoint, OneDrive voor Bedrijven en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b1f7-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="2b1f7-125">Office 365 Advanced Threat Protection (ATP) voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen het per ongeluk delen van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="2b1f7-126">Ga naar het [Security & Compliance Center](https://protection.office.com) en meld u aan met uw wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="2b1f7-127">Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**op **Beleid**en klik vervolgens op **VEILIGE BIJLAGEN van ATP**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="2b1f7-128">Onder **Bestanden beveiligen in SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="2b1f7-129">selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="2b1f7-130">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="2b1f7-131">Anti-malware inschakelen</span><span class="sxs-lookup"><span data-stu-id="2b1f7-131">Enable anti-malware</span></span>

<span data-ttu-id="2b1f7-132">Malware bestaat uit virussen en spyware.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="2b1f7-133">Virussen infecteren andere programma's en gegevens, en ze verspreiden zich over uw computer op zoek naar programma's te infecteren.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="2b1f7-134">Spyware verwijst naar malware die uw persoonlijke gegevens verzamelt, zoals aanmeldingsgegevens en persoonlijke gegevens, en stuurt deze terug naar de malwareauteur.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="2b1f7-135">Microsoft 365 heeft ingebouwde malware- en spamfiltermogelijkheden die binnenkomende en uitgaande berichten beschermen tegen schadelijke software en u helpen beschermen tegen spam.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="2b1f7-136">Zie [Anti-spam & bescherming tegen malware in Office 365 voor](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection) meer informatie</span><span class="sxs-lookup"><span data-stu-id="2b1f7-136">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="2b1f7-137">Ga als verkenner om ervoor te zorgen dat de verwerking tegen malware wordt uitgevoerd op bestanden met algemene bestandstypen voor bijlagen:</span><span class="sxs-lookup"><span data-stu-id="2b1f7-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="2b1f7-138">Klik op de knop Vorige in uw browser om terug te gaan naar de **pagina Beleid.**</span><span class="sxs-lookup"><span data-stu-id="2b1f7-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="2b1f7-139">Klik **op Anti-malware**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="2b1f7-140">Dubbelklik op het beleid met de naam **Standaard**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="2b1f7-141">Klik in het **beleidsvenster Anti-malware** op **Instellingen**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="2b1f7-142">Selecteer onder **het filter Algemene bijlagetypen**de optie **Aan**en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="2b1f7-143">Fase 3: Het beveiligingsdashboard onderzoeken</span><span class="sxs-lookup"><span data-stu-id="2b1f7-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="2b1f7-144">Met Office 365-bedreigingsbeheer u de toegang van mobiele apparaten tot de gegevens van uw organisatie beheren en beheren, uw organisatie beschermen tegen gegevensverlies en inkomende en uitgaande berichten helpen beschermen tegen schadelijke software en spam.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-144">Office 365 threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="2b1f7-145">U gebruikt ook bedreigingsbeheer om de reputatie van uw domein te beschermen en om te bepalen of afzenders kwaadwillig accounts uit uw domein spoofen.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="2b1f7-146">Ga als u op het beveiligingsdashboard:</span><span class="sxs-lookup"><span data-stu-id="2b1f7-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="2b1f7-147">Ga indien nodig naar het [Security & Compliance Center](https://protection.office.com) en meld u aan met uw wereldwijde beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="2b1f7-148">Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer**op **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="2b1f7-149">Neem een kijkje op alle kaarten op het dashboard om vertrouwd te raken met de verstrekte informatie.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="2b1f7-150">Zie [Beveiligingsdashboard voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="2b1f7-151">Fase 4: Microsoft Secure Score onderzoeken</span><span class="sxs-lookup"><span data-stu-id="2b1f7-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="2b1f7-152">Microsoft Secure Score toont uw beveiligingshouding als een getal, wat aangeeft dat uw huidige niveau ten opzichte van de functies die beschikbaar zijn in uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="2b1f7-153">Het geeft je ook een lijst met verbeteracties die je ondernemen om je score te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="2b1f7-154">Maak een nieuw tabblad in uw browser en ga naar het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/)en klik vervolgens op **Beveiligde score**.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="2b1f7-155">Noteer op het tabblad **Overzicht** uw huidige beveiligde score en hoe deze zich verhoudt tot het globale gemiddelde en abonnementen met een vergelijkbaar aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="2b1f7-156">Lees op het tabblad **Verbeteringsacties** de lijst met acties die u uitvoeren om uw score te verhogen.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="2b1f7-157">Zie [Microsoft Secure Score voor](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="2b1f7-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="2b1f7-158">Next steps</span></span>

<span data-ttu-id="2b1f7-159">Zie de stap [Verbeterde beveiliging configureren voor Microsoft 365](infoprotect-configure-increased-security-office-365.md) in de fase **Informatiebeveiliging** voor informatie en koppelingen om deze instellingen in productie te configureren.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-159">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="2b1f7-160">Ontdek aanvullende functies en mogelijkheden voor [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="2b1f7-160">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b1f7-161">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2b1f7-161">See also</span></span>

[<span data-ttu-id="2b1f7-162">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="2b1f7-162">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2b1f7-163">Microsoft 365 Enterprise implementeren</span><span class="sxs-lookup"><span data-stu-id="2b1f7-163">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2b1f7-164">Microsoft 365 Enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="2b1f7-164">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
