---
title: Aan de slag met aanvalssimulatietraining
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u simulatie training kunt gebruiken voor het uitvoeren van simulaties voor phishing en wachtwoorden in hun Microsoft 365 E5 of Microsoft Defender for Office 365-abonnement 2-organisaties.
ms.openlocfilehash: 2c00fb27748887c6b8e2fa1458b10f0c3405eef7
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877162"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="90f58-103">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="90f58-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="90f58-104">Als uw organisatie gebruikmaakt van Microsoft 365 E5 of Microsoft Defender for Office 365 (abonnement 2), waaronder het [onderzoek en de antwoord mogelijkheden](office-365-ti.md)van de organisatie, kunt u simulatie training voor hacken gebruiken in het Microsoft-Beveiligingscentrum voor het uitvoeren van realistische aanvalsscenario's in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="90f58-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="90f58-105">Met de gesimuleerde aanvallen kunt u gebruikers kwetsbaar maken en kwetsbaar maken voor een echte aanval met uw onderste regel.</span><span class="sxs-lookup"><span data-stu-id="90f58-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="90f58-106">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90f58-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="90f58-107">Simulatie training aanval vervangt de oude ervaring van een aanval van de versie van Office Simulator die wordt beschreven in [aanvals Simulator in Microsoft Defender voor Office 365](attack-simulator.md).</span><span class="sxs-lookup"><span data-stu-id="90f58-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90f58-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="90f58-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90f58-109">Als u het Microsoft Beveiligingscentrum wilt openen, gaat u naar <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="90f58-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="90f58-110">Simulatie voor simulatie van aanval via **e-mail en samenwerking** is beschikbaar op een \> **simulatie training** voor e-mail en samenwerking.</span><span class="sxs-lookup"><span data-stu-id="90f58-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="90f58-111">Als u direct naar een aanvals training wilt gaan, opent u <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="90f58-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="90f58-112">Zie voor meer informatie over de beschikbaarheid van een aanvals training in diverse Microsoft 365-abonnementen de [servicebeschrijving van Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="90f58-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="90f58-113">U moet beschikken over machtigingen voor de beveiliging & nalevings centrum of Azure Active Directory voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="90f58-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="90f58-114">Specifiek moet u lid zijn van **Organisatiebeheer**, **beveiligingsbeheerder** of een van de volgende rollen:</span><span class="sxs-lookup"><span data-stu-id="90f58-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="90f58-115">**Kwaadwillende Simulator-beheerders**: alle aspecten van simulaties van aanvals campagnes maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="90f58-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="90f58-116">**Schrijvers** van een aanval van de nettolading van een aanval: een aanval maken die een beheerder later kan initiëren.</span><span class="sxs-lookup"><span data-stu-id="90f58-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="90f58-117">Zie voor meer informatie [machtigingen in het artikel over naleving van beveiligings &](permissions-in-the-security-and-compliance-center.md) of [over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span><span class="sxs-lookup"><span data-stu-id="90f58-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

- <span data-ttu-id="90f58-118">Er zijn geen bijbehorende PowerShell-cmdlets voor simulaties van aanvals oefeningen.</span><span class="sxs-lookup"><span data-stu-id="90f58-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="90f58-119">Simulatie van aanval en opleidingen met betrekking tot de training voor Microsoft 365-Services met andere klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="90f58-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="90f58-120">Zie [Microsoft 365-gegevenslocaties](/microsoft-365/enterprise/o365-data-locations)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90f58-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="90f58-121">Simulatie van aanval is op dit moment niet beschikbaar in de volgende regio's: SGP, noch, UAE, ZAF, GER, BRA en CHE.</span><span class="sxs-lookup"><span data-stu-id="90f58-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="90f58-122">Simulaties</span><span class="sxs-lookup"><span data-stu-id="90f58-122">Simulations</span></span>

<span data-ttu-id="90f58-123">*Phishing* is een algemene term voor e-mail aanvallen waarbij gevoelige informatie wordt gestolen voor berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="90f58-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="90f58-124">*Phishing* is een onderdeel van een subset van technieken die we als _Social Engineering_ classificeren.</span><span class="sxs-lookup"><span data-stu-id="90f58-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="90f58-125">In het geval van een aanval met simulatie zijn er meerdere soorten technieken voor Social engineering.</span><span class="sxs-lookup"><span data-stu-id="90f58-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="90f58-126">**Credential oogst**: een aanvaller verzendt een bericht dat de ontvanger een URL bevat.</span><span class="sxs-lookup"><span data-stu-id="90f58-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="90f58-127">Wanneer de geadresseerde op de URL klikt, wordt deze doorgestuurd naar een website die meestal een dialoogvenster wordt weergegeven waarin de gebruiker om de gebruikersnaam en wachtwoord vraagt.</span><span class="sxs-lookup"><span data-stu-id="90f58-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="90f58-128">Meestal is de doelpagina bedoeld om een bekende website aan te geven om het vertrouwen van de gebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="90f58-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="90f58-129">**Bijlage met schadelijke software**: een aanvaller verzendt de geadresseerde een bericht dat een bijlage bevat.</span><span class="sxs-lookup"><span data-stu-id="90f58-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="90f58-130">Wanneer de geadresseerde de bijlage opent, wordt willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, zodat de aanvaller een extra code of verdere entrench zichzelf kan installeren.</span><span class="sxs-lookup"><span data-stu-id="90f58-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="90f58-131">**Koppeling in bijlage**: dit is een Hybrid van een Credential oogst.</span><span class="sxs-lookup"><span data-stu-id="90f58-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="90f58-132">Een aanvaller verzendt de geadresseerde een bericht met een URL in een bijlage.</span><span class="sxs-lookup"><span data-stu-id="90f58-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="90f58-133">Wanneer de geadresseerde de bijlage opent en op de URL klikt, wordt deze doorgestuurd naar een website die normaalgesproken een dialoogvenster toont waarin de gebruiker om de gebruikersnaam en wachtwoord vraagt.</span><span class="sxs-lookup"><span data-stu-id="90f58-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="90f58-134">Meestal is de doelpagina bedoeld om een bekende website aan te geven om het vertrouwen van de gebruiker te maken.</span><span class="sxs-lookup"><span data-stu-id="90f58-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="90f58-135">**Koppeling naar malware**: een aanvaller verzendt de geadresseerde een bericht met een koppeling naar een bijlage op een bekende bestandsshare site (bijvoorbeeld SharePoint Online of Dropbox).</span><span class="sxs-lookup"><span data-stu-id="90f58-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="90f58-136">Wanneer de geadresseerde op de URL klikt, wordt de bijlage geopend en willekeurige code (zoals een macro), op het apparaat van de gebruiker, zodat de aanvaller een extra code of verdere entrench zichzelf kan installeren.</span><span class="sxs-lookup"><span data-stu-id="90f58-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="90f58-137">**Drive by-URL**: een aanvaller verzendt een e-mailbericht met een URL.</span><span class="sxs-lookup"><span data-stu-id="90f58-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="90f58-138">Wanneer de geadresseerde op de URL klikt, wordt deze gezocht naar een website die wordt gebruikt om de achtergrond code uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="90f58-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="90f58-139">Met deze achtergrond code wordt geprobeerd informatie over de ontvanger te verzamelen of willekeurige code op hun apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="90f58-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="90f58-140">Meestal is de bestemmingswebsite een bekende website met een ongeoorloofde of een kloon van een bekende website.</span><span class="sxs-lookup"><span data-stu-id="90f58-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="90f58-141">Vertrouwd met de website helpt bij het overtuigen van de gebruiker dat de link veilig kan worden geklikt.</span><span class="sxs-lookup"><span data-stu-id="90f58-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="90f58-142">Deze methode wordt ook wel een _aanval met bewaterings hole_ genoemd.</span><span class="sxs-lookup"><span data-stu-id="90f58-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="90f58-143">Controleer de beschikbaarheid van de gesimuleerde phishingwebsite in de ondersteunde webbrowsers voordat u de URL in een malafide campagne gebruikt.</span><span class="sxs-lookup"><span data-stu-id="90f58-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="90f58-144">Hoewel we met veel URL-reputatie leveranciers werken om deze simulatie-Url's altijd toe te staan, hebben we niet altijd de volledige behoefte, zoals Google Safe Browse.</span><span class="sxs-lookup"><span data-stu-id="90f58-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="90f58-145">De meeste leveranciers bieden richtlijnen waarmee u altijd specifieke Url's kunt toestaan (bijvoorbeeld <https://support.google.com/chrome/a/answer/7532419> ).</span><span class="sxs-lookup"><span data-stu-id="90f58-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="90f58-146">De Url's die worden gebruikt voor de simulatie van aanvals oefeningen, worden beschreven in de volgende lijst:</span><span class="sxs-lookup"><span data-stu-id="90f58-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a><span data-ttu-id="90f58-147">Een simulatie maken</span><span class="sxs-lookup"><span data-stu-id="90f58-147">Create a simulation</span></span>

<span data-ttu-id="90f58-148">Zie [een malafide aanval simuleren](attack-simulation-training.md)voor stapsgewijze instructies voor het maken en verzenden van een nieuwe simulatie.</span><span class="sxs-lookup"><span data-stu-id="90f58-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="90f58-149">Een nettolading maken</span><span class="sxs-lookup"><span data-stu-id="90f58-149">Create a payload</span></span>

<span data-ttu-id="90f58-150">Zie [een aangepaste nettolading maken voor simulatie van aanvals training](attack-simulation-training-payloads.md)voor stapsgewijze instructies voor het maken van een nettolading voor gebruik binnen een simulatie.</span><span class="sxs-lookup"><span data-stu-id="90f58-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="90f58-151">Inzichten krijgen</span><span class="sxs-lookup"><span data-stu-id="90f58-151">Gaining insights</span></span>

<span data-ttu-id="90f58-152">Zie [inzichten maken via simulatie van aanval via een aanval](attack-simulation-training-insights.md)voor stapsgewijze instructies voor het maken van inzichten met rapporten.</span><span class="sxs-lookup"><span data-stu-id="90f58-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
