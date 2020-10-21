---
title: Beheer van mobiele apparaten voor Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Meer informatie over hoe contoso Microsoft intune gebruikt in Microsoft 365 for Enterprise voor het beheren van de apparaten en de apps die daarop worden uitgevoerd.
ms.openlocfilehash: d3f973827a9b05a415efe9225a2bdb3d83ccaf38
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649643"
---
# <a name="mobile-device-management-for-contoso"></a><span data-ttu-id="5e577-103">Beheer van mobiele apparaten voor Contoso</span><span class="sxs-lookup"><span data-stu-id="5e577-103">Mobile device management for Contoso</span></span>

<span data-ttu-id="5e577-104">Microsoft 365 voor Enterprise omvat intune en een set Azure-Services die ondersteuning bieden voor mobiel apparaat en toepassingen beheren en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="5e577-104">Microsoft 365 for enterprise includes Intune and a set of Azure services that support mobile device and application management and security.</span></span>

<span data-ttu-id="5e577-105">Contoso kent veel mobiele medewerkers.</span><span class="sxs-lookup"><span data-stu-id="5e577-105">Contoso has many mobile-enabled employees.</span></span> <span data-ttu-id="5e577-106">Sommige hebben kantoren op contoso locaties en sommige hebben geen kantoren.</span><span class="sxs-lookup"><span data-stu-id="5e577-106">Some have offices in Contoso locations, and some have no offices.</span></span> <span data-ttu-id="5e577-107">Contoso had behoefte aan een manier om de productiviteit van medewerkers in te schakelen, maar de apparaten, de gegevens op die apparaten en het gedrag van toepassingen veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="5e577-107">Contoso needed a way to enable employee productivity but keep the devices, the Contoso data stored on those devices, and application behavior secure.</span></span>

## <a name="plan"></a><span data-ttu-id="5e577-108">Plannen</span><span class="sxs-lookup"><span data-stu-id="5e577-108">Plan</span></span>

<span data-ttu-id="5e577-109">Contoso heeft de volgende intune-gebruik gevallen vastgesteld voor het beheer van mobiele apparaten voor Microsoft 365 for Enterprise:</span><span class="sxs-lookup"><span data-stu-id="5e577-109">Contoso identified the following Intune use cases of mobile device management for Microsoft 365 for enterprise:</span></span>

- <span data-ttu-id="5e577-110">E-mail en gegevens van Exchange Online beveiligen, zodat deze veilig kan worden geopend door mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="5e577-110">Protect Exchange Online email and data so it can be safely accessed by mobile devices.</span></span>
- <span data-ttu-id="5e577-111">Implementeer een versie van het BYOD-programma (online) voor Contoso medewerkers.</span><span class="sxs-lookup"><span data-stu-id="5e577-111">Implement a bring-your-own-device (BYOD) program for Contoso employees.</span></span>
- <span data-ttu-id="5e577-112">Problemen met de organisatie en beperkte telefoons en beperkte deelnemers gebruiken voor werknemers van contoso.</span><span class="sxs-lookup"><span data-stu-id="5e577-112">Issue organization-owned phones and limited-use shared tablets to Contoso employees.</span></span>

<span data-ttu-id="5e577-113">Contoso maakt geen gebruik van intune voor:</span><span class="sxs-lookup"><span data-stu-id="5e577-113">Contoso doesn't use Intune to:</span></span>

- <span data-ttu-id="5e577-114">Medewerkers in staat stellen om Microsoft 365 veilig te openen vanuit een openbare kiosk.</span><span class="sxs-lookup"><span data-stu-id="5e577-114">Allow employees to securely access Microsoft 365 from an unmanaged public kiosk.</span></span>
- <span data-ttu-id="5e577-115">Beveilig on-premises e-mailadres en gegevens, zodat het veilig kan worden geopend door mobiele apparaten, omdat er geen on-premises Microsoft Exchange-servers zijn.</span><span class="sxs-lookup"><span data-stu-id="5e577-115">Protect on-premises email and data so it can be safely accessed by mobile devices, because there are no on-premises Microsoft Exchange servers.</span></span>

## <a name="deploy"></a><span data-ttu-id="5e577-116">Implementeren</span><span class="sxs-lookup"><span data-stu-id="5e577-116">Deploy</span></span>

<span data-ttu-id="5e577-117">Dit is de manier waarop Contoso de infrastructuur voor het beheer van mobiele apparaten heeft ingesteld:</span><span class="sxs-lookup"><span data-stu-id="5e577-117">This is how Contoso set up their mobile device management infrastructure:</span></span>

- <span data-ttu-id="5e577-118">Stel intune in als de MDM-Authority (Mobile Device Management) en gebruik intune op Azure om inhoud te beheren en de apparaten te beheren</span><span class="sxs-lookup"><span data-stu-id="5e577-118">Set Intune as the Mobile Device Management (MDM) authority, and use Intune on Azure to administer content and manage the devices</span></span>
- <span data-ttu-id="5e577-119">Azure Active Directory-groepen (Azure AD) maken voor apparaten voor de registratie en intune-instellingen en het beleid voor voorwaardelijke toegang op basis van een apparaat</span><span class="sxs-lookup"><span data-stu-id="5e577-119">Created Azure Active Directory (Azure AD) groups for devices for enrollment and Intune settings and device-based Conditional Access policies</span></span>

  <span data-ttu-id="5e577-120">Zie [voorwaardelijke toegangsbeleid van Contoso](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="5e577-120">For more information, see [Contoso Conditional Access policies](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>

- <span data-ttu-id="5e577-121">Het Apple-platform is ingeschakeld voor ondersteuning van werknemers met iPads, iMacs en iPhones en van corporate zijnde iPhones</span><span class="sxs-lookup"><span data-stu-id="5e577-121">Enabled the Apple device platform to support employees with iPads, iMacs, and iPhones, and corporate-owned iPhones</span></span>
- <span data-ttu-id="5e577-122">Specifiek Contoso-voorwaardenbeleid gemaakt, dat wordt weergegeven tijdens de installatie van het bedrijfsportaal van Contoso op mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="5e577-122">Created Contoso-specific terms and conditions policies, which are seen during the installation of the Company Portal for Contoso on mobile devices</span></span>
- <span data-ttu-id="5e577-123">Voor apparaten die niet zijn ingeschreven, is een set Mobile Application Management-beleid (MAM) geïmplementeerd waarvoor verificatie is vereist voor toegang tot services van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e577-123">For devices that aren't enrolled, implemented a set of Mobile Application Management (MAM) policies to require authentication for access to Microsoft 365 services</span></span>
- <span data-ttu-id="5e577-124">Intune-beleid gemaakt dat het volgende afdwingt:</span><span class="sxs-lookup"><span data-stu-id="5e577-124">Created Intune policies that enforce:</span></span>
  - <span data-ttu-id="5e577-125">Toegestane apps.</span><span class="sxs-lookup"><span data-stu-id="5e577-125">Allowed apps.</span></span>
  - <span data-ttu-id="5e577-126">Apparaatversleuteling om toegang door onbevoegden te helpen voorkomen.</span><span class="sxs-lookup"><span data-stu-id="5e577-126">Device encryption to help prevent unauthorized access.</span></span>
  - <span data-ttu-id="5e577-127">Een pincode of wachtwoord van zes cijfers.</span><span class="sxs-lookup"><span data-stu-id="5e577-127">A six-digit PIN or password.</span></span>
  - <span data-ttu-id="5e577-128">Een inactiviteit-time-outperiode.</span><span class="sxs-lookup"><span data-stu-id="5e577-128">An inactivity-timeout period.</span></span>
  - <span data-ttu-id="5e577-129">Beveiliging tegen virussen en malware, en handtekening updates met Windows Defender op Windows 10-apparaten.</span><span class="sxs-lookup"><span data-stu-id="5e577-129">Antivirus and malware protection, and signature updates with Windows Defender on Windows 10 devices.</span></span>
  - <span data-ttu-id="5e577-130">Automatische updates op Windows 10-apparaten die de nieuwste beveiligingsupdates bevatten.</span><span class="sxs-lookup"><span data-stu-id="5e577-130">Automatic updates on Windows 10 devices that include the latest security updates.</span></span>
  - <span data-ttu-id="5e577-131">Certificaten naar beheerde apparaten pushen.</span><span class="sxs-lookup"><span data-stu-id="5e577-131">Pushing certificates to managed devices.</span></span>
  - <span data-ttu-id="5e577-132">Een duidelijke scheiding tussen bedrijfs- en persoonlijke gegevens. </span><span class="sxs-lookup"><span data-stu-id="5e577-132">A clear separation of business and personal data.</span></span> <span data-ttu-id="5e577-133">Gebruikers of beheerders kunnen selectief bedrijfsgegevens van het apparaat wissen en persoonlijke gegevens als foto’s, persoonlijke e-mailaccounts en persoonlijke bestanden ongemoeid laten.</span><span class="sxs-lookup"><span data-stu-id="5e577-133">Users or admins can selectively wipe corporate data from the device, while leaving personal data such as pictures, personal email accounts, and personal files untouched.</span></span>

<span data-ttu-id="5e577-134">Door contoso geregistreerde geïmplementeerde Pc's en eigen smartphones en tablets door ze toe te voegen aan de desbetreffende groepen van intune-apparaten.</span><span class="sxs-lookup"><span data-stu-id="5e577-134">Contoso enrolled deployed PCs and company-owned smartphones and tablets by adding them to the appropriate Intune device groups.</span></span> <span data-ttu-id="5e577-135">Ze hebben ook een BYOD-programma gemaakt voor werknemers die hun persoonlijke apparatuur kunnen registreren.</span><span class="sxs-lookup"><span data-stu-id="5e577-135">They also established a BYOD program for employees to enroll their personal devices.</span></span> <span data-ttu-id="5e577-136">Geregistreerde apparaten ontvangen intune-beleidsregels, wat resulteert in beheerde en beveiligde apparaten en hun toepassingen.</span><span class="sxs-lookup"><span data-stu-id="5e577-136">Enrolled devices receive Intune policies, which results in managed and secured devices and their applications.</span></span> <span data-ttu-id="5e577-137">Apparaten die niet zijn ingeschreven, hebben een Mobile Application Management-beleid (MAM) die toegestane toepassingen opgeven.</span><span class="sxs-lookup"><span data-stu-id="5e577-137">Devices that aren't enrolled have Mobile Application Management (MAM) policies that specify allowed applications.</span></span>

<span data-ttu-id="5e577-138">Dit is de implementatie architectuur voor mobiel Apparaatbeheer van contoso.</span><span class="sxs-lookup"><span data-stu-id="5e577-138">Here is the Contoso mobile device management deployment architecture.</span></span>

![Implementatie-infrastructuur van Contoso Mobile Device Management](../media/contoso-mdm/contoso-mdm-fig1.png)

## <a name="next-step"></a><span data-ttu-id="5e577-140">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="5e577-140">Next step</span></span>

<span data-ttu-id="5e577-141">[Meer informatie](contoso-info-protect.md) over hoe Contoso de mogelijkheden voor informatiebescherming van microsoft 365 for Enterprise gebruikt voor het classificeren, identificeren en beschermen van cruciale digitale activa binnen de organisatie.</span><span class="sxs-lookup"><span data-stu-id="5e577-141">[Learn](contoso-info-protect.md) how Contoso uses the information protection capabilities of Microsoft 365 for enterprise to classify, identify, and protect crucial digital assets across its organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="5e577-142">Zie ook</span><span class="sxs-lookup"><span data-stu-id="5e577-142">See also</span></span>

[<span data-ttu-id="5e577-143">Apparaatbeheer voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5e577-143">Device management for Microsoft 365</span></span>](device-management-roadmap-microsoft-365.md)

[<span data-ttu-id="5e577-144">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="5e577-144">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5e577-145">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="5e577-145">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)

