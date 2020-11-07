---
title: Standaard veilig in Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Meer informatie over het zoeken en gebruiken van e-mail beveiligingsrapporten voor uw organisatie. Beveiligingsrapporten voor e-mail zijn beschikbaar in de beveiligings & nalevings centrum.
ms.openlocfilehash: 0e38091981cd379dfc912be429c00d168dff775c
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944441"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="38d69-104">Standaard veilig in Office 365</span><span class="sxs-lookup"><span data-stu-id="38d69-104">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="38d69-105">' Veilig standaard ' is een term die wordt gebruikt voor het definiëren van de standaardinstellingen die zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="38d69-105">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span> 

<span data-ttu-id="38d69-106">De beveiliging moet echter worden gesaldeerd met productiviteit.</span><span class="sxs-lookup"><span data-stu-id="38d69-106">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="38d69-107">Dit kan gelden voor de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="38d69-107">This can include balancing across:</span></span>
- <span data-ttu-id="38d69-108">Bruikbaarheids functie: de instellingen zijn niet te vinden in de manier van gebruikers productiviteit.</span><span class="sxs-lookup"><span data-stu-id="38d69-108">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="38d69-109">Risico: beveiliging kan belangrijke activiteiten blokkeren.</span><span class="sxs-lookup"><span data-stu-id="38d69-109">Risk: security might block important activities.</span></span>
- <span data-ttu-id="38d69-110">Verouderde instellingen: sommige configuraties voor oudere producten en functies kunnen worden bijgehouden voor zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.</span><span class="sxs-lookup"><span data-stu-id="38d69-110">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span> 

<span data-ttu-id="38d69-111">Microsoft 365-organisaties met postvakken in Exchange Online zijn beveiligd via Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="38d69-111">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="38d69-112">Deze bescherming omvat:</span><span class="sxs-lookup"><span data-stu-id="38d69-112">This  protection includes:</span></span>
1. <span data-ttu-id="38d69-113">E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden ontvangen een melding.</span><span class="sxs-lookup"><span data-stu-id="38d69-113">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="38d69-114">Zie [anti-malwarebeleid in EOP configureren](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="38d69-114">See [Configure anti-malware policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).</span></span>
1. <span data-ttu-id="38d69-115">Malafide e-mailadres dat is aangeduid als ' hoge betrouwbaarheid ' wordt verwerkt overeenkomstig de actie tegen antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="38d69-115">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="38d69-116">Zie [Antispambeleid configureren in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="38d69-116">See [Configure anti-spam policies in EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="38d69-117">Aangezien Microsoft onze klanten de mogelijkheid geeft standaard te beschermen, worden sommige tenants overschreven voor malware of een hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="38d69-117">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="38d69-118">Deze overschrijvingen zijn:</span><span class="sxs-lookup"><span data-stu-id="38d69-118">These overrides include:</span></span>
- <span data-ttu-id="38d69-119">Lijsten met toegestane afzenders of toegestane domeinen (Antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="38d69-119">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="38d69-120">Veilige afzenders van Outlook</span><span class="sxs-lookup"><span data-stu-id="38d69-120">Outlook Safe senders</span></span>
- <span data-ttu-id="38d69-121">Lijst met toegestane IP-adressen (verbindingen filteren)</span><span class="sxs-lookup"><span data-stu-id="38d69-121">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="38d69-122">Meer informatie over deze overschrijvingen vindt u in [lijsten met veilige afzenders maken](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="38d69-122">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="38d69-123">Deze instelling is standaard veilig en is niet een instelling die kan worden in-of uitgeschakeld, maar de manier waarop onze filters van het vak werken, om ongewenste berichten in uw postvakken te houden.</span><span class="sxs-lookup"><span data-stu-id="38d69-123">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="38d69-124">Malware en kwaliteit van hoge betrouwbaarheid worden naar Quarantine verzonden.</span><span class="sxs-lookup"><span data-stu-id="38d69-124">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="38d69-125">Alleen beheerders kunnen berichten beheren die zijn gequarantined als malware of phishing van hoge betrouwbaarheid, en kunnen ze ook fout-positieven naar Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="38d69-125">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="38d69-126">Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="38d69-126">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="38d69-127">Ring</span><span class="sxs-lookup"><span data-stu-id="38d69-127">Exceptions</span></span>
<span data-ttu-id="38d69-128">De enige overschrijving waarmee alle filters worden overgeslagen omvat:</span><span class="sxs-lookup"><span data-stu-id="38d69-128">The only overrides that will bypass all filters include:</span></span>
- <span data-ttu-id="38d69-129">Exchange-Transport regels (ETR toe)/mail-stroom regels.</span><span class="sxs-lookup"><span data-stu-id="38d69-129">Exchange Transport Rules (ETR)/mail flow rules.</span></span>  <span data-ttu-id="38d69-130">Met behulp van regels voor e-mail stroom kunt u het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instellen in berichten in EOP.</span><span class="sxs-lookup"><span data-stu-id="38d69-130">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="38d69-131">Tenant accepteren/blokkeren: Url's en bestanden beheren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="38d69-131">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>


<span data-ttu-id="38d69-132">Dit soort overschrijvingen is handig voor:</span><span class="sxs-lookup"><span data-stu-id="38d69-132">These types of overrides are useful for:</span></span>
- <span data-ttu-id="38d69-133">Phishing-simulaties: gesimuleerde aanvallen kunnen u helpen gevoelige gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="38d69-133">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="38d69-134">Beveiligings-SecOps-postvakken: speciale postvakken die door beveiligings teams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="38d69-134">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="38d69-135">Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="38d69-135">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="38d69-136">Filters van derden: sommige leveranciers van derden adviseren om EOP (SCL =-1) uit te schakelen als het filter van een derde partij de filtering voor e-mail beheert.</span><span class="sxs-lookup"><span data-stu-id="38d69-136">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span>  <span data-ttu-id="38d69-137">Microsoft adviseert om EOP uit te schakelen als EOP is vereist voor Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="38d69-137">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> 
- <span data-ttu-id="38d69-138">Foutberichten: u kunt bepaalde berichten die nog door Microsoft worden geanalyseerd, toestaan door de [admin-inzendingen](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="38d69-138">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="38d69-139">Net als met alle overschrijvingen, is het raadzaam dat ze tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="38d69-139">As with all overrides, it is recommended that they are temporary.</span></span>
