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
description: Meer informatie over de standaardinstelling veilig in Exchange Online Protection (EOP)
ms.openlocfilehash: 1a68c14a2d37f1fc3bfb032c4d3ca34c09a89890
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527767"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="a4dff-103">Standaard veilig in Office 365</span><span class="sxs-lookup"><span data-stu-id="a4dff-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="a4dff-104">' Veilig standaard ' is een term die wordt gebruikt voor het definiëren van de standaardinstellingen die zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="a4dff-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="a4dff-105">De beveiliging moet echter worden gesaldeerd met productiviteit.</span><span class="sxs-lookup"><span data-stu-id="a4dff-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="a4dff-106">Dit kan gelden voor de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="a4dff-106">This can include balancing across:</span></span>

- <span data-ttu-id="a4dff-107">Bruikbaarheids functie: de instellingen zijn niet te vinden in de manier van gebruikers productiviteit.</span><span class="sxs-lookup"><span data-stu-id="a4dff-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="a4dff-108">Risico: beveiliging kan belangrijke activiteiten blokkeren.</span><span class="sxs-lookup"><span data-stu-id="a4dff-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="a4dff-109">Verouderde instellingen: sommige configuraties voor oudere producten en functies kunnen worden bijgehouden voor zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.</span><span class="sxs-lookup"><span data-stu-id="a4dff-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="a4dff-110">Microsoft 365-organisaties met postvakken in Exchange Online zijn beveiligd via Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="a4dff-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="a4dff-111">Deze bescherming omvat:</span><span class="sxs-lookup"><span data-stu-id="a4dff-111">This protection includes:</span></span>

1. <span data-ttu-id="a4dff-112">E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden ontvangen een melding.</span><span class="sxs-lookup"><span data-stu-id="a4dff-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="a4dff-113">Zie [anti-malwarebeleid in EOP configureren](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a4dff-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="a4dff-114">Malafide e-mailadres dat is aangeduid als ' hoge betrouwbaarheid ' wordt verwerkt overeenkomstig de actie tegen antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="a4dff-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="a4dff-115">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a4dff-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a4dff-116">Aangezien Microsoft onze klanten de mogelijkheid geeft standaard te beschermen, worden sommige tenants overschreven voor malware of phishing met een hoge betrouwbaarheid niet toegepast.</span><span class="sxs-lookup"><span data-stu-id="a4dff-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phishing.</span></span> <span data-ttu-id="a4dff-117">Deze overschrijvingen zijn:</span><span class="sxs-lookup"><span data-stu-id="a4dff-117">These overrides include:</span></span>

- <span data-ttu-id="a4dff-118">Lijsten met toegestane afzenders of toegestane domeinen (Antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="a4dff-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="a4dff-119">Veilige afzenders van Outlook</span><span class="sxs-lookup"><span data-stu-id="a4dff-119">Outlook Safe senders</span></span>
- <span data-ttu-id="a4dff-120">Lijst met toegestane IP-adressen (verbindingen filteren)</span><span class="sxs-lookup"><span data-stu-id="a4dff-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="a4dff-121">Meer informatie over deze overschrijvingen vindt u in [lijsten met veilige afzenders maken](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a4dff-121">More information on these overrides can be found in [Create safe sender lists](create-safe-sender-lists-in-office-365.md).</span></span>

<span data-ttu-id="a4dff-122">Deze instelling is standaard veilig en is niet een instelling die kan worden in-of uitgeschakeld, maar de manier waarop onze filters van het vak werken, om ongewenste berichten in uw postvakken te houden.</span><span class="sxs-lookup"><span data-stu-id="a4dff-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="a4dff-123">De malware en de kwaliteit van de hoge betrouwbaarheid worden naar Quarantine verzonden.</span><span class="sxs-lookup"><span data-stu-id="a4dff-123">Malware and high confidence phishing should be sent to quarantine.</span></span> <span data-ttu-id="a4dff-124">Alleen beheerders kunnen berichten beheren die zijn gequarantined als malware of phishing van hoge betrouwbaarheid, en kunnen ze ook fout-positieven naar Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="a4dff-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="a4dff-125">Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="a4dff-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="a4dff-126">Ring</span><span class="sxs-lookup"><span data-stu-id="a4dff-126">Exceptions</span></span>

<span data-ttu-id="a4dff-127">Met de enige Negeer functie voor het filteren van e-mail wordt het filteren van Exchange-e-mail stroom regels (ook wel wel transport regels genoemd) toegestaan.</span><span class="sxs-lookup"><span data-stu-id="a4dff-127">The only override that allows high confidence phishing message to bypass filtering is Exchange mail flow rules (also known as transport rules).</span></span> <span data-ttu-id="a4dff-128">Als u de e-mail stroom regels wilt gebruiken om het filteren te negeren, raadpleegt u [de e-mail stroom regels gebruiken om de SCL in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span><span class="sxs-lookup"><span data-stu-id="a4dff-128">To use mail flow rules to bypass filtering, see [Use mail flow rules to set the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span>

<span data-ttu-id="a4dff-129">Overschrijvingen mag alleen worden gebruikt voor:</span><span class="sxs-lookup"><span data-stu-id="a4dff-129">Overrides should only be used for:</span></span>

- <span data-ttu-id="a4dff-130">Malafide simulaties: gesimuleerde aanvallen kunnen u helpen gevoelige gebruikers te identificeren voordat een echte aanval uw organisatie beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="a4dff-130">Phishing simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="a4dff-131">Beveiligings-SecOps-postvakken: speciale postvakken die door beveiligings teams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="a4dff-131">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="a4dff-132">Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="a4dff-132">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="a4dff-133">Filters van derden: bepaalde leveranciers van derden raden u aan om EOP (SCL =-1) uit te schakelen als het filter van een derde partij de filtering voor e-mail beheert.</span><span class="sxs-lookup"><span data-stu-id="a4dff-133">Third-party filters: some third-party vendors will recommend turning off EOP (SCL=-1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="a4dff-134">Microsoft adviseert om EOP uit te schakelen als EOP is vereist voor Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="a4dff-134">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span> <span data-ttu-id="a4dff-135">In plaats daarvan kunt u in plaats daarvan [uitgebreid filteren op connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) inschakelen.</span><span class="sxs-lookup"><span data-stu-id="a4dff-135">Instead, the recommendation here is to turn on [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) instead.</span></span>
- <span data-ttu-id="a4dff-136">Foutberichten: u kunt bepaalde berichten die nog door Microsoft worden geanalyseerd, toestaan door de [admin-inzendingen](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a4dff-136">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="a4dff-137">Net als met alle overschrijvingen, is het raadzaam dat ze tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="a4dff-137">As with all overrides, it is recommended that they are temporary.</span></span>
