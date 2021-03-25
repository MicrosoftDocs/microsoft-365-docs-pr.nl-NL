---
title: Identiteits-, apparaat- en bedreigingsbeveiliging gebruiken voor privacyregels voor gegevens
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Voorkom inbreuken op persoonlijke gegevens met identiteits-, apparaat- en bedreigingsbeveiligingsservices van Microsoft 365.
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199463"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="f08ca-103">Identiteits-, apparaat- en bedreigingsbeveiliging gebruiken voor privacyregels voor gegevens</span><span class="sxs-lookup"><span data-stu-id="f08ca-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="f08ca-104">Microsoft 365 biedt een aantal mogelijkheden voor identiteits-, apparaat- en bedreigingsbeveiliging die organisaties kunnen gebruiken om te voldoen aan nalevingsregels voor gegevensbescherming.</span><span class="sxs-lookup"><span data-stu-id="f08ca-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="f08ca-105">In dit artikel wordt beschreven wat de privacyregels voor gegevens vereisen in deze gebieden en bevat een lijst met gerelateerde Microsoft 365-functies en -services met koppelingen naar meer informatie om u te helpen bij het voldoen aan implementatievereisten.</span><span class="sxs-lookup"><span data-stu-id="f08ca-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="f08ca-106">Hoe identiteits-, apparaat- en bedreigingsbeveiliging zich verhouden tot de privacyregel voor gegevens</span><span class="sxs-lookup"><span data-stu-id="f08ca-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="f08ca-107">Hoewel de privacyregels voor gegevens variëren in hun specificiteit, wordt de essentie van wat ze noemen opgenomen in artikel 5, lid 1, onder f, van de AVG, waarin wordt bepaald dat:</span><span class="sxs-lookup"><span data-stu-id="f08ca-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="f08ca-108">Persoonsgegevens worden verwerkt op een manier die de juiste beveiliging van de persoonsgegevens garandeert, met inbegrip van bescherming tegen ongeoorloofde of onrechtmatige verwerking en tegen onbedoeld verlies, vernieling of schade, met behulp van passende technische of organisatorische maatregelen ('integriteit en vertrouwelijkheid').</span><span class="sxs-lookup"><span data-stu-id="f08ca-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="f08ca-109">Omdat inbreuken op persoonlijke gegevens vaak worden veroorzaakt door compromitteerd beheer- of eindgebruikersaccount en schadelijke systeemtoegang.</span><span class="sxs-lookup"><span data-stu-id="f08ca-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="f08ca-110">Een hack van een beheerdersaccount kan bijvoorbeeld leiden tot exfiltratie van creditcardnummers van klanten of andere persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="f08ca-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="f08ca-111">Alle over het algemeen aanbevolen identiteits-, apparaat- en bedreigingsbeveiliging die mogelijk beschikbaar is met Microsoft 365, moet worden geïmplementeerd, wat wordt weerspiegeld in uw compliancescore, die wordt gevonden in Compliance Manager.</span><span class="sxs-lookup"><span data-stu-id="f08ca-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="f08ca-112">De resultaten van uw beoordelingswerk en Compliance Manager gebruiken</span><span class="sxs-lookup"><span data-stu-id="f08ca-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="f08ca-113">Compliance Manager bevat identiteits-, apparaat- en bedreigingsbeveiliging met behulp van deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="f08ca-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="f08ca-114">Identiteit komt overeen met de **categorie Control Access**</span><span class="sxs-lookup"><span data-stu-id="f08ca-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="f08ca-115">Apparaat komt overeen met de **categorie Apparaten** beheren</span><span class="sxs-lookup"><span data-stu-id="f08ca-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="f08ca-116">Bedreigingsbeveiliging komt overeen met de **categorie Beschermen tegen** bedreigingen</span><span class="sxs-lookup"><span data-stu-id="f08ca-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="f08ca-117">Als deze zijn geselecteerd in onze voorbeeldset met vier belangrijke privacyregels voor gegevens, geeft Compliance Manager 90 verbeteracties op, waarvan de meeste een '27' krijgen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="f08ca-118">Aangezien een dergelijk groot aantal door Compliance Manager voor deze categorieën wordt uitgeroepen, worden enkele veelgebruikte categorieën hier vermeld, ter referentie.</span><span class="sxs-lookup"><span data-stu-id="f08ca-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="f08ca-119">Gebruik [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) voor identiteit en de categorie Control **Access,** waarmee u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="f08ca-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="f08ca-120">Replay-resistant authentication implementeren (om 'Man in the middle' aanvallen te voorkomen)</span><span class="sxs-lookup"><span data-stu-id="f08ca-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="f08ca-121">Oudere verificatie blokkeren.</span><span class="sxs-lookup"><span data-stu-id="f08ca-121">Block legacy authentication.</span></span>
- <span data-ttu-id="f08ca-122">Beleidsregels voor gebruikersrisico's en aanmeldingsrisico's voor gebruikers configureren.</span><span class="sxs-lookup"><span data-stu-id="f08ca-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="f08ca-123">Voorwaardelijke toegang en meervoudige verificatie (MFA) inschakelen voor beheerders en niet-beheerders.</span><span class="sxs-lookup"><span data-stu-id="f08ca-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="f08ca-124">Wachtwoordbeleid configureren en afdwingen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="f08ca-125">Toegang tot bevoorrechte accounts beperken met Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="f08ca-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="f08ca-126">De toegang uitschakelen na beëindiging.</span><span class="sxs-lookup"><span data-stu-id="f08ca-126">Disable access upon termination.</span></span>
- <span data-ttu-id="f08ca-127">Controleer gebruikersaccounts en statuswijzigingen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="f08ca-128">Controleer rollengroep- en beheerwijzigingen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="f08ca-129">Microsoft [Endpoint Manager gebruiken](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) voor apparaten en de categorie Apparaten beheren, waarmee u het volgende kunt doen: </span><span class="sxs-lookup"><span data-stu-id="f08ca-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="f08ca-130">Blokkeer de cel met gebroken en geroote mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="f08ca-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="f08ca-131">Intune configureren voor mobiel apparaatbeheer.</span><span class="sxs-lookup"><span data-stu-id="f08ca-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="f08ca-132">Maak compliancebeleid voor Android-, iOS-, macOS- en Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="f08ca-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="f08ca-133">Maak een apparaatconfiguratieprofiel voor Android-, iOS-, macOS- en Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="f08ca-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="f08ca-134">Beleid voor app-beveiliging maken voor iOS en Windows.</span><span class="sxs-lookup"><span data-stu-id="f08ca-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="f08ca-135">Verberg gegevens met vergrendelingsscherm.</span><span class="sxs-lookup"><span data-stu-id="f08ca-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="f08ca-136">Wachtwoordbeleid implementeren voor mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="f08ca-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="f08ca-137">Vereisen dat mobiele apparaten worden vergrendeld bij inactiviteit.</span><span class="sxs-lookup"><span data-stu-id="f08ca-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="f08ca-138">Vereisen dat mobiele apparaten meerdere aanmeldingsfouten wissen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="f08ca-139">Gebruik [Exchange Online Protection en Microsoft Defender voor Office 365](../security/office-365-security/defender-for-office-365.md) voor de categorie Beschermen **tegen** bedreigingen, waarmee u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="f08ca-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="f08ca-140">Afzenderverificatie (SPF, DMARC en DKIM) inschakelen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="f08ca-141">Microsoft Defender voor Office 365 anti-phishingbeleid instellen.</span><span class="sxs-lookup"><span data-stu-id="f08ca-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="f08ca-142">Veilige bijlagen implementeren.</span><span class="sxs-lookup"><span data-stu-id="f08ca-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="f08ca-143">Veilige koppelingen implementeren.</span><span class="sxs-lookup"><span data-stu-id="f08ca-143">Implement Safe Links.</span></span>
- <span data-ttu-id="f08ca-144">Implementeert malwaredetectie- en antwoordbeleid.</span><span class="sxs-lookup"><span data-stu-id="f08ca-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="f08ca-145">Implementeert uitgaand en binnenkomende spambeleid.</span><span class="sxs-lookup"><span data-stu-id="f08ca-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="f08ca-146">Verwijzingen:</span><span class="sxs-lookup"><span data-stu-id="f08ca-146">References:</span></span>

- [<span data-ttu-id="f08ca-147">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="f08ca-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="f08ca-148">Beschermen tegen bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="f08ca-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="f08ca-149">Veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="f08ca-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="f08ca-150">Veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="f08ca-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="f08ca-151">Veilige documenten</span><span class="sxs-lookup"><span data-stu-id="f08ca-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
