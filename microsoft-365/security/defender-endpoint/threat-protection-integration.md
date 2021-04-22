---
title: Microsoft Defender voor Eindpunt integreren met andere Microsoft-oplossingen
description: Lees hoe Microsoft Defender voor Eindpunt integreert met andere Microsoft-oplossingen, waaronder Microsoft Defender voor identiteit en Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, conditional access, office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935531"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a><span data-ttu-id="acd22-104">Microsoft Defender voor Eindpunt en andere Microsoft-oplossingen</span><span class="sxs-lookup"><span data-stu-id="acd22-104">Microsoft Defender for Endpoint and other Microsoft solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="acd22-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="acd22-105">**Applies to:**</span></span>
- [<span data-ttu-id="acd22-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="acd22-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="acd22-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acd22-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="acd22-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="acd22-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="acd22-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="acd22-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a><span data-ttu-id="acd22-110">Integreren met andere Microsoft-oplossingen</span><span class="sxs-lookup"><span data-stu-id="acd22-110">Integrate with other Microsoft solutions</span></span>

<span data-ttu-id="acd22-111">Microsoft Defender voor Eindpunt wordt rechtstreeks geïntegreerd met verschillende Microsoft-oplossingen.</span><span class="sxs-lookup"><span data-stu-id="acd22-111">Microsoft Defender for Endpoint directly integrates with various Microsoft solutions.</span></span>

### <a name="azure-defender"></a><span data-ttu-id="acd22-112">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="acd22-112">Azure Defender</span></span>
<span data-ttu-id="acd22-113">Microsoft Defender voor Eindpunt biedt een uitgebreide oplossing voor serverbeveiliging, inclusief mogelijkheden voor het detecteren en reageren van eindpunten (EDR) op Windows-servers.</span><span class="sxs-lookup"><span data-stu-id="acd22-113">Microsoft Defender for Endpoint provides a comprehensive server protection solution, including endpoint detection and response (EDR) capabilities on Windows Servers.</span></span>

### <a name="azure-sentinel"></a><span data-ttu-id="acd22-114">Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="acd22-114">Azure Sentinel</span></span>
<span data-ttu-id="acd22-115">Met de Microsoft Defender voor Eindpunt-connector kunt u waarschuwingen van Microsoft Defender voor Eindpunt streamen naar Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="acd22-115">The Microsoft Defender for Endpoint connector lets you stream alerts from Microsoft Defender for Endpoint into Azure Sentinel.</span></span> <span data-ttu-id="acd22-116">Op deze manier kunt u beveiligingsgebeurtenissen in uw organisatie uitgebreider analyseren en playbooks maken voor een effectieve en onmiddellijke reactie.</span><span class="sxs-lookup"><span data-stu-id="acd22-116">This will enable you to more comprehensively analyze security events across your organization and build playbooks for effective and immediate response.</span></span>

### <a name="azure-information-protection"></a><span data-ttu-id="acd22-117">Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="acd22-117">Azure Information Protection</span></span>
<span data-ttu-id="acd22-118">Onlangs hebben we de integratie van Azure Information Protection afgeschaft, omdat onze endpoint-DLP-mogelijkheden een verbeterde detectie- en beveiligingsoplossing bevatten voor gevoelige gegevens die zijn opgeslagen op eindpuntapparaten, zodat er meer zichtbaarheid en integratie tussen oplossingen mogelijk is.</span><span class="sxs-lookup"><span data-stu-id="acd22-118">We recently deprecated the Azure Information Protection integration as our Endpoint DLP capabilities incorporate an improved discovery and protection solution for sensitive data stored on endpoint devices that facilitates greater visibility and integration between solutions.</span></span> <span data-ttu-id="acd22-119">Dit is aangekondigd in de volgende [blog.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555)</span><span class="sxs-lookup"><span data-stu-id="acd22-119">This was announced in the following [blog](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555).</span></span> <span data-ttu-id="acd22-120">We raden klanten aan over te gaan op het gebruik van Endpoint DLP.</span><span class="sxs-lookup"><span data-stu-id="acd22-120">We recommend that customers move to using Endpoint DLP.</span></span>

### <a name="conditional-access"></a><span data-ttu-id="acd22-121">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="acd22-121">Conditional Access</span></span>
<span data-ttu-id="acd22-122">De dynamische apparaatrisicoscore van Microsoft Defender voor Eindpunt is geïntegreerd in de evaluatie Voorwaardelijke toegang, zodat alleen veilige apparaten toegang hebben tot resources.</span><span class="sxs-lookup"><span data-stu-id="acd22-122">Microsoft Defender for Endpoint's dynamic device risk score is integrated into the Conditional Access evaluation, ensuring that only secure devices have access to resources.</span></span> 

### <a name="microsoft-cloud-app-security"></a><span data-ttu-id="acd22-123">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="acd22-123">Microsoft Cloud App Security</span></span>
<span data-ttu-id="acd22-124">Microsoft Cloud App Security maakt gebruik van Microsoft Defender for Endpoint-eindpuntsignalen om direct inzicht te krijgen in het gebruik van cloudtoepassing, waaronder het gebruik van niet-ondersteunde cloudservices (schaduw-IT) van alle bewaakte apparaten van Microsoft Defender voor Endpoint.</span><span class="sxs-lookup"><span data-stu-id="acd22-124">Microsoft Cloud App Security leverages Microsoft Defender for Endpoint endpoint signals to allow direct visibility into cloud application usage including the use of unsupported cloud services (shadow IT) from all Microsoft Defender for Endpoint monitored devices.</span></span>

### <a name="microsoft-defender-for-identity"></a><span data-ttu-id="acd22-125">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="acd22-125">Microsoft Defender for Identity</span></span>
<span data-ttu-id="acd22-126">Verdachte activiteiten zijn processen die worden uitgevoerd onder een gebruikerscontext.</span><span class="sxs-lookup"><span data-stu-id="acd22-126">Suspicious activities are processes running under a user context.</span></span> <span data-ttu-id="acd22-127">De integratie tussen Microsoft Defender voor Eindpunt en Microsoft Defender voor identiteit biedt de flexibiliteit om een cyberbeveiligingsonderzoek uit te voeren tussen activiteiten en identiteiten.</span><span class="sxs-lookup"><span data-stu-id="acd22-127">The integration between Microsoft Defender for Endpoint and Microsoft Defender for Identity provides the flexibility of conducting cyber security investigation across activities and identities.</span></span>

### <a name="microsoft-defender-for-office"></a><span data-ttu-id="acd22-128">Microsoft Defender voor Office</span><span class="sxs-lookup"><span data-stu-id="acd22-128">Microsoft Defender for Office</span></span>
<span data-ttu-id="acd22-129">[Defender voor Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helpt uw organisatie te beschermen tegen malware in e-mailberichten of bestanden via veilige koppelingen, veilige bijlagen, geavanceerde mogelijkheden voor anti-phishing en spoof intelligence.</span><span class="sxs-lookup"><span data-stu-id="acd22-129">[Defender for Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) helps protect your organization from malware in email messages or files through Safe Links, Safe Attachments, advanced Anti-Phishing, and spoof intelligence capabilities.</span></span> <span data-ttu-id="acd22-130">De integratie tussen Microsoft Defender voor Office 365 en Microsoft Defender voor Eindpunt stelt beveiligingsanalisten in staat om upstream te gaan om het ingangspunt van een aanval te onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="acd22-130">The integration between Microsoft Defender for Office 365 and Microsoft Defender for Endpoint enables security analysts to go upstream to investigate the entry point of an attack.</span></span> <span data-ttu-id="acd22-131">Door het delen van bedreigingsinformatie kunnen aanvallen worden beperkt en geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="acd22-131">Through threat intelligence sharing, attacks can be contained and blocked.</span></span> 

>[!NOTE]
> <span data-ttu-id="acd22-132">Defender voor Office 365-gegevens worden weergegeven voor gebeurtenissen in de afgelopen 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="acd22-132">Defender for Office 365 data is displayed for events within the last 30 days.</span></span> <span data-ttu-id="acd22-133">Voor waarschuwingen worden Defender voor Office 365-gegevens weergegeven op basis van de eerste activiteitstijd.</span><span class="sxs-lookup"><span data-stu-id="acd22-133">For alerts, Defender for Office 365 data is displayed based on first activity time.</span></span> <span data-ttu-id="acd22-134">Daarna zijn de gegevens niet meer beschikbaar in Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="acd22-134">After that, the data is no longer available in Defender for Office 365.</span></span>

### <a name="skype-for-business"></a><span data-ttu-id="acd22-135">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="acd22-135">Skype for Business</span></span>
<span data-ttu-id="acd22-136">De integratie van Skype voor Bedrijven biedt analisten een manier om te communiceren met een mogelijk gecompromitteerde gebruiker of apparaateigenaar via een eenvoudige knop vanuit de portal.</span><span class="sxs-lookup"><span data-stu-id="acd22-136">The Skype for Business integration provides a way for analysts to communicate with a potentially compromised user or device owner through a simple button from the portal.</span></span>

## <a name="microsoft-365-defender"></a><span data-ttu-id="acd22-137">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acd22-137">Microsoft 365 Defender</span></span>
<span data-ttu-id="acd22-138">Met Microsoft 365 Defender vormen Microsoft Defender voor Eindpunt en diverse microsoft-beveiligingsoplossingen een geïntegreerde suite voor bedrijfsdefensie vóór en na inbreuk die inheems is geïntegreerd in eindpunten, identiteit, e-mail en toepassingen om geavanceerde aanvallen op te sporen, te voorkomen, te onderzoeken en automatisch te beantwoorden.</span><span class="sxs-lookup"><span data-stu-id="acd22-138">With Microsoft 365 Defender, Microsoft Defender for Endpoint and various Microsoft security solutions form a unified pre- and post-breach enterprise defense suite that natively integrates across endpoint, identity, email, and applications to detect, prevent, investigate and automatically respond to sophisticated attacks.</span></span> 
 
[<span data-ttu-id="acd22-139">Meer informatie over Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acd22-139">Learn more about Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a><span data-ttu-id="acd22-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="acd22-140">Related topics</span></span>
- [<span data-ttu-id="acd22-141">Integratie en andere geavanceerde functies configureren</span><span class="sxs-lookup"><span data-stu-id="acd22-141">Configure integration and other advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="acd22-142">Overzicht van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acd22-142">Microsoft 365 Defender overview</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [<span data-ttu-id="acd22-143">Microsoft 365 Defender inschakelen</span><span class="sxs-lookup"><span data-stu-id="acd22-143">Turn on Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [<span data-ttu-id="acd22-144">Gebruikers, gegevens en apparaten beveiligen met Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="acd22-144">Protect users, data, and devices with Conditional Access</span></span>](conditional-access.md)
