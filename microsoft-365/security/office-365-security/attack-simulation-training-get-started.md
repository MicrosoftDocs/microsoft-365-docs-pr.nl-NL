---
title: Aan de slag met aanvalssimulatietraining
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
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
description: Beheerders kunnen meer informatie krijgen over het gebruik van de training voor de aanvalsaanvallen op de nabootsing van phishing en wachtwoordaanvallen in hun organisaties met Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ec5b8175db6eb03e59a31a4dc21d9649c5e7616
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289890"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="d26a2-103">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="d26a2-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="d26a2-104">Als uw organisatie beschikt over Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2, waarin de mogelijkheden voor bedreigingen onderzoeken en antwoorden zijn [betrokken,](office-365-ti.md)kunt u de analysetraining voor aanvallen in het Microsoft-beveiligingscentrum gebruiken om realistische scenario's met aanvallen uit te voeren in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d26a2-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="d26a2-105">Deze gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren en te vinden voordat een echte aanval uw onderlijn beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="d26a2-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="d26a2-106">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d26a2-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="d26a2-107">Trainingstraining voor de aanval vervangt de oude Attack Simulator v1-ervaring die wordt beschreven in [Attack Simulator in Microsoft Defender voor Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="d26a2-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d26a2-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d26a2-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d26a2-109">Als u het Microsoft-beveiligingscentrum wilt openen, gaat u naar <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="d26a2-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="d26a2-110">Training voor de aanvalstraining voor de aanval is beschikbaar op **de training voor de e-mail-** en \> **samenwerkingstraining voor de aanvals-aanval.**</span><span class="sxs-lookup"><span data-stu-id="d26a2-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="d26a2-111">Als u rechtstreeks naar de training voor de aanvalsen wilt gaan, opent <https://security.microsoft.com/attacksimulator> u .</span><span class="sxs-lookup"><span data-stu-id="d26a2-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="d26a2-112">Zie de servicebeschrijving van de Microsoft Defender voor [Office 365-service](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van de training voor de aanvalstraining voor verschillende Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="d26a2-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="d26a2-113">U moet machtigingen toegewezen krijgen in het beveiligings- & compliancecentrum of in Azure Active Directory voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d26a2-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="d26a2-114">U moet lid zijn van **Organisatiebeheer,** Beveiligingsbeheerder of een van de volgende rollen:</span><span class="sxs-lookup"><span data-stu-id="d26a2-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="d26a2-115">**Administrators van de Attack Simulator:** alle aspecten van de aanvalscampagnes maken en beheren.</span><span class="sxs-lookup"><span data-stu-id="d26a2-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="d26a2-116">**Attack Simulator Payload Authors:** Maak nettoladingen voor aanvallen die een beheerder later kan starten.</span><span class="sxs-lookup"><span data-stu-id="d26a2-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="d26a2-117">Zie Machtigingen in het [beveiligings-](permissions-in-the-security-and-compliance-center.md) en & of [beheerdersrollen voor meer informatie.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="d26a2-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="d26a2-118">Er zijn geen bijbehorende PowerShell-cmdlets voor de training voor de attack-training.</span><span class="sxs-lookup"><span data-stu-id="d26a2-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="d26a2-119">Het analyseren van aanvallen en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="d26a2-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="d26a2-120">Zie Microsoft [365-gegevenslocaties voor meer informatie.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="d26a2-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="d26a2-121">De aanvalssjoin is momenteel niet beschikbaar in de volgende regio's: SGP, NOR, UAE, ZAF, GER, BRA en CHE.</span><span class="sxs-lookup"><span data-stu-id="d26a2-121">Attack simulation is currently not available in the following regions: SGP, NOR, UAE, ZAF, GER, BRA, and CHE.</span></span>

## <a name="simulations"></a><span data-ttu-id="d26a2-122">Vereenspelingen</span><span class="sxs-lookup"><span data-stu-id="d26a2-122">Simulations</span></span>

<span data-ttu-id="d26a2-123">*Phishing* is een algemene term voor e-mailaanvallen die proberen gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="d26a2-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="d26a2-124">*Phishing* maakt deel uit van een subset van technieken die we classificeren als _social engineering._</span><span class="sxs-lookup"><span data-stu-id="d26a2-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="d26a2-125">In de training voor de aanvals-ulatie zijn meerdere soorten social engineering-technieken beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="d26a2-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="d26a2-126">**Referentiegegevens**: een aanvaller stuurt de ontvanger een bericht met een URL.</span><span class="sxs-lookup"><span data-stu-id="d26a2-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="d26a2-127">Wanneer de geadresseerde op de URL klikt, wordt deze naar een website gestuurd waar meestal een dialoogvenster wordt weergegeven waarin de gebruiker wordt gevraagd om zijn of haar gebruikersnaam en wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="d26a2-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="d26a2-128">Meestal heeft de doelpagina een eigen site met een bekende naam om het vertrouwen in de gebruiker op te bouwen.</span><span class="sxs-lookup"><span data-stu-id="d26a2-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="d26a2-129">**Malwarebijlage:** een aanvaller stuurt de ontvanger een bericht dat een bijlage bevat.</span><span class="sxs-lookup"><span data-stu-id="d26a2-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="d26a2-130">Wanneer de ontvanger de bijlage opent, wordt er willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, om de aanvaller te helpen aanvullende code te installeren of zichzelf verder te beschermen.</span><span class="sxs-lookup"><span data-stu-id="d26a2-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="d26a2-131">**Koppeling in bijlage:** Dit is een hybride voor het gebruik van referenties.</span><span class="sxs-lookup"><span data-stu-id="d26a2-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="d26a2-132">Een aanvaller stuurt de ontvanger een bericht met een URL in een bijlage.</span><span class="sxs-lookup"><span data-stu-id="d26a2-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="d26a2-133">Wanneer de geadresseerde de bijlage opent en op de URL klikt, wordt deze naar een website gestuurd waar meestal een dialoogvenster wordt weergegeven waarin de gebruiker wordt gevraagd om zijn gebruikersnaam en wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="d26a2-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="d26a2-134">Meestal heeft de doelpagina een eigen site met een bekende naam om het vertrouwen in de gebruiker op te bouwen.</span><span class="sxs-lookup"><span data-stu-id="d26a2-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="d26a2-135">**Koppeling naar malware:** een aanvaller stuurt de ontvanger een bericht met een koppeling naar een bijlage op een bekende site voor het delen van bestanden (bijvoorbeeld SharePoint Online of Dropbox).</span><span class="sxs-lookup"><span data-stu-id="d26a2-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="d26a2-136">Wanneer de ontvanger op de URL klikt, wordt de bijlage geopend en wordt er willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker om de aanvaller te helpen bij het installeren van extra code of om zichzelf verder te beschermen.</span><span class="sxs-lookup"><span data-stu-id="d26a2-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="d26a2-137">**Drive-by-url:** een aanvaller stuurt de ontvanger een bericht dat een URL bevat.</span><span class="sxs-lookup"><span data-stu-id="d26a2-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="d26a2-138">Wanneer de geadresseerde op de URL klikt, wordt deze naar een website geleid die achtergrondcode probeert uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d26a2-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="d26a2-139">Met deze achtergrondcode wordt geprobeerd informatie over de ontvanger te verzamelen of willekeurige code op het apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="d26a2-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="d26a2-140">Meestal is de doelwebsite een bekende website die is gekloond of een kloon van een bekende website.</span><span class="sxs-lookup"><span data-stu-id="d26a2-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="d26a2-141">Als u bekend bent met de website, zorgt u ervoor dat de gebruiker ervan op de koppeling klikt.</span><span class="sxs-lookup"><span data-stu-id="d26a2-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="d26a2-142">Deze techniek wordt ook wel een _watergat-aanval genoemd._</span><span class="sxs-lookup"><span data-stu-id="d26a2-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="d26a2-143">Controleer de beschikbaarheid van de gesimuleerde phishing-URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="d26a2-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="d26a2-144">Hoewel we met veel leveranciers van URL-reputatie werken om deze url's altijd toe te staan, hebben we niet altijd volledige dekking (bijvoorbeeld Veilig browsen van Google).</span><span class="sxs-lookup"><span data-stu-id="d26a2-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="d26a2-145">De meeste leveranciers bieden richtlijnen waarmee u altijd specifieke URL's (bijvoorbeeld) kunt <https://support.google.com/chrome/a/answer/7532419> toestaan.</span><span class="sxs-lookup"><span data-stu-id="d26a2-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="d26a2-146">In de volgende lijst worden de URL's beschreven die worden gebruikt bij de training voor de aanvalstraining voor de aanvallen:</span><span class="sxs-lookup"><span data-stu-id="d26a2-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="d26a2-147">Een computerstimulatie maken</span><span class="sxs-lookup"><span data-stu-id="d26a2-147">Create a simulation</span></span>

<span data-ttu-id="d26a2-148">Zie Een phishing-aanval simuleren voor stapsgewijse [instructies](attack-simulation-training.md)over het maken en verzenden van een nieuwe ulatie.</span><span class="sxs-lookup"><span data-stu-id="d26a2-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="d26a2-149">Een nettolading maken</span><span class="sxs-lookup"><span data-stu-id="d26a2-149">Create a payload</span></span>

<span data-ttu-id="d26a2-150">Voor stapsgewijre instructies over het maken van een nettolading voor gebruik in eenulatie, zie Een aangepaste nettolading maken voor de [attack-training.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="d26a2-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="d26a2-151">Inzichten verkrijgen</span><span class="sxs-lookup"><span data-stu-id="d26a2-151">Gaining insights</span></span>

<span data-ttu-id="d26a2-152">Zie Inzichten krijgen via de trainingstraining voor de aanvalstraining voor stapsgewijse instructies over hoe u inzichten kunt verkrijgen met [rapporten.](attack-simulation-training-insights.md)</span><span class="sxs-lookup"><span data-stu-id="d26a2-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>
