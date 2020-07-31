---
title: Identiteits-, apparaat- en bedreigingsbescherming gebruiken voor regelgeving voor gegevensprivacy
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
ms.custom: ''
description: Voorkom inbreuken op persoonsgegevens met identiteits-, apparaat- en bedreigingsbeveiligingsservices van Microsoft 365.
ms.openlocfilehash: a309b5d0ba5f939cf89a31d7ac91ca3aac25ce0d
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46520979"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="95e55-103">Identiteits-, apparaat- en bedreigingsbescherming gebruiken voor regelgeving voor gegevensprivacy</span><span class="sxs-lookup"><span data-stu-id="95e55-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="95e55-104">Microsoft 365 biedt een aantal mogelijkheden voor identiteits-, apparaat- en bedreigingsbescherming die organisaties kunnen gebruiken om te voldoen aan de nalevingsvoorschriften voor gegevensprivacy.</span><span class="sxs-lookup"><span data-stu-id="95e55-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="95e55-105">In dit artikel wordt beschreven wat de regelgeving inzake gegevensprivacy op deze gebieden vereist en wordt een overzicht gegeven van gerelateerde Microsoft 365-functies en -services met koppelingen naar meer informatie om u te helpen de implementatievereisten aan te pakken.</span><span class="sxs-lookup"><span data-stu-id="95e55-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="95e55-106">Hoe identiteits-, apparaat- en bedreigingsbescherming zich verhouden tot de regelgeving voor gegevensprivacy</span><span class="sxs-lookup"><span data-stu-id="95e55-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="95e55-107">Hoewel de regels voor gegevensprivacy verschillen in hun specificiteit, wordt de essentie van wat zij vragen opgenomen in artikel 5, lid 1, onder f), artikel 5, lid 1, onder f), van de AVG, waarin staat dat:</span><span class="sxs-lookup"><span data-stu-id="95e55-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="95e55-108">Persoonsgegevens worden verwerkt op een wijze die een passende beveiliging van de persoonsgegevens waarst omgaat, met inbegrip van bescherming tegen ongeoorloofde of onrechtmatige verwerking en tegen onopzettelijke schade, vernietiging of schade, met behulp van passende technische of organisatorische maatregelen ('integriteit en vertrouwelijkheid').</span><span class="sxs-lookup"><span data-stu-id="95e55-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="95e55-109">Omdat inbreuken op persoonlijke gegevens vaak worden veroorzaakt door administratieve of eindgebruikersaccountcompromissen en schadelijke systeemtoegang.</span><span class="sxs-lookup"><span data-stu-id="95e55-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="95e55-110">Bijvoorbeeld, een admin account hack kan resulteren in exfiltratie van klant creditcardnummers of andere persoonlijke informatie.</span><span class="sxs-lookup"><span data-stu-id="95e55-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="95e55-111">Alle algemene aan te raden identiteit, apparaat en bedreigingsbescherming die mogelijk beschikbaar is met Microsoft 365, moeten mogelijk worden geïmplementeerd, wat wordt weerspiegeld in uw nalevingsscore.</span><span class="sxs-lookup"><span data-stu-id="95e55-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your Compliance Score.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-score"></a><span data-ttu-id="95e55-112">Aan de hand van de resultaten van uw beoordelingswerk en compliancescore</span><span class="sxs-lookup"><span data-stu-id="95e55-112">Using the results of your assessment work and Compliance Score</span></span>

<span data-ttu-id="95e55-113">Compliance Score omvat identiteits-, apparaat- en bedreigingsbescherming met behulp van deze categorieën:</span><span class="sxs-lookup"><span data-stu-id="95e55-113">Compliance Score includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="95e55-114">Identiteit komt overeen met de categorie **Controletoegang**</span><span class="sxs-lookup"><span data-stu-id="95e55-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="95e55-115">Apparaat komt overeen met de categorie **Apparaten beheren**</span><span class="sxs-lookup"><span data-stu-id="95e55-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="95e55-116">Bedreigingsbescherming komt overeen met de categorie **Protect Against Threats**</span><span class="sxs-lookup"><span data-stu-id="95e55-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="95e55-117">Als deze worden geselecteerd in onze voorbeeldset van vier belangrijke regelgeving voor gegevensprivacy, specificeert compliancescore 90 verbeteringsacties, waarvan de meeste een "27" scoren.</span><span class="sxs-lookup"><span data-stu-id="95e55-117">If these are selected across our sample set of four major data privacy regulations, Compliance Score specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="95e55-118">Aangezien een dergelijk groot aantal wordt opgeroepen door Compliance Score voor deze categorieën, worden enkele van de meest voorkomende hier vermeld, ter referentie.</span><span class="sxs-lookup"><span data-stu-id="95e55-118">Since such a large number are called out by Compliance Score for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="95e55-119">Gebruik [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) voor identiteit en de categorie Control **Access,** waarmee u:</span><span class="sxs-lookup"><span data-stu-id="95e55-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="95e55-120">Implementeer replay-resistente authenticatie (om "Man in the middle" aanvallen te voorkomen)</span><span class="sxs-lookup"><span data-stu-id="95e55-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="95e55-121">Verouderde verificatie blokkeren.</span><span class="sxs-lookup"><span data-stu-id="95e55-121">Block legacy authentication.</span></span>
- <span data-ttu-id="95e55-122">Configureer het risicobeleid van gebruikers en het risico van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="95e55-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="95e55-123">Voorwaardelijke toegang en multi-factor authenticatie (MFA) inschakelen voor beheerders en niet-beheerders.</span><span class="sxs-lookup"><span data-stu-id="95e55-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="95e55-124">Wachtwoordbeleid configureren en afdwingen.</span><span class="sxs-lookup"><span data-stu-id="95e55-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="95e55-125">Beperk de toegang tot bevoorrechte accounts met Azure AD Privileged Identity Management.</span><span class="sxs-lookup"><span data-stu-id="95e55-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="95e55-126">Schakel de toegang uit bij beëindiging.</span><span class="sxs-lookup"><span data-stu-id="95e55-126">Disable access upon termination.</span></span>
- <span data-ttu-id="95e55-127">Gebruikersaccounts en statuswijzigingen controleren.</span><span class="sxs-lookup"><span data-stu-id="95e55-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="95e55-128">Rolgroep en administratieve wijzigingen bekijken.</span><span class="sxs-lookup"><span data-stu-id="95e55-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="95e55-129">Gebruik [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) voor apparaten en de categorie Apparaten **beheren,** waarmee u:</span><span class="sxs-lookup"><span data-stu-id="95e55-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="95e55-130">Blokkeer de gevangenis gebroken en geworteld mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="95e55-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="95e55-131">Configureer Intune voor beheer van mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="95e55-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="95e55-132">Maak nalevingsbeleid voor Android-, iOS-, macOS- en Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="95e55-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="95e55-133">Maak een apparaatconfiguratieprofiel voor Android-, iOS-, macOS- en Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="95e55-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="95e55-134">Maak beleid voor app-beveiliging voor iOS en Windows.</span><span class="sxs-lookup"><span data-stu-id="95e55-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="95e55-135">Informatie verbergen met vergrendelingsscherm.</span><span class="sxs-lookup"><span data-stu-id="95e55-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="95e55-136">Voer wachtwoordbeleid voor mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="95e55-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="95e55-137">Mobiele apparaten moeten vergrendelen bij inactiviteit.</span><span class="sxs-lookup"><span data-stu-id="95e55-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="95e55-138">Mobiele apparaten moeten meerdere aanmeldingsfouten wissen.</span><span class="sxs-lookup"><span data-stu-id="95e55-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="95e55-139">Gebruik [Exchange Online Protection en Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) voor de categorie Protect Against **Threats,** waarmee u:</span><span class="sxs-lookup"><span data-stu-id="95e55-139">Use [Exchange Online Protection and Office 365 Advanced Threat Protection (ATP)](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="95e55-140">Afzenderverificatie inschakelen (SPF, DMARC en DKIM).</span><span class="sxs-lookup"><span data-stu-id="95e55-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="95e55-141">Het atp-beleid (Advanced Threat Protection) (Advanced Threat Protection) instellen.</span><span class="sxs-lookup"><span data-stu-id="95e55-141">Set up Office 365 Advanced Threat Protection (ATP) anti-phishing policies.</span></span>
- <span data-ttu-id="95e55-142">Implementeer ATP Safe Attachments.</span><span class="sxs-lookup"><span data-stu-id="95e55-142">Implement ATP Safe Attachments.</span></span>
- <span data-ttu-id="95e55-143">Implementeer ATP Safe Links.</span><span class="sxs-lookup"><span data-stu-id="95e55-143">Implement ATP Safe Links.</span></span>
- <span data-ttu-id="95e55-144">Implementeer het beleid voor malwaredetectie en -respons.</span><span class="sxs-lookup"><span data-stu-id="95e55-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="95e55-145">Implementeer uitgaand en binnenkomend spambeleid.</span><span class="sxs-lookup"><span data-stu-id="95e55-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="95e55-146">Verwijzingen:</span><span class="sxs-lookup"><span data-stu-id="95e55-146">References:</span></span>

- [<span data-ttu-id="95e55-147">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="95e55-147">Common identity and device access policies</span></span>](../enterprise/identity-access-policies.md)
- [<span data-ttu-id="95e55-148">Beschermen tegen bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="95e55-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="95e55-149">ATP-veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="95e55-149">ATP Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="95e55-150">Veilige ATP-koppelingen</span><span class="sxs-lookup"><span data-stu-id="95e55-150">ATP Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="95e55-151">Veilige bijlagen in ATP</span><span class="sxs-lookup"><span data-stu-id="95e55-151">ATP Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
