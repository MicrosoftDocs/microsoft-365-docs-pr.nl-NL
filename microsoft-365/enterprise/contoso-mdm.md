---
title: Beheer van mobiele apparaten voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Meer inzicht in hoe Contoso Microsoft Intune in Microsoft 365 voor bedrijven gebruikt om de apparaten en de apps die erop worden uitgevoerd, te beheren.
ms.openlocfilehash: 6d7783e8c2d9b78b63bf9eefe761fbc52d0b280f
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753991"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="8ea6d-103">Beheer van mobiele apparaten voor Contoso</span><span class="sxs-lookup"><span data-stu-id="8ea6d-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="8ea6d-104">Microsoft 365 voor bedrijven bevat Intune en een set Azure-services die ondersteuning bieden voor mobiel apparaat- en toepassingsbeheer en -beveiliging.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="8ea6d-105">Contoso heeft veel mobiele werknemers.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="8ea6d-106">Sommige hebben kantoren op Contoso-locaties en sommige hebben geen kantoren.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="8ea6d-107">Contoso had behoefte aan een manier om de productiviteit van medewerkers in te schakelen, maar de apparaten, de gegevens op die apparaten en het gedrag van toepassingen veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="8ea6d-108">Plannen</span><span class="sxs-lookup"><span data-stu-id="8ea6d-108">Plan</span></span>

<span data-ttu-id="8ea6d-109">Contoso heeft de volgende Intune-gebruiksgevallen voor mobiel apparaatbeheer voor Microsoft 365 voor bedrijven geïdentificeerd:</span><span class="sxs-lookup"><span data-stu-id="8ea6d-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="8ea6d-110">Bescherm Exchange Online e-mail en gegevens zodat deze veilig toegankelijk zijn op mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="8ea6d-111">Implementeert een BYOD-programma (Bring-your-own-device) voor Medewerkers van Contoso.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="8ea6d-112">Problemen met telefoons die eigendom zijn van de organisatie en gedeelde tablets voor beperkt gebruik aan contoso-werknemers.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="8ea6d-113">Contoso gebruikt Intune niet voor:</span><span class="sxs-lookup"><span data-stu-id="8ea6d-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="8ea6d-114">Sta werknemers toe veilig toegang te krijgen tot Microsoft 365 vanuit een niet-bemande openbare kiosk.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="8ea6d-115">Bescherm on-premises e-mail en gegevens, zodat deze veilig kunnen worden gebruikt op mobiele apparaten, omdat er geen on-premises Microsoft-Exchange zijn.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="8ea6d-116">Implementeren</span><span class="sxs-lookup"><span data-stu-id="8ea6d-116">Deploy</span></span>

<span data-ttu-id="8ea6d-117">Dit is de manier waarop Contoso de infrastructuur voor het beheer van mobiele apparaten heeft ingesteld:</span><span class="sxs-lookup"><span data-stu-id="8ea6d-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="8ea6d-118">Stel Intune in als de MDM-autoriteit (Mobile Device Management) en gebruik Intune op Azure om inhoud te beheren en de apparaten te beheren</span><span class="sxs-lookup"><span data-stu-id="8ea6d-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="8ea6d-119">Gemaakt Azure Active Directory (Azure AD) groepen voor apparaten voor inschrijvings- en Intune-instellingen en op apparaten gebaseerd beleid voor voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8ea6d-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="8ea6d-120">Zie Beleidsregels voor Voorwaardelijke toegang [van Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="8ea6d-121">Het Apple-apparaatplatform ingeschakeld om werknemers te ondersteunen met iPads, iMacs en iPhones en iPhones van het bedrijf</span><span class="sxs-lookup"><span data-stu-id="8ea6d-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="8ea6d-122">Specifiek Contoso-voorwaardenbeleid gemaakt, dat wordt weergegeven tijdens de installatie van het bedrijfsportaal van Contoso op mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="8ea6d-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="8ea6d-123">Voor apparaten die niet zijn geregistreerd, heeft u een reeks MAM-beleidsregels (Mobile Application Management) geïmplementeerd om verificatie te vereisen voor toegang tot Microsoft 365 services</span><span class="sxs-lookup"><span data-stu-id="8ea6d-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="8ea6d-124">Intune-beleid gemaakt dat het volgende afdwingt:</span><span class="sxs-lookup"><span data-stu-id="8ea6d-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="8ea6d-125">Toegestane apps.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-125">Allowed apps.</span></span>
  - <span data-ttu-id="8ea6d-126">Apparaatversleuteling om onbevoegde toegang te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="8ea6d-127">Een pincode of wachtwoord met zes cijfers.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="8ea6d-128">Een time-outperiode voor inactiviteit.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="8ea6d-129">Antivirus- en malwarebeveiliging en handtekeningupdates met Windows Defender op Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="8ea6d-130">Automatische updates op Windows 10 apparaten met de meest recente beveiligingsupdates.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="8ea6d-131">Certificaten naar beheerde apparaten pushen.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="8ea6d-132">Een duidelijke scheiding tussen bedrijfs- en persoonlijke gegevens. </span><span class="sxs-lookup"><span data-stu-id="8ea6d-132">A clear separation of business and personal data.</span></span> <span data-ttu-id="8ea6d-133">Gebruikers of beheerders kunnen selectief bedrijfsgegevens van het apparaat wissen en persoonlijke gegevens als foto’s, persoonlijke e-mailaccounts en persoonlijke bestanden ongemoeid laten.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-133">Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="8ea6d-134">Contoso heeft geïmplementeerde pc's en smartphones en tablets van het bedrijf geregistreerd door ze toe te voegen aan de juiste Intune-apparaatgroepen.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="8ea6d-135">Ze hebben ook een BYOD-programma ingesteld voor werknemers om hun persoonlijke apparaten in te schrijven.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="8ea6d-136">Geregistreerde apparaten ontvangen Intune-beleid, wat resulteert in beheerde en beveiligde apparaten en hun toepassingen.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="8ea6d-137">Apparaten die niet zijn geregistreerd, hebben MAM-beleid (Mobile Application Management) dat toegestane toepassingen opgeeft.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="8ea6d-138">Hier is de implementatiearchitectuur voor mobiele apparaatbeheer van Contoso.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Implementatie-infrastructuur voor mobiel apparaatbeheer van Contoso](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="8ea6d-140">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="8ea6d-140">Next step</span></span>

<span data-ttu-id="8ea6d-141">Lees hoe Contoso gebruikmaakt van de [informatiebeveiligingsmogelijkheden](contoso-info-protect.md) van Microsoft 365 voor ondernemingen om essentiële digitale activa in de hele organisatie te classificeren, te identificeren en te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="8ea6d-141">Learn how Contoso uses the [information protection capabilities](contoso-info-protect.md) of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ea6d-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8ea6d-142">See also</span></span>

[<span data-ttu-id="8ea6d-143">Apparaatbeheer voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8ea6d-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="8ea6d-144">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8ea6d-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8ea6d-145">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="8ea6d-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

