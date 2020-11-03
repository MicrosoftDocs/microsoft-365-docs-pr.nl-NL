---
title: Identiteit, apparaat en bedreigings bescherming gebruiken voor data privacy verordening
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
description: Voorkom dat persoonlijke gegevens worden geschonden met identiteits-, service-en Threat Protection-Services van Microsoft 365.
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847176"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="e6e79-103">Identiteit, apparaat en bedreigings bescherming gebruiken voor data privacy verordening</span><span class="sxs-lookup"><span data-stu-id="e6e79-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="e6e79-104">Microsoft 365 biedt een aantal mogelijkheden voor identiteiten, apparaten en beveiliging van bedreigingen waarmee organisaties zich kunnen helpen aan de nalevings regels van de regelgeving voor informatie.</span><span class="sxs-lookup"><span data-stu-id="e6e79-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="e6e79-105">In dit artikel wordt uitgelegd wat de vereisten voor data privacy op deze gebieden zijn, en een lijst met verwante Microsoft 365-functies en-services, met koppelingen naar meer informatie om de implementatievereisten te adresseren.</span><span class="sxs-lookup"><span data-stu-id="e6e79-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="e6e79-106">Hoe de identiteit, het apparaat en de bedreigingsbeveiliging betrekking hebben op de regelgeving voor data privacy</span><span class="sxs-lookup"><span data-stu-id="e6e79-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="e6e79-107">Hoewel de regelgeving voor de privacy in hun eigeniteit verschilt, is de essentie van de inhoud van de inhoud van het AVG-artikel 5 (1) (f), waarin wordt aangegeven dat:</span><span class="sxs-lookup"><span data-stu-id="e6e79-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="e6e79-108">Persoonlijke gegevens worden verwerkt op een wijze die de juiste veiligheid van de persoonsgegevens waarborgt, met inbegrip van de bescherming tegen ongeoorloofde of onwettige verwerking en tegen toevallige verlies, vernietiging of schade, op basis van adequate technische of organisatie maatregelen (' integriteit en vertrouwelijkheid ').</span><span class="sxs-lookup"><span data-stu-id="e6e79-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="e6e79-109">Aangezien persoonlijke gegevens schendingen vaak worden veroorzaakt door een administratieve of eindgebruikers account en toegang tot een kwaadaardige systeem.</span><span class="sxs-lookup"><span data-stu-id="e6e79-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="e6e79-110">Een account van een beheerder kan bijvoorbeeld hacken exfiltration van creditcardnummers van klanten of andere persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="e6e79-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="e6e79-111">Alle algemeen verzorg bare identiteit, apparaat en bedreigings bescherming met Microsoft 365, moet worden geïmplementeerd, welke worden weergegeven in de compliance-Score.</span><span class="sxs-lookup"><span data-stu-id="e6e79-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="e6e79-112">De resultaten van uw beoordelings werk en Compliance Manager gebruiken</span><span class="sxs-lookup"><span data-stu-id="e6e79-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="e6e79-113">Nalevings beheer met identiteit, apparaat en bedreigingsbeveiliging bevat de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="e6e79-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="e6e79-114">Identiteit komt overeen met de categorie **toegangsbeheer**</span><span class="sxs-lookup"><span data-stu-id="e6e79-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="e6e79-115">Apparaat komt overeen met de categorie **apparaten beheren**</span><span class="sxs-lookup"><span data-stu-id="e6e79-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="e6e79-116">Bedreigingsbeveiliging komt overeen met de categorie **bescherming tegen bedreigingen**</span><span class="sxs-lookup"><span data-stu-id="e6e79-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="e6e79-117">Als deze optie is geselecteerd in onze Voorbeeldset met vier belangrijke informatie over de privacy, geeft Compliance Manager 90-verbeterings acties op, waarvan de meeste een ' 27 ' gescoorde.</span><span class="sxs-lookup"><span data-stu-id="e6e79-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="e6e79-118">Aangezien een dergelijk grote nummer wordt genoemd door Compliance Manager voor deze categorieën, worden enkele van de meest voorkomende items hier weergegeven voor naslaginformatie.</span><span class="sxs-lookup"><span data-stu-id="e6e79-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="e6e79-119">Azure [Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) gebruiken voor de identiteit en de categorie **toegangsbeheer** , waarmee u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="e6e79-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="e6e79-120">Herspeel bestendige verificatie implementeren (om man in het midden te helpen voorkomen)</span><span class="sxs-lookup"><span data-stu-id="e6e79-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="e6e79-121">Verouderde authenticatie blokkeren.</span><span class="sxs-lookup"><span data-stu-id="e6e79-121">Block legacy authentication.</span></span>
- <span data-ttu-id="e6e79-122">Beleidsregels voor gebruikers risico en gebruikersaanmelding configureren.</span><span class="sxs-lookup"><span data-stu-id="e6e79-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="e6e79-123">Schakel voorwaardelijke toegang en multi-factor Authentication (MFA) in voor beheerders en niet-beheerders.</span><span class="sxs-lookup"><span data-stu-id="e6e79-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="e6e79-124">Wachtwoordbeleidsregels configureren en afdwingen.</span><span class="sxs-lookup"><span data-stu-id="e6e79-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="e6e79-125">Toegang tot geprivilegieerde accounts beperken met een Azure AD-geprivilegieerde identiteitsbeheer.</span><span class="sxs-lookup"><span data-stu-id="e6e79-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="e6e79-126">Toegang uitschakelen na beëindiging.</span><span class="sxs-lookup"><span data-stu-id="e6e79-126">Disable access upon termination.</span></span>
- <span data-ttu-id="e6e79-127">Controleer gebruikersaccounts en statuswijzigingen.</span><span class="sxs-lookup"><span data-stu-id="e6e79-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="e6e79-128">Rollen groepen en beheerders wijzigingen bekijken.</span><span class="sxs-lookup"><span data-stu-id="e6e79-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="e6e79-129">Gebruik [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) voor apparaten en de categorie **apparaten beheren** , waarmee u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="e6e79-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="e6e79-130">Blokkeer jail verbroken en geroote mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="e6e79-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="e6e79-131">InTune configureren voor Mobile Device Management.</span><span class="sxs-lookup"><span data-stu-id="e6e79-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="e6e79-132">Nalevingsbeleid maken voor Android-, iOS-, macOS-en Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="e6e79-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="e6e79-133">Maak een apparaatconfiguratie-profiel voor Android-, iOS-, macOS-en Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="e6e79-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="e6e79-134">Maak app-beveiligingsbeleid voor iOS en Windows.</span><span class="sxs-lookup"><span data-stu-id="e6e79-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="e6e79-135">Gegevens verbergen met vergrendelingsscherm.</span><span class="sxs-lookup"><span data-stu-id="e6e79-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="e6e79-136">Beleidsregels voor het wachtwoord implementeren voor mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="e6e79-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="e6e79-137">Mobiele apparaten moeten worden vergrendeld bij inactiviteit.</span><span class="sxs-lookup"><span data-stu-id="e6e79-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="e6e79-138">Vereisen dat mobiele apparaten meerdere aanmeldingsfouten wissen.</span><span class="sxs-lookup"><span data-stu-id="e6e79-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="e6e79-139">Gebruik [Exchange Online Protection en Microsoft Defender voor Office 365](../security/office-365-security/office-365-atp.md) voor de categorie **beveiliging tegen bedreigingen** , waarmee u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="e6e79-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="e6e79-140">Verzender verificatie inschakelen (SPF, DMARC en DKIM).</span><span class="sxs-lookup"><span data-stu-id="e6e79-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="e6e79-141">Microsoft Defender for Office 365 anti phishing policies instellen.</span><span class="sxs-lookup"><span data-stu-id="e6e79-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="e6e79-142">Veilige bijlagen implementeren.</span><span class="sxs-lookup"><span data-stu-id="e6e79-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="e6e79-143">Veilige koppelingen implementeren.</span><span class="sxs-lookup"><span data-stu-id="e6e79-143">Implement Safe Links.</span></span>
- <span data-ttu-id="e6e79-144">Detectie van malware en antwoord beleid implementeren.</span><span class="sxs-lookup"><span data-stu-id="e6e79-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="e6e79-145">Implementeer uitgaand en inkomend spam beleid.</span><span class="sxs-lookup"><span data-stu-id="e6e79-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="e6e79-146">Verwijzingen</span><span class="sxs-lookup"><span data-stu-id="e6e79-146">References:</span></span>

- [<span data-ttu-id="e6e79-147">Algemeen beleid voor identiteiten en apparaattoegang</span><span class="sxs-lookup"><span data-stu-id="e6e79-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="e6e79-148">Beveiliging tegen bedreigingen in Office 365</span><span class="sxs-lookup"><span data-stu-id="e6e79-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="e6e79-149">Veilige bijlagen</span><span class="sxs-lookup"><span data-stu-id="e6e79-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="e6e79-150">Veilige koppelingen</span><span class="sxs-lookup"><span data-stu-id="e6e79-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="e6e79-151">Veilige documenten</span><span class="sxs-lookup"><span data-stu-id="e6e79-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
