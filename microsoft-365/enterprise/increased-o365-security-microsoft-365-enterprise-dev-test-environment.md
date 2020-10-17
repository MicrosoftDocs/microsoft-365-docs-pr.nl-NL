---
title: Verbeterde Microsoft 365-beveiliging voor uw Microsoft 365 voor Enterprise testomgeving
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
description: Gebruik deze test lab-handleiding voor het inschakelen van extra Microsoft 365-beveiligingsinstellingen voor uw Microsoft 365 voor Enterprise test omgeving.
ms.openlocfilehash: 7c3300111f5999714b87a176087207a1651cdcaf
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487398"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="31d68-103">Verbeterde Microsoft 365-beveiliging voor uw Microsoft 365 voor Enterprise testomgeving</span><span class="sxs-lookup"><span data-stu-id="31d68-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="31d68-104">*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*</span><span class="sxs-lookup"><span data-stu-id="31d68-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="31d68-105">Aan de hand van de instructies in dit artikel configureert u aanvullende instellingen voor Microsoft 365 om de beveiliging in uw Microsoft 365 voor Enterprise testomgeving te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="31d68-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="31d68-107">Klik op [Hier](../downloads/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.</span><span class="sxs-lookup"><span data-stu-id="31d68-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="31d68-108">Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken</span><span class="sxs-lookup"><span data-stu-id="31d68-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="31d68-109">Als u de beveiliging voor Microsoft 365 slechts op een lichte manier met de minimumvereisten wilt configureren, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="31d68-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="31d68-110">Als u een verbeterde Microsoft 365-beveiliging in een gesimuleerde onderneming wilt configureren, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="31d68-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="31d68-111">Voor het testen van de beveiliging van Microsoft 365 is de gesimuleerde Enterprise-testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest.</span><span class="sxs-lookup"><span data-stu-id="31d68-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="31d68-112">U kunt dit hier opgeven als optie, zodat u geautomatiseerde licenties en groepslidmaatschappen kunt testen en experimenteert in een omgeving die een typische organisatie voorstelt.</span><span class="sxs-lookup"><span data-stu-id="31d68-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="31d68-113">Fase 2: verbeterde Microsoft 365-beveiliging configureren</span><span class="sxs-lookup"><span data-stu-id="31d68-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="31d68-114">In deze fase schakelt u de verbeterde Microsoft 365-beveiliging in voor uw Microsoft 365 voor Enterprise testomgeving.</span><span class="sxs-lookup"><span data-stu-id="31d68-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="31d68-115">Zie voor meer informatie en instellingen [uw Tenant configureren voor een betere beveiliging](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span><span class="sxs-lookup"><span data-stu-id="31d68-115">For additional details and settings, see [Configure your tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="31d68-116">SharePoint Online configureren voor het blokkeren van apps die moderne verificatie niet ondersteunen</span><span class="sxs-lookup"><span data-stu-id="31d68-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="31d68-117">Voor apps waarvoor geen ondersteuning biedt voor moderne verificatie, gelden geen [identiteits-en Apparaattoegang-configuraties](../security/office-365-security/microsoft-365-policies-configurations.md) , wat een belangrijk element is van het beveiligen van uw microsoft 365-abonnement en de bijbehorende digitale activa.</span><span class="sxs-lookup"><span data-stu-id="31d68-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="31d68-118">Ga naar het Microsoft 365-Beheercentrum ( [https://portal.microsoft.com](https://portal.microsoft.com) ) en meld u aan bij uw Microsoft 365-test abonnement met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="31d68-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="31d68-119">Als u de testomgeving lichtgewicht Microsoft 365 gebruikt, meldt u zich aan bij uw lokale computer.</span><span class="sxs-lookup"><span data-stu-id="31d68-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="31d68-120">Als u de gesimuleerde Enterprise Microsoft 365 testomgeving gebruikt, kunt u de [Azure-Portal](https://portal.azure.com) gebruiken om verbinding te maken met de virtuele computer van CLIENT1 en vervolgens aan te melden bij CLIENT1.</span><span class="sxs-lookup"><span data-stu-id="31d68-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="31d68-121">Klik op het nieuwe **Microsoft 365-Beheercentrum** , onder **beheer centra** in het linker navigatiedeelvenster, op **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="31d68-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="31d68-122">Klik op het tabblad nieuw **SharePoint-Beheercentrum** op **beleids > toegangsbeheer**.</span><span class="sxs-lookup"><span data-stu-id="31d68-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="31d68-123">Klik op **apps die moderne verificatie niet ondersteunen**, selecteer **toegang blokkeren**en klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="31d68-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="31d68-124">Geavanceerde Bedreigingsbeveiliging inschakelen voor SharePoint, OneDrive voor bedrijven en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="31d68-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="31d68-125">Office 365 Advanced Threat Protection (ATP) voor SharePoint, OneDrive en Microsoft teams beschermt uw organisatie per ongeluk om kwaadaardige bestanden te delen.</span><span class="sxs-lookup"><span data-stu-id="31d68-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="31d68-126">Ga naar de [beveiligings & nalevings centrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="31d68-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="31d68-127">Klik in het linker navigatiedeelvenster onder **bedreigings beheer**op **beleidsregels**en klik vervolgens op **veilige bijlagen voor ATP**.</span><span class="sxs-lookup"><span data-stu-id="31d68-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="31d68-128">Onder **bestanden beschermen in SharePoint, OneDrive en Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="31d68-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="31d68-129">Selecteer **ATP inschakelen voor SharePoint, OneDrive en Microsoft teams**.</span><span class="sxs-lookup"><span data-stu-id="31d68-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="31d68-130">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="31d68-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="31d68-131">Schakel anti malware in</span><span class="sxs-lookup"><span data-stu-id="31d68-131">Enable anti-malware</span></span>

<span data-ttu-id="31d68-132">Malware is samengesteld uit virussen en spyware.</span><span class="sxs-lookup"><span data-stu-id="31d68-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="31d68-133">Virussen infecteren andere Programma's en gegevens, en de personen die op de computer worden verspreid, op zoek naar Programma's.</span><span class="sxs-lookup"><span data-stu-id="31d68-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="31d68-134">Spyware verwijst naar malware waarmee uw persoonlijke gegevens worden verzameld, zoals aanmeldingsgegevens en persoonlijke gegevens, en stuurt u de malware vervolgens terug naar de auteur van de malware.</span><span class="sxs-lookup"><span data-stu-id="31d68-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="31d68-135">Microsoft 365 heeft ingebouwde functies voor het filteren van malware en spam en helpt inkomende en uitgaande berichten van schadelijke software te beschermen en u te helpen beschermen tegen ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="31d68-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="31d68-136">Zie [antispam & bescherming tegen malware](../security/office-365-security/anti-spam-and-anti-malware-protection.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="31d68-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="31d68-137">U kunt als volgt controleren of de verwerking van schadelijke software wordt uitgevoerd voor bestanden met veelgebruikte bestandstypen voor bijlagen:</span><span class="sxs-lookup"><span data-stu-id="31d68-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="31d68-138">Klik op de knop terug in uw browser om terug te gaan naar de pagina **beleid** .</span><span class="sxs-lookup"><span data-stu-id="31d68-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="31d68-139">Klik op **anti malware**.</span><span class="sxs-lookup"><span data-stu-id="31d68-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="31d68-140">Dubbelklik op het beleid met de naam **standaard**.</span><span class="sxs-lookup"><span data-stu-id="31d68-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="31d68-141">Klik in het venster **anti-malwarebeleid** op **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="31d68-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="31d68-142">Selecteer onder **algemene typen bijlagen**de optie **aan**en klik vervolgens op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="31d68-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="31d68-143">Fase 3: het beveiligings dashboard onderzoeken</span><span class="sxs-lookup"><span data-stu-id="31d68-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="31d68-144">Met behulp van risicobeheer in Microsoft 365 kunt u de toegang tot de gegevens van uw organisatie beheren en beheren, uw organisatie beschermen tegen gegevensverlies en inkomende en uitgaande berichten beschermen tegen schadelijke software en spam.</span><span class="sxs-lookup"><span data-stu-id="31d68-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="31d68-145">U kunt ook risicobeheer gebruiken om de reputatie van uw domein te beschermen en te bepalen of een van de afzenders schadelijk accounts zijn van uw domein.</span><span class="sxs-lookup"><span data-stu-id="31d68-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="31d68-146">Het beveiligings dashboard weergeven:</span><span class="sxs-lookup"><span data-stu-id="31d68-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="31d68-147">Ga zo nodig naar de [beveiligings & nalevings centrum](https://protection.office.com) en meld u aan met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="31d68-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="31d68-148">Klik in het linker navigatiedeelvenster onder **Threat Management**op **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="31d68-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="31d68-149">Neem contact op met alle kaarten op het dashboard om uzelf vertrouwd te maken met de verstrekte informatie.</span><span class="sxs-lookup"><span data-stu-id="31d68-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="31d68-150">Zie voor meer informatie het [beveiligings dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span><span class="sxs-lookup"><span data-stu-id="31d68-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="31d68-151">Fase 4: Microsoft Secure Score bestuderen</span><span class="sxs-lookup"><span data-stu-id="31d68-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="31d68-152">Secure Score van Microsoft toont uw beveiligings-Posture als een getal, dat uw huidige niveau aangeeft ten opzichte van de functies die beschikbaar zijn in uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="31d68-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="31d68-153">U hebt ook een lijst met verduidelijkings acties die u kunt ondernemen om de score te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="31d68-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="31d68-154">Maak een nieuw tabblad in uw browser en ga naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/)en klik op **Secure Score**.</span><span class="sxs-lookup"><span data-stu-id="31d68-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="31d68-155">Op het tabblad **overzicht**  kunt u uw huidige beveiligde Score en de manier waarop deze worden vergeleken met het algemene gemiddelde en de abonnementen met een vergelijkbaar aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="31d68-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="31d68-156">Lees in de lijst met acties op het tabblad **kwaliteits verbeteringen** de actie die u kunt uitvoeren om de score te verhogen.</span><span class="sxs-lookup"><span data-stu-id="31d68-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="31d68-157">Zie [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="31d68-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="31d68-158">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="31d68-158">Next steps</span></span>

<span data-ttu-id="31d68-159">Verken de functies en mogelijkheden van extra [informatiebescherming](m365-enterprise-test-lab-guides.md#information-protection) in uw testomgeving.</span><span class="sxs-lookup"><span data-stu-id="31d68-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="31d68-160">Zie ook</span><span class="sxs-lookup"><span data-stu-id="31d68-160">See also</span></span>

[<span data-ttu-id="31d68-161">Microsoft 365 Enterprise-testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="31d68-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="31d68-162">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="31d68-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="31d68-163">Documentatie voor Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="31d68-163">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
