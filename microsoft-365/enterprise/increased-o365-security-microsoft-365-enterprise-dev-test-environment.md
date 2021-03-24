---
title: Verbeterde microsoft 365-beveiliging voor uw Microsoft 365 voor ondernemingstestomgeving
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
description: Gebruik deze testlaboratoriumhandleiding om aanvullende beveiligingsinstellingen van Microsoft 365 in te stellen voor uw Microsoft 365 voor ondernemingstestomgeving.
ms.openlocfilehash: 186452396af4227a94a7f6cd0fa0109e9d6a7e17
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051268"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1da74-103">Verbeterde microsoft 365-beveiliging voor uw Microsoft 365 voor ondernemingstestomgeving</span><span class="sxs-lookup"><span data-stu-id="1da74-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1da74-104">*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*</span><span class="sxs-lookup"><span data-stu-id="1da74-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="1da74-105">Met de instructies in dit artikel configureert u aanvullende Microsoft 365-instellingen om de beveiliging in uw Microsoft 365 voor ondernemingstestomgeving te verhogen.</span><span class="sxs-lookup"><span data-stu-id="1da74-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1da74-107">Klik op [Hier](../downloads/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="1da74-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="1da74-108">Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen</span><span class="sxs-lookup"><span data-stu-id="1da74-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="1da74-109">Als u alleen de beveiliging van Microsoft 365 op een lichtgewicht manier wilt configureren met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="1da74-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1da74-110">Als u de beveiliging van Microsoft 365 in een gesimuleerde onderneming wilt verbeteren, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="1da74-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1da74-111">Voor het testen van de verbeterde beveiliging van Microsoft 365 is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="1da74-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="1da74-112">Het wordt hier als optie aangeboden, zodat u geautomatiseerde licenties en groepslidmaatschap kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="1da74-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="1da74-113">Fase 2: Verbeterde beveiliging van Microsoft 365 configureren</span><span class="sxs-lookup"><span data-stu-id="1da74-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="1da74-114">In deze fase kunt u de beveiliging van Microsoft 365 voor uw Microsoft 365-testomgeving voor ondernemingen verbeteren.</span><span class="sxs-lookup"><span data-stu-id="1da74-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="1da74-115">Zie Uw tenant configureren voor meer beveiliging voor [meer informatie en instellingen.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)</span><span class="sxs-lookup"><span data-stu-id="1da74-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="1da74-116">SharePoint Online configureren om apps te blokkeren die geen moderne verificatie ondersteunen</span><span class="sxs-lookup"><span data-stu-id="1da74-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="1da74-117">Apps die geen ondersteuning bieden voor moderne verificatie, kunnen niet worden toegepast op [identiteits- en apparaattoegangsconfiguraties.](../security/defender-365-security/microsoft-365-policies-configurations.md) Dit is een belangrijk onderdeel van het beveiligen van uw Microsoft 365-abonnement en de digitale assets.</span><span class="sxs-lookup"><span data-stu-id="1da74-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="1da74-118">Ga naar het Microsoft 365-beheercentrum () en meld u aan bij uw Test lab-abonnement van [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="1da74-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="1da74-119">Als u de lichtgewicht Microsoft 365-testomgeving gebruikt, meld u dan aan vanaf uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="1da74-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="1da74-120">Als u de gesimuleerde microsoft 365-testomgeving voor ondernemingen gebruikt, gebruikt u de [Azure-portal](https://portal.azure.com) om verbinding te maken met de virtuele client1-machine en u vervolgens aan te melden vanaf CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="1da74-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="1da74-121">Klik op het nieuwe **tabblad Microsoft 365-beheercentrum** onder **Beheercentra** in het linkernavigatiedeelvenster op **SharePoint.**</span><span class="sxs-lookup"><span data-stu-id="1da74-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="1da74-122">Klik op het nieuwe **tabblad SharePoint-beheercentrum** op **Beleid > Access-besturingselement.**</span><span class="sxs-lookup"><span data-stu-id="1da74-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="1da74-123">Klik **op Apps die geen moderne verificatie ondersteunen,** selecteer Toegang **blokkeren** en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="1da74-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="1da74-124">Defender inschakelen voor Office 365 voor SharePoint, OneDrive voor Bedrijven en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1da74-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="1da74-125">Defender voor Office 365 voor SharePoint, OneDrive en Microsoft Teams beschermt uw organisatie tegen onbedoeld delen van schadelijke bestanden.</span><span class="sxs-lookup"><span data-stu-id="1da74-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="1da74-126">Ga naar het [Beveiligingscentrum & compliancecentrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="1da74-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="1da74-127">Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** op **Beleid** en klik vervolgens **op Veilige bijlagen.**</span><span class="sxs-lookup"><span data-stu-id="1da74-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="1da74-128">Onder **Bestanden beveiligen in SharePoint, OneDrive en Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="1da74-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="1da74-129">selecteer **ATP voor SharePoint, OneDrive en Microsoft Teams in- en uit.**</span><span class="sxs-lookup"><span data-stu-id="1da74-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="1da74-130">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="1da74-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="1da74-131">Anti-malware inschakelen</span><span class="sxs-lookup"><span data-stu-id="1da74-131">Enable anti-malware</span></span>

<span data-ttu-id="1da74-132">Malware bestaat uit virussen en spyware.</span><span class="sxs-lookup"><span data-stu-id="1da74-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="1da74-133">Virussen besmetten andere programma's en gegevens en verspreiden zich op uw computer op zoek naar programma's om te infecteren.</span><span class="sxs-lookup"><span data-stu-id="1da74-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="1da74-134">Spyware verwijst naar malware die uw persoonlijke gegevens verzamelt, zoals aanmeldingsgegevens en persoonlijke gegevens, en stuurt deze terug naar de malwareauteur.</span><span class="sxs-lookup"><span data-stu-id="1da74-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="1da74-135">Microsoft 365 beschikt over ingebouwde mogelijkheden voor malware en spamfilters die binnenkomende en uitgaande berichten helpen beschermen tegen schadelijke software en u helpen beschermen tegen spam.</span><span class="sxs-lookup"><span data-stu-id="1da74-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="1da74-136">Zie [Anti-spam & anti-malwarebeveiliging](../security/defender-365-security/anti-spam-and-anti-malware-protection.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="1da74-136">For more information, see [Anti-spam & anti-malware protection](../security/defender-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="1da74-137">Als u ervoor wilt zorgen dat anti-malwareverwerking wordt uitgevoerd op bestanden met veelgebruikte bestandstypen voor bijlagen:</span><span class="sxs-lookup"><span data-stu-id="1da74-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="1da74-138">Klik op de knop Terug in uw browser om terug te gaan naar de **pagina Beleid.**</span><span class="sxs-lookup"><span data-stu-id="1da74-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="1da74-139">Klik **op Anti-malware.**</span><span class="sxs-lookup"><span data-stu-id="1da74-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="1da74-140">Dubbelklik op het beleid met de naam **Standaard.**</span><span class="sxs-lookup"><span data-stu-id="1da74-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="1da74-141">Klik in **het venster Anti-malwarebeleid** op **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="1da74-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="1da74-142">Selecteer **onder Gemeenschappelijke bijlagetypen de** optie **Aan** en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="1da74-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="1da74-143">Fase 3: Het beveiligingsdashboard bekijken</span><span class="sxs-lookup"><span data-stu-id="1da74-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="1da74-144">Bedreigingsbeheer in Microsoft 365 kan u helpen de toegang van mobiele apparaten tot de gegevens van uw organisatie te beheren en beheren, uw organisatie te beschermen tegen gegevensverlies en binnenkomende en uitgaande berichten te beschermen tegen schadelijke software en spam.</span><span class="sxs-lookup"><span data-stu-id="1da74-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="1da74-145">U gebruikt bedreigingsbeheer ook om de reputatie van uw domein te beschermen en om te bepalen of afzenders accounts van uw domein al dan niet met kwaadwillende bedoelingen vervalsen.</span><span class="sxs-lookup"><span data-stu-id="1da74-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="1da74-146">Het beveiligingsdashboard bekijken:</span><span class="sxs-lookup"><span data-stu-id="1da74-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="1da74-147">Ga indien nodig naar het [Beveiligingscentrum & compliancecentrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="1da74-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="1da74-148">Klik in het linkernavigatiedeelvenster onder **Bedreigingsbeheer** op **Dashboard.**</span><span class="sxs-lookup"><span data-stu-id="1da74-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="1da74-149">Bekijk alle kaarten op het dashboard om vertrouwd te raken met de verstrekte informatie.</span><span class="sxs-lookup"><span data-stu-id="1da74-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="1da74-150">Zie Beveiligingsdashboard [voor meer informatie.](../security/defender-365-security/security-dashboard.md)</span><span class="sxs-lookup"><span data-stu-id="1da74-150">For more information, see [Security Dashboard](../security/defender-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="1da74-151">Fase 4: Microsoft Secure Score onderzoeken</span><span class="sxs-lookup"><span data-stu-id="1da74-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="1da74-152">Microsoft Secure Score toont uw beveiligingsstatus als een getal, wat uw huidige niveau aangeeft ten opzichte van de functies die beschikbaar zijn in uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="1da74-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="1da74-153">U krijgt ook een lijst met verbeteracties die u kunt uitvoeren om uw score te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="1da74-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="1da74-154">Maak een nieuw tabblad in uw browser en ga naar het [Microsoft 365-beveiligingscentrum](https://security.microsoft.com/)en klik vervolgens op **Score beveiligen.**</span><span class="sxs-lookup"><span data-stu-id="1da74-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="1da74-155">Noteer **op het**  tabblad Overzicht uw huidige Secure Score en hoe deze zich verhoudt tot het globale gemiddelde en abonnementen met een vergelijkbaar aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="1da74-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="1da74-156">Lees op **het tabblad** Acties voor verbetering de lijst met acties die u kunt uitvoeren om uw score te verhogen.</span><span class="sxs-lookup"><span data-stu-id="1da74-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="1da74-157">Zie Microsoft Secure Score voor [meer informatie.](../security/defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="1da74-157">For more information, see [Microsoft Secure Score](../security/defender/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1da74-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="1da74-158">Next steps</span></span>

<span data-ttu-id="1da74-159">Ontdek extra [functies en](m365-enterprise-test-lab-guides.md#information-protection) mogelijkheden voor informatiebeveiliging in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="1da74-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1da74-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1da74-160">See also</span></span>

[<span data-ttu-id="1da74-161">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="1da74-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1da74-162">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="1da74-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="1da74-163">Microsoft 365 enterprise-documentatie</span><span class="sxs-lookup"><span data-stu-id="1da74-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)