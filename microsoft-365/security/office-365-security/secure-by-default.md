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
ms.openlocfilehash: 50d1c64e4d8343fdb9b25bfcbeee5d988ddc6b8a
ms.sourcegitcommit: 9dbc6a08177aaca112e84d30dbaa79a0a8e9dbf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2020
ms.locfileid: "48945328"
---
# <a name="secure-by-default-in-office-365"></a><span data-ttu-id="ba1c6-103">Standaard veilig in Office 365</span><span class="sxs-lookup"><span data-stu-id="ba1c6-103">Secure by default in Office 365</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ba1c6-104">' Veilig standaard ' is een term die wordt gebruikt voor het definiëren van de standaardinstellingen die zo veilig mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-104">"Secure by default" is a term used to define the default settings that are most secure as possible.</span></span>

<span data-ttu-id="ba1c6-105">De beveiliging moet echter worden gesaldeerd met productiviteit.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-105">However, security needs to be balanced with productivity.</span></span> <span data-ttu-id="ba1c6-106">Dit kan gelden voor de volgende taken:</span><span class="sxs-lookup"><span data-stu-id="ba1c6-106">This can include balancing across:</span></span>

- <span data-ttu-id="ba1c6-107">Bruikbaarheids functie: de instellingen zijn niet te vinden in de manier van gebruikers productiviteit.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-107">Usability: settings should not get in the way of user productivity.</span></span>
- <span data-ttu-id="ba1c6-108">Risico: beveiliging kan belangrijke activiteiten blokkeren.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-108">Risk: security might block important activities.</span></span>
- <span data-ttu-id="ba1c6-109">Verouderde instellingen: sommige configuraties voor oudere producten en functies kunnen worden bijgehouden voor zakelijke redenen, zelfs als nieuwe, moderne instellingen zijn verbeterd.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-109">Legacy settings: Some configurations for older products and features might need to be maintained for business reasons, even if new, modern settings are improved.</span></span>

<span data-ttu-id="ba1c6-110">Microsoft 365-organisaties met postvakken in Exchange Online zijn beveiligd via Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="ba1c6-110">Microsoft 365 organizations with mailboxes in Exchange Online are protected by Exchange Online Protection (EOP).</span></span> <span data-ttu-id="ba1c6-111">Deze bescherming omvat:</span><span class="sxs-lookup"><span data-stu-id="ba1c6-111">This protection includes:</span></span>

1. <span data-ttu-id="ba1c6-112">E-mail met verdachte malware wordt automatisch in quarantaine geplaatst en geadresseerden ontvangen een melding.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-112">Email with suspected malware will automatically be quarantined and recipients will be notified.</span></span> <span data-ttu-id="ba1c6-113">Zie [anti-malwarebeleid in EOP configureren](configure-anti-malware-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ba1c6-113">See [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).</span></span>
1. <span data-ttu-id="ba1c6-114">Malafide e-mailadres dat is aangeduid als ' hoge betrouwbaarheid ' wordt verwerkt overeenkomstig de actie tegen antispambeleid.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-114">Phishing email identified as "high confidence" will be handled according to the anti-spam policy action.</span></span> <span data-ttu-id="ba1c6-115">Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="ba1c6-115">See [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="ba1c6-116">Aangezien Microsoft onze klanten de mogelijkheid geeft standaard te beschermen, worden sommige tenants overschreven voor malware of een hoge betrouwbaarheid.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-116">Because Microsoft wants to keep our customers secure by default, some tenants overrides are not applied for malware or high confidence phish.</span></span> <span data-ttu-id="ba1c6-117">Deze overschrijvingen zijn:</span><span class="sxs-lookup"><span data-stu-id="ba1c6-117">These overrides include:</span></span>

- <span data-ttu-id="ba1c6-118">Lijsten met toegestane afzenders of toegestane domeinen (Antispambeleid)</span><span class="sxs-lookup"><span data-stu-id="ba1c6-118">Allowed sender lists or allowed domain lists (anti-spam policies)</span></span>
- <span data-ttu-id="ba1c6-119">Veilige afzenders van Outlook</span><span class="sxs-lookup"><span data-stu-id="ba1c6-119">Outlook Safe senders</span></span>
- <span data-ttu-id="ba1c6-120">Lijst met toegestane IP-adressen (verbindingen filteren)</span><span class="sxs-lookup"><span data-stu-id="ba1c6-120">IP Allow List (connection filtering)</span></span>

<span data-ttu-id="ba1c6-121">Meer informatie over deze overschrijvingen vindt u in [lijsten met veilige afzenders maken](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span><span class="sxs-lookup"><span data-stu-id="ba1c6-121">More information on these overrides can be found in [Create safe sender lists](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365).</span></span>

<span data-ttu-id="ba1c6-122">Deze instelling is standaard veilig en is niet een instelling die kan worden in-of uitgeschakeld, maar de manier waarop onze filters van het vak werken, om ongewenste berichten in uw postvakken te houden.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-122">Secure by default here is not a setting that could be turned on or off, but the way our filtering works out of the box to keep potentially dangerous or unwanted messages out of your mailboxes.</span></span> <span data-ttu-id="ba1c6-123">Malware en kwaliteit van hoge betrouwbaarheid worden naar Quarantine verzonden.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-123">Malware and high confidence phish should be sent to quarantine.</span></span> <span data-ttu-id="ba1c6-124">Alleen beheerders kunnen berichten beheren die zijn gequarantined als malware of phishing van hoge betrouwbaarheid, en kunnen ze ook fout-positieven naar Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-124">Only admins can manage messages that were quarantined as malware or high confidence phishing and they can also report false positives to Microsoft from there.</span></span> <span data-ttu-id="ba1c6-125">Zie voor meer informatie geplaatste [berichten en bestanden beheren als beheerder in EOP](manage-quarantined-messages-and-files.md)</span><span class="sxs-lookup"><span data-stu-id="ba1c6-125">For more information, see [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)</span></span>

## <a name="exceptions"></a><span data-ttu-id="ba1c6-126">Ring</span><span class="sxs-lookup"><span data-stu-id="ba1c6-126">Exceptions</span></span>

<span data-ttu-id="ba1c6-127">De enige overschrijving waarmee alle filters worden overgeslagen omvat:</span><span class="sxs-lookup"><span data-stu-id="ba1c6-127">The only overrides that will bypass all filters include:</span></span>

- <span data-ttu-id="ba1c6-128">Exchange-Transport regels (ETR toe)/mail-stroom regels.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-128">Exchange Transport Rules (ETR)/mail flow rules.</span></span> <span data-ttu-id="ba1c6-129">Met behulp van regels voor e-mail stroom kunt u het betrouwbaarheidsniveau voor ongewenste e-mail (SCL) instellen in berichten in EOP.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-129">Use mail flow rules to set the spam confidence level (SCL) in messages in EOP.</span></span>
- <span data-ttu-id="ba1c6-130">Tenant accepteren/blokkeren: Url's en bestanden beheren in de lijst Tenant toestaan/blokkeren.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-130">Tenant Allow/Block List: Manage URLs and files in the Tenant Allow/Block List.</span></span>

<span data-ttu-id="ba1c6-131">Dit soort overschrijvingen is handig voor:</span><span class="sxs-lookup"><span data-stu-id="ba1c6-131">These types of overrides are useful for:</span></span>

- <span data-ttu-id="ba1c6-132">Phishing-simulaties: gesimuleerde aanvallen kunnen u helpen gevoelige gebruikers te identificeren voordat een echte aanval van invloed is op uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-132">Phish simulations: simulated attacks can help you identify vulnerable users before a real attack impacts your organization.</span></span>
- <span data-ttu-id="ba1c6-133">Beveiligings-SecOps-postvakken: speciale postvakken die door beveiligings teams worden gebruikt om ongefilterde berichten te ontvangen (zowel goed als slecht).</span><span class="sxs-lookup"><span data-stu-id="ba1c6-133">Security/SecOps mailboxes: dedicated mailboxes used by security teams to get unfiltered messages (both good and bad).</span></span> <span data-ttu-id="ba1c6-134">Teams kan vervolgens controleren of ze schadelijke inhoud bevatten.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-134">Teams can then review to see if they contain malicious content.</span></span>
- <span data-ttu-id="ba1c6-135">Filters van derden: sommige leveranciers van derden adviseren om EOP (SCL =-1) uit te schakelen als het filter van een derde partij de filtering voor e-mail beheert.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-135">Third-party filters: some third party vendors will recommend turning off EOP (SCL = -1) as the third-party filter will manage the mail filtering.</span></span> <span data-ttu-id="ba1c6-136">Microsoft adviseert om EOP uit te schakelen als EOP is vereist voor Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-136">Microsoft does not recommend turning off EOP as EOP is required for Defender for Office 365.</span></span>
- <span data-ttu-id="ba1c6-137">Foutberichten: u kunt bepaalde berichten die nog door Microsoft worden geanalyseerd, toestaan door de [admin-inzendingen](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="ba1c6-137">False positives: you may want to allow certain messages that are still being analyzed by Microsoft [via Admin submissions](admin-submission.md).</span></span> <span data-ttu-id="ba1c6-138">Net als met alle overschrijvingen, is het raadzaam dat ze tijdelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="ba1c6-138">As with all overrides, it is recommended that they are temporary.</span></span>
