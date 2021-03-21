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
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze training voor de aanvalssimulatie kunnen gebruiken om gesimuleerde phishing- en wachtwoordaanvallen uit te voeren in hun Microsoft 365 E5- of Microsoft Defender voor Office 365 Plan 2-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6e344153ef433bc13b16136e584ec4da73fcef6a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921346"
---
# <a name="get-started-using-attack-simulation-training"></a><span data-ttu-id="20ee7-103">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="20ee7-103">Get started using Attack simulation training</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="20ee7-104">Als uw organisatie Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2 heeft, met mogelijkheden voor bedreigingsonderzoek en [reactie,](office-365-ti.md)kunt u de training voor de aanvalssimulatie in het Microsoft-beveiligingscentrum gebruiken om realistische aanvalsscenario's in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="20ee7-104">If your organization has Microsoft 365 E5 or Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack simulation training in the Microsoft Security Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="20ee7-105">Deze gesimuleerde aanvallen kunnen u helpen bij het identificeren en vinden van kwetsbare gebruikers voordat een echte aanval van invloed is op uw bottom line.</span><span class="sxs-lookup"><span data-stu-id="20ee7-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="20ee7-106">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="20ee7-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="20ee7-107">Aanvalssimulatietraining vervangt de oude Attack Simulator v1-ervaring die wordt beschreven in [Attack Simulator in Microsoft Defender voor Office 365.](attack-simulator.md)</span><span class="sxs-lookup"><span data-stu-id="20ee7-107">Attack simulation training replaces the old Attack Simulator v1 experience that's described in [Attack Simulator in Microsoft Defender for Office 365](attack-simulator.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="20ee7-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="20ee7-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="20ee7-109">Als u het Microsoft-beveiligingscentrum wilt openen, gaat u naar <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="20ee7-109">To open the Microsoft Security Center, go to <https://security.microsoft.com/>.</span></span> <span data-ttu-id="20ee7-110">Training voor aanvalssimulaties is beschikbaar op **training voor e-mail en** \> **samenwerkingssimulaties** voor aanvallen.</span><span class="sxs-lookup"><span data-stu-id="20ee7-110">Attack simulation training is available at **Email and collaboration** \> **Attack simulation training**.</span></span> <span data-ttu-id="20ee7-111">Als u rechtstreeks naar de training Aanvalssimulatie wilt gaan, opent u <https://security.microsoft.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="20ee7-111">To go directly to Attack simulation training, open <https://security.microsoft.com/attacksimulator>.</span></span>

- <span data-ttu-id="20ee7-112">Zie Microsoft [Defender voor Office 365-servicebeschrijving](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van training voor aanvalssimulaties in verschillende Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="20ee7-112">For more information about the availability of Attack simulation training across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="20ee7-113">U moet machtigingen krijgen toegewezen in het Beveiligings- & Compliancecentrum of in Azure Active Directory voordat u de procedures in dit artikel kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="20ee7-113">You need to be assigned permissions in the Security & Compliance Center or in Azure Active Directory before you can do the procedures in this article.</span></span> <span data-ttu-id="20ee7-114">U moet lid zijn van **Organisatiebeheer,** **Beveiligingsbeheerder** of een van de volgende rollen:</span><span class="sxs-lookup"><span data-stu-id="20ee7-114">Specifically, you need to be a member of **Organization Management**, **Security Administrator**, or one of the following roles:</span></span>
  - <span data-ttu-id="20ee7-115">**Aanvalssimulatorbeheerders:** maak en beheerd alle aspecten van aanvalssimulatiecampagnes.</span><span class="sxs-lookup"><span data-stu-id="20ee7-115">**Attack Simulator Administrators**: Create and managed all aspects of attack simulation campaigns.</span></span>
  - <span data-ttu-id="20ee7-116">**Attack Simulator Payload Authors:** Maak aanvalsladingen die een beheerder later kan starten.</span><span class="sxs-lookup"><span data-stu-id="20ee7-116">**Attack Simulator Payload Authors**: Create attack payloads that an admin can initiate later.</span></span>

  <span data-ttu-id="20ee7-117">Zie Machtigingen [in het Beveiligings-](permissions-in-the-security-and-compliance-center.md) & compliancecentrum of Over beheerdersrollen voor [meer informatie.](../../admin/add-users/about-admin-roles.md)</span><span class="sxs-lookup"><span data-stu-id="20ee7-117">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) or [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

- <span data-ttu-id="20ee7-118">Er zijn geen bijbehorende PowerShell-cmdlets voor de training voor de aanvalssimulatie.</span><span class="sxs-lookup"><span data-stu-id="20ee7-118">There are no corresponding PowerShell cmdlets for Attack simulation training.</span></span>

- <span data-ttu-id="20ee7-119">Aanvalssimulatie en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="20ee7-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="20ee7-120">Zie Microsoft [365-gegevenslocaties](../../enterprise/o365-data-locations.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="20ee7-120">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span> <span data-ttu-id="20ee7-121">Aanvalssimulatie is beschikbaar in de volgende regio's: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN en KOR.</span><span class="sxs-lookup"><span data-stu-id="20ee7-121">Attack simulation is available in the following regions: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, and KOR.</span></span>

## <a name="simulations"></a><span data-ttu-id="20ee7-122">Simulaties</span><span class="sxs-lookup"><span data-stu-id="20ee7-122">Simulations</span></span>

<span data-ttu-id="20ee7-123">*Phishing* is een algemene term voor e-mailaanvallen die gevoelige informatie proberen te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="20ee7-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="20ee7-124">*Phishing* maakt deel uit van een subset van technieken die we classificeren als _social engineering._</span><span class="sxs-lookup"><span data-stu-id="20ee7-124">*Phishing* is a part of a subset of techniques we classify as _social engineering_.</span></span>

<span data-ttu-id="20ee7-125">In de training voor de aanvalssimulatie zijn er meerdere typen technieken voor sociale techniek beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="20ee7-125">In Attack simulation training, multiple types of social engineering techniques are available:</span></span>

- <span data-ttu-id="20ee7-126">**Referentieoogst:** een aanvaller stuurt de geadresseerde een bericht met een URL.</span><span class="sxs-lookup"><span data-stu-id="20ee7-126">**Credential harvest**: An attacker sends the recipient a message that contains a URL.</span></span> <span data-ttu-id="20ee7-127">Wanneer de geadresseerde op de URL klikt, wordt deze naar een website gestuurd waarin meestal een dialoogvenster wordt weergegeven waarin de gebruiker om zijn gebruikersnaam en wachtwoord wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20ee7-127">When the recipient clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="20ee7-128">Meestal wordt de doelpagina als themed gebruikt om een bekende website te vertegenwoordigen om vertrouwen in de gebruiker op te bouwen.</span><span class="sxs-lookup"><span data-stu-id="20ee7-128">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="20ee7-129">**Malwarebijlage:** een aanvaller stuurt de geadresseerde een bericht met een bijlage.</span><span class="sxs-lookup"><span data-stu-id="20ee7-129">**Malware attachment**: An attacker sends the recipient a message that contains an attachment.</span></span> <span data-ttu-id="20ee7-130">Wanneer de geadresseerde de bijlage opent, wordt willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker om de aanvaller te helpen extra code te installeren of zichzelf verder te verschansen.</span><span class="sxs-lookup"><span data-stu-id="20ee7-130">When the recipient opens the attachment, arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="20ee7-131">**Koppeling in bijlage:** Dit is een hybride referentieoogst.</span><span class="sxs-lookup"><span data-stu-id="20ee7-131">**Link in attachment**: This is a hybrid of a credential harvest.</span></span> <span data-ttu-id="20ee7-132">Een aanvaller stuurt de geadresseerde een bericht met een URL in een bijlage.</span><span class="sxs-lookup"><span data-stu-id="20ee7-132">An attacker sends the recipient a message that contains a URL inside of an attachment.</span></span> <span data-ttu-id="20ee7-133">Wanneer de geadresseerde de bijlage opent en op de URL klikt, wordt deze naar een website gestuurd waarin meestal een dialoogvenster wordt weergegeven waarin de gebruiker om zijn gebruikersnaam en wachtwoord wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="20ee7-133">When the recipient opens the attachment and clicks on the URL, they're taken to a website that typically shows a dialog box that asks the user for their username and password.</span></span> <span data-ttu-id="20ee7-134">Meestal wordt de doelpagina als themed gebruikt om een bekende website te vertegenwoordigen om vertrouwen in de gebruiker op te bouwen.</span><span class="sxs-lookup"><span data-stu-id="20ee7-134">Typically, the destination page is themed to represent a well-known website in order to build trust in the user.</span></span>

- <span data-ttu-id="20ee7-135">**Koppeling naar malware:** Een aanvaller stuurt de geadresseerde een bericht met een koppeling naar een bijlage op een bekende site voor het delen van bestanden (bijvoorbeeld SharePoint Online of Dropbox).</span><span class="sxs-lookup"><span data-stu-id="20ee7-135">**Link to malware**: An attacker sends the recipient a message that contains a link to an attachment on a well-known file sharing site (for example, SharePoint Online or Dropbox).</span></span> <span data-ttu-id="20ee7-136">Wanneer de geadresseerde op de URL klikt, wordt de bijlage geopend en wordt willekeurige code (bijvoorbeeld een macro) uitgevoerd op het apparaat van de gebruiker, om de aanvaller te helpen extra code te installeren of zichzelf verder te verschansen.</span><span class="sxs-lookup"><span data-stu-id="20ee7-136">When the recipient clicks on the URL, the attachment opens and arbitrary code (for example, a macro) is run on the user's device to help the attacker install additional code or further entrench themselves.</span></span>

- <span data-ttu-id="20ee7-137">**Drive-by-url:** Een aanvaller stuurt de geadresseerde een bericht met een URL.</span><span class="sxs-lookup"><span data-stu-id="20ee7-137">**Drive-by-url**: An attacker sends the recipient a messages that contains a URL.</span></span> <span data-ttu-id="20ee7-138">Wanneer de geadresseerde op de URL klikt, wordt deze naar een website geleid die probeert achtergrondcode uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="20ee7-138">When the recipient clicks on the URL, they're taken to a website that tries to run background code.</span></span> <span data-ttu-id="20ee7-139">Met deze achtergrondcode wordt geprobeerd informatie over de ontvanger te verzamelen of willekeurige code op het apparaat te implementeren.</span><span class="sxs-lookup"><span data-stu-id="20ee7-139">This background code attempts to gather information about the recipient or deploy arbitrary code on their device.</span></span> <span data-ttu-id="20ee7-140">Meestal is de doelwebsite een bekende website die is gecompromitteerd of een kloon van een bekende website.</span><span class="sxs-lookup"><span data-stu-id="20ee7-140">Typically, the destination website is a well-known website that has been compromised or a clone of a well-known website.</span></span> <span data-ttu-id="20ee7-141">Vertrouwdheid met de website helpt de gebruiker ervan te overtuigen dat de koppeling veilig is om op te klikken.</span><span class="sxs-lookup"><span data-stu-id="20ee7-141">Familiarity with the website helps convince the user that the link is safe to click.</span></span> <span data-ttu-id="20ee7-142">Deze techniek wordt ook wel een _watergat-aanval genoemd._</span><span class="sxs-lookup"><span data-stu-id="20ee7-142">This technique is also known as a _watering hole attack_.</span></span>

> [!NOTE]
> <span data-ttu-id="20ee7-143">Controleer de beschikbaarheid van de gesimuleerde phishing-URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="20ee7-143">Check the availability of the simulated phishing URL in your supported web browsers before you use the URL in a phishing campaign.</span></span> <span data-ttu-id="20ee7-144">Hoewel we met veel URL-reputatieleveranciers werken om deze URL's voor simulaties altijd toe te staan, hebben we niet altijd volledige dekking (bijvoorbeeld Google Safe Browsing).</span><span class="sxs-lookup"><span data-stu-id="20ee7-144">While we work with many URL reputation vendors to always allow these simulation URLs, we don't always have full coverage (for example, Google Safe Browsing).</span></span> <span data-ttu-id="20ee7-145">De meeste leveranciers bieden richtlijnen waarmee u altijd specifieke URL's kunt toestaan <https://support.google.com/chrome/a/answer/7532419> (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="20ee7-145">Most vendors provide guidance that allows you to always allow specific URLs (for example, <https://support.google.com/chrome/a/answer/7532419>).</span></span>

<span data-ttu-id="20ee7-146">De URL's die worden gebruikt door training voor de aanvalssimulatie worden in de volgende lijst beschreven:</span><span class="sxs-lookup"><span data-stu-id="20ee7-146">The URLs that are used by Attack simulation training are described in the following list:</span></span>

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

### <a name="create-a-simulation"></a><span data-ttu-id="20ee7-147">Een simulatie maken</span><span class="sxs-lookup"><span data-stu-id="20ee7-147">Create a simulation</span></span>

<span data-ttu-id="20ee7-148">Zie Een phishing-aanval simuleren voor stapsgewijs instructies over het maken en verzenden van een nieuwe [simulatie.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="20ee7-148">For step by step instructions on how to create and send a new simulation, see [Simulate a phishing attack](attack-simulation-training.md).</span></span>

### <a name="create-a-payload"></a><span data-ttu-id="20ee7-149">Een payload maken</span><span class="sxs-lookup"><span data-stu-id="20ee7-149">Create a payload</span></span>

<span data-ttu-id="20ee7-150">Zie Een aangepaste payload maken voor de trainingstraining aanvalssimulatie voor stapsgewijs instructies over het maken van een payload voor gebruik in [een simulatie.](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="20ee7-150">For step by step instructions on how to create a payload for use within a simulation, see [Create a custom payload for Attack simulation training](attack-simulation-training-payloads.md).</span></span>

### <a name="gaining-insights"></a><span data-ttu-id="20ee7-151">Inzichten verkrijgen</span><span class="sxs-lookup"><span data-stu-id="20ee7-151">Gaining insights</span></span>

<span data-ttu-id="20ee7-152">Zie Inzichten verkrijgen via de trainingstraining Aanvalssimulatie voor [stapsgewijs](attack-simulation-training-insights.md)instructies over het verkrijgen van inzichten met rapportage.</span><span class="sxs-lookup"><span data-stu-id="20ee7-152">For step by step instructions on how to gain insights with reporting, see [Gain insights through Attack simulation training](attack-simulation-training-insights.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20ee7-153">Attack Simulator gebruikt veilige koppelingen in Defender voor Office 365 om veilig klikgegevens bij te houden voor de URL  in het payloadbericht dat wordt verzonden naar geadresseerden van een phishingcampagne, zelfs als de instelling Gebruikersklikken niet bijhouden in beleid voor veilige koppelingen is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="20ee7-153">Attack Simulator uses Safe Links in Defender for Office 365 to securely track click data for the URL in the payload message that's sent to targeted recipients of a phishing campaign, even if the **Do not track user clicks** setting in Safe Links policies is turned on.</span></span>